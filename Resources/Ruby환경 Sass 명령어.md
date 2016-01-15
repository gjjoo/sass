# Ruby환경 Sass 명령어

```sh
$ sass -h                             # 도움말 보기
$ sass [options] [input] [output]     # 컴파일(한번만)

# sass -w [INPUT]:[OUTPUT], 지속적인 관찰(폴더)
$ sass --watch [input]:[output]

# sass -w [INPUT]:[OUTPUT], 지속적인 관찰(파일)
$ sass --watch [input.sass]:[output.css]
$ sass -w -t compact [input]:[output] # nested expanded compact compressed

### Options ###
# -v, --version     : 버전확인
# -t, --style Name  : 스타일 정의
# --sourcemap=TYPE  : 소스맵 사용
# -w, --watch       : 파일 및 폴더 감지하여 빌드
# -E ENCODING       : 아웃풋 인코딩 설정

$ sass -E utf-8 sass/style.scss css/style.css # 인코딩 옵션 설정 -E utf-8
```

