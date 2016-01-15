# Selector Functions

## `selector-nest($selectors…)`
Nests selector beneath one another like they would be nested in the stylesheet.
하나 아래에 중첩 된 선택은 그것과 같은 스타일에 중첩됩니다.
```scss
@param  {[String, List]} $selectors…
@return {List}
@examples
  selector-nest(".foo", ".bar", ".baz") /* .foo .bar .baz */
  selector-nest(".a .foo", ".b .bar")   /* .a .foo .b .bar */
  selector-nest(".foo", "&.bar")        /* .foo.bar */
```

## `selector-append($selectors…)`
Appends selectors to one another without spaces in between.
사이의 공백없이 선택자를 추가합니다.
```scss
@param  {[String, List]} $selectors…
@return {List}
@examples
  selector-append(".foo", ".bar", ".baz") /* .foo.bar.baz */
  selector-append(".a .foo", ".b .bar")   /* .a .foo.b .bar */
  selector-append(".foo", "-suffix")      /* .foo-suffix */
```

## `selector-extend($selector, $extendee, $extender)`
Extends $extendee with $extender within $selector.
`$selector`내에서 `$extender`와 `$extendee`를 확장합니다.
```scss
@param  {List} $selector
@param  {List} $extendee
@param  {List} $extender
@return {List}
@examples
  selector-extend(".a .b", ".b", ".foo .bar") /* .a .b, .a .foo .bar, .foo .a .bar */
```

## `selector-replace($selector, $original, $replacement)`
Replaces $original with $replacement within $selector.
`$selector`내에서 `$original`와 `$replacement`를 확장합니다.
```scss
@param  {String, List} $selector
@param  {String, List} $original
@param  {String, List} $replacement
@return {List}
@examples
  selector-replace(".foo .bar", ".bar", ".baz")         /* .foo .baz */
  selector-replace(".foo.bar.baz", ".foo.baz", ".qux")  /* .bar.qux */
```

## `selector-unify($selector1, $selector2)`
Unifies two selectors to produce a selector that matches elements matched by both.
유사한 요소 모두를 일치 선택자로 생산하기 위해 두 선택자를 단결합니다.
```scss
@param  {String, List} $selector1
@param  {String, List} $selector2
@return {List, Null}
@examples
  selector-unify(".a", ".b")        /* .a.b */
  selector-unify(".a .b", ".x .y")  /* .a .x .b.y, .x .a .b.y */
  selector-unify(".a.b", ".b.c")    /* .a.b.c */
  selector-unify("#a", "#b")        /* null */
```

## `is-superselector($super, $sub)`
Returns whether $super matches all the elements $sub does, and possibly more.
`$super`가 아마도 더 많은 모든 요소 `$sub`에서 일치하는지 여부를 확인합니다.
```scss
@param  {String, List} $super
@param  {String, List} $sub
@return {Bool}
@examples
  is-superselector(".foo", ".foo.bar")  /* true */
  is-superselector(".foo.bar", ".foo")  /* false */
  is-superselector(".bar", ".foo .bar") /* true */
  is-superselector(".foo .bar", ".bar") /* false */
```

## `simple-selectors($selector)`
Returns the simple selectors that comprise a compound selector.
복합 선택기를 구성하는 간단한 선택자를 반환합니다.
```scss
@param  {String} $selector
@return {List}
@examples
  simple-selectors(".foo.bar")      /* .foo, .bar */
  simple-selectors(".foo.bar.baz")  /* .foo, .bar, .baz */
```

## `selector-parse($selector)`
Parses a selector into the format returned by &.
복합 선택기를 구성하는 간단한 선택자를 반환합니다.
```scss
@param  {String, List} $selector
@return {List}
@examples
  selector-parse(".foo .bar, .baz .bang") /* .foo .bar, .baz .bang */
```