<https://beomi.github.io/2016/12/28/HowToSetup-Virtualenv-VirtualenvWrapper/>

<https://beomi.github.io/>

윈도우os에 대한 내용은 없지만 장고 서버에 대한 내용이 많은거 같다.

출처<http://technerd.tistory.com/52>


    myvirtualenv 로 가상환경 이름을 설정했다.
    위의 URL로 익히도록 하자

    python 패키지는 pip라는 패키지 인스톨러를 사용해서 CLI로 쉽게 다운로드 받을수 있다. 
    windows 환경에서 python 공식 홈페이지의 안내를 따라서 python을 설치하고 나면 pip도 자동으로 함꼐 설치가 되니 바로 사용할 수 있다.

    실서비스를 개발하는 경우에는 프로젝트가 개발하는 과정에서 사용한 패키지의 버전에 의존성을 지니는 경우가 많다.
    즉 서로 다른 프로젝트의 django버전이 다른데 두개를 다 이용 해야되는 것이다.

    이런 경우에 virtualenv라는 패키지가 훌륭한 솔루션을 제공해준다.
    이것은 가상환경이다.
    하나의 pC위에 가상머신으로 여러개의 OS를 설치해서 
    각 OS에서는 자신이 이 PC를 독점하고 있는 것처럼 인식하게 해서 사용할 수 있듯이 
    하나의 PC위에 가상의 개발환경을 여러개 구성해놓고 각 개발 환경을 쉽게 옮겨 다닐수 있게 도와준다.

    이렇듯 유용한 virtualenv의 사용을 더 수월하게 도와주는 패키지가 virtualenvwrapper 이다.
    virtualenv 자체를 사용할때는 커맨드가 좀 복잡한데 이를 더 간단한 커맨드로 사용할 수 있게 감싸주는 프로그램이다.

virtualenv와 virtualenvwrapper 패키지를 설치한다. virtualenvwrapper 자체는 OSX/Linux 기반이므로, Windows를 위해서 개발된 virtualenvwrapper-win을 사용한다.

```poweshell
> pip install virtualenv

> pip install virtualenvwrapper-win

> mkvirtualenv 
이 커맨드를 인식할 경우 성공이다.
```

"WORKON_HOME" 환경변수를 설정한다. 생성한 virtualenv 들이 저장될 디렉토리 위치이다. 원하는 디렉토리로 설정하면 된다

```powershell
> setx WORKON_HOME 원하는_디렉토리_위치

```

setx 커맨드로 새로 생성한 환경변수는, 현재 프롬포트 창에서는 반영이 안되어있으므로, 끄고 새로운 프롬포트를 실행한다. mkvirtualenv 커맨드로 새로운 가상환경을 생성한다. 생성뒤에 자동으로 그 가상환경으로 진입한다.
```powershell
> mkvirtualenv 원하는_가상환경_이름

...

(원하는_가상환경_이름) > 
```

workon 커맨드로 가상환경에 진입할 수 있다. (가상환경_이름)이 표시되면 해당 가상환경에 진입한 것이다.

```powershell
> workon 원하는_가상환경_이름

...

(원하는_가상환경_이름) >
```

가상환경에 진입한 뒤에 pip로 설치한 Python 패키지는, 해당 가상환경에서만 유효하다. 아래와 같이 가상환경에서 pip로 Django를 설치한다.

```powershell
(원하는_가상환경_이름) > pip install django
```
pip list 커맨드로 확인해보면 Django가 설치됬음을 확인할 수 있다.

가상환경 밖으로 나와서 pip list 커맨드로 확인해보면 Django가 설치되어있지 않음을 확인할 수 있다.








<http://handam.tistory.com/127>

CRLF는 윈도에서만 LF는 MAC Linux에서 줄바꿈으로 사용 크로스 플랫폼은 골치아프다.

<https://tutorial.djangogirls.org/ko/django_start_project/>

처음에는 이걸 보고 했는데 python manage.py migrate 이걸 실행하면 가상환경에서는 잘 되지 않는다. 

왜그러지..??????????????????????? 구글링을 해봐도 답은 안나오고 다른 가상환경 설정하는 법을 배웠다.

<https://programmers.co.kr/learn/courses/6/lessons/466#>

프로그래머스 장고 강의(??)나중에 볼것