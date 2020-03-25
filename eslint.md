## .eslintrc.js

eslint 를 사용하며 겪는 혼란스러움을 정리하며 해결해 보자

### IntelliJ

* Settings
  * Editor > Code Style > HTML > Other
    * Do not indent children of 항목에 ```script``` 태그를 추가한다.
* .eslintrc.js 파일 수정후에 ```Apply ESLint Code Style rules``` 로 Code Sylte 에 반영한다.

### rules

#### space-before-function-paren

```function``` 선언시나 호출시에 함수명이나 ```function``` 키워드와 괄호 사이에 공백을 둘지를 설정.

* 공백이 필요함이 기본
* 나는 없는게 조은거 같다
* https://eslint.org/docs/rules/space-before-function-paren

```javascript
    // disallow a space before function parenthesis
    'space-before-function-paren': ['error', 'never'],
```

#### no-trailing-spaces

라인 끝에 붙는 불필요한 공백을 에러로 잡아준다. 

* 이걸 꼭 Rule 로 걸어야 하는 건지는 모르겠다. 
* [EditorCofnig](https://editorconfig.org/) 설정으로 IDE 에서 Reformat 하면 자동으로 줄 끝 공백이 제거되니깐 살려 두어도 될것 같다.
* https://eslint.org/docs/rules/no-trailing-spaces

```.editorconfig```
```
trim_trailing_whitespace = true
```

```javascript
    // allow trailing whitespace at the end of lines 
    'no-trailing-spaces': 'off'
```

#### eol-last

파일의 맨 끝이 개행문자(```\n```) 로 끝나야 한다.

* Unix 에서는 상식이라고 한다. 파일을 합치거나 append 를 하는 경우를 고려하면 좋아보이긴 한다만... 
* 잘 납득은 안가지만 [EditorConfg](https://editorconfig.org/) 의 ```insert_final_newline``` 옵션을 사용하면 자동으로 처리가 되니 적용해도 무방하겠다.
* [insert_final_newline](https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties)

**.editorconfig 파일** 에 아래와 같이 설정되어 있어야 한다.
```
insert_final_newline = true
```
