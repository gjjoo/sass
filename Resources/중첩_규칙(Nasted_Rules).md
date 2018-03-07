# 중첩 규칙(Nasted Rules)

Sass는 CSS 규칙을 서로 중첩 할 수 있습니다.

```scss
#main p {
  color: #00ff00;
  width: 97%;

  .redbox {
    background-color: #ff0000;
    color: #000000;
  }
}
```

is compiled to:

```scss
#main p {
  color: #00ff00;
  width: 97%;
}
#main p .redbox {
  background-color: #ff0000;
  color: #000000; 
}
```

이것으로 부모 선택 반복을 방지 할 수 있습니다. 다만 중첩 된 selector가 많을 경우 CSS가 복잡해 질 수 있으며, 뿐만 아니라 콜백 지옥을 맛볼 수도 있습니다.

```scss
div#main {
  width: 97%;

  div.page {
    font-size: 2em;
    div.aside {
      position: fixed;
      top: 0;
      left: 0;
      ul.menu {
        margin: 0;
        padding: 0;
        li.menut-item {
          i {
            font-size: 11px;
          }
          a { 
            font-weight: bold;
            img {
              vertical-align: bottom;
            }
          }
        }
      }
    }
  }
  // 위 코드를 보면 중괄호의 닫는 시점이 햇갈릴 것입니다.

  pre { font-size: 3em; }
}
```

is complied to:

```scss
// 적절하지 않은 중첩 코드는 아래와 같이 쓸데없는 CSS 선택자를 남용하여 생성하게 되니 주의해야 합니다.

div#main {
  width: 97%;
}
div#main div.page {
  font-size: 2em;
}
div#main div.page div.aside {
  position: fixed;
  top: 0;
  left: 0;
}
div#main div.page div.aside ul.menu {
  margin: 0;
  padding: 0;
}
div#main div.page div.aside ul.menu li.menut-item i {
  font-size: 11px;
}
div#main div.page div.aside ul.menu li.menut-item a {
  font-weight: bold;
}
div#main div.page div.aside ul.menu li.menut-item a img {
  vertical-align: bottom;
}
div#main pre {
  font-size: 3em;
}
```