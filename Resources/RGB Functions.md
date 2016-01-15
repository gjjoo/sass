# RGB Functions

## `rgb($red, $green, $blue)`
Creates a Color object from red, green, and blue values.
빨강, 초록, 파랑 값에서 색상을 작성합니다.
```sass
@param  {Number} $red   : 0 ~ 255
@param  {Number} $green : 0 ~ 255
@param  {Number} $blue  : 0 ~ 255
@return {Color}
@examples
  p { color: rgb(255,0,0) }       /* red */
  p { color: rgb(0,100,0) }       /* darkgreen */
  p { color: rgb(0,0,100) }       /* #000064 */
  p { color: rgb(300,0,0) }       /* red */
  p { color: rgb(255,-10,0) }     /* red */
  p { color: rgb(110%, 0%, 0%) }  /* red */
```

## `rgba($red, $green, $blue, $alpha)`
Creates a Color from red, green, blue, and alpha values.
빨강, 초록, 파랑 및 알파 값에서 색상을 작성합니다.
```scss
@param  {Number} $red   : 0 ~ 255 or 0% ~ 100%
@param  {Number} $green : 0 ~ 255 or 0% ~ 100%
@param  {Number} $blue  : 0 ~ 255 or 0% ~ 100%
@param  {Number} $alpha : 0 ~ 1
@return {Color}
@examples
  p { color: rgba(255,0,0,1) }          /* red */
  p { color: rgba(100%,0%,0%,1) }       /* red */
  p { color: rgba(0,0,255,0.5) }        /* rgba(0, 0, 255, 0.5) */
  p { color: rgba(100%, 50%, 0%, 0.1) } /* rgba(255, 128, 0, 0.1) */
```

## `red($color)`
Gets the red component of a color.
색의 빨강 구성 요소를 가져옵니다.
```scss
@param  {Color} $color
@return {Number} : 0 ~ 255
@examples
  red(#fac) /* 255 */
  red(#a04) /* 170 */
  red(#7cc) /* 119 */
```

## `green($color)`
Gets the green component of a color.
색의 초록 구성 요소를 가져옵니다.
```scss
@param  {Color} $color
@return {Number} : 0 ~ 255
@examples
  green(#fac) /* 170 */
  green(#a04) /* 0 */
  green(#7cc) /* 204 */
```

## `blue($color)`
Gets the blue component of a color.
색의 파랑 구성 요소를 가져옵니다.
```scss
@param  {Color} $color
@return {Number} : 0 ~ 255
@examples
  blue(#fac) /* 204 */
  blue(#a04) /* 68 */
  blue(#7cc) /* 204 */
```

## `mix($color1, $color2, $weight:50%)`
Mixes two colors together.
두 개의 색상을 혼합합니다.
```scss
@param  {Color}  $color1
@param  {Color}  $color2
@param  {Number} $weight : 0% ~ 100%
@return {Number} : 0 ~ 255
@examples
  mix(#f00, #00f)                 /* purple */
  mix(#f00, #00f, 25%)            /* #4000bf */
  mix(rgba(255, 0, 0, 0.5), #00f) /* rgba(63, 0, 191, 0.75) */
```