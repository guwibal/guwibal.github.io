---
layout: post
title:  "깃허브를 이용해 블로그 시작하기"
date:   2022-06-19 14:11:21 +0900
categories: 개발
---
블로그를 시작해야겠다고 결심하고 플랫폼을 찾던 중 눈에 띈 것이 바로 깃허브였다.  

이전부터 깃허브가 호스팅을 지원한다는건 알고 있었지만, DBMS 설치가 불가능한데 어떤 식으로 홈페이지를 구성할 수 있는건지 궁금했다.  

### 1.깃허브 Repository 준비 
 
우선은 깃허브에 가입한다. 가입과 로그인 과정은 생략한다.  

![join1](https://user-images.githubusercontent.com/89822715/174467381-c6453b53-fe76-4084-9e58-f22a07ebae34.PNG)

Github Repository를 생성한다.  

![join2](https://user-images.githubusercontent.com/89822715/174467444-eeaa6dac-fbca-4f3d-9284-91373ad039bf.png)

Repository name은 NAME.github.io 형식으로 등록하면 된다.(난 이미 해당 이름으로 Reopsitory를 만들어 두었기 때문에 오류가 발생하는 것이다.)

Repository를 생성했으면, 해당 코드를 Local 저장소로 저장해 보자.  

![join3](https://user-images.githubusercontent.com/89822715/174469641-60b7dd76-f48d-46c1-9e52-1daa6de27277.png)
  
이 주소를 깃으로 내려받는다.

단, 먼저 PC에 git을 설치해야 한다. 내 경우 윈도우 환경이므로 [https://git-scm.com/downloads](https://git-scm.com/downloads) 에서 윈도우용으로 다운받았다.  

![join4](https://user-images.githubusercontent.com/89822715/174469844-7c4ec0e6-2c15-4f20-bf81-c7099486f011.png)  

![join5](https://user-images.githubusercontent.com/89822715/174469921-15fde5a0-dc60-49d6-9821-7fae4f9e4b00.png)  

자신의 운영체제에 맞게 설치한다.(설치과정은 생략한다. 난 모두 기본 설정으로 설치했다)  

설치가 정상적으로 되었다면, 윈도우에 설치된 Git Bash를 실행시켜서 Name과 Email을 설정해 준다.  

```
$git config --global user.name "Name"  
```
```
$git config --global user.email "EMAIL" 
```

이렇게 PC에 깃이 정상적으로 연결되었다면, CMD를 열어서 git 명령어를 사용할 수 있다.  

![join6](https://user-images.githubusercontent.com/89822715/174470179-4b9accab-33e1-4a0b-8988-bf132d834f50.png)


![join07](https://user-images.githubusercontent.com/89822715/174470298-28fb52ef-ce29-4b46-8d2b-3cd692569c48.png)


```
git clone HTTPS주소
```

위의 이미지대로면 C:\Users\ProDesk\guwibal.github.io 폴더가 생성되고, Git의 내용이 복제되어 있을 것이다. 이제 이 장소가 블로그 Repository가 되어, 여기에 블로그를 다운받아 코드를 수정하고 다시 Repository에 업로드 하는 식으로 작업이 가능하다.

### 2. Ruby와 Jekill 설치

자, 이제 본격적으로 블로그를 생성하기 위해 Ruby와 Jekill을 설치하자.

Ruby 다운로드 사이트 [https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)에서 WITH DEVKIT을 다운받는다.

![join8](https://user-images.githubusercontent.com/89822715/174470533-e08b4db3-73c3-400c-b938-aea52454900e.png)

난 가장 최신 버전을 다운받았다. 다운 후 설치를 진행한다. 기본 설정으로도 문제없이 설치된다.

설치가 끝났으면, 윈도우 검색창에서 Ruby를 검색하여 Start Command Prompt with Ruby를 실행한다.

![join9](https://user-images.githubusercontent.com/89822715/174470859-bddb9db4-40f4-48d7-a367-fb6b5265d15a.png)

콘솔창에서 gem 명령어를 통해 지킬과 필요한 패키지들을 설치한다.

```
gem install jekyll  
gem install minima  
gem install bundler  
gem install jekyll-feed  
gem install tzinfo-data  
```

이제 로컬에서 지킬로 블로그를 생성하고 실행할 수 있다. 블로그를 설치할 폴더(C:\Users\ProDesk\guwibal.github.io)로 이동해서 다음 코드를 입력한다.

```
jekyll new ./
```

```
bundle install
```

```
jekyll serve
```

![1](https://user-images.githubusercontent.com/89822715/174471205-10f38e24-8b37-4321-bc56-16ba1f2ae219.PNG)

단, 위와 같은 에러가 발생하면서 서버가 실행되지 않는 경우가 있다. 이유는 루비 3.0 버전 부터 gem에 webrick이 포함되지 않기 때문이다. 아래 코드를 사용해 수동으로 설치해 준다.

```
bundle add webrick
```

설치가 완료되면 다시 지킬을 실행한다.

```
jekyll serve
```

![join10](https://user-images.githubusercontent.com/89822715/174471314-784df98f-321b-4e38-8c98-f16ae7e9f80a.png)

웹 브라우저로 http://localhost:4000/ 에 접속하면 로컬 머신 상에서 작동하는 블로그를 미리 볼 수 있다.

### 3. Jekyll 테마 적용

이제 블로그에 테마를 적용해 보자. 내 경우 [https://jamstackthemes.dev/ssg/jekyll/](https://jamstackthemes.dev/ssg/jekyll/)에서 Minimalist 테마를 설치해 보았다.

![join12](https://user-images.githubusercontent.com/89822715/174471726-2b4c9369-867e-4762-8166-0ad5379ce8db.png)

해당 테마를 배포하는 github로 이동한다.

![join13](https://user-images.githubusercontent.com/89822715/174471829-23a577b4-fee0-4384-9396-ce9408264f1f.png)

여기서 ZIP 파일을 다운받아 내용물을 블로그 폴더 내부에 붙여넣는다.

그 후, 다시 루비 CMD로 번들 인스톨 코드를 실행한다.

```
bundle install
```

이로써 블로그에 테마가 적용되었다.

### 4. 테마 수정 및 포스트 작성

블로그 폴더의 _congif.yml 을 열어 설정들을 수정한다. 타이틀, 로고파일 경로, 이메일 등 여러가지를 수정할 수 있다.

포스트의 경우는 _posts 폴더 밑에 .markdown 파일을 생성해서 작성한다. 작명법은 YYYY-mm-dd-subject.markdown 방식으로 가능하다.

확장자명을 보면 알 수 있듯이, 포스트 파일은 markdown 문법으로 작성한다. 마크다운에 대해서는 다음에 알아보고, 우선은 마크다운 파일을 쉽게 작성하기 위한 에디터를 설치한다.

난 우선 사용하기 쉬운 Markdown Pad를 사용해 보기로 하였다. [http://markdownpad.com/](http://markdownpad.com/) 에서 다운로드 후 설치한다.

설치 후 실행하면 오류가 발생할 텐데, 해결방법은 awesomium_v1.6.6_sdk_win 을 설치하면 된다. [참고](http://markdownpad.com/faq.html#livepreview-directx) 링크를 제공한다.

![join14](https://user-images.githubusercontent.com/89822715/174472958-75d57228-25da-4268-9ea3-c5800b6f8227.png)

정상적으로 설치되면 위와 같이 마크다운 문법으로 작성된 글을 미리보기 가능하다. 이로써 포스트 작성이 보다 수월해 질 것이다.

그런데, 이렇게 작성된 글은 어떻게 확인 가능할까? 일단 경로 URL의 패턴은 다음으로 유추된다.

```
/category/YYYY/mm/dd/subject.html
```

확인 방법은 index.md 파일 하단에 아래 코드를 삽입하여 포스트 리스트를 생성하여 링크를 눌러본 것이다.

{% raw %}
```
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
```
{% endraw %}

![join15](https://user-images.githubusercontent.com/89822715/174473374-d3e9cd63-e234-460f-8a33-cd62afe29d73.png)

그러면 메인 페이지 최하단에 다음과 같이 포스트 리스트가 보이게 된다.

또, index.md 파일은 markdown 사용법에 대한 기본적인 예제들로 이루어져 있다. 앞으로의 블로깅에 도움이 될 것이다.

### 5. 깃허브에 배포

지금까지 작성한 블로그를 깃허브에 배포해 보자. CMD를 열고 다음의 코드를 입력하면 된다.

```
git add .  
git commit -m "커밋 메세지"  
git push
```

### 마무리

첫 포스트인 깃허브와 지킬을 활용한 블로그 만들기는 이로서 일단락 한다. 아직 블로그라고 부르기 힘든 모양새이지만 앞으로 점점 다듬어 가면서 제대로 된 블로그를 만들어 나갈 것이다.