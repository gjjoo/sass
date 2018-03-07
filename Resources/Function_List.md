# Function List

## RGB Functions
Function | Description
-------- | -----------
`rgb($red, $green, $blue)` | 빨강, 초록, 파랑 값에서 색상을 작성합니다.
`rgba($red, $green, $blue, $alpha)` | 빨강, 초록, 파랑 및 알파 값에서 색상을 작성합니다.
`red($color)` | 색의 빨강 구성 요소를 가져옵니다.
`green($color)` | 색의 초록 구성 요소를 가져옵니다.
`blue($color)` | 색의 파랑 구성 요소를 가져옵니다.
`mix($color1, $color2, $weight:50%)` | 두 개의 색상을 혼합합니다.

## HSL Functions
Function | Description
-------- | -----------
`hsl($hue, $saturation, $lightness)` | 색조, 채도 및 밝기 값에서 색상을 작성합니다.
`hsla($hue, $saturation, $lightness, $alpha)` | 색조, 채도, 밝기 및 알파 값에서 색상을 작성합니다.
`hue($color)` | 색의 색조 구성 요소를 가져옵니다.
`saturation($color)` | 색의 채도 구성 요소를 가져옵니다.
`lightness($color)` | 색의 밝기 구성 요소를 가져옵니다.
`adjust_hue($color, $degrees)` | 색상의 색조를 변경합니다.
`lighten($color, $amount)` | 색상을 밝게 만듭니다.
`darken($color, $amount)` | 색상 어둡게 만듭니다.
`saturate($color, $amount)` | 색상에 좀 더 많은 채도를 만듭니다.
`desaturate($color, $amount)` | 색상에 좀 더 낮은 채도를 만듭니다.
`grayscale($color)` | 회색 음영으로 색상을 변환합니다. 이것은 `desaturate($color, 100%)`와 동일합니다.
`complement($color)` | 색의 보수를 반환합니다. 이것은 `adjust-hue($color, 180deg)`와 동일합니다.
`invert($color)` | 색을 뒤집습니다. 불투명도가 방치되면서 적색, 녹색, 청색의 값이반전됩니다.

## Opacity Functions
Function | Description
-------- | -----------
`alpha($color)` | 색상의 알파 성분 (불투명도)를 반환합니다. 달리 명시 되지 않는 한 값은 1입니다.
`opacity($color)` | 색상의 알파 성분 (불투명도)를 반환합니다. 달리 명시 되지 않는 한 값은 1입니다.
`rgba($color, $alpha)` | 기존 색상의 투명도를 설정합니다.
`opacify($color, $amount)` | 색상을 불투명하게 만듭니다.
`fade-in($color, $amount)` | 색상을 불투명하게 만듭니다.
`transparentize($color, $amount)` | 색상을 투명하게 만듭니다.
`fade-out($color, $amount)` | 색상을 투명하게 만듭니다.

## Number Functions
Function | Description
-------- | -----------
`percentage($number)` | 단위없는 숫자를 백분율로 변환합니다.
`round($number)` | 가장 가까운 정수로 반올림 합니다.
`ceil($number)` | 다음 정수로 숫자를 올립니다.
`floor($number)` | 이전 정수로 숫자를 내립니다.
`min($numbers…)` | 여러 숫자의 최소를 찾습니다.
`max($numbers…)` | 여러 숫자의 최소를 찾습니다.
`random([$limit])` | 임의의 수를 반환합니다.

## String Functions
Function | Description
-------- | -----------
`unquote($string)` | 문자열에서 따옴표를 제거합니다.
`quote($string)` | 문자열에 따옴표를 추가합니다.
`str_length($string)` | 문자열의 문자 수를 돌려줍니다.
`str_insert($string, $insert, $index)` | `$insert`의 값을 `$string`의 `$index` 위치에 삽입합니다.
`str_index($string, $substring)` | `$string`에서 `$substring`의 첫 번째 항목의 인덱스를 돌려줍니다.
`str_slice($string, $start-at, $end-at:-1)` | `$string`에서 문자열을 추출합니다.
`to_upper_case($string)` | 대문자로 된 문자열로 변환합니다.
`to_lower_case($string)` | 소문자로 된 문자열로 변환합니다.

