## Atomic Design 이란?


아토믹 디자인은 디자인 패턴을 만드는 하나의 방법록으로서 5개의 구분된 단계가 있습니다.


Atoms (원자)

- 원자는 물질의 기본 빌딩 블록 (html, tag 단위)

Molecules(분자)

- 분자는 함께 결합된 원자 그룹이며 화합물의 가장 작은 기본 단위 입니다.

Organisms(유기체)

- 비교적 복잡하며 인터페이스에서 구분된 영역을 활성화하는 서로 결합되어 있는 분자 그룹이다.

Templates

- 컴포넌트들을 배치하고 설계의 구조를 보여준다
- 여러 개의 다른 유기체 그룹으로 구성되며 디자인 HTML전체적인 레이아웃이 보이는 그룹

Pages

- 실제 컨텐츠들을 배치한 UI를 보여주며, 템플릿의 구체화된 인스턴스이다
- 템플릿에서 실제 콘텐츠가 바인딩되어 유저에게 보이고 사용되고 리뷰될 단계



## Atomic Design 구분 기준

컴포넌트가 logic을 가지나?

yes => **orginism  예시)  Header / Form / NavigationBar ...**

no = >  컴포넌트 안에 다른 컴포넌트가 있나?

yes => **molucule 예시)  TextField(Material UI) / SearchBox(Input + Button)...**

no  => **atom  예시)  html의 태그 객체. Input / Button / CheckBox / Division...**