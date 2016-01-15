# Miscellaneous Functions

## `if($condition, $if-true, $if-false)`
Returns one of two values, depending on whether or not $condition is true.
`$condition`이 참인지 여부에 따라 두 값중 하나를 반환합니다.
```scss
@param  {Base} $condition : 조건식
@param  {Node} $if-true   : 조건이 참일 경우
@param  {Node} $if-false  : 조건이 거짓일 경우
@return {Base}
@examples
  if(true, 1px, 2px)  /* 1px */
  if(false, 1px, 2px) /* 2px */
```

## `unique-id()`
Returns a unique CSS identifier.
고유 CSS 식별자를 돌려줍니다.
```scss
@return {String}
@examples
  unique-id() /*  해당 식별자는 인용되지 않은 문자열로 반환됩니다. */
```