## Other Color Functions
Function | Description
-------- | -----------
`adjust_color($color, [$red], [$green], [$blue], [$hue], [$saturation], [$lightness], [$alpha])` | 증가 또는 색의 1 이상의 특성을 감소시킨다. 빨강, 녹색, 파랑, 색조, 채도, 값 및 알파 속성을 변경할 수 있습니다.
`scale_color($color, [$red], [$green], [$blue], [$saturation], [$lightness], [$alpha])` | 유동적 색상 중 하나 이상의 속성을 확장 할 수 있습니다. 빨강, 녹색, 파랑, 채도, 값 및 알파 속성을 변경할 수 있습니다.
`change_color($color, [$red], [$green], [$blue], [$hue], [$saturation], [$lightness], [$alpha])` | 색상 중 하나 이상의 속성을 변경합니다. 빨강, 녹색, 파랑, 색조, 채도, 값 및 알파 속성을 변경할 수 있습니다.
`ie_hex_str($color)` | IE의 필터에 의해 이해되는 형식으로 색상을 변환합니다.

## List Functions
Function | Description
-------- | -----------
`length($list)` | 리스트의 길이를 반환합니다. 뿐만 아니라 맵에 쌍의 수를 반환 할 수 있습니다.
`nth($list, $n)` | 목록에서 특정 항목을 돌려줍니다.
`set-nth($list, $n, $value)` | 목록에서 n 번째 항목을 대체합니다.
`join($list1, $list2, [$separator:auto])` | 하나에 두 개의 목록을 함께 결합합니다.
`append($list1, $val, [$separator:auto])` | 리스트의 끝에 단일 값을 추가합니다.
`zip($lists…)` | 하나의 다차원 목록에 여러 개의 목록을 결합합니다.
`index($list, $value)` | 목록 내의 값의 위치를 돌려줍니다.
`list-separator($list)` | 목록의 분리를 돌려줍니다.

## Map Functions
Function | Description
-------- | -----------
`map-get($map, $key)` | 주어진 키와 관련된 맵의 값을 돌려줍니다.
`map-merge($map1, $map2)` | 새로운 맵에 두 개의 맵을 병합합니다.
`map-remove($map, $keys…)` | 기존 맵에서 키를 제거하여 새로운 맵을 돌려줍니다.
`map-keys($map)` | 맵에 있는 모든 키의 리스트를 돌려줍니다.
`map-values($map)` | 맵에 있는 모든 값의 리스트를 돌려줍니다.
`map-has-key($map, $key)` | 맵에 지정된 키의 값이 있는지 없는지 판단하여 참/거짓 값으로 돌려줍니다.
`keywords($args)` | 가변 인수를 취하는 함수에 전달 된 키워드를 돌려줍니다.

## Selector Functions
Function | Description
-------- | -----------
`selector-nest($selectors…)` | 하나 아래에 중첩 된 선택은 그것과 같은 스타일에 중첩됩니다.
`selector-append($selectors…)` | 사이의 공백없이 선택자를 추가합니다.
`selector-extend($selector, $extendee, $extender)` | `$selector`내에서 `$extender`와 `$extendee`를 확장합니다.
`selector-replace($selector, $original, $replacement)` | `$selector`내에서 `$original`와 `$replacement`를 확장합니다.
`selector-unify($selector1, $selector2)` | 유사한 요소 모두를 일치 선택자로 생산하기 위해 두 선택자를 단결합니다.
`is-superselector($super, $sub)` | `$super`가 아마도 더 많은 모든 요소 `$sub`에서 일치하는지 여부를 확인합니다.
`simple-selectors($selector)` | 복합 선택기를 구성하는 간단한 선택자를 반환합니다.
`selector-parse($selector)` | 복합 선택기를 구성하는 간단한 선택자를 반환합니다.

## Introspection Functions
Function | Description
-------- | -----------
`feature-exists($feature)` | 현재 사스 런타임에 기능이 존재하는지 여부를 반환합니다.
`variable-exists($name)` | 지정된 이름을 가지는 변수가 현재 범위에 있는지 여부를 반환합니다.
`global-variable-exists($name)` | 지정된 이름을 가지는 변수가 전역 범위에 있는지 여부를 반환합니다.
`function-exists($name)` | 지정된 이름의 함수가 존재하는지 여부를 반환합니다.
`mixin-exists($name)` | 지정된 이름의 믹스 인이 존재하는지 여부를 반환합니다.
`inspect($value)` | Sass 안에서 표현될 것 같은 값을 문자열 표현으로 반환합니다.
`type-of($value)` | 값의 형태를 반환합니다.
`unit($number)` | 숫자와 관련된 단위를 돌려줍니다.
`unitless($number)` | 숫자에서 단위 여부를 반환합니다.
`comparable($number1, $number2)` | 두 숫자가 추가 감산, 또는 비교 될 수 있는지 여부를 반환합니다.
`call($name, $args…)` | 동적으로 Sass 함수를 호출합니다.

## Miscellaneous Functions
Function | Description
-------- | -----------
`if($condition, $if-true, $if-false)` | `$condition`이 참인지 여부에 따라 두 값중 하나를 반환합니다.
`unique-id()` | 고유 CSS 식별자를 돌려줍니다.