# 리눅스 prefix 제외하고 파일명 변경



A_abcdefg_1234567.jpg 라는 파일이 있는 경우 맨 앞 A_를 제외 하고 싶다. 그럴경우 특정 디렉토리에 파일을 몰아놓고, 아래 스크립트를 수행하면 된다.

```shell
remove=A_
for i in "$remove"*; do mv "$i" "${i#"$remove"}"; done
```



[ 참조 URL ] http://unix.stackexchange.com/questions/163864/how-to-remove-prefix-from-multiple-files-in-a-directory

