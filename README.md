# mbcac_team

## 팀 프로젝트 안내
* 주제: 열심히 하자
* 기간: 3달
  + 1달: 분석
  + 1달: 설계
  + 1달: 구현
    - 1주: 로그인
    - 2주: 게시판
    - 3주: 뉴스
<a name="top"></a>  
1. [code1](#code1)  
2. [code2](#code2)  
3. [code3](#code3)  
4. [code4](#code4)  
5. [code5](#code5)  
5. [code6](#code6)  


## 아래의 코드를 참고하세요
```jsp
<%@ page language="java" contentType="application/json; charset=UTF-8"
    pageEncoding="UTF-8" trimDirectiveWhitespaces="true"%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<jsp:useBean id="dao" class="com.mbcac.jdbc.BoardDAO"/>
<jsp:useBean id="board" class="com.mbcac.jdbc.BoardVO">
   <jsp:setProperty name="board" property="*"/>
</jsp:useBean>
<c:set var="added" value="${dao.add(board)}"/>
{"added":${added}}
```
[github마크다운으로 색상 설정하기](https://gist.github.com/luigiMinardi/4574708d404cdf4fe0da7ac6fe2314db)  
$\color{#ff0000}{\textsf{색상 설정}}$  
<p>
   
<a name="code1">code1</a>  [go to top](#top)
```jsp
<%@ page language="java" contentType="application/json; charset=UTF-8"
    pageEncoding="UTF-8" trimDirectiveWhitespaces="true"%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<jsp:useBean id="dao" class="com.mbcac.jdbc.BoardDAO"/>
<jsp:useBean id="board" class="com.mbcac.jdbc.BoardVO">
   <jsp:setProperty name="board" property="*"/>
</jsp:useBean>
<c:set var="added" value="${dao.add(board)}"/>
{"added":${added}}
```
<a name="code2">code2</a>  [go to top](#top)
```jsp
<%@ page language="java" contentType="application/json; charset=UTF-8"
    pageEncoding="UTF-8" trimDirectiveWhitespaces="true"%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<jsp:useBean id="dao" class="com.mbcac.jdbc.BoardDAO"/>
<jsp:useBean id="board" class="com.mbcac.jdbc.BoardVO">
   <jsp:setProperty name="board" property="*"/>
</jsp:useBean>
<c:set var="added" value="${dao.add(board)}"/>
{"added":${added}}
```

<a name="code3">code3</a>  [go to top](#top)
```jsp
<%@ page language="java" contentType="application/json; charset=UTF-8"
    pageEncoding="UTF-8" trimDirectiveWhitespaces="true"%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<jsp:useBean id="dao" class="com.mbcac.jdbc.BoardDAO"/>
<jsp:useBean id="board" class="com.mbcac.jdbc.BoardVO">
   <jsp:setProperty name="board" property="*"/>
</jsp:useBean>
<c:set var="added" value="${dao.add(board)}"/>
{"added":${added}}
```

<a name="code4">code4</a>  [go to top](#top)
```jsp
<%@ page language="java" contentType="application/json; charset=UTF-8"
    pageEncoding="UTF-8" trimDirectiveWhitespaces="true"%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<jsp:useBean id="dao" class="com.mbcac.jdbc.BoardDAO"/>
<jsp:useBean id="board" class="com.mbcac.jdbc.BoardVO">
   <jsp:setProperty name="board" property="*"/>
</jsp:useBean>
<c:set var="added" value="${dao.add(board)}"/>
{"added":${added}}
```

<a name="code5">code5</a>  [go to top](#top)
```jsp
<%@ page language="java" contentType="application/json; charset=UTF-8"
    pageEncoding="UTF-8" trimDirectiveWhitespaces="true"%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<jsp:useBean id="dao" class="com.mbcac.jdbc.BoardDAO"/>
<jsp:useBean id="board" class="com.mbcac.jdbc.BoardVO">
   <jsp:setProperty name="board" property="*"/>
</jsp:useBean>
<c:set var="added" value="${dao.add(board)}"/>
{"added":${added}}
```

<a name="code5">code5</a>  [go to top](#top)
```jsp
<%@ page language="java" contentType="application/json; charset=UTF-8"
    pageEncoding="UTF-8" trimDirectiveWhitespaces="true"%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<jsp:useBean id="dao" class="com.mbcac.jdbc.BoardDAO"/>
<jsp:useBean id="board" class="com.mbcac.jdbc.BoardVO">
   <jsp:setProperty name="board" property="*"/>
</jsp:useBean>
<c:set var="added" value="${dao.add(board)}"/>
{"added":${added}}
```
<a name="code6">code6</a> [go to top](#top)
```jsp
<%@ page language="java" contentType="application/json; charset=UTF-8"
    pageEncoding="UTF-8" trimDirectiveWhitespaces="true"%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

<jsp:useBean id="dao" class="com.mbcac.jdbc.BoardDAO"/>
<jsp:useBean id="board" class="com.mbcac.jdbc.BoardVO">
   <jsp:setProperty name="board" property="*"/>
</jsp:useBean>
<c:set var="added" value="${dao.add(board)}"/>
{"added":${added}}
```
<a name="code7">code7</a> [go to top](#top)
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
