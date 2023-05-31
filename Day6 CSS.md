# 05\.29 Day6 CSS

## 引用字型檔

* 用link或@import來引用外部字型連結（例如：Google Font）

```html
<style>
  @import url('https://fonts.googleapis.com/css2?family=Comic+Neue:wght@300&display=swap');
  #title {font-family: "Comic Neue", cursive;}
</style>
```

* 用@font-face來讓使用者端從伺服器下載字型檔，即便使用者的電腦中沒有也能呈現

  * font-face內可以定義字型名稱

```html
<style>
      @font-face {
        font-family: "Alex Brush";
        src: url("./alex-brush/AlexBrush-Regular.ttf");
      }
      #title {
        font-family: "Alex Brush";
      }
</style>
```

## Font Family

* font-family: “font name“, Arial , generic-family

  * font name如果中間有空白，需要用引號包起來

  * 當左側字型找不到時，就會使用電腦中的預設通用字型來使用

  * 一共有五種通用字型：

    1. **Serif**：有襯線字型

    2. **Sans-serif**：無襯線字型

    3. **Monospace**：等寬字型

    4. **Cursive**：仿手寫

    5. **Fantasy**：有裝飾、比較華麗的字型

```html
<style>
  @import url('https://fonts.googleapis.com/css2?family=Comic+Neue:wght@300&display=swap');
  #title {font-family: "Comic Neue", cursive;}
</style>
```

## Inherit 繼承

* 繼承概念：parent元素有的CSS樣式，有些會繼承給包含的child元素

  * 不是每個東西都會被繼承：如border

  * 通常文字相關的會被繼承

* inherit值：可以透過設定CSS屬性值為inherit來強制繼承parent元素的樣式

```html
<style>
      div {
        font-family: "Comic Sans MS";
        color: blue;
        border: 2px solid orange;
      }
      p {
        border: inherit;
        color: initial;
        font-family: Arial;
      }
</style>

<body>
    ABCDEFG
    <div>
      ABCDEFG
      <p>ABCDEFG</p>
    </div>
</body>
```

* initial：可以透過設定CSS屬性值為initial來重設顏色

* 繼承過的屬性也可以再重新指定

# 在CSS中使用變數

## 宣告變數與取用變數

* \--parameter:value：用兩個減號宣告變數

* var(--parameter)：取用儲存好的變數

  * **如果取用的變數沒有inherit到，會無法成功（變數的宣告位置只能在其元素和包含的子元素中使用）**

  * 所以通常宣告變數會在html元素或root元素中宣告，彈性比較大

```html
<style>
      /*成功範例*/
      html {
        --apple: green;
      }
      h5 {
        color: var(--apple);
      }
       /*失敗範例（沒有繼承到變數）*/
      h4 {
        --cat: orange;
      }
      h6 {
        color: var(--cat);
      }
</style>

<body>
    <h4>h4 測試顏色設定</h4>
    <h5>h5 測試顏色設定</h5>
    <h6>h6 測試顏色設定</h6>
</body>
```

---

## calc()計算

* 用calc()可以實現基本的運算，且可以**不需要相同單位**

* \+或-的運算兩邊需要用空白符號，\*跟/不用，但是為了統一及美觀，建議也都加上兩邊的空白符號

```html
<head>
   <style>
      div {
        height: 100px;
        background-color: lightcoral;
      }

      .demo1 {
        width: 500px;
      }

      .demo2 {
        width: calc(100px + 400px);
      }

      .demo3 {
        width: calc(100% * 0.85);
      }
    </style>
  </head>

  <body>
    <h3>calc function 接受一個四則運算式，並回傳運算後的結果</h3>
    <hr />
    <div class="demo1"></div>
    <hr />
    <div class="demo2"></div>
    <hr />
    <div class="demo3"></div>
  </body>
```

---

## border 邊線

### border: width || style || color

* 是三個屬性的簡寫，彼此順序調換一樣可以運行

```css
.normalBorder{
            border-width: 5px;
            border-color: blue;
            border-style: solid;
}
```

* border-width：設定四個邊的寬度

  * 如果是寫成1-4個值

    * 一個值：全部

      兩個值：上下 左右

      三個值：上 左右 下

      四個值：上 右 下 左 （順時針方向）

