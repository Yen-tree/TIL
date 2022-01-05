# git add 에러 - LF will be replaced by CRLF

## 2022.01.05(수)

코드

```
$ git add .
```

에러

```
warning: LF will be replaced by CRLF in .idea/inspectionProfiles/profiles_
settings.xml.
The file will have its original line endings in your working directory
```

- 맥 또는 리눅스를 쓰는 개발자와 윈도우 쓰는 개발자가 Git으로 협업할 때 발생하는 **Whitespace** 에러

- 유닉스 시스템에서는 한 줄의 끝이 **LF(Line Feed)**로 이루어지는 반면, 윈도우에서는 줄 하나가 **CR(Carriage Return)**와 **LF(Line Feed)**, 즉 **CRLF**로 이루어지기 때문이다.

### 해결

core.autocrlf 기능을 키면 된다.

윈도우

```
git config --global core.autocrlf true
```

