# Project-Construction : 노동자의 출석 및 심리검사 테스트용 서비스와 관리자 서비스

// 주소

건설현장 근로자 안전 * 조건관리를 위한 '게임기반의 디지털 웹'



## System Architecture


## Features

### PC Page

### Mobile Page

**Main**|**Information**
-----|-----
<img src = "https://github.com/project-construction/Spring/assets/37824506/1ed1ff55-ad51-46b9-880a-8b5ec6327e2e" width="100%">|<img src = "https://github.com/project-construction/Spring/assets/37824506/c6b0a36b-11d7-4dd5-9723-38771ed826e7" width="100%">
메인화면|출석체크 화면

## URL

### Attendance
  - /attend/check : testDB의 ischeck값 반환
  - /attend/attend : json로 code값을 받아서 codeDB의 code값과 비교하여 isCheck 변환
  - /attend/login : 토큰에 맞는 그날의 testDB 생성
  - /attend/code : Role이 MANAGER인 경우 codeDB의 오늘 날짜의 team code를 변경가능

### Notice
  - /notice/write : json으로 title, content 값을 받아 공지사항 작성
  - /notice/update : json으로 id, title, content 값을 받아 공지사항 수정
  - /notice/{id} : 공지사항 번호로 공지사항 상세 조회
  - /notice/writer/{id} : 공지사항 작성자로 공지사항 검색
  - /notice/title/{title} : 검색어가 제목에 포함된 공지사항 검색
  - /notice/delete/{id} : 해당 번호의 공지사항 삭제
  - /notice/all : 공지사항 전체 조회
  
### UnityContent
  - /unityContent/insertContent : unity컨텐츠에 대한 점수를 받아 testDB에 저장, isCheck가 true일 시에만 적용
  - /unityContent/allInfo : 토큰의 email을 통해 testDB의 현재 날짜에 대한 모든 정보를 Json으로 반환
  
### Survey_dass
  - /survey/update : dass-21 점수 업데이트
  - /survey/check : 금일 근로자의 dass-21 검사 확인

### Worker
  - /worker/wait : 회원가입한 근로자의 승인대기 목록 출력
  - /worker/approval : 근로자의 회원가입 승인
  - /worker/team : 어떤 팀의 속한 모든 근로자의 정보 출력
  - /worker/info : 어떤 근로자의 기본정보 출력
  - /worker/score : 어떤 근로자의 검사점수 출력

### Sign
  - /sign/save : 웹에서 응답받은 전자서명 encoding 문자열 저장
  - /sign/signs : 어떤 유저의 전자서명 encoding 문자열 모두 출력

### Member 
  - /auth/login : 호출 시 응답받은 정보를 확인하여 토큰과 함께 로그인
  - /auth/signup : 중복유저 검사 후 회원가입


## Backend API

![1](https://github.com/project-construction/Spring/assets/37824506/87bdbfbd-8999-4071-9077-7486ad5d0426)
![2](https://github.com/project-construction/Spring/assets/37824506/a60c2478-4540-4263-8875-2f2ef4015adf)


## Tech Stack

|Frontend|Backend|DevOps|Etc|
|:------:|:---:|:---:|:---:|
|![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)<br>![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)<br>![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?&style=for-the-badge&logo=TailwindCSS&logoColor=white)<br>![axios](https://img.shields.io/badge/axios-0.27.2-661ddf.svg?)|![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)<br>![Swagger](https://img.shields.io/badge/Swagger-85EA2D.svg?style=for-the-badge&logo=Swagger&logoColor=white)</br>|![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)<br>![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)<br>![Docker](https://img.shields.io/badge/docker-F9AB00.svg?style=for-the-badge&logo=docker&logoColor=white)|![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=Postman&logoColor=white) ![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=Git&logoColor=white)<br>


## **Initialization**
- clone the repository

```bash
$ git clone https://github.com/project-construction/Spring.git
$ cd project-construction
```


### Directory Structure (프론트, 백엔드, AI)   // 수정요함

```bash
frontend
├─build
├─dist
├─node_modules
├─public
└─src
    ├─assets
    │  ├─fonts
    │  └─icons
    ├─components
    └─pages

nginx
├─Dockerfile
└─nginx.conf

backend
├─temp
├─app.py
├─connection.py
├─manage.py
└─models.py

ai
├─ai-model
├─app.py
├─connection.py
├─manage.py
└─consumer.py
```

## Team ‘IMS’

Design : 김상규

Frontend : 김나현, 조은상, 염예찬, 박윤진, 정소영

Backend : 김상규, 조은상, 염예찬, 방남현, 정소영

Unity : 김동현, 박찬민
