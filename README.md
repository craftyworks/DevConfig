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
* [putty](https://www.putty.org/)
* [Multi PuTTY Manager](https://sourceforge.net/projects/multiputtymanager/)
* [FileZilla](https://filezilla-project.org/)
* [D2 Coding Font](https://github.com/naver/d2codingfont)


## 개발툴 설치
* oepnJDK
* Git
* Gradle
* Maven
* eclipse IDE
* IntelliJ IDEA
* lombok
* Java Decompiler

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
1. Confg
    ```
    git config --global user.email "craftyworks@gmail.com"
    git config --global user.name "ddam40"
    git config --global core.editor /usr/bin/vim
    git config --global alias.co checkout
    git config --global alias.br branch
    git config --global alias.ci commit
    git config --global alias.st status
    ```
    
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

### eclipse
1. download
    * https://www.eclipse.org/downloads/packages/
1. install
    * 경로 : \AREA 88\tools\eclipse
1. eclipse.ini 수정
    ```
    -vm
    C:\AREA 88\tools\java\zulu8\bin\javaw.exe
    -vmargs
    -Dfile.encoding=UTF-8
    ```
    
### IntelliJ IDEA
1. download
    * https://www.jetbrains.com/ko-kr/idea/download/
1. install
    * 경로 : \AREA 88\tools\IntelliJ IDEA CE
1. idea64.exe.vmoptions 수정
    ```
    -Dfile.encoding=UTF-8
    ```

### lombok
1. download
    * https://projectlombok.org/download
1. install
    1. eclipse
    ```
    java -jar lombok.jar
    # eclipse 설치 경로 지정
    ```
    1. IntelliJ IDEA
    ```
    install Lombok plugin
    ```

### JD GUI
1. download
    * http://java-decompiler.github.io/
1. install
    * 경로 : \AREA 88\tools\jd-gui
    * JD-Eclipse 설치
    ```
    Download JD-Eclipse ZIP file,
    Launch Eclipse,
    Click on "Help > Install New Software...",
    Drag and drop ZIP file on dialog windows,
    ...
    ```
    
## 개발툴 환경설정
### eclipse

### IntelliJ IDEA
* Settings
    * Appearance & Behavier > System Settings
        ```
        Default Directory : C:\AREA 88\workspace
        ```
    * Build > Compiler > Annotation Processors 
        ```
        Enable annotation processing
        ```
    * Editor > Code Style > Java
        ```
        Tab size : 2
        Indent : 2
        Continuation indent : 4
        ```

* Structure for New Projects
    * Project Settings > Project
        ```
        Project SDK : 1.8
        ```
## Virtual Machine

> 저렴한 노트북을 구했더니 Bios 에 VT-X 활성 옵션이 존재하지 않음. 
> 64bit VM 을 돌릴 방법이 없어서 Ubuntu + Docker 환경은 포기한다. 

### Hyper-V
* Enable Hyper-V
    * 관리자 권한으로 Windows PowerShell 실행
    ```
    Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
    ```
    * systeminfo 실행하여 Hyper-V 요구사항 확인

### WSL
* Enable WSL
    * 관리자 권한으로 Windows PowerShell 실행
    ```
    Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
    ```
* Download Ubuntu
    * Microsoft Store 에서 Ubuntu 검색 후 설치
* Ubuntu 실행
    ```
    Enter New UNIX username: ddam40
    ```
* Root 계정 패스워드
    ```
    sudo passwd root
    ```
* apt 주소 변경
    ```
    sudo vi /etc/apt/sources.list
    :%s/archive.ubuntu.com/ftp.daum.net/g
    :%s/security.ubuntu.com/ftp.daum.net/g
    wq
    
    sudo apt-get update
    sudo apt full-upgrade
    ```
* Locale 변경
    ```
    locale
    locale -a
    sudo apt-get install language-pack-ko
    sudo vi /etc/default/locale
        LANG=ko_KR.UTF-8
    ```
### VirtualBox
* download
    * https://www.virtualbox.org/wiki/Downloads
* install
    * 경로 : \AREA 88\tools\VirtualBox\

### Vagrant
* download
    * https://www.vagrantup.com/downloads.html
* install
    * 경로 : \AREA 88\tools\Vagrant
