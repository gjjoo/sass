# 변수(Variables)

### Sass 변수($)
- 변수를 정의할 때 묶어서 관리할 파일(e.g: `_config.scss`)을 통해 제어한다.
- 변수를 정의하지 않아 오류가 발생할 확률이 있다면, [`!default`](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#variable_defaults_) 플래그를 사용해 오류를 방지한다.
- 나머지 연산으로 처리되거나, 문자열 안에 변수를 설정할 경우 [인터폴레이션(보간법, `#{$variable}`)](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#interpolation_)을 사용한다.



