# 믹스인(Mixin)

## 믹스인(Mixin) 기본 정의
스타일 전반에 걸쳐 재사용 할 수 있는 스타일을 정의 하여 사용 할 수 있습니다.

믹스인 정의(Defining a Mixin)
- Sass: `=`
- SCSS: `@mixin`

```scss
@mixin large-text {
  font: {
    family: Arial;
    size: 20px;
    weight: bold;
  }
  color: #ff0000;
}
```

믹스인 호출(Including a Mixin)
- Sass: `+`
- SCSS: `@include`

```scss
.page-title {
  @include large-text; // 앞서 정의한 large-text 믹스인을 호출함
  padding: 4px;
  margin-top: 10px;
}
```

is complied to:

```scss
.page-title {
  font-family: Arial;
  font-size: 20px;
  font-weight: bold;
  color: #ff0000;
  padding: 4px;
  margin-top: 10px;
}
```

## 전달 인자(Arguments)
@mixin으로 정의된 모듈에 인자를 전달하여 변수로써 믹스인 내부에서 사용 할 수 있습니다.

```scss
@mixin sexy-border($color, $width) {
  border: {
    color: $color;
    width: $width;
    style: dashed;
  }
}
p { @include sexy-border(blue, 1in); }
```

is complied to:

```scss
p {
  border-color: blue;
  border-width: 1in;
  border-style: dashed;
}
```

### 믹스인(Mixin)은 전달 인자의 기본값을 지정할 수 있습니다.
해당 인자를 전달하지 않은 경우, 디폴트 값이 대신 사용됩니다.

```scss
@mixin sexy-border($color, $width: 1in) {
  border: {
    color: $color;
    width: $width;
    style: dashed;
  }
}
p { @include sexy-border(blue); }
h1 { @include sexy-border(blue, 2in); }
```

is complied to:

```scss
p {
  border-color: blue;
  border-width: 1in;
  border-style: dashed;
}
h1 {
  border-color: blue;
  border-width: 2in;
  border-style: dashed;
}
```

## 키워드 전달 인자(Keyword Arguments)
명시적으로 특정 키워드를 인수로 사용할 수 있습니다. 명명 된 인수는 임의의 순서로 전달 될 수 있으며, 디폴트 값과 인수를 생략 할 수 있습니다.

```scss
p { @include sexy-border($color: blue); }
h1 { @include sexy-border($color: blue, $width: 2in); }
```

## 가변 전달 인자(Variable Arguments)
전달할 인자의 개수가 고정되지 않고, 가변적으로 변할 떄 주로 사용어지며, 호출 시 전달 받은 인자를 List로 처리합니다.

```scss
@mixin box-shadow($shadows...) {
  -moz-box-shadow: $shadows;
  -webkit-box-shadow: $shadows;
  box-shadow: $shadows;
}

.shadows {
  @include box-shadow(0px 4px 5px #666, 2px 6px 10px #999);
}
```

### 믹스인 변수를 호출할 때 인자가 또한 사용될 수 있습니다.
각 값은 별도의 인수로 전달되도록 List로 확장하거나, 키워드 인수로 처리되도록 Map을 확장하여 사용할 수 있습니다.

```scss
@mixin colors($text, $background, $border) {
  color: $text;
  background-color: $background;
  border-color: $border;
}

$values: #ff0000, #00ff00, #0000ff;
.primary {
  @include colors($values...);
}

$value-map: (text: #00ff00, background: #0000ff, border: #ff0000);
.secondary {
  @include colors($value-map...);
}
```

is complied to:

```scss
.primary {
  color: #ff0000;
  background-color: #00ff00;
  border-color: #0000ff;
}
.secondary {
  color: #00ff00;
  background-color: #0000ff;
  border-color: #ff0000;
}
```

## 믹스인 콘텐츠 블럭(Passing Content Blocks to a Mixin)

```scss
@mixin apply-to-ie6-only {
  * html {
    @content;
  }
}
@include apply-to-ie6-only {
  #logo {
    background-image: url(/logo.gif);
  }
}
```

Generates:

```scss
* html #logo {
  background-image: url(/logo.gif);
}
```

### 변수 범위 및 내용 블록(Variable Scope and Content Blocks)

```scss
$color: white;
@mixin colors($color: blue) {
  background-color: $color;
  @content;
  border-color: $color;
}
.colors {
  @include colors { color: $color; }
}
```

Compiles to:

```scss
.colors {
  background-color: blue;
  color: white;
  border-color: blue;
}
```