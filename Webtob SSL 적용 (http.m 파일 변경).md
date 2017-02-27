# Webtob SSL 적용 (http.m 파일 변경)

http.m 관련파일을 수정하여야 Apache의 conf파일을 변경한 것과 같다. 
Node 선언 부분에 80포트가 설정되어 있는데 443도 추가하여야 https로 통신할때 forbidden이 나오지 않는다.

단순 수정으로는 반영이 안되고 컴파일을 진행해야 하는데, 코드는 아래와 같다.

```shell
wscfl -i 설정파일명 -o 컴파일된파일명
wscfl -i http_ssl.m -o sslconfig
```

반드시 wsdown과 wsboot로 재기동을 진행해야하고, sslconfig파일로 default 컴파일 파일을 변경할 경우 아래 명령어로 시작명령어를 수정하여야 한다.

```shell
wsboot -f 파일명
wsboot -f sslconfig
```

* browser 보안이슈로 인해서 cipher suite에 대한 설정이 추가로 진행되었다.

[ 참조 URL ] https://www.kicassl.com/cstmrsuprt/ntc/searchNtcDetail.sg?page=&ntcSeq=96&mode=&searchType=subject&searchWord=&searchRowCnt=10

[ 참조 URL ] https://yessign.or.kr/ssl/FileDown.do?atch_seq=285&dir=/data

[ 참조 URL ] http://testing.pe.kr/xe/?mid=computer_01&document_srl=3318&category=2244&sort_index=readed_count&order_type=asc