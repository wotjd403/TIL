## Babel

- 바벨을 이용하면 ES6 문법을 ES5로, JSX 문법을 JS로 변환되므로 브라우저 호환성을 높일 수 있다.

사용 패키지

- @babel/core : 리액트는 es6를 사용하므로 여러 브라우저에서 사용가능하도록 es5이하 버전으로 syntax를 변경해줍니다.
- @babel/preset-react : jsx를 쓸 수 있습니다.jsx는 react 공식홈페이지 나옵니다. 자바스크립트 확장판이랍니다.
- @babel/preset-env : es6 -> es5이하로 설정에 맞게 트랜스파일됩니다.
- babel-loader : 자바스크립트 파일을 babel preset/plugin과 webpack을 사용하여 es5로 컴파일 해주는 plugin*jsx -> javascript 로 컴파일*html webpack plugin
- @babel/plugin-proposal-class-properties : class property 관련된 문제를 해결하기 위해 사용합니다. hooks를 쓰실때는 없어도 됩니다.

.babelrc : babel plugin들을 모아놓고 사용할 설정파일