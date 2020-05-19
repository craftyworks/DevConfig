# 🐵 IDE 단축키

생산성 향상을 위한 IDE 단축키

* Visual Studio Code
* IntelliJ IDEA
* Android Studio
* Vim

## Visual Studio Code

Action | Binding
--- | ---
Delete Line | Ctrl + Shift + K | 
Move line up/down | Alt + ↑/↓ | 
Go back/forward | Alt + ←/→ | 
Show/Hide Terminal | Ctrl + ` | 
Close Editor | Ctrl + F4 | 
Close Window | Ctrl + w | 
Format Document | Shift + Alt + f |
Quick Fix | Ctrl + .|

> https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf

### VSCodeVim

settings.json

```json
    "vim.useSystemClipboard": true,
    "vim.insertModeKeyBindings": [
      {
          "before": ["j", "j"],
          "after": ["<Esc>"]
      },
      {
          "before": ["k", "k"],
          "after": ["<Esc>"]
      }
    ],
```
> https://github.com/VSCodeVim/Vim

## IntelliJ IDEA

Action | Binding
--- | ---
Show Intention Actions and quick-fixes | Alt + Enter
Smart Code Completion | Ctrl + Shift + Space
Rename | Shift + F6
Search Everywhere | Double Shift
Toggle Maximizing editor | Ctrl + Shift + F12
Recent files popup | Ctrl + E
Move line up/down | Shift + Alt + ↑/↓  
Reformat Code | Ctrl + Alt + L
Organize import | Ctrl + Alt + O
Settings | Ctrl + Alt + S
Go to Implementation | Ctrl + Alt + B
Go to Declaration | Ctrl + B
Next Highlited Error | F2
Previous Highlited Error | Shift + F2
Create Test | Ctrl + Shift + T
Override Methods | Ctrl + O
Generate... | Alt + Insert
Quick Javadoc | Ctrl + Q
Activate Project Window | Alt + 1
Switch focus to editor | ESC
🥝 Find Usages | Alt + F7
Line Comment | Ctrl + /
Block Comment | Ctrl + Shift + /
Refactor this | Ctrl + Shift + Alt + T
Compare Files | Ctrl + D
Move to Line/Column | Ctrl + G
🍄 Code Folding Expand | Ctrl + ```+``` or ```=```
🍄 Code Folding Collapse | Ctrl + ```-```
Code Folding Expand All | Ctrl + Shift + ```+``` or ```=```
Code Folding Collapse All | Ctrl + Shift + ```-```
Insert Live Template | Ctrl + J

> https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf

> https://www.jetbrains.com/help/idea/mastering-keyboard-shortcuts.html

### .ideavimrc

```
set clipboard+=unnamed

nnoremap <leader>rr :action Run<cr>
nnoremap <leader>ss :action Android.SyncProject<cr>

imap jj <ESC>
imap kk <ESC>

```

### Live Template

* Abbreviation : log
* Applicable : Java > Declaration
* text
```java
private final org.slf4j.Logger log = org.slf4j.LoggerFactory.getLogger( this.getClass() );
$END$
```

## Android Studio

Action | Binding | 
--- | ---
Delete Line | Ctrl + Y | 
Make Project | Ctrl + F9 | 
Run | Shift + F10 | 
Stop | Ctrl + F2 | 

> https://developer.android.com/studio/intro/keyboard-shortcuts

## Vim

Action | Bindng
--- | ---
현재 커서에서 줄 끝까지 삭제 | d$ 또는 D
현재 커서에서 줄 끝까지 삭제하고 insert mode | c$ 또는 C
명령어 모드에서 붙여넣기 | Ctrl + R 후 0..9
Column Selection Mode | Ctrl + V 

![](/assets/images/vim_shortcut.jpg)

![](/assets/images/vim_move_shortcut.jpg)

> 출처 : https://itisfun.tistory.com/281

### ESC 키매핑 바꾸기

VIM 을 사용하면 ESC 키를 겁나게 누르게 되어 있다.  그런데 지리적으로 키보드 좌측상단에 있다보니 왼쪽 약지 손가락을 쭉펴서 찾아가야 한다. 처음 VI 가 태어날 당시에는 키보드에서 ESC 키의 위치가 현재와 달리 지금의 Tab 키 자리 였다고 한다.

![ADM-3A terminal](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/KB_Terminal_ADM3A.svg/1200px-KB_Terminal_ADM3A.svg.png)

검색해보면 여러가지 방법이 나오긴 하는데...  
일단은 jj 를 써보기로 한다.

```
:imap jj <ESC>
:imap kk <ESC>
```

### .vrapperrc

파일 : %UESRPROFILE%/.vrapperrc

```
imap jj <ESC>
imap kk <ESC>
```

참고 : [Document - Configuration](http://vrapper.sourceforge.net/documentation/?topic=configuration)

## Chrome

> 크롬도 `IDE` 가 맞다?

Action | Binding
--- | ---
새 창 열기 | Ctrl + n
새 탭을 열어 이동 | Ctrl + t
다음에 연 탭으로 이동 | Ctrl + Tab 또는 🍄 `Ctrl + PgDn`
이전에 연 탭으로 이동 | Ctrl + Shift + Tab 또는 🍄 `Ctrl + PgUp`
cycle through open tabs | Ctrl + `1 ~ 8`
맨 오른쪽 탭으로 이동 | Ctrl + 9
현재 탭 닫기 | Ctrl + w 또는 Ctrl + F4
검색주소창으로 이동 | Ctrl + l
페이지의 모든 항목 확대 | Ctrl + `+`
페이지의 모든 항목 축소 | Ctrl + `-`
웹페이지와 화면을 한 번에 아래로 스크롤 | Space
웹페이지와 화면을 한 번에 위로 스크롤 | Shift + Space
페이지 맨위로 이동 | Home
페이지 맨아래로 이동 | End
페이지 새로고침ㅣCtrl + r

