# calculator 만들기(1) 
## css
---

1️⃣ grid-template-columns: repeat(4, 100px) && grid-template-rows: repeat(5, 100px);

계산기 버튼 grid 레이아웃 구현 >> `grid` 사용
```css
  .calculatorBtn {
    display: grid;
    grid-template-columns: repeat(4, 100px);    /* 세로로 100px 너비를 4번 반복한다 */
    grid-template-rows: repeat(5, 100px);       /* 가로로 100px 너비를 5번 반복한다 */
    justify-content: center;
    align-items: center;
}
```



2️⃣ grid-column: span 2;

계산기 버튼 2칸을 1칸으로 합치기

```css
  .spanTwo {
    grid-column: span 2;
}
  // 2칸으로 합치고 싶은 html태그에 클래스 spanTwo를 적용한 뒤 css로 `span 2`를 적용한다
```



3️⃣ `수식 input`(.previous)과 `결과값 input`(.current)을 다르게 적용하기

수식이 입력되는 칸을 column으로 2등분 한 뒤, 아래 input은 수식을 적용 

➡ `=` 버튼을 누르면 `.current`(아래 input)에는 연산 값이 남고, 수식은 `.previous`(위 input)로 올라간다

```css
.previous {
    font-size: 22px;
    text-align: right;     /* 입력되는 값은 오른쪽부터 화면에 출력되도록 */
}

.current {
    font-size: 33px;
    text-align: right;
    white-space: normal;   /* 자동줄바꿈 처리 속성 */
}
```

```js
// 계산(=) 기능
function resultCalculation() {
    const calBtn = document.querySelector(".result");   // '=' 버튼

    calBtn.addEventListener("click", (e) => {
        // console.log(e.target.value);
        previous.value = current.value;                         // current값은 previous값으로 대입하고
        current.value = eval(current.value).toLocaleString();   // current값은 연산된 값(eval)
    });
}
resultCalculation();
```
