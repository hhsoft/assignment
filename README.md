# assignment




git 명령어

                                                                https://brainbackdoor.tistory.com/15
<일반적인 작업시 사용하는 명령어>

 $ cd [깃 로컬 저장소 경로]
 $ git checkout -b [브랜치 이름]
 $ git add .
 $ git commit -m "[커밋 메시지]"
 $ git push origin [브랜치 이름]
 웹에서 merge 요청

 $ git merge master (내 branch로 받아오는 작업)


<새로운 로컬 저장소 만들기>

 $ cd Desktop
 $ mkdir sample
 $ cd sample/
 $ git init
 git init을 잘못한 경우엔 .git을 삭제하면 된다.


<git 저장소 상태 보기>

 $ git status


<Add to Index>

 $ git add . 
 or
 $ git add [커밋할 파일명]


<Commit>

 $ git commit -m "[커밋메시지]"
-의미있는(논리적인 한가지) 작업을 한가지 했으면 commit을 해라


<.gitignore>

 *.o 
 *.sqlite 
 *.bak 
 *.old 
 .DS_Store 
 logs/
-무시해야 하는 바이너리 파일 등을 .gitignore 파일에 기술하면 커밋에서 제외된다.


<Log 확인>

 $ git log --oneline --decorate --graph


<이전 상태로 변경 예>

 $ git reset -- [파일이름]
 $ git reset --hard [커밋아이디]
 $ git reset --hard -> 마지막 commit으로 돌아갈때
 $ git reset --hard HEAD^ 한단계 앞
 $ git reset --hard HEAD^^ 두단계 앞 (git reset --hard HEAD~2)
 $ git reset --hard HEAD^2 (두번째 부모)
-(파일 변경사항은 그대로 두고) add 혹은 commit을 뒤로 돌아가게 하는 용도


<원격 저장소 연결>

 1. 원격 저장소 확인
 $ git remote -v

 2. github에서 repository 생성

 3. local과 remote repository 연결 (일반적으로 원격저장소 이름은 origin으로 세팅함)
 $ git remote add origin [깃 원격 저장소 주소]


<git branch>
  
 1. branch 생성(HEAD 에 생김)
 $ git branch [브랜치이름]  

 1-1. 특정 위치에 branch 생성
 $ git branch -f [브랜치이름] [커밋아이디]

 2. 로컬 브랜치 확인
 $ git branch
 $ git branch -v (해당 브랜치의 commit ID도 보임)

 3. 원격 브랜치 확인
 $ git branch -r 

 4. master로 이동 후 merge
 $ git checkout -f master
 $ git merge [브랜치이름]


<git push>

 $ git push origin master 
 $ git push --force 


<git pull>
  
 $ git pull 
-pull = fetch + merge
-fetch : 원격에서 local 저장소로 가져옴
-merge : local 저장소로 가져온 내용을 Working Directory에 반영 및 Index에 적용하는 것 (그리하여 git status 명령어로 확인시에 변경사항이 체크되지 않는 것임)


<git clone>
  
 $ git clone [깃 원격 저장소 주소] [로컬 원격 저장소 경로]
-remote 주소 설정이 자동으로 세팅됨


<git tag>
  
 $ git tag [태깅] [커밋아이디]
 $ git push origin [태깅] 
-실 배포버전을 위한 용도
-태깅하고 push하면 github의 release에 올라감
-태깅하고 commit해도 HEAD위치가 갱신되지 않는다.




markdown 문법

                              https://simhyejin.github.io/2016/06/30/Markdown-syntax/
<제목 Headers>

#으로 시작하는 텍스트.
#은 하나부터 여섯개까지 쓸 수 있고, #이 늘어날때마다 제목의 수준은 내려간다.
(보통 글씨 크기가 작아진다.)

　　# h1

또는 -, =을 이용하여 h1, h2를 쓸 수 있다.

　　h1
　　===

　　h2
　　—


<인용 Blockquotes>

>으로 시작하는 텍스트

　　> 인용문	
  
  　>> 인용문안의 인용문


<코드 블럭 Code Blocks>

``` 혹은 ~~~ 코드 첫 줄과 마지막 줄에 Back quote ( ` ) 또는 물결( ~ ) 3개 삽입

　　```
　　이것은
　　코드 블럭
　　입니다
　　```

　　~~~
　　이것은 
　　코드 블럭
　　입니다
　　~~~


<인라인 코드 Inline Code Blocks>

`(Back quote)로 감싸진 텍스트

　　`인라인 코드 블럭`
  
  
<강조 Emphasis>

기울여 쓰기(italic) : * 또는 _로 감싼 텍스트
굴게쓰기(bold) : ** 또는 __로 감싼 텍스트

　　*기울여쓰기(italic)*
　　_기울여쓰기(italic)_

　　**굵게쓰기(bold)**
　　__굵게쓰기(bold)__


<수평선 Horizontal Rules>

- 또는 * 또는 _ 을 3개 이상 작성
(단, -을 사용할 경우 header로 인식할 수 있으니 이 전 라인은 비워두어야한다.)

　　---	
　　***	
　　___


<외부 링크 External Links>

[링크](http://example.com "링크 제목") 인라인 링크
[링크1][1] [1]: http://example1.com/ "링크제목1" 참조 링크
<example.com/> <example@example.com> url 링크

　　인라인 링크
　　[Google](http://www.google.co.kr “구글”)

　　참조 링크 
　　[Google][1]
　　[Naver][2]
　　[1]: http://google.com/ “구글”
　　[2]: http://naver.com/ “네이버”	

　　URl 링크
　　<http://google.com/>
　　<example@gmail.com/>


<내부 링크 Internal (Anchored) Links>

[링크](#id) 내부 링크
　　[목차](#index)


<순서 있는 리스트 Ordered Lists>

No. 숫자 다음 .을 찍는다. (적힌 숫자랑 상관없이 순서대로 번호가 매겨진다.)

　　1. list item 1
　　1. list item 2
　　2. list item 3
　　0. list item 4
　　3. list item 5


<순서 없는 리스트 Unordered Lists>

*, +, - 으로 시작

　　* list item 1
  　　 * list item 1-1
  　　 * list item 1-2
     
　　+ list item 1
  　　 + list item 1-1
  　　 + list item 1-2
     
　　- list item 1
  　　 - list item 1-1
  　　 - list item 1-2


<테이블 Tables>

　　테이블 생성
　　Header 1 | Header 2
　　--------- | ---------
　　Content 1 | Content 3
　　Content 2 | Content 4

　　테이블 정렬
　　| Header 1 | Header 2 | Header 3 |
　　| :-------- | :--------: | --------: |
　　| Left | Center | Right |


<이미지 Adding Images>

　　인라인 이미지
　　![alt text](/test.png )

　　링크 이미지
　　![alt text](image_URL)

　　참조 이미지
　　![alt text][1]
　　[1]: /test.png


<각주 Footnotes>

각주입니다[^id]
[^id]: 각주에 대한 설명.

