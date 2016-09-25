# checkbox에 대한 css style

해외출장 예산체크 버튼을 변경하기 위해 checkbox의 style을 적용해보았다.
원리는 기존의 checkbox에 대해서 `display:none` 처리 이후에 가상의 before구문을 통해서 새로운 체크박스를 보여주는 방식.

[ 참조링크 ]: http://ichbintaeeun.tistory.com/16



중간에 체크박스는 U+2713을 사용하였다.

[ 참조링크 ]: http://www.utf8icons.com/character/10003/check-mark



### 전체소스

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Document</title>
<style>
.checkbox {
    display: none;
}

.checkbox + label{
    display: inline-block;
    cursor: pointer;
    position: relative;
    padding-left: 20px;
    margin-right: 15px;
    font-size: 13px;
}

.checkbox:checked + label:before {
    content: "\2713";  /* 체크모양 */
    font-size: 13px;
    font-weight:800;
    color: #fff;
    text-align: center;
    line-height: 13px;
}
.checkbox + label:before {
    content: "";
    display: inline-block;

    width: 14px;
    height: 14px;

    margin-right: 10px;
    position: absolute;
    left: 0;
    bottom: 1px;
    background-color: #ccc;
    border-radius: 2px;
    box-shadow: inset 0px 1px 1px 0px rgba(0, 0, 0, .3), 0px 1px 0px 0px rgba(255, 255, 255, .8);
}
.checkbox-success:checked + label:before {
    background:#5cb85c;
}
.checkbox-danger:checked + label:before {
    background:#d9534f;
}
</style>
</head>
<body>
	<input type="checkbox" id="chk" class="checkbox checkbox-success"/>
	<label for="chk">라벨</label>

	<input type="checkbox" id="chk2" class="checkbox checkbox-danger"/>
	<label for="chk2">라벨</label>
</body>
</html>
```
