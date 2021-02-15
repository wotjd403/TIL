## Eslint란

- Javascript 코드에서 발견된 문제 패턴을 식별하기 위한 정적 코드 분석도구이다.
- JSLint, JSHint와 같이 다른 JavaScript 정적 분석 도구들도 있지만, ESLint가 커스터마이징이 쉽고 확장성이 뛰어나 많이 쓰이고 있는 추세이다.
- ESLint는 스타일 가이드를 좀 더 편리하게 적용하기 위해 사용하기도 하는데, 외부에 공개되어 많은 개발자가 사용 중인 Airbnb Style Guide, Google Style Guide 가 그 대표적인 예입니다.

설치 가이드 

```jsx
yarn add eslint
yarn eslint --init
```

사용중인 옵션

```jsx
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
	plugins: [ 'react', '@typescript-eslint'],
  extends: [ //extends 부분에는 확장 설정을 넣어줍니다. 위의 예시에는 airbnb사의 코딩 스타일을 따르도록 설정했습니다.
		'airbnb',
    'plugin:react/recommended',
    'plugin:@typescript-eslint/recommended',
    'prettier/@typescript-eslint',
    'plugin:prettier/recommended'
  ],
  parser: '@typescript-eslint/parser',
  parserOptions: { //parserOptions에는 자바스크립트 버전, 모듈 사용 여부 등을 설정할 수 있습니다.
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 12,
    sourceType: 'module',
  },
//rules 에는 extends와 plugins에 대한 세부 설정을 변경하는 코드를 넣을 수 있습니다. 
//값을 0으로 주면 에러 검출을 하지 않고, 1로 주면 경고, 2로 주면 에러를 표시합니다.
  rules: { 
		아래 정리해둠
  },
};
```

## 사용중인 rule

```jsx
옵션명 : 사용하는 옵션 이름 명시
**what** : 어떤 역할을 하는 옵션인지 명시
why : 우리 코드에서 왜 사용하는지 명시
영향도 : 해당 옵션의 값에 따라 코드가 어떤 방식으로 변경되는지 명시
사용 예제 : 사용 방법 명시		

**기본 룰은 airbnb에 룰을 기본으로 사용합니다.**

**"react/jsx-filename-extension": [1, { "extensions": [".tsx", ".ts"] }],**
**옵션명** : react/jsx-filename-extension
**what** : JSX 문법을 포함 할 수 있는 파일 확장자를 제한하는 rule
**why** : 현재 사용중인 airbnb 룰(.js, .jsx) 에서 'ts, tsx' 파일에서도 JSX 문법을 사용하기 위해 해당 rule 적용
**사용 예제** : 
[모든 파일 대상]
"rules": {
  "react/jsx-filename-extension": [1, { "allow": "as-needed" }]
}
[특정 파일 지정]
"rules": {
  "react/jsx-filename-extension": [1, { "extensions": [".[확장자]", ".js", ...] }]
}

**"react/jsx-one-expression-per-line': off,**
**옵션명** : react/jsx-one-expression-per-line
**what** : 한줄에 하나의 JSX 요소를 사용하는지 확인하기 위한 옵션입니다.
**why** : 현재 사용중인 airbnb 룰에서는 기본 한줄에 여러 요소를 허용하지 않도록 설정되어 있어 
ex) <div> test {test}</div> 예시와 같이 여러 요소를 사용하기 위해 해당 rule를 해제하였습니다.  
**사용 예제** :
[한줄 요소만 허용]
"rules": {
'react/jsx-one-expression-per-line': ['error', { allow: 'single-child' }],
}

**"import/no-extraneous-dependencies": ["error", {"devDependencies": true}],**
**옵션명** : import/no-extraneous-dependencies
**what** : 외부 패키지 사용을 금지하는 옵션입니다.
**why** : 현재 사용중인 airbnb 룰에서는 모든 외부 패키지 사용금지가 설정되어 있었으나
테스트 또는 개발 환경을 구성하는 devDependency에서는 외부 패키지 사용을 허용하도록 해당 rule을 적용하였습니다.
**사용 예제** :
[특정 경로만 허용]
"rules": {
		'import/no-extraneous-dependencies': [ "error", {"devDependencies": [ 
			'test/**', ( 허용할 패키지 경로 추가)...] 	
	}]
}	
	
**"import/no-unresolved": "off"**
**옵션명** : import/no-unresolved
**what** : import시 file/module이 정확한 경로인지 확인을 위한 옵션입니다
**why** : 현재 사용중인 airbnb 룰에서는 import 파일 경로를 상대경로로 표현 설정되어 있었으나
상대경로 설정시 depth가 깊어지는 문제점으로 해당 rule을 해제하였습니다.
**사용 예제** :
[ commonjs, amd import 방식 허용]
"rules": {
		'import/no-unresolved': ['error', { (commonjs,amd): true, caseSensitive: true }],
//caseSensitive : 경로 설정시 대소문자 예외 설정
}				

**'import/extensions': [ 'error', 'ignorePackages', { js: 'never', jsx: 'never', ts: 'never', tsx: 'never', json: 'never', }, ],**
**옵션명** : import/extensions
**what** : import시 경로에 파일 확장자명을 생략할것인지 확인하기 위한 옵션입니다.
**why** : 현재 사용중인 airbnb 룰에서 (.js, .jsx) 확장자만을 생략 가능하게 설정되어 있어 
'ts, tsx' 확장자도 생략할수 있게 해당 rule 적용하였습니다.
**사용 예제** :
[확장자명을 생략해야 하는 특정 확장자 명시]
"rules": {
'import/extensions': [ 'error', 'ignorePackages', { js: 'never', jsx: 'never', ts: 'never', tsx: 'never', json: 'never', }, ],
}	

[전체 확장자 명시 생략, js만 확장자 명시]
"rules": {
'import/extensions': [ 'error', 'never', { js: 'always'}, ],
}	
		
****"no-use-before-define": "off",
**옵션명** : no-use-before-define
**what** : 변수가 정의되기 전에 사용을 확인하는 옵션입니다.
**why** : ('React' was used before it was defined  no-use-before-define) 문제발생 해결을 위해 off 하였습니다.

```

## Eslint plugin rule

typescriot plugin 

[@typescript-eslint/eslint-plugin](https://www.npmjs.com/package/@typescript-eslint/eslint-plugin)

eslint-plugin-react

[eslint-plugin-react](https://www.npmjs.com/package/eslint-plugin-react)

eslint-plugin-jsx-a11y

[eslint-plugin-jsx-a11y](https://www.npmjs.com/package/eslint-plugin-jsx-a11y)

eslint rule 

[List of available rules](https://eslint.org/docs/rules/)