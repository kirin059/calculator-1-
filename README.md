# calculator 만들기(1) 
## css
---

1️⃣ grid-template-columns: repeat(4, 100px) && grid-template-rows: repeat(5, 100px);

계산기 버튼 grid 레이아웃 구현 >> `grid` 사용
```css
  .calculatorBtn {
    display: grid;
    grid-template-columns: repeat(4, 100px);    /* 세로로 100px 너비를 4번 반복한다 */
    grid-template-rows: repeat(5, 100px);
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
  // 클래스 spanTwo를 적용한 뒤 css로 `span 2`를 적용한다
```



3️⃣ `수식 input`(.previous)과 `결과값 input`(.current)을 다르게 적용하기

수식이 입력되는 칸을 column으로 2등분 한 뒤, 아래 input은 수식을 적용 

➡ `=` 버튼을 누르면 아래 input에는 연산 값이 남고, 수식은 위 input으로 올라간다

```css
.previous {
    font-size: 22px;
    text-align: right;     /* 입력은 오른쪽부터 */
}

.current {
    font-size: 33px;
    text-align: right;
    white-space: normal;   /* 자동줄바꿈 처리 속성 */
}
```
