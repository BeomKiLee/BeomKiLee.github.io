# How To Edit The Profile

이 페이지는 어떻게 Web Profile을 편집하는지를 다룬다.

## Install VS code or Bracket

텍스트 에디터를 사용해서 수정하는 편이 편하다. 보편적인 에디터로는 [VS Code](https://code.visualstudio.com/)가 있고 웹개발 전용으로는 [Bracket](http://brackets.io/)가 있다. 이미 텍스트 에디터가 있다면 상관 없다.

## Set Up

1. [여기](https://git-scm.com/download/) 에서 git을 설치한다. 걍 default로 되어 있는 선택지를 계속 ok 하면 된다.
2. 바탕화면, 혹은 원하는 폴더에서 cmd를 연다. (화면 우클릭 후 여기에서 cmd 열기, 혹은 폴더의 address bar를 클릭 한 후 cmd를 쓰면 됨)
3. `git clone https://github.com/BeomKiLee/BeomKiLee.github.io.git` 을 붙여 넣고 Enter
4. 그러면 그 폴더 안에 코드가 생겨난다. 폴더를 열고, `index.html`을 아까 설치한 text editor로 열자. 수정을 시작 할 수 있다.

## 내용 수정 방법

### 텍스트 수정
그냥 원하는 텍스트를 입력하면 된다. 텍스트는 기본적으로 html tag 안에 있다.

### 링크 수정
눌렀을 때 다른 페이지로 가는 link의 경우 해당 섹션의 href="" 에 있는 것을 수정한다. `https://`나 `http://`를 반드시 붙이도록 한다.

### 섹션 추가
코드에서 `<!-- 시작 -->` 부분부터 `<!-- 끝 -->` 부분까지 복사해서 붙여넣고 필요한 부분을 바꾼다.

### 심볼 수정
`<h1>&#x25A6;</h1>` 에서 <h1></h1> 사이에 있는 것을 [여기](https://www.w3schools.com/html/html_symbols.asp)서 찾은 것으로 바꿔야 한다.

### icon 바꾸기

이 코드는 email 모양의 버튼을 만든다.
```html
    <li class="list-inline-item">
        <a href="mailto:bxl5195@psu.edu" target="_top">
            <span class="fa-stack fa-lg">
                <i class="fa fa-circle fa-stack-2x"></i>
                <!-- 이 줄의 코드가 fa-envelope이라는 아이콘을 불러옴 -->
                <i class="fa fa-envelope fa-stack-1x fa-inverse"></i>
            </span>
        </a>
    </li>

```

이것을 바꾸려면 `<i class="fa fa-envelope fa-stack-1x fa-inverse"></i>` 의 `fa-envelope`을  
[여기](https://fontawesome.com/icons?d=gallery)나 [여기](https://fontawesome.com/v4.7.0/icons/)서 아이콘을 찾은 뒤 코드를 카피해서 바꾸면 된다.

### 수정 내용 반영 방법

1. 수정이 잘 되었는지 index.html을 열어서 확인한다. 가능하면 수정 중간 중간에 해주어서 잘못 되면 바로 텍스트 에디터에서 ctrl + z를 하는게 좋다.  
2. 다 확인 한 후에는 cmd를 다시 index.html이 있는 beomkilee.github.io 폴더에서 연다  
3. `git add .`  
4. `git commit -m "변경 사항에 대한 내용"`  
5. 'git push origin master`  

또, 만약 매번 github id와 pw를 입력하는 것이 귀찮다면 이런 방법도 있다.

1. `git config -l` 하면 화면에 뭐가 막 뜬다. 그냥 ctrl + c 아니면 ctrl + z로 나오면 된다.
2. `git config remote.origin.url https://BeomKiLee:비밀번호@github.com/BeomKiLee/BeomKiLee.github.io.git` 에서 비밀번호를 니 비번으로 바꾼 후 enter
3. 그러면 다음부터는 일일이 로그인 할 필요가 없다.
4. 참고로 github에는 절대 비밀번호 올리지 말자. 잘못해서 해킹 당하면 망함.

### Conventions in File Structuring

`assets` 폴더는 html에서 보여지는 코드가 아닌 자료형들을 가지고 있다. icon, document, img가 나뉘어 있는데 가능하면 새로운 이미지나 문서등을 추가할 때 저 폴더 안에 제대로 넣자. 그래야 코드 정리도 편하다. resume의 경우 `./assets/document/` 폴더에 넣는게 좋다.

`meta` 폴더 안에는 웹페이지 관리와 관련된 문서를 담아둔다. 그 편이 보기 편하다.