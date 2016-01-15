# Opacity Functions

## `alpha($color)` == `opacity($color)`
Returns the alpha component (opacity) of a color. This is 1 unless otherwise specified.
This function also supports the proprietary Microsoft alpha(opacity=20) syntax as a special case.

색상의 알파 성분 (불투명도)를 반환합니다. 달리 명시 되지 않는 한 값은 1입니다.
이 함수는 특별한 경우로써 독점적인 마이크로소프트의 `alpha(opacity=20)` 구문을 지원합니다.
```scss
@param  {Color} $color
@return {Number} : 0 ~ 1
@examples
  alpha(rgba(100%, 50%, 0%, 0.5)) /* 0.5 */
  alpha(lighten(#800, 20%))       /* 1 */
  alpha(lightness(#ff3366))       /* opacity(60%) */
  alpha(hsl(120, 100%, 25%))      /* 1 */
  alpha(#05ffff)                  /* 1 */
  alpha(#ffff50)                  /* 1 */
  
  opacity(rgba(100%, 50%, 0%, 0.5)) /* 0.5 */
  opacity(lighten(#800, 20%))       /* 1 */
  opacity(lightness(#ff3366))       /* opacity(60%) */
  opacity(hsl(120, 100%, 25%))      /* 1 */
  opacity(#05ffff)                  /* 1 */
  opacity(#ffff50)                  /* 1 */
```

## `rgba($color, $alpha)`
Sets the opacity of an existing color.
기존 색상의 투명도를 설정합니다.
```scss
@param  {Color}  $color
@param  {Number} $alpha : 0 ~ 1
@return {Color}
@examples
  p { color: rgba(#102030, 0.5) } /* rgba(16, 32, 48, 0.5) */
  p { color: rgba(blue, 0.2) }    /* rgba(0, 0, 255, 0.2) */
```

## `opacify($color, $amount)` == `fade-in($color, $amount)`
Makes a color more opaque.
색상을 불투명하게 만듭니다.
```scss
@param  {Color}  $color
@param  {Number} $amount : 0 ~ 1
@return {Color}
@examples
  p { color: opacify(rgba(0, 0, 0, 0.5), 0.1) }     /* rgba(0, 0, 0, 0.6) */
  p { color: opacify(rgba(0, 0, 0, 0.5), 0.4) }     /* rgba(0, 0, 0, 0.9) */
  p { color: opacify(rgba(0, 0, 17, 0.8), 0.2) }    /* #000011 */    
  p { color: opacify(rgba(255, 0, 17, 0.2), 0.5) }  /* rgba(255, 0, 17, 0.7) */
  
  p { color: fade-in(rgba(0, 0, 0, 0.5), 0.1) }     /* rgba(0, 0, 0, 0.6) */
  p { color: fade-in(rgba(0, 0, 0, 0.5), 0.4) }     /* rgba(0, 0, 0, 0.9) */
  p { color: fade-in(rgba(0, 0, 17, 0.8), 0.2) }    /* #000011 */    
  p { color: fade-in(rgba(255, 0, 17, 0.2), 0.5) }  /* rgba(255, 0, 17, 0.7) */
```

## `transparentize($color, $amount)` == `fade-out($color, $amount)`
Makes a color more opaque.
색상을 투명하게 만듭니다.
```scss
@param  {Color}  $color
@param  {Number} $amount : 0 ~ 1
@return {Color}
@examples
  p { color: transparentize(rgba(0, 0, 0, 0.5), 0.1) }     /* rgba(0, 0, 0, 0.4) */
  p { color: transparentize(rgba(0, 0, 0, 0.5), 0.4) }     /* rgba(0, 0, 0, 0.1) */
  p { color: transparentize(rgba(0, 0, 17, 0.8), 0.2) }    /* rgba(0, 0, 17, 0.6) */
  p { color: transparentize(rgba(255, 0, 17, 0.2), 0.5) }  /* rgba(255, 0, 17, 0) */
    
  p { color: fade-out(rgba(0, 0, 0, 0.5), 0.1) }     /* rgba(0, 0, 0, 0.4) */
  p { color: fade-out(rgba(0, 0, 0, 0.5), 0.4) }     /* rgba(0, 0, 0, 0.1) */
  p { color: fade-out(rgba(0, 0, 17, 0.8), 0.2) }    /* rgba(0, 0, 17, 0.6) */
  p { color: fade-out(rgba(255, 0, 17, 0.2), 0.5) }  /* rgba(255, 0, 17, 0) */
```