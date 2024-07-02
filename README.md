# mbcac_project (h1)
## 팀프로젝트 안내 (h2)
  * : ul ol : 목록 만들기
    
  * 주제 : 열심히 하자
  * 기간 : 3달
    + 1달 : 분석
    + 1달 : 설계
    + 1달 : 구현
      - 하위항목
      - 1주 로그인
      - 2주 게시판
      - 3주 뉴스
 ## 아래코드를 참고하세요
 ```
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
```