* border-style：設定四個邊的樣式

  * 如果是寫成1-4個值

    * 一個值：全部

      兩個值：上下 左右

      三個值：上 左右 下

      四個值：上 右 下 左 （順時針方向）

  * 常用樣式：

    * solid：實線

    * dashed：虛線

    * dotted：虛點線

    * double：類似框框的線

* border-radius：可以填入長度或百分比

  * 可以指定要左上左下右上右下哪個角

  * 如果是寫成1-4個值

    * 一個值：全部

       兩個值：左上+右下 右上+左下（對角線）

       三個值：左上 右上+左下 右下

       四個值：左上 右上 右下 左下（順時針方向）

---

## background

### background: image || position || repeat || attachment

* **順序不可以更改！**

```html
    <style>
      body {
        /* background-image: url("./img/logo.png");
        background-repeat: no-repeat;
        background-attachment: fixed;
        background-position: right top; */
        background: url("img/logo.png") right top no-repeat fixed;
      }
    </style>
```

* background-image：背景圖片
  *  linear-gradient 線性漸層

        * linear-gradient(角度,第一個顏色,第二個顏色,第三個顏色…)

        * 角度：可以寫to bottom right、.25turn、90deg都可以

* background-repeat：背景重複設定

  * repeat：預設重複填滿整個container

  * no-repeat：不重複

  * repeat-x：x軸上重複

  * repeat-y：y軸上重複

* background-attachment：背景如何固定

  * scroll：背景隨著滾輪滾動而變動

  * fixed：固定背景即使滾輪往下滑也會一直出現（預設在左上角）

* background-position：背景位置

  * left、right、top、bottom：固定在上下左右（左上左下右上右下）

* background-clip：定義背景圖片的渲染範圍

  * border-box：預設值，跟邊緣一樣

  * padding-box：從內容開始一路到padding的範圍

  * content-box：內容範圍

  * text：文字變成背景遮色片，文字就會出現背景的顏色或圖片（需要前面加前綴詞使用）

---

## clip-path

* 可以產生各種多邊形或圓形

* clip-path: polygon(A頂點x位置 A頂點y位置,B頂點x位置 B頂點y位置,C頂點x位置 C頂點y位置)

  * 可以一直設定頂點下去產生不同多邊形

  * 位置是用百分比，0的話就是0%的顏色

  * 如果想要多邊形要順時針或逆時針擇一順序寫頂點

* clip-path: circle(圓的半徑, 圓心x位置 圓形y位置)

  * 半徑跟圓心位置一樣是用百分比

```css
clip-path: polygon(50% 43%, 0 100%, 90% 68%);
clip-path: polygon(20% 0%, 0% 20%, 30% 50%, 0% 80%, 20% 100%, 50% 70%, 80% 100%, 100% 80%, 70% 50%, 100% 20%, 80% 0%, 50% 30%);
clip-path: circle(50% at 50% 50%);
```

---

## object-fit

* content如何填滿content box

* object-fit：

  * fill：預設填滿

  * cover：會依短邊等比例放大，放不下的會直接捨棄

  * contain：等比例保留整張圖片完整呈現在content box中，可能會變很小

  * none：不調整尺寸，放進去content box，放不下的直接捨棄

  * scale-down：會選擇none或contain其中一個比較小的大小去塞content box

---

## padding

* padding：設定四個邊的內邊距

  * 如果是寫成1-4個值

    * 一個值：全部

      兩個值：上下 左右

      三個值：上 左右 下

      四個值：上 右 下 左 （順時針方向）

---

## margin

* margin：設定四個邊跟其他物件的距離（外邊距）

  * 如果是寫成1-4個值

    * 一個值：全部

      兩個值：上下 左右

      三個值：上 左右 下

      四個值：上 右 下 左 （順時針方向）

  * auto：

    * 水平方向的auto，計算的距離取決於可用空間（剩餘空間）

      * margin:auto; 

### margin collapse

* 如果一個間距的左右兩邊設定的距離不一樣，如A的margin-left:50px 右邊B的margin-right:80px，兩者的距離會是130px

* 但如果兩個物件是垂直排列，會造成margin collapse，此時兩邊設定不一樣的間距會以最大的邊距爲主，如A的margin-bottom:50px 下面B的margin-top:80px，兩者的距離就會是80px


## 要設定範圍邊距時，要先將範圍設定出來！

* 用border或background-color先框出來範圍才會知道要怎麼設定比較好

## 強烈建議要實作之前先用註解把自己的思路與步驟打下來！

