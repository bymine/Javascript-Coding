# Password Generator

이 프로젝트는 랜덤 비밀번호 생성기를 구현한 것입니다. 사용자는 패스워드의 길이와 옵션을 설정하여 패스워드를 생성할 수 있습니다.

- [참고 영상](https://www.youtube.com/watch?v=825u2Puaej0&t=708s)

## 화면

<img src="https://github.com/bymine/Javascript-Coding/assets/71866185/6f603e0f-587d-4fb9-ac2c-73c615d07aa1" width="800" height="500">

## 구조

비밀번호 생성기는 다음과 같은 기능을 제공합니다.

1. 비밀번호 길이 조절: 사용자는 슬라이더를 이용하여 원하는 길이로 비밀번호를 조절할 수 있습니다.

2. 문자 옵션 선택: 사용자는 대소문자, 숫자, 특수기호 등의 옵션을 체크박스로 선택할 수 있습니다.

3. 중복 허용 및 공백 포함 설정: 사용자는 중복 허용 여부와 공백 포함 여부를 체크박스로 설정할 수 있습니다.

4. 비밀번호 생성: 사용자가 설정한 조건에 따라 비밀번호를 생성합니다.

5. 비밀번호 복사: 생성된 비밀번호 문자열을 클립보드에 복사하여 사용자가 쉽게 붙여넣을 수 있도록 합니다.

## 학습

### innerText, innerHTML 차이

- `innerText`는 요소의 텍스트 내용만을 반환합니다.

- `innerHTML`은 HTML 태그와 텍스트를 반환합니다.

```html
<div class="example">
  <strong>This is a text</strong>
</div>
```

```javascript
const example = document.querySelector(".example");
console.log(example.innerHTML); //출력  <p>This is a text</p>
console.log(example.innerText); //출력  'This is a text'
```

<br/>

### css 가상요소 ::before, ::after

- CSS의 가상요소 `::before`와 `::after`는 HTML 요소의 내부의 시작 부분이나 끝 부분에 가상으로 콘텐츠를 추가하는 데 사용됩니다.

- `::before`는 선택한 요소의 시작 부분에 가상의 요소를 생성합니다.

- `::after`는 선택한 요소의 끝 부분에 가상의 요소를 생성합니다.

```html
<div class="example">
  <strong>This is a text</strong>
</div>
```

```css
.example {
  display: flex;
}

.example ::before {
  content: "Before content";
  color: blue;
}
.example::after {
  content: "After content";
  color: red;
}
```

##### 예시 화면

![가상요소예제](https://github.com/bymine/Javascript-Coding/assets/71866185/9b71d4ba-c52c-4458-96b8-46db9b4c3087)

<br/>

### clipboard 사용법

- 특정 요소를 클릭했을 때 클립보드에 복사하게 해주는 스크립트입니다.

```javascript
//복사히기
navigator.clipboard.writeText(passwordInput.value);
```
