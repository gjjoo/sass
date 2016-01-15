# List Functions

## `length($list)`
Returns the length of a list. This can return the number of pairs in a map as well.
리스트의 길이를 반환합니다. 뿐만 아니라 맵에 쌍의 수를 반환 할 수 있습니다.
```sass
@param  {Base} $list
@return {Number}
@examples
  length(10px) /* 1 */
  length(10px 20px 30px) /* 3 */
  length((width: 10px, height: 20px)) /* 2 */
```

## `nth($list, $n)`
Returns a specific item in a list.
목록에서 특정 항목을 돌려줍니다.
```sass
@param  {Base}   $list
@param  {Number} $n
@return {List}
@examples
  nth(10px 20px 30px, 1) /* 10px */
  nth((Helvetica, Arial, sans-serif), 3) /* sans-serif */
  nth((width: 10px, length: 20px), 2) /* length 20px */
```

## `set-nth($list, $n, $value)`
Replaces the nth item in a list.
목록에서 n 번째 항목을 대체합니다.
```sass
@param  {Base}   $list
@param  {Number} $n
@param  {Base}   $value
@return {List}
@examples
  set-nth($list: 10px 20px 30px, $n: 2, $value: -20px -10px) /* 10px -20px -10px 30px */
  set-nth($list: 20px 30px, $n: 1, $value: -20px); /* -20px 30px */
```

## `join($list1, $list2, [$separator:auto])`
Joins together two lists into one.
하나에 두 개의 목록을 함께 결합합니다.
```sass
@param  {Base}   $list1
@param  {Base}   $list2
@param  {String} $separator : auto(default) | comma | space
@return {List}
@examples
  join(10px 20px, 30px 40px) /* 10px 20px 30px 40px */
  join((blue, red), (#abc, #def)) /* blue, red, #abc, #def */
  join(10px, 20px) /* 10px 20px */
  join(10px, 20px, comma) /* 10px, 20px */
  join((blue, red), (#abc, #def), space) /* blue red #abc #def */
```

## `append($list1, $val, [$separator:auto])`
Appends a single value onto the end of a list.
리스트의 끝에 단일 값을 추가합니다.
```sass
@param  {Base}   $list
@param  {Base}   $val
@param  {String} $separator : auto(default) | comma | space
@return {List}
@examples
  append(10px 20px, 30px) /* 10px 20px 30px */
  append((blue, red), green) /* blue, red, green */
  append(10px 20px, 30px 40px) /* 10px 20px 30px 40px */
  append(10px, 20px, comma) /* 10px, 20px */
  append((blue, red), green, space) /* blue red green */
```

## `zip($lists…)`
Combines several lists into a single multidimensional list.
하나의 다차원 목록에 여러 개의 목록을 결합합니다.
```sass
@param  {Base} $lists…
@return {List}
@examples
  zip(1px 1px 3px, solid dashed solid, red green blue) /* 1px solid red, 1px dashed green, 3px solid blue */
```

## `index($list, $value)`
Returns the position of a value within a list.
목록 내의 값의 위치를 돌려줍니다.
```sass
@param  {Base} $list
@param  {Base} $value
@return {Number, Null}
@examples
  index(1px solid red, solid) /* 2 */
  index(1px solid red, dashed) /* null */
```

## `list-separator($list)`
Returns the separator of a list.
목록의 분리를 돌려줍니다.
```sass
@param  {Base} $list
@return {String} : comma | space
@examples
  list-separator(1px 2px 3px) /* space */
  list-separator((1px, 2px, 3px)) /* comma */
  list-separator('foo') /* space */
```