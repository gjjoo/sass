# 데이터 유형(Data_type)

### [데이터 유형(자료형)](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#data_types)
- 비어있음 `null`
- 숫자 `number`
- 문자 `string`
- 컬러 `color`
- 불린 `boolean`
- 리스트 `list`
- 맵 `map`

#### 데이터 유형을 체크하는 함수
> type-of( $data-type )

```scss
// [Null, 비어있음(부정)]
$font-size: null !default
$line-height: null !default

// [Number, 숫자]
// 실수(1.45), 정수(0, 9, -10), 소수(0.8, -0.3), 단위 포함/미포함 숫자
$font-size: 14px
$line-height: 1.5
.wrapper
    font-size: $font-size     // $font-size 변수 값은 숫자(단위 포함)
    line-height: $line-height // $line-height 변수 값은 숫자(단위 미포함)

// [String, 문자]
// 홑따옴표, 쌍따옴표, 따옴표가 없는 경우도 있음
.button
    $font-family: 'Nanum Gothic', nanumgothic, Dotum, Sans-Serif
    font: #{$font-size}/#{$line-height} $font-family

// [Color, 컬러(색상)]
// #rrggbb, rgb(), hsl(), rgba(), hsla(), colorname
.button.primary
    background-color: #FC414B
    color: rgb(255,255,255)

// [Boolean, 불린(논리)]
// true, false
@if $show-layout == true
    .show-layout
        display: block

// [List, 리스트(배열)]
// 1em 2em 0em 4em / 'Times New Roman', Times, Serif
$button-list: ('play', 'pause', 'stop', 'rewind')

// [maps, 맵(객체)]
$headings: (h1: 42px, h2: 38px, h3: 32px, h4: 22px, h5: 16px, h6: 14px)
```