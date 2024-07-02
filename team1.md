# Team1 숙지사항

# mbc_team
# window에서 자격증명 확인 / github 관련 자격증명 삭제
## github.com 회원가입
## github.com 사이트에서 Repository 생성
* Repository 주소복사
## git 다운로드
  * user.name / user.email 등록
    + git config --golbal user.name ="개인아이디"
    + git config --golbal user.email ="개인이메일주소"
  * git config --list : 등록된 항목 확인
## github 토큰 신청 / 발급
 + github.com  화면 우측상단 아이콘 클릭 -> s


## 원격 Repository에 원격 리파지토리 복사


## 로컬 저장소의 내용변경 및 원격저장소 에 병합(push)하기
* 로컬 저장소에 있는 파일을 변경하고 저장한다.
* git add . : 현재 디렉토리(프로젝트 루트)에서 staging 작업실행(업로드할 파일을 모은다.)
* git status : 현재 상태 확인
* git commit -m "변경내용 메세지" :
* git status
* git pussh -u origin main : origin은 원격저장소의 주소에 대한 별칭으로 로컬에 설정된 상태임, main : 원격 저장소 브랜치 이름
* 웹 브라우저 하단의 초록버튼을 누르고 화면이 전환되면 브라우저를 닫는다.
* git 명령어를 실행하던 콘솔창을 닫고  다시 실행한다.
* git status 명령으로 git의 형대 작업상태 확인
* 파일의 변경 상태가 표시되지 않으면 대상파일을 열고 다시 변경하고 저장한다.
* git add : 변경된 로컬 저장소의 내용을 staging
* git status : 변경된 파일이 git에 의해 표시되는지 확인
* git commit -m "변경내용 메세지" 
* git status : : 위에서 commit한 정보가 확인이 되는지
* git push origin main : 최종적으로 로컬프로젝트를 원격저장소(origin)의 main브랜치에 병합한다.
* github.com에 접속하여 해당 파일의 내용이 변경되어 있는지 확인한다.
   
