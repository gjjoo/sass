# Sass란?

Sass는 CSS의 힘과 우아함을 더해주는 확장 언어입니다.
Sass는 단지 CSS의 부족한 기능을 도울 뿐이고, 우리는 이미 CSS를 알고 있기에 Sass를 시작하는 것은 어렵지 않습니다.
Sass에는 두가지 종류가 있습니다. Ruby 기반의 Ruby Sass와 C로 만들어진 LibSass 이 두 가지 입니다.

1. 설치방법
  - 루비설치
  - 루비 및 Gem 버전 확인
  - Gem 명령어를 이용한 Sass 설치
2. RubySass 명령어
  - `-h, --help`
  - `-v, --version`
  - `-t, --style Name`
  - `-w, --watch`
  - `-E ENCODING`
  - `--sourcemap=TYPE`
3. Sass GUI Applications
  - CodeKit(mac) - 유료
  - Compass.app(win,mac) - 유료
  - Hammer(mac) - 유료
  - Koala(win,mac) - 무료
  - LiveReolad(win,mac) - 유료
  - Mixture(win,mac) - 유료
  - Prepros(win,mac) - 유료
  - Scout(win,mac) - 무료
4. Sass Intro
  - Sass -> CSS 코드를 출력하는 4가지 스타일
  - Sass와 SCSS 문법 차이
  - 주석 사용 방법
  - `@import` 호출
    - 스타일 모듈 관리
    - 언더바(_) 호출 제어
    - 중첩 `@import` (선택자 상속)
  - CSS 소스맵
5. Sass Basic
  - 중첩 규칙(Nested Rules)
  - 부모, 참조 선택자(&)
  - 중첩 속성
    - `font, margin, border, padding, background, list, column, box, transition, animation, text, min, max`
  - RWD, 미디어퉈리
  - 선택자 상속(Selector Inheritance)
    - `@extend`
    - `!optional`
  - 대체 선택자(Placeholder Selector)
    - `%`
6. Sass Advanced
  - 변수(Variables, $)
    - `변수 기본 값 설정($, !default)`
  - 데이터 타입(Data Type)
    - `Null, Number, String & Color, Boolean, list, map`
  - 디버그(Debug)
    - `@debug`
    - `@warn`
    - `@error`
  - 연산(Operations)
    - `덧셈(+), 뺄셈(-), 곱셈(*), 나눗셈(/), 나머지(%)`
  - 비교 연산(Comparison Operations)
    - `크다(>), 작다(<), 크거나 같다(>=), 작거나 같다(<=), 같다(==), 다르다(!=) `
  - 문자 연산(String Operations)
    - `+`
  - 보간법(Interpolation)
    - `#{}`: 내부 처리
  - Boolean 연산
    - `and, or, not`: `@if`문과 함께 사용
  - List와 Map은 연산을 지원하지 않음
  - 믹스인(Mixin)
    - SCSS: `@mixin`선언 / `@include`호출
    - Sass: `=`선언 / `+`호출
    - 정적믹스인
    - 전달인자
    - 동적믹스인
    - 전달인자 기본 값 설정(오류 방지)
    - 키워드 전달인자
    - 가변 전달인자
    - 콘텐츠 블록 `@content`
  - 함수(Function)
    - `@function`, `@return`
    - Sass 내장 함수들...
      - `RGB, HSL, Opacity, Number, String, Other Color, List, Map, Selector, Introspection, Miscellaneous`
  - 조건(Conditions)
    - `@if`
    - `@else if`
    - `@else`
  - 반복(Loops)
    - `@while`: `(iteration)` == JS의 while문
    - `@for`: `(iteration, from ~ [to, through])` == JS의 for문
    - `@each`: `(iteration, in ~ [list, map])` == JS의 forEach문 또는 for~in문