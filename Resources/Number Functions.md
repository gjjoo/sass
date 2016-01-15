# Number Functions

### `percentage($number)`
Converts a unitless number to a percentage.
단위없는 숫자를 백분율로 변환합니다.
```sass
@param  {Number} $number
@return {Number}
@examples
  percentage(0.2)           /* 20% */
  percentage(100px / 50px)  /* 200% */
```

### `round($number)`
Rounds a number to the nearest whole number.
가장 가까운 정수로 반올림 합니다.
```sass
@param  {Number} $number
@return {Number}
@examples
  round(10.4px) /* 10px */
  round(10.6px) /* 11px */
```

### `ceil($number)`
Rounds a number up to the next whole number.
다음 정수로 숫자를 올립니다.
```sass
@param  {Number} $number
@return {Number}
@examples
  ceil(10.4px)  /* 11px */
  ceil(10.6px)  /* 11px */
```

### `floor($number)`
Rounds a number down to the previous whole number.
이전 정수로 숫자를 내립니다.
```sass
@param  {Number} $number
@return {Number}
@examples
  floor(10.4px)  /* 10px */
  floor(10.6px)  /* 10px */
```

### `min($numbers…)`
Finds the minimum of several numbers.
여러 숫자의 최소를 찾습니다.
```sass
@param  {[Number]} $numbers…
@return {Number}
@examples
  min(1px, 4px)       /* 1px */
  min(5em, 3em, 4em)  /* 3em */
```

### `max($numbers…)`
Finds the maximum of several numbers.
여러 숫자의 최소를 찾습니다.
```sass
@param  {[Number]} $numbers…
@return {Number}
@examples
  max(1px, 4px)       /* 4px */
  max(5em, 3em, 4em)  /* 5em */
```

### `random([$limit])`
Returns a random number.
임의의 수를 반환합니다.
```sass
@param  {Number} $limit
@return {Number}
@examples
  random()    /* 0 ~ 1 사이의 소수 */
  random(10)  /* 1 ~ 10 사이의 정수 */
```