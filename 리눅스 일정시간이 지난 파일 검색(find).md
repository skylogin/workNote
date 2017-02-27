# 리눅스 일정시간이 지난 파일 검색(find)

```shell
find ./* -mtime +365
```

**find**명령어를 통해 일정시간이 지난 파일에 대한 검색이 가능하다.
기본문법은 *find 경로 -mitme +숫자* 이며 mtime의 1은 하루를 의미한다.

mtime말고 atime과 ctime도 있는데, 변경된 시간으로 검색하는 것이 좋기에 mtime으로 보면 될 것 같다.

mmin도 있으나 분까지 조사할일은 없겠지..