## prettier란 ?

Prettier는 코드 포멧팅 도구로 파일 저장 시점이나 Git 에 커밋할 때 코드를 자동으로 포맷팅 해줌으로써 일관된 코딩 형태를 유지하도록 해준다.

설치 가이드

```jsx
yarn add prettier
echo {~}> .prettierrc.*
```

사용 옵션

```jsx
{
	"tabWidth": 2, // 탭 너비 
  "printWidth": 80, //  줄 바꿈 할 폭 길이
  "useTabs": false, // 탭 사용 여부
  "semi": true, // 세미콜론 사용 여부
  "singleQuote": true, // single 쿼테이션 사용 여부
  "trailingComma": "all", // 여러 줄을 사용할 때, 후행 콤마 사용 방식
  "bracketSpacing": false, // 객체 리터럴에서 괄호에 공백 삽입 여부 

//  "endOfLine": "auto", // EoF 방식, OS별로 처리 방식이 다름 
//  "htmlWhitespaceSensitivity": "css", // HTML 공백 감도 설정
//  "jsxBracketSameLine": false, // JSX의 마지막 `>`를 다음 줄로 내릴지 여부 
//  "jsxSingleQuote": false, // JSX에 singe 쿼테이션 사용 여부
//  "proseWrap": "preserve", // markdown 텍스트의 줄바꿈 방식 (v1.8.2)
//  "quoteProps": "as-needed" // 객체 속성에 쿼테이션 적용 방식
//  "vueIndentScriptAndStyle": true, // Vue 파일의 script와 style 태그의 들여쓰기 여부 (v1.19.0)
//  "parser": '', // 사용할 parser를 지정, 자동으로 지정됨
//  "filepath": '', // parser를 유추할 수 있는 파일을 지정
//  "rangeStart": 0, // 포맷팅을 부분 적용할 파일의 시작 라인 지정
//  "rangeEnd": Infinity, // 포맷팅 부분 적용할 파일의 끝 라인 지정,
//  "requirePragma": false, // 파일 상단에 미리 정의된 주석을 작성하고 Pragma로 포맷팅 사용 여부 지정 (v1.8.0)
//  "insertPragma": false, // 미리 정의된 @format marker의 사용 여부 (v1.8.0)

}
```