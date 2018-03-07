# Ruby환경 sass-convert 명령어

```sh
$ sass-convert [OPTIONS] [INPUT] [OUTPUT]
$ sass-convert scss/style.scss sass/style.sass
```

```sh
# 옵션
-F / --from      # 변경할 파일 문법 (css|sass|scss)
-T / --to        # 변경하여 생성할 파일 문법 (sass|scss)
-R / --recursive # 하위 디렉토리까지 모두 변환
--indent t       # 스페이스가 아닌, 탭으로 들여쓰기 (2|t)
```

```sh
# 디렉토리 이름
sass    # [INPUT] 소스 폴더 이름
convert # [OUTPUT] 내보낼 폴더 이름
```

```sh
# 컴파일 결과
$ sass-convert -F scss -T sass -R --indent t sass convert

    convert sass/common/_classes.scss
     create convert/common/_classes.sass
    convert sass/common/_normalize.scss
     create convert/common/_normalize.sass
    convert sass/sass-part/_comments.scss
     create convert/sass-part/_comments.sass
    convert sass/sass-part/_nested.scss
     create convert/sass-part/_nested.sass
    convert sass/style.scss
     create convert/style.sass
```

```sh
# sourcemap 옵션 설정
$ sass -w --sourcemap=none sass/style.scss:css/style.css # --sourcemap=none
```