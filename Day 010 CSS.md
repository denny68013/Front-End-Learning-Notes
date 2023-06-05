# 06\.02 Day 10 CSS

## 單位

### 絕對單位

- 實際大小，在螢幕上的固定大小。

- px：point 最常用

- pt：pixel 印表機常用

### 相對單位

- 依照parent元素的設定而有變化，

- em與rem的預設字型大小（html元素的font-size）是16px。假設三個設定如下，中大小一樣。

   ```css
       <p style="font-size: 16px">apple-1</p>
       <p style="font-size: 1em">apple-2</p>
       <p style="font-size: 1rem">apple-3</p>
   ```

- rem：**根元素(root element)**當基準的倍數大小

   - 3rem就是根元素設定的三倍大

- em：依照**parent element**當基準的倍數

- %：相對於parent element的比例

   - 注意height要先設定parent element的高度才會生效

- vh：viewport height，以**視窗的高度**去決定大小（省略%符號）

   - 80vh就是視窗的80%高度

- vw：viewport width，以**視窗的寬度**去決定大小（省略%符號）

   - 80vw就是視窗的80%寬度

## RWD Responsive Web Design 響應式網頁設計

- 根據裝置的大小去調整網站的視覺架構，如果網站要使用響應式，則meta的資訊一定要寫

- width=device-width：頁面寬度等同裝置寬度

- initial-scale=1.0：畫面初始比例為100%，不放大不縮小

```html
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

### @media

- @media 媒體類型 and (條件) {要調整的樣式}：在條件滿足的時候，改變樣式

```css
@media screen and (max-width: 600px) 
{
  span {
    font-size: 72px;
        }
}
```

- 媒體類型：

   - all (default)

   - print

   - screen

   - speech

- 常用條件：

- 可以使用and或or（用,逗號就是or）或not來滿足特定或多重條件

   - width：寬度

      - max-width：在設定寬度以下的時候

      - min-width：在設定寬度以上的時候

      - 如果是從寬度小寫到大，因為後蓋前的因素，所以可以定義三個寬度條件就好（中間那個條件可以少寫一個）

      ```css
      @media screen and (max-width: 700px) {}
      @media screen and (min-width: 700px) {}
      @media screen and (min-width: 1000px) {}
      /*第二列可以不用再多寫一個 and (max-width:1000px) */
      ```

      - 寬度在設定的時候可以先把斷點想好再下去寫樣式。

   - orientation：瀏覽方向

      - portrait：直式

      - landscape：橫放

   - aspect-ratio：顯示區域的長寬比例

   - device-aspect-ration：裝置的長寬比例

### Transition

- transition: property || duration || timing-function || delay：如果沒有設定秒數，預設是0

   - transition-duration：需要轉場的屬性（多種屬性的話用逗號隔開）

   - transition-property：要轉場的項目

   - transition-timing-function：轉場變化曲線

      - 可以使用[https://cubic-bezier.com/](https://cubic-bezier.com/#.17,.67,.83,.67) 調整

### Transform

- 調整元素變化

   - translate(X,Y)：改變X、Y位置

   - scale(長,寬)：放大縮小長或寬比例

   - rotate(角度)：正數是順時針、負數是逆時針，角度的數值後要加deg

   - skew(X方向角度、Y方向角度)：傾斜角度

   - matrix(六個數值)：可以一次調整上述屬性，只是是由矩陣方式計算

### animation

- @keyframes 動畫名：定義動畫

   - 可以使用from to或百分比來代表動畫的進度

```css
      @keyframes example {
        from {
          background-color: blue;
        }
        to {
          background-color: yellow;
        }
      }

      @keyframes apple {
        0% {
          background-color: red;
        }
        25% {
          background-color: blue;
        }
        50% {
          background-color: yellow;
        }
        75% {
          background-color: green;
        }
        100% {
          background-color: red;
        }
```

- animation-name：套用動畫名稱

- animation-duration：動畫時間

- animation-iteration-count：動畫重複次數

   - infinite：無限循環
