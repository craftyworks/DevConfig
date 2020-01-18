# DevConfig
로컬PC 개발환경 구성 절차

## 디렉토리 구조
* AREA 88
    * download
    * repository
    * tools
    * workspace
    
## 필수유틸리티 설치

* [Notepad++](https://notepad-plus-plus.org/)
* [7-zip](https://www.7-zip.org/)
* [ZoomIt](https://docs.microsoft.com/ko-kr/sysinternals/downloads/zoomit)
* [칼무리](https://kalmuri.kilho.net/)
* [paint.net](https://www.getpaint.net/download.html)

## 개발툴 설치
* oepnJDK
* Git
* Gradle
* Maven
* eclipse IDE
* IntelliJ IDEA

### openJDK
1. download
    * https://www.azul.com/downloads/zulu-community/
1. install
    * 경로 : \AREA 88\tools\java\zulu8
1. 환경변수
    ```
    JAVA_HOME : \AREA 88\tools\java\zulu8
    PATH : %JAVA_HOME%\bin
    ```

### Git
1. download
    * https://git-scm.com/downloads
1. install
    * 경로 : \AREA 88\tools\Git
    
### Maven
1. download
    * https://maven.apache.org/download.cgi
1. install
    * 경로 : \AREA 88\tools\Maven
1. 환경변수
    ```
    PATH : \AREA 88\tools\Maven\bin
    ```
1. settings.xml
    * 경로 : ~\.m2\settings.xml
    ```
    <localRepository>C:\AREA 88\repository</localRepository>
    ```
