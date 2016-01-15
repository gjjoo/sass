# Other Color Functions

## `adjust_color($color, [$red], [$green], [$blue], [$hue], [$saturation], [$lightness], [$alpha])`
Increases or decreases one or more properties of a color. This can change the red, green, blue, hue, saturation, value, and alpha properties.
증가 또는 색의 1 이상의 특성을 감소시킨다. 빨강, 녹색, 파랑, 색조, 채도, 값 및 알파 속성을 변경할 수 있습니다.
```sass
@param  {Color}  $color
@param  {Number} $red         : -255 ~ 255
@param  {Number} $green       : -255 ~ 255
@param  {Number} $blue        : -255 ~ 255
@param  {Number} $hue         : -360deg ~ 360deg
@param  {Number} $saturation  : -100% ~ 100%
@param  {Number} $lightness   : -100% ~ 100%
@param  {Number} $alpha       : -1 ~ 1
@return {Color}
@examples
  p { color: adjust-color(#102030, $blue: 5) }  /* #102035 */
  p { color: adjust-color(#102030, $red: -5, $blue: 5) } /* #0b2035 */
  p { color: adjust-color(hsl(25, 100%, 80%), $lightness: -30%, $alpha: -0.4) } /* hsla(25, 100%, 50%, 0.6), rgba(255, 106, 0, 0.6) */
```

## `scale_color($color, [$red], [$green], [$blue], [$saturation], [$lightness], [$alpha])`
Fluidly scales one or more properties of a color. This can change the red, green, blue, saturation, value, and alpha properties. 
유동적 색상 중 하나 이상의 속성을 확장 할 수 있습니다. 빨강, 녹색, 파랑, 채도, 값 및 알파 속성을 변경할 수 있습니다.
```sass
@param  {Color}  $color
@param  {Number} $red         : -255 ~ 255
@param  {Number} $green       : -255 ~ 255
@param  {Number} $blue        : -255 ~ 255
@param  {Number} $saturation  : -100% ~ 100%
@param  {Number} $lightness   : -100% ~ 100%
@param  {Number} $alpha       : -1 ~ 1
@return {Color}
@examples
  p { color: scale-color(hsl(120, 70%, 80%), $lightness: 50%) } /* hsl(120, 70%, 90%), #d4f7d4 */
  p { color: scale-color(rgb(200, 150%, 170%), $green: -40%, $blue: 70%) } /* rgb(200, 90, 229), #c899ff */
  p { color: scale-color(hsl(200, 70%, 80%), $saturation: -90%, $alpha: -30%) } /* hsla(200, 7%, 80%, 0.7), rgba(200, 205, 208, 0.7) */
```

## `change_color($color, [$red], [$green], [$blue], [$hue], [$saturation], [$lightness], [$alpha])`
Changes one or more properties of a color. This can change the red, green, blue, hue, saturation, value, and alpha properties.
색상 중 하나 이상의 속성을 변경합니다. 빨강, 녹색, 파랑, 색조, 채도, 값 및 알파 속성을 변경할 수 있습니다.
```sass
@param  {Color}  $color
@param  {Number} $red         : 0 ~ 255
@param  {Number} $green       : 0 ~ 255
@param  {Number} $blue        : 0 ~ 255
@param  {Number} $hue         : 0deg ~ 360deg
@param  {Number} $saturation  : 0% ~ 100%
@param  {Number} $lightness   : 0% ~ 100%
@param  {Number} $alpha       : 0 ~ 1
@return {Color}
@examples
  p { color: change-color(#102030, $blue: 5) } /* #102005 */
  p { color: change-color(#102030, $red: 120, $blue: 5) } /* #782005 */
  p { color: change-color(hsl(25, 100%, 80%), $lightness: 40%, $alpha: 0.8) } /* rgba(204, 85, 0, 0.8) */
```

## `ie_hex_str($color)`
Converts a color into the format understood by IE filters.
IE의 필터에 의해 이해되는 형식으로 색상을 변환합니다.
```sass
@param  {Color} $color
@return {String}
@examples
  ie-hex-str(#abc)                  /* #FFAABBCC */
  ie-hex-str(#3322BB)               /* #FF3322BB */
  ie-hex-str(rgba(0, 255, 0, 0.5))  /* #8000FF00 */
```