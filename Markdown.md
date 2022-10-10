# ***Markdown***


<br>

# HEAD_1
## HEAD_2
### HEAD_3
#### HEAD_5
##### HEAD_6
###### HEAD_7

HEAD (None)
<br>

___
<br>

### 아래처럼 라인을 추가하려면 "___" underscore 3번
혹은 `<hr>` 입력으로도 가능

___
## 줄바꿈

`<br>` 입력 혹은
  
띄어쓰기 두번
  
___
<br>

***Bold*** - `***단어***`<br>
*italic* - `*단어*`<br>
~~strikethrough~~ - `~~단어~~`<br>
<br>

___
## Quote
> `>`
>> `>>`
>>> `>>>`
>>>> `>>>>`
>>>>> `>>>>>`
>>>>>> `>>>>>>`
>>>>>>> `>>>>>>>`
<br>

___
## Bullet list

* Bullet list
* `* Bullet list`
    * Bullet list
    * `들여쓰기 + * Bullet list`
        * Bullet list  
        * `들여쓰기 + * Bullet list`

<br>

- Bullet list
- `- Bullet list`
    - Bullet list
    - `들여쓰기 + - Bullet list`
        - Bullet list  
        - `들여쓰기 + - Bullet list`
<br>

___
## Numbered list
<br>


1. Number list
1. `1. Number list`
    1. Number list
    1. `들여쓰기 + 1. Number list`
    1. 굳이 숫자대로 입력하지 않아도 
    1. 자동으로 숫자 정렬이 되요.
    1. `1. 자동으로 숫자 정렬이 되요.`
<br>

___
## Link
<br>

Click [Here](https://github.com/Xenrose/Xenrose)
<br>
Click `[Here](https://github.com/Xenrose/Xenrose)`
<br>
___
## image
<br>

![iamge description](https://avatars.githubusercontent.com/u/114465217?v=4)

`![iamge description](https://avatars.githubusercontent.com/u/114465217?v=4)`

___

## Table
<br>

|(1,1)|(1,2)|
|--|--|
|(2,1)|(2,2)|

```
|(1,1)|(1,2)|
|--|--|
|(2,1)|(2,2)|
```


|왼쪽 정렬|왼쪽 정렬|
|:--|:--|
|왼쪽|왼쪽|
```
|왼쪽 정렬|왼쪽 정렬|
|:--|:--|
|왼쪽|왼쪽|
```

|오른쪽 정렬|오른쪽 정렬|
|--:|--:|
|오른쪽|오른쪽|
```
|오른쪽 정렬|오른쪽 정렬|
|--:|--:|
|오른쪽|오른쪽|
```

|중앙 정렬|중앙 정렬|
|:--:|:--:|
|중앙|중앙|
```
|중앙 정렬|중앙 정렬|
|:--:|:--:|
|중앙|중앙|
```
___
## Code
<br>

코드를 쓰고 싶다면 `` 으로 감싸요<br>
`print("이런식으로 입력 가능")`

만약 긴 코드라면
```
print("``` 세번을 쓰면 됩니다.```")
```

```python
print("```뒤에 사용하는 코드를 적으면 하이라이트도 가능합니다.```")
print("```python```")
```
___
## Font

<span style="color:red">Font</span>
<br>
```
<span style="color:red">Font</span>
```
<br>

<span style="color:#F8766D">16진수 Font</span>
```
<span style="color:#F8766D">16진수 Font</span>
```
<br>


<p style="font-size:20px">font-size:20px</p>

```
<p style="font-size:20px">font-size:20px</p>
```

<span style="color:red ; font-size:20px">Font 색상 + Font size</span>
```
<span style="color:red ; font-size:20px">Font 색상 + Font size</span>
```

* 색상 - Color:color code
* 굵기 - font-weight:bold
* 기울기 - font-style:italic
* 크기 - font-size:00px or 00% or 00em
* 글꼴 - font-family:굴림, 돋움 등
* 줄높이 line-height: 00px or 00% or 00em
  
___
## 수학식 (tex)

ex1)  
$y = x$  
`$y = x$`
  

ex2)  
$$\sqrt[5](x^3+y^2+z^1)/xyz$$
`$$\sqrt[5](x^3+y^2+z^1)/xyz$$`
  
ex3)  
$\sqrt[5](x^3+y^2+z^1)\over XYZ$  
`$$\sqrt[5](x^3+y^2+z^1)\over XYZ$$`
___
## Task list  
  

* ***이건 gitgub에서만 적용됩니다.***

- [ ] 해야할 일 1
- [x] 해결한 일 1
- [ ] 해야할 일 2
- [ ] 해야할 일 3
- [x] 해결한 일 2

```
- [ ] 해야할 일 1
- [x] 해결한 일 1
- [ ] 해야할 일 2
- [ ] 해야할 일 3
- [x] 해결한 일 2
```
___
