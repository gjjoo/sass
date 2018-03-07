# String Functions

### `unquote($string)`
Removes quotes from a string.
문자열에서 따옴표를 제거합니다.
```sass
@param  {String} $string
@return {String}
@examples
  unquote("foo")  /* foo */
  unquote(foo)    /* foo */
```

### `quote($string)`
Adds quotes to a string.
문자열에 따옴표를 추가합니다.
```sass
@param  {String} $string
@return {String}
@examples
  quote("foo")  /* "foo" */
  quote(foo)    /* "foo" */
```

### `str_length($string)`
Returns the number of characters in a string.
문자열의 문자 수를 돌려줍니다.
```sass
@param  {String} $string
@return {Number}
@examples
  str-length("foo") /* 3 */
```

### `str_insert($string, $insert, $index)`
Inserts $insert into $string at $index.
`$insert`의 값을 `$string`의 `$index` 위치에 삽입합니다.
```sass
@param  {String} $string
@param  {String} $insert
@param  {Number} $index
@return {Number}
@examples
  str-insert("abcd", "X", 1)  /* "Xabcd" */
  str-insert("abcd", "X", 4)  /* "abcXd" */
  str-insert("abcd", "X", 5)  /* "abcdX" */
```

### `str_index($string, $substring)`
Returns the index of the first occurrence of $substring in $string.
`$string`에서 `$substring`의 첫 번째 항목의 인덱스를 돌려줍니다.
```sass
@param  {String} $string
@param  {String} $substring
@return {Number, Null}
@examples
  str-index(abcd, a)  /* 1 */
  str-index(abcd, ab) /* 1 */
  str-index(abcd, X)  /* null */
  str-index(abcd, c)  /* 3 */
```

### `str_slice($string, $start-at, $end-at:-1)`
Extracts a substring from $string.
`$string`에서 문자열을 추출합니다.
```sass
@param  {String} $string
@param  {Number} $start-at
@param  {Number} $end-at
@return {String}
@examples
  str-slice("abcd", 2, 3)   /* "bc" */
  str-slice("abcd", 2)      /* "bcd" */
  str-slice("abcd", -3, -2) /* "bc" */
  str-slice("abcd", 2, -2)  /* "bc" */
```

### `to_upper_case($string)`
Converts a string to upper case.
대문자로 된 문자열로 변환합니다.
```sass
@param  {String} $string
@return {String}
@examples
  to-upper-case(abcd) /* ABCD */
```

### `to_lower_case($string)`
Converts a string to lower case.
소문자로 된 문자열로 변환합니다.
```sass
@param  {String} $string
@return {String}
@examples
  to-lower-case(ABCD) /* abcd */
```