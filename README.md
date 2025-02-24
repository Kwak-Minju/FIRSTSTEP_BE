<h1 align="center">Welcome to FIRST STEP <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="48px"></h1>
<p>
</p>
<center>
    <img src="./readMesrc/logo.png" alt="Firststep" style="zoom:76%;" align="center"/>
</center>
<br>
> First Step / 한걸음 대여소 (신세계 I&C 2nd 모듈 프로젝트)

##### 🏠 [GitHub_Backend](https://github.com/Kwak-Minju/FIRSTSTEP_BE) 🏠 [GitHub_Front](https://github.com/Kwak-Minju/FIRSTSTEP_FE)


## ✨ Description
```sh
필요한 물폼 혹은 필요 없는 물품을 서로 공유하며 더 좋은 세상으로 한 걸음 나아가는 커뮤니티
```
## 🤼‍♂️Author
```sh
🐯 곽민주 : 마이페이지, 게시물 조회/수정/삭제, 게시물 대여/반납
🐉 조수아 : 데이터베이스, 게시판, 게시물 대여/반납, 로그인/로그아웃, 회원탈퇴, 비밀번호 변경
🐺 김기성 : 로그인
🐶 김서연 : 팀장, 회원가입
🐱 신명호 : 홈
```

## 🔍 기능
```sh
- 게시판 등록/수정/보기/삭제
- 로그인/로그아웃
- 회원가입/회원탈퇴
- 마이페이지(대여물품 조회, 비밀번호 변경)
- 게시물 대여/반납
```

## 🔧 기술 스택
### Front-end
![Static Badge](https://img.shields.io/badge/React-%2361DAFB?logo=react&logoColor=white)
![Static Badge](https://img.shields.io/badge/HTML5-%23E34F26?logo=html5&logoColor=white)
![Static Badge](https://img.shields.io/badge/CSS3-%231572B6?logo=css3&logoColor=white)
### Backend
![Static Badge](https://img.shields.io/badge/Python3-3776AB?logo=Python&logoColor=%23FFFFFF) ![Static Badge](https://img.shields.io/badge/Flask-000000?logo=Flask&logoColor=%23FFFFFF)
### Database
![Static Badge](https://img.shields.io/badge/MySQL-%234479A1?logo=mysql&logoColor=white)

## 🏛️Architecture
<center>
    <img src="./readMesrc/architecture.png" alt="FIRSTSTEP"/>    
</center>

## 🗃️DB
<center>
    <img src="./readMesrc/db.png" alt="FIRSTSTEP"/>    
</center>

## 🏃 Steps to run

### 🗄️Backend

```bash
$ cd FIRSTSTEP_BE
$ python install -r requirements.txt
$ python server.py
```

### 💻Frontend 

```bash
$ cd FIRSTSTEP_FE
$ npm install
$ npm run
```
## 📌주요 코드

```python
# Flask / MySQL 연동
def getCon():
  return pymysql.connect(host="localhost",
                     user="root", password="1234",
                     db="firststep",
                     charset="utf8",
                     cursorclass=pymysql.cursors.DictCursor)

# axios를 통한 서버와의 비동기 통신
axios.put(`http://127.0.0.1:5000/boardEdit/${boardId}`, {title : title, content : content}, { headers: { 'Content-Type': 'application/json' } })
        .then(res => {
            setEdit(!edit);
            setBoardData(res.data)
        }).catch(err => console.log(err));
```

<br>

## 📖 API 명세서
| Index | Method | URL | Description | Parameters |
| --- | --- | --- | --- | --- |
| 1 | GET | /boardlist | 게시판 데이터 조회 |  |
| 2 | GET | /boardlist/<searchWordKey>/<searchWord> | 게시물 검색 |  |
| 3 | GET | /board/detail/<boardId>/<token> | 게시물 상세 정보 조회 |  |
| 4 | GET | /mypage/<token> | 마이페이지 대여 목록 조회 |  |
| 5 | GET | /mypage/chageName/<token> | 마이페이지 사용자 이름 반환 |  |
| 6 | PUT | /boardEdit/<boardId> | 게시물 수정 | title : string content : string |
| 7 | DELETE | /boardDelete/<boardId> | 게시물 삭제 |  |
| 8 | POST | /boardWrite | 게시물 작성 | title : string location : string content : string userId : int |
| 9 | GET | /login/<ID>/<password> | 로그인 |  |
| 10 | GET | /checkid/<token> | 사용자 확인 |  |
| 11 | POST | /signup | 회원 가입 | ID : string password : string password_confirm : string name : string phoneNumber : string |
| 12 | DELETE | /signout/<token> | 회원 탈퇴 |  |
| 13 | POST | /commentWrite | 댓글 작성 | token : string boardId : int content: string |
| 14 | GET | /boardlist/<boardId>/commentlist | 댓글 조회 |  |
| 15 | DELETE | /commentdelete/<commentId> | 댓글 삭제 |  |
| 16 | POST | /checkpassword/<token> | 비밀번호 확인 | constpassword : string |
| 17 | PUT | /changepassword/<token> | 비밀번호 변경 | newPassword : string |
| 18 | PUT | /boardrent/<userId> | 대여 | boardId : int returnData : date |
| 19 | DELETE | /boardreturn/<boardId> | 반납 |  |

## 🔍 Overview
### 1. main 페이지
<center>
    <img src="./readMesrc/mainPage.png" alt="FIRSTSTEP"/>    
</center>

### 2. 공지사항 페이지
<center>
    <img src="./readMesrc/noticePage.png" alt="FIRSTSTEP"/>    
</center>

### 3. 로그인 페이지
<center>
    <img src="./readMesrc/loginPage.png" alt="FIRSTSTEP"/>    
</center>

### 4. 회원가입 페이지
<center>
    <img src="./readMesrc/signupPage.png" alt="FIRSTSTEP"/>    
</center>

### 5. 마이페이지
<center>
    <img src="./readMesrc/myPage.png" alt="FIRSTSTEP"/>    
</center>

### 6. 상세 페이지
<center>
    <img src="./readMesrc/detailPage.png" alt="FIRSTSTEP"/>    
</center>
<center>
    <img src="./readMesrc/detail2Page.png" alt="FIRSTSTEP"/>    
</center>
<br>