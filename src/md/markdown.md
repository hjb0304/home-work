# 🔍 마크다운 문법

일반 텍스트 기반의 경량 마크업 언어다. 서식이 있는 문서를 작성하는 데 사용되며, 일반 마크업 언어에 비해 문법이 쉽고 간결하다는 특징이 있다. github 저장소의 정보를 기록하는 README.md 파일에서 자주 쓰인다.

<br>

## 제목(Headings)

제목을 표시한다. h1~h6까지 표시할 수 있다. 제목 앞뒤에 빈 줄을 넣어야 한다.

- 제목 레벨 1 <br>

  ```

  # 제목1

  ```

  # 제목1

- 제목 레벨 2 <br>

  ```

  ## 제목2

  ```

  ## 제목2

    <br>

## 문단(Paragraphs)

문단을 생성한다. 문단을 구분하기 위해서는 빈 줄을 사용한다.<br>

```
문단 내용1

문단 내용2
```

문단 내용1

문단 내용2

<br>

## 줄 바꿈(Line Breaks)

줄 바꿈을 하고 싶다면 문단이 끝난 후 두 칸의 공백을 만든다. 또는 html 태그인 **br**을 사용할 수 있다.

```
문단 내용1
문단 내용2

문단 내용1<br>
문단 내용2
```

문단 내용1  
문단 내용2

문단 내용1<br>
문단 내용2

<br>

## 굵게(Bold)

텍스트를 굵게 표시한다.

```
**굵은 텍스트**
__굵은 텍스트__
```

**굵은 텍스트**  
**굵은 텍스트**

  <br>
  
## 기울임체(Italic)

텍스트를 기울임체로 표시한다. 단어 중간에 있는 글자를 기울임체로 표시할 때는 \_대신 \*을 사용한다.

```
*기울인 텍스트*
_기울인 텍스트_
```

_기울인 텍스트_  
_기울인 텍스트_

  <br>

## 굵고 기울인 텍스트(Bold and Italic)

텍스트를 굵고 기울게 표시한다. 단어 중간에 있는 글자를 굵고 기울게 표시할 때는 \_대신 \*을 사용한다.

```
***굵고 기울인 텍스트***
___굵고 기울인 텍스트___
```

**_굵고 기울인 텍스트_**  
**_굵고 기울인 텍스트_**

  <br>
  
## 인용문(Blockquotes)

인용문을 표시한다. 인용문 앞뒤에 빈 줄을 넣어야 한다.

```

> 인용문

```

> 인용문

  <br>

여러 문단이 있는 인용문은 문단 사이의 빈 줄에 >을 추가한다.

```

> 인용문1
>
> 인용문2

```

> 인용문1
>
> 인용문2

  <br>
  
인용문이 중첩될 경우 중첩하려는 문단 앞에 >>을 추가한다.
```

> 인용문1
>
> > 인용문2

```

> 인용문1
>
> > 인용문2

<br>

## 순서 있는 목록(Ordered Lists)

순서가 있는 목록을 표시한다.
```

1. 첫번째 항목
2. 두번째 항목
3. 세번째 항목

```
1. 첫번째 항목
2. 두번째 항목
3. 세번째 항목

  <br>

들여쓰기를 통해 목록 안에 다른 목록을 넣을 수 있다.
```

1. 첫번째 항목
2. 두번째 항목
   1. 두번째 항목 - 1
   2. 두번째 항목 - 2
3. 세번째 항목

```
1. 첫번째 항목
2. 두번째 항목
    1. 두번째 항목 - 1
    2. 두번째 항목 - 2
3. 세번째 항목

  <br>

## 순서 없는 목록(Unordered Lists)

순서가 없는 목록을 표시한다. 한 목록 내에서는 동일한 구분 기호를 사용해야 한다.
```

- 첫번째 항목
- 두번째 항목
- 세번째 항목

* 첫번째 항목
* 두번째 항목
* 세번째 항목

- 첫번째 항목
- 두번째 항목
- 세번째 항목

```
- 첫번째 항목
- 두번째 항목
- 세번째 항목

* 첫번째 항목
* 두번째 항목
* 세번째 항목

+ 첫번째 항목
+ 두번째 항목
+ 세번째 항목

  <br>

들여쓰기를 통해 목록 안에 다른 목록을 넣을 수 있다.
```

- 첫번째 항목
- 두번째 항목
  - 두번째 항목 - 1
  - 두번째 항목 - 2
- 세번째 항목

```
- 첫번째 항목
- 두번째 항목
  - 두번째 항목 - 1
  - 두번째 항목 - 2
- 세번째 항목

  <br>

## 코드(Code)

단어나 구문을 코드로 표시한다.
```

`단어`: 이 단어는 이런 뜻이다.

```
`단어`: 이 단어는 이런 뜻이다.

  <br>

## 코드 블록(Code Blocks)

코드 블록을 표시할 수 있다. 첫 번째 구분 기호 뒤에 언어를 지정하면 색상 강조 표시가 된다.
```

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

````

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
~~~json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
~~~

  <br>

## 링크(Links)

링크를 표시할 수 있다.
```
[Google](https://www.google.com/?hl=ko)로 이동합니다.
```
[Google](https://www.google.com/?hl=ko)로 이동합니다.

<br>

링크에 대한 제목은 URL 뒤에 ""로 묶어 표시한다. 사용자가 링크 위에 마우스를 올리면 제목이 툴팁으로 표시된다.
```
[Google](https://www.google.com/?hl=ko "검색 엔진 사이트")로 이동합니다.
```
[Google](https://www.google.com/?hl=ko "검색 엔진 사이트")로 이동합니다.

<br>

## 이미지

이미지를 표시한다. [] 안에는 대체 텍스트를 넣고, 제목을 표시하고 싶다면 이미지 경로 뒤에 "" 안에 넣는다.
```
![The San Juan Mountains 이미지](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg "San Juan Mountains")
```
![The San Juan Mountains 이미지](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg  "San Juan Mountains")

<br>

이미지에 링크를 넣고 싶다면 이미지의 마크다운을 []로 묶고 링크를 () 안에 추가한다.
```
[![The San Juan Mountains 이미지](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg "San Juan Mountains")](https://www.flickr.com)
```
[![The San Juan Mountains 이미지](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg "San Juan Mountains")](https://www.flickr.com)

````

<br>

## 참고 사이트

> https://www.markdownguide.org/basic-syntax/
