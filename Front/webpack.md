## Webpack

웹팩은 웹페이지에서 사용되는 모든 자원들을 번들링 해주는 라이브러리이다.

- webpack : 모든 리액트 파일을 하나의 컴파일된 하나의 자바스크립트 파일에 넣기 위해
- webpack-dev-server : 실시간 개발 서버 환경을 구동할수 있게 해줌
- webpack-cli : build 스크립트를 통해 webpack 커맨드를 사용하기 위해
- html-webpack-plugin : html에 bundle된 자바스크립트 파일을 <script>...</script>형태로 추가해줍니다.

webpack Externals 

webpack 빌드 시 이 옵션에 어떠한 라이브러리에 대해서 명시가 되어 있을 경우, 빌드시 package가 설치 되어 있지 않더라도 런타임 단계에서 해당 라이브러리를 끌어올 수 있다.

## 사용중인 plugin

1. Clean Webpack plugin

빌드 이전 결과물을 제거하는 플러그인으로 빌드 결과물은 웹팩에서 아웃풋 경로에 설장한 곳으로 폴더 및 파일들이 모이는데 빌드 했을시 이전 빌드내용이 삭제되지 않고 그대로 남아있는 경우도 있어 이것을 해결해주는 플러그인이다.

2. MiniCssExtractPlugin

번들 결과에서 CSS를 별도의 파일로 추출하는 플러그인으로, JS파일 당 CSS파일을 작성한다

3. HtmlWebpackPlugin

따로 분리하여 번들한 css파일과 js파일을 각각 html 파일에 link 태그, script태그로 추가해줘야 한다. HtmlWebpackPlugin은 이것을 자동화 해준다. 웹팩의 기본 플러그인은 아니라서 따로 설치해야한다.

2. Fork ts checker Webpack plugin

typescript의 타입을 **분리된 프로세스**에서 체크해주는 웹팩 플러그인입니다

웹팩이 타입스크립트 파일을 만나면 그 파일을 해석하기 위해서 첫번째로 로더가 필요합니다. 

그래서 우리는 **awesome-typescript-loader또는** ts-loader를 사용하고

 **loader**에 **type checker**를 붙이기 위해 이 **fork-ts-checker-webpack-plugin**을 사용함.

**tip) awesome-typescript-loader가 ts-loader 에 비해서 incremental build가 매우 느리다**

2. eslint-webpack-plugin

eslint-loader더 이상 사용되지 않으며 eslint-webpack-plugin 대안으로 사용