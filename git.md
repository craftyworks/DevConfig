# Git

## Link

* [Git documentation](https://git-scm.com/doc)

## Config

### 기본 Editor 수정

Editor 를 Visual Studio Code 로 변경

```shell
git config --global core.deitor "code --wait"
```

### .gitconfig 수정 시 에디터 열기

* ```-e``` 옵션을 사용하면 ```.gitcofnig``` 파일을 에디터로 수정할 수 있다.

```shell
git config --global -e
```

### git st 한글 깨짐

`git st` 시 한글 파일명이 깨지는 경우, 아래 설정을 추가한다.

```shell
git config --global core.quotepath false
```

### git log 한글 깨짐

`git log` 시 한글 본문이 escape 되어 나타나는 경우에 아래 환경변수를 추가한다.

```shell
set LC_ALL=ko_KR.UTF-8
```

### difftool 변경

* Visual Studio Code 를 difftool, mergetool 로 설정한다.
* [P4Merge](https://www.perforce.com/products/helix-core-apps/merge-diff-tool-p4merge) 보다는 VS Code 가 나은것 같다.
* 아래 설정 적용 후 ```git diff``` 대신 ```git difftool``` 명령 사용

```shell
[diff]
	tool = vscode
[difftool "vscode"]
    cmd = code --wait --diff $LOCAL $REMOTE
[difftool "p4merge"]
	path = C:/Program Files/Perforce/p4merge.exe
[difftool]
	prompt = false
[merge]
	tool = vscode
[mergetool "vscode"]
	cmd = code --wait $MERGED
[mergetool "p4merge"]
	path = C:/Program Files/Perforce/p4merge.exe
[mergetool]
	prompt = false
```
## ~/.gitconfig

현재 설정 업데이트

```gitconfig
[user]
	name = craftyworks
	email = craftyworks@gmail.com
[alias]
	co = checkout
	br = branch
	ci = commit
	st = status
[core]
	quotepath = false
	editor = code --wait
[credential]
	helper = manager
[diff]
	tool = vscode
[difftool "vscode"]
    cmd = code --wait --diff $LOCAL $REMOTE
[difftool "p4merge"]
	path = C:/Program Files/Perforce/p4merge.exe
[difftool]
	prompt = false
[merge]
	tool = vscode
[mergetool "vscode"]
	cmd = code --wait $MERGED
[mergetool "p4merge"]
	path = C:/Program Files/Perforce/p4merge.exe
[mergetool]
	prompt = false
```

## Emoji commit message

* https://gitmoji.carloscuesta.me/
* [Git commit message emoji](https://gist.github.com/parmentf/035de27d6ed1dce0b36a)
* https://github.com/dannyfritz/commit-message-emoji

### Ground Rules

| 작업 구분 | 이모지
| --- | ---
| Initial Commit | 🎉 `:tada:`
| Bug Fix | 🐛 `:bug:`
|| 💥 `:boom:` 
| Improving structure, performance, ui | 🎨 `:art:`
|| 🚀 `:rocket:` 
|| 💡 `:bulb:`
|| 💄 `:lipstick:` 
| Snapshot, Versionning | 📌 `:pushpin:`
|| 🔖 `:bookmark: `
| Comment | 🏷️ `:label:`
|| 📝 `:pencil: `
|| 📚	`:books:`
| Restore, 원복 | 🔙 `:back:`
|| ⏪ `:rewind:`
| Delete File or Code | ❌ `:x:`
|| ⚡️ `:zap:` 
|| 🔥 `:fire:`
| Move or Rename | 🚚 `:truck: `
| Fixme | 💩 `:poop:`
|| 💤 `:zzz:`
| Refactor code	| 🔨 `:hammer:`

