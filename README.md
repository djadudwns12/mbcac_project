# mbcac_project (h1)
## 팀프로젝트 안내 (h2)
  * : ul ol : 목록 만들기
    
  * 주제 : 열심히 하자
  * 기간 : 3달
    + 1달 : 분석
    + 1달 : 설계
    + 1달 : <span style=" color: #555">구현</span>
      - 하위항목
      - 1주 로그인
      - 2주 게시판
      - 3주 뉴스

<a name="top"></a>
 ## 아래코드를 참고하세요
 <a name="code1">codd1</a>
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

- 인라인 스타일 시트
<span style="color:red">구현</span>

구현 `red` 


[github마크다운 색상설정하기](https://docs.github.com/ko/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
$\color{#ff0000}{\textsf(색상설정)}$


<p></p>
<a name="code2">codd2</a>
```jsp
<%@page import="com.mbcac.testBoard.service.Pagination"%>
<%@page import="com.mbcac.testBoard.vo.BoardVO"%>
<%@page import="java.util.List"%>
<jsp:useBean id="dao" class="com.mbcac.testBoard.dao.BoardDAO"/>
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>

<!DOCTYPE html>
<html>
<head>
<%-- <c:set var="list" value="${dao.getList_C(param.page)}"></c:set> --%>
 <!-- 내가 만든것 -->
<%--  <c:set var="pg" value="${dao.getList_C(param.page)}" /> --%>
 <!-- 강사님 자료 -->
 <c:set var="pg" value="${dao.getHierarchicalList(param.page,param.ipp)}"></c:set>
 
 
<meta charset="UTF-8">
<style type="text/css">
    body {
        font-family: Arial, sans-serif;
       /*  background-color: #f0f0f0; */
        color: #333;
        margin: 0;
        padding: 0;
    }
    main {
        width: 60%;
        margin: 2em auto;
        padding: 1em;
        background-color: #fff;
        border-radius: 8px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    main h2 {
        text-align: center;
        color: #555;
    }
    table {
        width: 100%;
        border-collapse: collapse;
        margin: 1em 0;
    }
    th, td {
        border: 1px solid #ddd;
        padding: 0.8em;
       /*  text-align: center; */
    }
    th {
        background-color: #f4f4f4;
        color: #333;
    }
    tr:nth-child(even) {
        background-color: #f9f9f9;
    }
    tr:hover {
        background-color: #f1f1f1;
        cursor: pointer;
    }
    .button-container {
        text-align: center;
        margin: 1em 0;
    }
    button, input[type="button"] {
        padding: 0.5em 1em;
        border: none;
        border-radius: 4px;
        background-color: #007BFF;
        color: white;
        cursor: pointer;
        margin: 0.5em;
    }
    button:hover, input[type="button"]:hover {
        background-color: #0056b3;
    }
    .search {
        text-align: center;
        margin: 1em 0;
    }
    .search label {
        margin-right: 0.5em;
    }
    .search input[type="text"] {
        padding: 0.5em;
        border: 1px solid #ddd;
        border-radius: 4px;
    }
    .search select {
        padding: 0.5em;
        border: 1px solid #ddd;
        border-radius: 4px;
    }
    body {
	background-image: url("img/tor.gif");
	 background-repeat: no-repeat; 
	  background-size : cover; 
	  
}
button.cp {
	background-color: #dfd;
}
.title{
	text-align: left;
}
</style>
<title>게시판 리스트</title>
</head>
<body>
<main>
<h2>게시판 목록</h2>
<table>
    <tr>
        <th>번호</th>
        <th>제목</th>
        <th>작성자</th>
        <th>조회수</th>
    </tr>
    <c:forEach var="board" items="${pg.items}">
    <tr onclick="window.location.href='boardDetail_M.jsp?bnum=${board.bnum}&page=${pg.getCurrentPage()}'">
        <td>${board.bnum}</td>
        <td class="title">${board.title}</td>
        <td>${board.author}</td>
        <td>${board.hits}</td>
    </tr>
    </c:forEach>
</table>

<div class="search">
<c:forEach var="i" begin="1" end="${pg.totalPages}">
<a href="boardList_M.jsp?page=${i}">[ ${i} ]</a>
</c:forEach>
</div> 

<div class="search">
<c:forEach var="p" items="${pg.getPageNums()}">
<c:choose>
	<c:when test="${p == pg.currentPage}">
		<a href="boardList_MC.jsp?page=${p}"><button class="cp">${p}</button></a>
	</c:when>
	<c:otherwise>
		<a href="boardList_MC.jsp?page=${p}"><button>${p}</button></a>
	</c:otherwise>
</c:choose>

<%-- <a href="boardList_MC.jsp?page=${i}">[ ${i} ]</a> --%>
</c:forEach> 


</div>

	


<div class="button-container">
    <a href="boardInput_MC.jsp"><input type="button" value="추가페이지 이동"></a>
</div>

<div class="search">
    <form action="search.jsp" method="get">
        <input type="hidden" name="cmd" value="search">
        <label for="cat">검색 카테고리</label>
        <select name="cat" id="cat">
            <option value="제목">제목</option>
            <option value="작성자">작성자</option>
        </select>
        <label for="keyword">키워드</label>
        <input type="text" name="keyword" id="keyword">
        <button type="submit">검색</button>
    </form>
</div>
</main>
</body>
</html>

```


<p></p>
<a name="code3">codd3</a> [go to top] #top
```jsp
<%@page import="com.mbcac.testBoard.service.Pagination"%>
<%@page import="com.mbcac.testBoard.vo.BoardVO"%>
<%@page import="java.util.List"%>
<jsp:useBean id="dao" class="com.mbcac.testBoard.dao.BoardDAO"/>
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>

<!DOCTYPE html>
<html>
<head>
<%-- <c:set var="list" value="${dao.getList_C(param.page)}"></c:set> --%>
 <!-- 내가 만든것 -->
<%--  <c:set var="pg" value="${dao.getList_C(param.page)}" /> --%>
 <!-- 강사님 자료 -->
 <c:set var="pg" value="${dao.getHierarchicalList(param.page,param.ipp)}"></c:set>
 
 
<meta charset="UTF-8">
<style type="text/css">
    body {
        font-family: Arial, sans-serif;
       /*  background-color: #f0f0f0; */
        color: #333;
        margin: 0;
        padding: 0;
    }
    main {
        width: 60%;
        margin: 2em auto;
        padding: 1em;
        background-color: #fff;
        border-radius: 8px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    main h2 {
        text-align: center;
        color: #555;
    }
    table {
        width: 100%;
        border-collapse: collapse;
        margin: 1em 0;
    }
    th, td {
        border: 1px solid #ddd;
        padding: 0.8em;
       /*  text-align: center; */
    }
    th {
        background-color: #f4f4f4;
        color: #333;
    }
    tr:nth-child(even) {
        background-color: #f9f9f9;
    }
    tr:hover {
        background-color: #f1f1f1;
        cursor: pointer;
    }
    .button-container {
        text-align: center;
        margin: 1em 0;
    }
    button, input[type="button"] {
        padding: 0.5em 1em;
        border: none;
        border-radius: 4px;
        background-color: #007BFF;
        color: white;
        cursor: pointer;
        margin: 0.5em;
    }
    button:hover, input[type="button"]:hover {
        background-color: #0056b3;
    }
    .search {
        text-align: center;
        margin: 1em 0;
    }
    .search label {
        margin-right: 0.5em;
    }
    .search input[type="text"] {
        padding: 0.5em;
        border: 1px solid #ddd;
        border-radius: 4px;
    }
    .search select {
        padding: 0.5em;
        border: 1px solid #ddd;
        border-radius: 4px;
    }
    body {
	background-image: url("img/tor.gif");
	 background-repeat: no-repeat; 
	  background-size : cover; 
	  
}
button.cp {
	background-color: #dfd;
}
.title{
	text-align: left;
}
</style>
<title>게시판 리스트</title>
</head>
<body>
<main>
<h2>게시판 목록</h2>
<table>
    <tr>
        <th>번호</th>
        <th>제목</th>
        <th>작성자</th>
        <th>조회수</th>
    </tr>
    <c:forEach var="board" items="${pg.items}">
    <tr onclick="window.location.href='boardDetail_M.jsp?bnum=${board.bnum}&page=${pg.getCurrentPage()}'">
        <td>${board.bnum}</td>
        <td class="title">${board.title}</td>
        <td>${board.author}</td>
        <td>${board.hits}</td>
    </tr>
    </c:forEach>
</table>

<div class="search">
<c:forEach var="i" begin="1" end="${pg.totalPages}">
<a href="boardList_M.jsp?page=${i}">[ ${i} ]</a>
</c:forEach>
</div> 

<div class="search">
<c:forEach var="p" items="${pg.getPageNums()}">
<c:choose>
	<c:when test="${p == pg.currentPage}">
		<a href="boardList_MC.jsp?page=${p}"><button class="cp">${p}</button></a>
	</c:when>
	<c:otherwise>
		<a href="boardList_MC.jsp?page=${p}"><button>${p}</button></a>
	</c:otherwise>
</c:choose>

<%-- <a href="boardList_MC.jsp?page=${i}">[ ${i} ]</a> --%>
</c:forEach> 


</div>

	


<div class="button-container">
    <a href="boardInput_MC.jsp"><input type="button" value="추가페이지 이동"></a>
</div>

<div class="search">
    <form action="search.jsp" method="get">
        <input type="hidden" name="cmd" value="search">
        <label for="cat">검색 카테고리</label>
        <select name="cat" id="cat">
            <option value="제목">제목</option>
            <option value="작성자">작성자</option>
        </select>
        <label for="keyword">키워드</label>
        <input type="text" name="keyword" id="keyword">
        <button type="submit">검색</button>
    </form>
</div>
</main>
</body>
</html>



```
