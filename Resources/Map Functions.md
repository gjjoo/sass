# Map Functions

### `map-get($map, $key)`
Returns the value in a map associated with a given key.
주어진 키와 관련된 맵의 값을 돌려줍니다.
```sass
@param  {Map}  $map
@param  {Base} $key
@return {Base}
@examples
  map-get(("foo": 1, "bar": 2), "foo") /* 1 */
  map-get(("foo": 1, "bar": 2), "bar") /* 2 */
  map-get(("foo": 1, "bar": 2), "baz") /* null */
```

### `map-merge($map1, $map2)`
Merges two maps together into a new map.
새로운 맵에 두 개의 맵을 병합합니다.
```sass
@param  {Map} $map1
@param  {Map} $map2
@return {Map}
@examples
  map-merge(("foo": 1), ("bar": 2))           /* ("foo": 1, "bar": 2) */
  map-merge(("foo": 1, "bar": 2), ("bar": 3)) /* ("foo": 1, "bar": 3) */
```

### `map-remove($map, $keys…)`
Returns a new map with keys removed.
기존 맵에서 키를 제거하여 새로운 맵을 돌려줍니다.
```sass
@param  {Map}    $map
@param  {[Base]} $keys…
@return {Map}
@examples
  map-remove(("foo": 1, "bar": 2), "bar")                   /* ("foo": 1) */
  map-remove(("foo": 1, "bar": 2, "baz": 3), "bar", "baz")  /* ("foo": 1) */
  map-remove(("foo": 1, "bar": 2), "baz")                   /* ("foo": 1, "bar": 2) */
```

### `map-keys($map)`
Returns a list of all keys in a map.
맵에 있는 모든 키의 리스트를 돌려줍니다.
```sass
@param  {Map} $map
@return {List}
@examples
  map-keys((foo: 1, bar: 2)) /* foo, bar */
  map-keys(("foo": 1, "bar": 2)) /* "foo", "bar" */
```

### `map-values($map)`
Returns a list of all values in a map.
맵에 있는 모든 값의 리스트를 돌려줍니다.
```sass
@param  {Map} $map
@return {List}
@examples
  map-values(("foo": 1, "bar": 2))            /* 1, 2 */
  map-values(("foo": 1, "bar": 2, "baz": 1))  /* 1, 2, 1 */
```

### `map-has-key($map, $key)`
Returns whether a map has a value associated with a given key.
맵에 지정된 키의 값이 있는지 없는지 판단하여 참/거짓 값으로 돌려줍니다.
```sass
@param  {Map}  $map
@param  {Base} $key
@return {Bool}
@examples
  map-has-key(("foo": 1, "bar": 2), "foo")  /* true */
  map-has-key(("foo": 1, "bar": 2), "baz")  /* false */
```

### `keywords($args)`
Returns the keywords passed to a function that takes variable arguments.
가변 인수를 취하는 함수에 전달 된 키워드를 돌려줍니다.
```sass
@param  {ArgList} $args
@return {Map}
@examples
  @mixin foo($args...) {
    @debug keywords($args); //=> (arg1: val, arg2: val)
  }

  @include foo($arg1: val, $arg2: val);
```