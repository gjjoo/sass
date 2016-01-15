# HSL Functions

## `hsl($hue, $saturation, $lightness)`
Creates a Color from hue, saturation, and lightness values.
색조, 채도 및 밝기 값에서 색상을 작성합니다.
```sass
@param  {Number} $hue        : 0 ~ 360 degress
@param  {Number} $saturation : 0% ~ 100%
@param  {Number} $lightness  : 0% ~ 100%
@return {Color}
@examples
  p { color: hsl(0, 100%, 50%) }   /* red */
  p { color: hsl(120, 100%, 50%) } /* lime */
  p { color: hsl(120, 100%, 25%) } /* green */
  p { color: hsl(120, 100%, 75%) } /* #80ff80 */
  p { color: hsl(120, 75%, 75%) }  /* #8fef8f */
```

## `hsla($hue, $saturation, $lightness, $alpha)`
Creates a Color from hue, saturation, lightness, and alpha values.
색조, 채도, 밝기 및 알파 값에서 색상을 작성합니다.
```sass
@param  {Number} $hue        : 0 ~ 360 degress
@param  {Number} $saturation : 0% ~ 100%
@param  {Number} $lightness  : 0% ~ 100%
@param  {Number} $alpha      : 0 ~ 1
@return {Color}
@examples
  p { color: hsla(120, 100%, 50%, 1) }   /* lime */
  p { color: hsla(240, 100%, 50%, 0.5) } /* rgba(0, 0, 255, 0.5) */
  p { color: hsla(30, 100%, 50%, 0.1) }  /* rgba(255, 128, 0, 0.1) */
```

## `hue($color)`
Gets the hue component of a color.
색의 색조 구성 요소를 가져옵니다.
```sass
@param  {Color} $color
@return {Number} : 0deg ~ 360deg
@examples
  hue(#fff)     /* 0deg */
  hue(#000)     /* 0deg */
  hue(#ff3366)  /* 345deg */
  hue(#3333ff)  /* 240deg */
  hue(#af9cff)  /* 251.51515deg */
```

## `saturation($color)`
Gets the saturation component of a color.
색의 채도 구성 요소를 가져옵니다.
```sass
@param  {Color} $color
@return {Number} : 0% ~ 100%
@examples
  saturation(#fff)     /* 0% */
  saturation(#000)     /* 0% */
  saturation(#ff3366)  /* 100% */
  saturation(#3333ff)  /* 100% */
  saturation(#af9cff)  /* 100% */
```

## `lightness($color)`
Gets the lightness component of a color.
색의 밝기 구성 요소를 가져옵니다.
```sass
@param  {Color} $color
@return {Number} : 0% ~ 100%
@examples
  lightness(#fff)     /* 100% */
  lightness(#000)     /* 0% */
  lightness(#ff3366)  /* 60% */
  lightness(#3333ff)  /* 60% */
  lightness(#af9cff)  /* 80.58824% */
```

## `adjust_hue($color, $degrees)`
Changes the hue of a color.
색상의 색조를 변경합니다.
```sass
@param  {Color}  $color
@param  {Number} $degrees : -360deg ~ 360deg
@return {Color}
@examples
  p { color: adjust-hue(hsl(120, 30%, 90%), 60deg) }  /* hsl(180, 30%, 90%), #deeded */
  p { color: adjust-hue(hsl(120, 30%, 90%), -60deg) } /* hsl(60, 30%, 90%), #ededde */
  p { color: adjust-hue(#811, 45deg) }                /* #886a11 */
```

## `lighten($color, $amount)`
Makes a color lighter.
색상을 밝게 만듭니다.
```sass
@param  {Color}  $color
@param  {Number} $amount : 0% ~ 100%
@return {Color}
@examples
  p { color: lighten(hsl(0, 0%, 0%), 30%) } /* hsl(0, 0, 30), #4d4d4d */
  p { color: lighten(#800, 20%) }           /* #ee0000 */
```

## `darken($color, $amount)`
Makes a color darker.
색상 어둡게 만듭니다.
```sass
@param  {Color}  $color
@param  {Number} $amount : 0% ~ 100%
@return {Color}
@examples
  p { color: darken(hsl(25, 100%, 80%), 30%) }  /* hsl(25, 100%, 50%), #ff6a00 */
  p { color: darken(#800, 20%) }                /* #220000 */
```

## `saturate($color, $amount)`
Makes a color more saturated.
색상에 좀 더 많은 채도를 만듭니다.
```sass
@param  {Color}  $color
@param  {Number} $amount : 0% ~ 100%
@return {Color}
@examples
  p { color: saturate(hsl(120, 30%, 90%), 20%) }  /* hsl(120, 50%, 90%), #d9f2d9 */
  p { color: saturate(#855, 20%) }                /* #9e3f3f */
```

## `desaturate($color, $amount)`
Makes a color less saturated.
색상에 좀 더 낮은 채도를 만듭니다.
```sass
@param  {Color}  $color
@param  {Number} $amount : 0% ~ 100%
@return {Color}
@examples
  p { color: desaturate(hsl(120, 30%, 90%), 20%) } /* hsl(120, 10%, 90%), #e3e8e3 */
  p { color: desaturate(#855, 20%) } /* #726b6b */
```

## `grayscale($color)`
Converts a color to grayscale. This is identical to desaturate(color, 100%).
회색 음영으로 색상을 변환합니다. 이것은 `desaturate($color, 100%)`와 동일합니다.
```sass
@param  {Color} $color
@return {Color}
@examples
  p { color: grayscale(#769CFF) } /* #bbbbbb */
  p { color: grayscale(#5AFF9C) } /* #adadad */
  p { color: grayscale(#2C42FF) } /* #969696 */
  p { color: grayscale(#FF2A41) } /* #959595 */
  p { color: grayscale(#242424) } /* #242424 */
  p { color: grayscale(#CC31C3) } /* #7f7f7f */
```

## `complement($color)`
Returns the complement of a color. This is identical to adjust-hue(color, 180deg).
색의 보수를 반환합니다. 이것은 `adjust-hue($color, 180deg)`와 동일합니다.
```sass
@param  {Color} $color
@return {Color}
@examples
  p { color: complement(#fa0000) } /* #00fafa */
  p { color: complement(#0000af) } /* #afaf00 */
  p { color: complement(#00fc00) } /* #fc00fc */
```

## `invert($color)`
Returns the inverse (negative) of a color. The red, green, and blue values are inverted, while the opacity is left alone.
색을 뒤집습니다. 불투명도가 방치되면서 적색, 녹색, 청색의 값이반전됩니다.
```sass
@param  {Color} $color
@return {Color}
@examples
  p { color: invert(#fa0000) } /* #05ffff */
  p { color: invert(#0000af) } /* #ffff50 */
  p { color: invert(#00fc00) } */ #ff03ff */
```