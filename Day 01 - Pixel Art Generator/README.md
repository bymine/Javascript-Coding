# Pixel Art Generator

이 프로젝트는 픽셀 아트 생성기를 구현한 것으로, 사용자가 원하는 크기의 픽셀 아트를 만들고 다양한 색상을 이용해 그림을 그릴 수 있는 기능을 제공합니다. 사용자는 넓이와 높이를 조절하여 원하는 크기의 캔버스를 생성할 수 있으며, 그리기, 초기화, 지우기, 색상 선택 등의 기능을 활용하여 창작 활동을 즐길 수 있습니다.

- [참고 영상](https://www.youtube.com/watch?v=DfDPJqD3FjI&list=PLkC56g8fboI0HghByzVuD2Vz8ROUXfF_j)

## 시연 영상

<img src="https://github.com/bymine/Javascript-Coding/assets/71866185/7efcf7b9-e1e3-4fb8-ad57-7e1ae8c03464" width="300" height="300">

## 구조

이 프로젝트는 다음 두 가지 영역으로 구성됩니다.

### 옵션 선택 영역

사용자가 픽셀 아트의 크기를 조절하고 그리기 도구를 선택하는 공간입니다. 이 영역에는 다음과 같은 요소가 포함됩니다:

- 넓이와 높이를 조절하는 입력창
- 만들기, 초기화, 지우기, 그리기 버튼
- 그림을 그릴 때 사용할 색상 선택 영역

### 픽셀 영역

사용자가 선택한 크기의 캔버스가 표시되는 공간입니다. 사용자는 다음과 같은 기능을 활용할 수 있습니다:

- 그리기 도구를 이용하여 원하는 색상으로 그림을 그리거나 지울 수 있음
- 드래그 움직임을 통해 그리고 지우는 기능
- 클릭을 통해 그리고 지우는 기능

## 학습

### javascrpt

Pixel을 그리는 방법

- gridButton에 클릭시 발생하는 이벤트리스너 등록
- 높이만큼 `<div class="gridRow"></div>` 생성 및 `<div class="container"></div>`의 자식요소로 등록
- 넓이만큼 `<div class="gridCol"></div>` 생성 및 `<div class="gridRow"></div>`의 자식 요소로 등록

```javascript
let container = document.querySelector(".container");
let gridButton = document.getElementById("submit-grid");
let gridWidth = document.getElementById("width-range");
let gridHeight = document.getElementById("height-range");

gridButton.addEventListener("click", () => {
  container.innerHTML = "";

  for (let i = 0; i < gridHeight.value; i++) {
    let div = document.createElement("div");
    div.classList.add("gridRow");

    for (let j = 0; j < gridWidth.value; j++) {
      let col = document.createElement("div");
      col.classList.add("gridCol");

      div.appendChild(col);
    }

    container.appendChild(div);
  }
});
```

```css
.gridCol {
  height: 1em;
  width: 1em;
  border: 1px solid #ddd;
}

.gridRow {
  display: flex;
}
```

![픽셀 그리는 법](https://github.com/bymine/Javascript-Coding/assets/71866185/0e4bce9d-15d3-4da6-9e37-97c3b21dc249)

### css

자바스크립트 터치 이벤트, 마우스 이벤트 정리  
[정리 내용 바로가기](https://developer-bymine.tistory.com/20)

요소를 화면 가운데 정렬하는 방법

1. top, left, translate를 이용한 가운데 정렬

```css
body {
  background-color: #43a047;
}

.wrapper {
  background-color: #fff;
  width: 80vmin;
  position: absolute;
  transform: translate(-50%, -50%);
  top: 50%;
  left: 50%;
  padding: 40px 20px;
  border-radius: 8px;
}
```

2. flex를 이용한 가운데 정렬

```css
body {
  background-color: #43a047;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.wrapper {
  background-color: #fff;
  width: 80vmin;
  padding: 40px 20px;
  border-radius: 8px;
}
```

3. maring auto를 이용한 가운데 정렬

```css
body {
  background-color: #43a047;
}

.wrapper {
  background-color: #fff;
  width: 80vmin;
  height: 80vmin;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  margin: auto;
  padding: 40px 20px;
  border-radius: 8px;
}
```
