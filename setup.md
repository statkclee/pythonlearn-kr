---
layout: page
title: 환경설정
permalink: /setup/
---

### 1. 모두를 위한 파이썬 (파이썬3)

"정보교육을 위한 파이썬 - 데이터 과학자로의 여정"은 
원제가 `Python for Informatics: Exploring Information` 영문이고 **LaTeX** 으로 작성된 반면 모두를 위한 파이썬 (파이썬3), 원제는 `Python for Everybody - Exploring Data In Python 3`는 [pandoc](http://pandoc.org/)과 [마크다운](https://daringfireball.net/projects/markdown/)을 기반으로 하고 있다. 즉, 마크다운으로 파이썬3 책 콘텐츠를 저작하고 `.pdf`, `.html`, `.epub` 전자책은 [pandoc](http://pandoc.org/)이 작업을 담당하는 구조를 갖추고 있다.

#### 1.2. 작업환경 구출

데비안계열 리눅스(우분투, 민트 등)는 다음 명령어로 번역을 위한 작업환경을 갖추게 된다.

~~~ 
$ sudo apt-get install texlive-full
$ sudo apt-get install pandoc
~~~
{.shell}

맥사용자는 다음 웹사이트를 참조하여 필요한 소프트웨어를 설치한다.

- [https://tug.org/mactex/](https://tug.org/mactex/)
- [https://www.tug.org/mactex/mactextras.html](https://www.tug.org/mactex/mactextras.html)

#### 1.1. PDF, HTML, EPUB 전자책 

`bash book.sh` 명령어를 실행시키면 `x.pdf`, `x.epub` 파일 생성된다. 주의할 점은 `book.sh` 빌드 스크립트는 **파이썬2** 기반으로 하여 꼭 **파이썬2** 를 사용한다. 맥에서 파이썬2, 파이썬3를 함께 사용하는 방법은 [stackoverflow QnA](http://stackoverflow.com/questions/18671253/how-can-i-use-homebrew-to-install-both-python-2-and-3-on-mac)를 참조한다.
[^python2-python3]

[^python2-python3]: [How can I use Homebrew to install both Python 2 and 3 on Mac?](http://stackoverflow.com/questions/18671253/how-can-i-use-homebrew-to-install-both-python-2-and-3-on-mac)

~~~ 
$ bash book.sh
~~~

- `htmlbook.sh` : `.html` 파일을 생성하는데 작업결과는 `books/html` 파일에 담겨진다.
- `zipbook.sh` : `Trinket` 브랜드를 갖는 html 전자책 두권을 생성한다. 하나는 인터랙티브 기능을 갖는 것으로 인터넷에 연결되어야 하고, 다른 하나는 코드에 하이라이트 강조 기능이 들어간다. `/book/zips/pfe.zip` 파일에 작업결과가 담긴다.
- `trinketbook.sh` : [https://books.trinket.io/](https://books.trinket.io/) 사이트에 호스트되는 템프릿 작업결과를 생성하는데 `books/trinket/pfe` 작업결과가 담긴다.

아마존 킨들, KindleGen 전자책 파일 `.mobi`는 `x.mobi`로 생성된다. 

[https://www.amazon.com/gp/feature.html?docId=1000765211](https://www.amazon.com/gp/feature.html?docId=1000765211)

리눅스 사용자의 경우 다음 명령어를 실행시키면 된다.

~~~
$ curl -O http://kindlegen.s3.amazonaws.com/kindlegen_linux_2.6_i386_v2_9.tar.gz
$ tar xfv kindlegen_linux_2.6_i386_v2_9.tar.gz 
$ cp kindlegen /usr/local/bin
~~~
{.shell}

#### 1.3. 한국어 번역

본인 운영체제에 맞는 작업환경을 구축했다면, 세브란스 교수님이 작성한 빌드 스크립트를 콘솔창에서 실행하여 `bash book.sh` 명령어를 실행했을 때 제대로 되는지 확인을 먼저한다. 빌드 스크립트를 실행했는데 문제가 생기면 다시 위로 올라가서 제대로 번역환경을 설정했는지 재검토한다. `bash book.sh`가 정상적으로 실행되면 `.pdf` 파일이 생성된다. 그러면 이제 본격적으로 한글번역을 위한 작업환경을 설정한다. 중요한 것은 아래 `정보교육을 위한 파이썬 (파이썬2)`에서 LaTeX 한글 환경을 잘 설정했다면 GitHub에서 클론하고 나서 `bash book.sh` 빌드 스크립트를 실행하면 문제가 없을 것이다.

1. [GitHub](https://github.com) 계정을 생성한다.
1. [모두를 위한 파이썬 - 파이썬3 한국어 번역](https://github.com/statkclee/pythonlearn-kr) GitHub 저장소를 포크한다.
    - [모두를 위한 파이썬 - 파이썬3 한국어 번역](https://statkclee.github.io/pythonlearn-kr)에서 한국어 번역에 대한 전반적인 내용을 확인한다.
1. 포크해서 본인 GitHub 계정으로 가져온 후에 클론(clone)하여 작업 컴퓨터로 내려받는다.
    - 번역에 대한 모든 파일은 다운로드 받은 저장소 아래 `book3` 디렉토리에 저장되어 있다. `book3/mkd_files` 디렉토리에는 마크다운 영어 전체 원문이 각 장별로 구분되어 저장되어 있다. 
1. 마크다운으로 번역 작업을 해서 Push하고, 풀요청(Pull Request)를 보낸다.

**마크다운 한글 번역**

- [마크다운 기초](http://statkclee.github.io/modern-scientific-authoring/02-markdown-kr.html)
- [고급 마크다운](http://statkclee.github.io/modern-scientific-authoring/03-advanced-kr.html)


### 2. 정보교육을 위한 파이썬 (파이썬2)

"정보교육을 위한 파이썬 - 데이터 과학자로의 여정"은 
원제가 `Python for Informatics: Exploring Information` 영문이고 **LaTeX** 으로 작성되었다.
따라서, 번역을 위한 기본 작업흐름은 LaTeX 으로 문서를 저작하는 것과 동일하다. 다만, 최종 결과물이 `.pdf` 파일 뿐만 아니라 HTML 웹사이트 `.html`, 전자책 `.epub`, `.mobi` 로 변환을 하는 작업과정이 추가된다.

#### 2.1. PDF, HTML, EPUB 전자책 

` book.tex` 파일이 최종 작업 `.tex` 파일로 각장 파일과 `00-cover.tex`, `AD-copyright.tex` 파일을 모두 포함하고 있다. LaTeX 파일에 오류가 없다면 다음 명령어로 `.pdf` 파일을 만들어 낸다.

~~~ 
$ bash book.sh
~~~ 
{.shell}

HTML 웹사이트 `.html` 파일을 생성하려면 다음과 같이 명령어를 입력하면 `html` 디렉토리가 생성되고 그 내부에 `.html` 파일이 저장된다.

~~~ 
$ bash html.sh
~~~ 
{.shell}

`.epub`, `.mobi` 확장자를 갖는 전자책을 생성하고 한다면 [Calibre](http://www.calibre-ebook.com/) 소프트웨어를 사용해서 제작한다.

1. HTML 파일을 zip 파일로 압축한다.
1. 압축한 `.zip` 파일을 [Calibre](http://www.calibre-ebook.com/)에 끌어 넣는다.
1. EPUB 으로 변환한다.
    - 제목과 저자를 설정한다.
    - `Cover`를 설정한다.
    - Do not do heuristic processing
    - Blank out the Insert page breaks before regex
1. 디렉토리를 정하고 디스크에 저장한다.

#### 2.2. 파이썬2 작업환경 

**맥 사용자**

맥환경에서 파이썬2 기반 번역을 할 경우 `mactex` 만 설치하면 된다. 다만, `hevea` 관련 HTML을 생성하려면 `mactextras`를 갖고 시도를 해보고 문제가 있는 경우 리눅스를 활용한다.

- [https://tug.org/mactex/](https://tug.org/mactex/)
- [https://www.tug.org/mactex/mactextras.html](https://www.tug.org/mactex/mactextras.html)

**리눅스 사용자**

리눅스 사용자의 경우 다음 LaTeX 작업 환경을 순차로 설치한다.

~~~ 
$ sudo apt-get install texlive-latex-base
$ sudo apt-get install texlive-latex-recommended
$ sudo apt-get install texlive-fonts-recommended 
$ sudo apt-get install texlive-latex-extra
$ sudo apt-get install hevea
$ sudo apt-get install imagemagick
~~~ 
{.shell}

#### 1.3. 한국어 번역 파이썬2 작업환경 

파이썬2 작업환경에서 한국어 번역을 위해서 LaTeX를 한국어 환경에 맞춰 설치를 한다. 자세한 내용은 아래 [데이터 과학을 위한 저작도구](https://statkclee.github.io/ds-authoring/) **한글 LaTeX** 을 참조한다.

- [문서 프로그래밍 - 한글 LaTeX 사전준비](https://statkclee.github.io/ds-authoring/latex.html)
    - [한글 LaTeX 소개](https://statkclee.github.io/ds-authoring/latex-intro.html)
    - [한글 LaTeX 윈도우 설치](https://statkclee.github.io/ds-authoring/latex-install-windows.html)
    - [한글 LaTeX 설치환경 가상화](https://statkclee.github.io/ds-authoring/latex-virtual.html)
    - [한글 LaTeX 편집기](https://statkclee.github.io/ds-authoring/latex-utils.html)


