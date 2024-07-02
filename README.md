# mbcac_project (h1)
## 팀프로젝트 안내 (h2)
  * : ul ol : 목록 만들기
    
  * 주제 : 열심히 하자
  * 기간 : 3달
    + 1달 : 분석
    + 1달 : 설계
    + 1달 : <span style="color:red">구현</span>
      - 하위항목
      - 1주 로그인
      - 2주 게시판
      - 3주 뉴스
 ## 아래코드를 참고하세요
 ``` jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
    <%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
    <c:set var="pbnum" value="${param.bnum}" />
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>게시판 입력폼</title>
<script src="https://code.jquery.com/jquery-3.7.1.min.js" integrity="sha256-/JqT3SQfawRcv/BIHPThkBvs0OEvtFFmqPF/lYI/Cxo=" crossorigin="anonymous"></script>
<script type="text/javascript">
   function saveBoard() 
   {
      var serForm = $('#addBoard').serialize();
      $.ajax({
         url:'insert_c.jsp',
         method:'post',
         cache:false,
         data:serForm,
         dataType:'json',
         success:function(res){
            alert(res.saved > 0 ? '게시글 저장 성공':'저장 실패');
            if(res.saved > 0){
            	
            location.href='boardDetail_M.jsp?bnum='+res.saved;
            }
         },
         error:function(xhr,status,err){
            alert('에러:' + err);
         }
         
      });
   }
</script>
<style type="text/css">
    body {
        font-family: 'Arial', sans-serif;
        background-color: #f4f4f9;
        margin: 0;
        padding: 0;
    }
    main {
        margin: 2em auto;
        padding: 1.5em;
        max-width: 600px;
        background-color: #fff;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        border-radius: 8px;
    }
    main h3 {
        text-align: center;
        color: #333;
        margin-bottom: 1.5em;
    }
    #container {
        padding: 1em;
    }
    #container > div {
        margin-bottom: 1em;
    }
    label {
        display: inline-block;
        width: 70px;
        font-weight: bold;
        color: #555;
        vertical-align: top;
    }
    .content {
        display: inline-block;
        width: calc(100% - 80px);
        background-color: #eef;
        padding: 0.5em;
        border-radius: 5px;
    }
    .buttons {
        text-align: center;
        margin-top: 1.5em;
    }
    .buttons a {
        text-decoration: none;
        margin: 0 10px;
    }
    .buttons button {
        background-color: #007bff;
        color: white;
        border: none;
        padding: 0.5em 1em;
        border-radius: 5px;
        cursor: pointer;
    }
    .buttons button:hover {
        background-color: #0056b3;
    }
</style>


</head>
<body>

<main>
<h3>게시판 입력</h3>
<div id="container">
<form id="addBoard">
<input type="hidden" name="cmd" value="insertBoard">
<input type="hidden" name="p_bnum" value="${pbnum}">
<div><label>제목</label><div class="content"><input type="text" name="title" id="title"></div></div>
<div><label>작성자</label><div class="content"><input type="text" name="author" id="author"></div></div>
<div><label>내용</label><div class="content"><textarea style="width: 300px; height: 100px;" name="contents" id="contents"></textarea></div></div>
</form>
<div class="buttons" ><button type="button" onclick="saveBoard()">작성</button></div>
</div>
</main>
</body>
</html>
```

```
<span style="color:red">구현</span>
```

