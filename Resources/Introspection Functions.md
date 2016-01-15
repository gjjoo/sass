# Introspection Functions

## `feature-exists($feature)`
Returns whether a feature exists in the current Sass runtime.
현재 사스 런타임에 기능이 존재하는지 여부를 반환합니다.
```scss
@param  {String} $feature
@return {Bool}
@examples
  feature-exists(global-variable-shadowing); /* true */
  feature-exists(extend-selector-pseudoclass); /* true */
  feature-exists(units-level-3); /* true */
  feature-exists(at-error); /* true */
```

## `variable-exists($name)`
Returns whether a variable with the given name exists in the current scope.
지정된 이름을 가지는 변수가 현재 범위에 있는지 여부를 반환합니다.
```scss
@param  {String} $name : '$'기호는 포함하지 않습는다.
@return {Bool}
@examples
  $a-false-value: false;
  variable-exists(a-false-value) /* true */
  
  variable-exists(nonexistent) /* false */
```

## `global-variable-exists($name)`
Returns whether a variable with the given name exists in the global scope.
지정된 이름을 가지는 변수가 전역 범위에 있는지 여부를 반환합니다.
```scss
@param  {String} $name : '$'기호는 포함하지 않습는다.
@return {Bool}
@examples
  $a-false-value: false;
  global-variable-exists(a-false-value) /* true */
  
  .foo {
    $some-var: false;
    @if global-variable-exists(some-var) { /* false, doesn't run */ }
  }
```

## `function-exists($name)`
Returns whether a function with the given name exists.
지정된 이름의 함수가 존재하는지 여부를 반환합니다.
```scss
@param  {String} $name
@return {Bool}
@examples
  function-exists(lighten); /* true */
  
  @function myfunc { @return "something"; }
  function-exists(myfunc); /* true */
```

## `mixin-exists($name)`
Returns whether a mixin with the given name exists.
지정된 이름의 믹스 인이 존재하는지 여부를 반환합니다.
```scss
@param  {String} $name
@return {Bool}
@examples
  mixin-exists(nonexistent) /* false */
  
  @mixin red-text { color: red; }
  mixin-exists(red-text) /* true */
```

## `inspect($value)`
Returns the string representation of a value as it would be represented in Sass.
Sass 안에서 표현될 것 같은 값을 문자열 표현으로 반환합니다.
```scss
@param  {Base} $value
@return {String}
@examples
  inspect(aaa bbb ccc)            /* aaa bbb ccc */
  inspect((key1: aaa, key2: bbb)) /* (key1: aaa, key2: bbb) */
  inspect(10px)                   /* 10px */
  inspect(rgba(#FF7F00, 0.4))     /* rgba(255, 127, 0, 0.4) */
```

## `type-of($value)`
Returns the type of a value.
값의 형태를 반환합니다.
```scss
@param  {Base} $value
@return {String}
@examples
  type-of(100px)  /* number */
  type-of(asdf)   /* string */
  type-of("asdf") /* string */
  type-of(true)   /* bool */
  type-of(#fff)   /* color */
  type-of(blue)   /* color */
```

## `unit($number)`
Returns the units associated with a number.
숫자와 관련된 단위를 돌려줍니다.
```scss
@param  {Number} $number
@return {String}
@examples
  unit(100)         /* '' */
  unit(100px)       /* px */
  unit(3em)         /* em */
  unit(10px * 5em)  /* em*px */
  unit(10px * 5em / 30cm / 1rem) /* em/rem */
```

## `unitless($number)`
Returns whether a number has units.
숫자에서 단위 여부를 반환합니다.
```scss
@param  {Number} $number
@return {Bool} : 단위가 없으면 true | 단위가 있으면 false
@examples
  unitless(100)     /* true */
  unitless(100px) /* false */
```

## `comparable($number1, $number2)`
Returns whether two numbers can be added, subtracted, or compared.
두 숫자가 추가 감산, 또는 비교 될 수 있는지 여부를 반환합니다.
```scss
@param  {Number} $number1
@param  {Number} $number2
@return {Bool}
@examples
  comparable(2px, 1px)    /* true */
  comparable(100px, 3em)  /* false */
  comparable(10cm, 3mm)   /* true */
```

## `call($name, $args…)`
Dynamically calls a Sass function.
동적으로 Sass 함수를 호출합니다.
```scss
@param  {String} $name  : 함수 이름
@param  {Base}   $args… : 해당 함수 이름의 인자 값
@examples
  call(rgb, 10, 100, 255) /* #0a64ff */
  call(scale-color, #0a64ff, $lightness: -10%) /* #0058ef */
  
  $fn: nth;
  call($fn, (a b c), 2) /* b */
```