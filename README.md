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
* Android Studio
* Visual Studio Code
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
> remote 작업 시 github 로그인 과정이 귀찮다. 로그인 정보를 cache 하여 이 과정을 생략 가능하다. 자세한 설명은 [이곳](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage) 을 참고하자.
```
git config --global credential.helper store
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
### Android Studio 
1. download
    * https://developer.android.com/studio/?hl=ko
1. install
    * 경로 : \AREA 88\tools\Android Studio
1. studio64.exe.vmoptions 수정
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

* Java > Editor > Content Assist > Favorites
    * New Type 추가
    ```
    org.assertj.core.api.Assertions 
    ```
* General > Appearance > Colors and Fonts
    * Basic > Text Font : Edit 클릭하여 D2 Coding Font 로 변경
* General > Compare/Patch
    * Ignore white space : 체크
* Validation
    * Suspend all validators : 체크
* General > Editors > Text Editors > Spelling
    * Enable spell checking : 체크 해제
* Java > Code Style > Organize Imports
    * Number of static imports needed for .* : 99 에서 0 으로 변경
* Java > Editor > Save Actions
    * Perform the selected action on save : 체크
    * Organize imports : 체크
* General > Editors > Text Editors
    * Display tab width : 2
    * Insert spaces for tabs : 체크
> tab 으로 검색해서 Space Only, Tab Size 2 로 변경
> Code Formatter 도 수정

* Java > Editor > Templates
    * test 추가
    ```java
    @${testType:newType(org.junit.Test)}
    public void ${testName}() throws Exception {
     ${staticImport:importStatic('org.assertj.core.api.Assertions.*','org.junit.Assert.*')}${cursor}
    }
    ```
    
* General > Content Types
    * Text > HTML 에 *.mustache 추가 [mustache 파일을 HTML Editor 로 편집]
    
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
        Imports Tab > Names count to use static import with '*': 0
        ```
    * Editor > Font
        ```
        D2Coding
        ```
    * Editor > General > Auto Import
        ```
        Add unambiguous imports on the fly
        Optimize imports on the fly
        ```
    * Tools > Terminal
        ```
        Shell Path : C:\Windows\System32\bash.exe 
        ```
    * Editor > General > Appearance
        ```
        Show whitespaces
        ```

* Structure for New Projects
    * Project Settings > Project
        ```
        Project SDK : 1.8
        ```
### VS Code
    * Render Witespace : Boundary

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

#### Vagrant Proxy Setting
* Windows 환경변수 설정
```
set http_proxy=http://yourproxyserver:port
set https_proxy=https://yourproxyserver:port
```

* plugin 설치
```
vagrant plugin install vagrant-proxyconf
```

* Vagrantfile
```
  if Vagrant.has_plugin?("vagrant-proxyconf")
 config.proxy.http     = "http://70.10.15.10:8080"
 config.proxy.https    = "http://70.10.15.10:8080"
 config.proxy.no_proxy = "localhost,127.0.0.1"
  end
```
  
#### Vagrant Box Download URL
proxy 환경 등으로 인해 vagrant box add 가 실패하는 경우에 Browser 에서 url 로 접근하여 파일 다운로드 가능하다.
1. [Vagrant Cloud](https://app.vagrantup.com/boxes/search) 에서 다운받고자 하는 Box 를 검색한다.
1. 해당 Box 클릭 > Version 클릭하면 주소창의 URL 이 다음과 같이 표시된다.
    > https://app.vagrantup.com/{group name}/boxes/{box name}/versions/{version}
1. 위 주소 뒤에 다음과 같이 provider 정보를 추가한다.
    > https://app.vagrantup.com/{group name}/boxes/{box name}/versions/{version}/providers/{provider}.box
1. example
    ```
    # hashicorp/precise64, v1.1.0, virtualbox
    https://app.vagrantup.com/hashicorp/boxes/precise64/versions/1.1.0/providers/virtualbox.box
    
    # hashicorp/precise64, v1.1.0, hyperv
    https://app.vagrantup.com/hashicorp/boxes/precise64/versions/1.1.0/providers/hyperv.box
    ```

#### Vagrant ssh 오류 해결
* centos/7 설치 후 vagrant ssh 시도 시 오류 발생
```
vagrant ssh
vagrant@xxx.xxx.xxx.xxx: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).
```

* 상세 로그를 출력
```
vagrant ssh -- -vvv
```

* private key 의 권한이 너무 오픈되어 있다고 함;
```
debug1: Trying private key: D:/AREA 88/workspace/vagrant-centos/.vagrant/machines/default/hyperv/private_key
debug3: Bad permissions. Try removing permissions for user: S-1-5-11 on file D:/AREA 88/workspace/vagrant-centos/.vagrant/machines/default/hyperv/private_key.
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions for 'D:/AREA 88/workspace/vagrant-centos/.vagrant/machines/default/hyperv/private_key' are too open.
It is required that your private key files are NOT accessible by others.
```

* 콘솔 창에서 아래 명령어로 현재 유저에게만 권한 부여
```
icacls vagrant-centos /inheritance:r /grant {사용자}:(OI)(CI)F
```
