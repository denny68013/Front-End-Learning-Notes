# 05.30 Day7 CSS

## box model

* 在設定width和height的時候，是設定哪個範圍？

  * content ? padding ? border ?

  * **預設寬高其實只有包含到content，所以加上border或padding後都會比原本設定的範圍更大**

  * **所以理想設定是加了border和padding後，版面會跟訂好的版面一樣大或在之內，所以可以透過box-sizing去調整**

* box-sizing：設定box model的範圍

  * content-box：預設，寬高設定在content範圍

  * border-box：寬高設定包含border範圍

    ![image 4.png](./05.29%20Day6%20CSS-assets/image%204.png)

---

## box-shadow

* 產生物件的陰影

* box-shadow:offset-x（x軸偏移） | offset-y（y軸偏移） | blur-radius（模糊程度） | spread-radius （發散程度）| color（顏色）

## text-shadow

* 產生文字陰影

* text-shadow:offset-x（x軸偏移） | offset-y（y軸偏移） | blur-radius（模糊程度） | color（顏色）

---

## overflow

* 在一個固定的大小（有設定寬高）的地方才會發生溢出的狀況

* 中文字會自動換行，但英文和數字不會，會往右邊溢出

* 當content超出parent element box的時候要如何顯示

  * visible：直接溢出可見

  * hidden：超出的範圍藏起來

  * clip：超出的範圍直接裁掉，禁止任何形式的捲動（相比hidden可捲動），可以單獨設定在x軸或y軸（但hidden不行）

  * scroll：產生可以水平跟垂直方向的卷軸，有溢出的部分會變成可捲動

  * auto：看哪個方向溢出產生該方向可捲動的卷軸

## text-overflow

* 決定文字溢出時的呈現

  * clip：預設值，會把多出去的裁掉

  * ellipsis：會產生「…」符號取代溢出的文字

    * 但這要配合以下兩個CSS語法使用，才會呈現！

    ```css
    overflow: hidden;
    white-space: nowrap;
    ```

## white-space

* 決定空白字元怎麼處理

  * normal：連續的空白被合併、換行會被視為空白字元，換行只在文字會溢出時發生。

  * nowrap：跟normal一樣處理空白字元，但是不強制換行

## overflow-wrap（word-wrap）、word-break

* 決定文字如何換行

  * overflow-wrap：前身的名字也就是word-wrap，告訴瀏覽器如果斷行後的結果還是會溢出container，那要怎麼處理

    * normal：預設值

    * break-word：只有**當一個單詞換行後，還是超出container的時候才會強制斷詞換行**，但其他詞不會（比較符合一般情境）

  * word-break：決定如何斷「一個詞」，非CJK文本會遇到

    * normal：預設值

    * break-all：非CJK文本會把**所有**碰到container邊界的詞拆開換行顯示

    * keep-all：以詞斷行，會保留超出container的文字不會換行

* 具體差別參考：<https://juejin.cn/post/6844903667863126030>

* CJK文本：單詞有意義的文本，像中文（Chinese）、日文（Japanese）、韓文（Korean）

---

## Vendor Prefix 供應商前綴詞

* 不同瀏覽器前面會有需要加上的前綴詞，讓想使用的CSS比較新的樣式在使用者的瀏覽器上支援

* 不同瀏覽器的前綴詞以下解說摘自MDN

  * `-webkit-` (Chrome, Safari, newer versions of Opera and Edge, almost all iOS browsers including Firefox for iOS; basically, any WebKit or Chromium-based browser)

  * `-moz-` (Firefox)

  * `-o-` (old pre-WebKit versions of Opera)

  * `-ms-` (Internet Explorer and Microsoft Edge, before Chromium)

* 不確定該功能是否支援的話可以 <https://caniuse.com/> 網頁查詢

## \-webkit-line-clamp

* 可以限制container中的內容呈現指定的行數

---

## opacity

* 控制物件的透明度，用0（完全透明）到1（不透明）去調整

---

## color

* 顏色表示法

  * 語義：lightcoral

  * rgb(red,green,blue)：rgb(240, 128, 128)（省略的透明度默認為1，不透明）

  * rgba(red,green,blue,alpha)：rgba(240, 128, 128,1)

  * hsl(hue,saturation,lightness)：hsl(0, 79%, 72%)

    * hue沒有單位、saturation和lightness都有單位

  * 十六進制表現法#RGB：\#f08080 （省略的透明度默認為ff，不透明）

  * 十六進制表現法#RGB\[A\]：\#f08080\[ff\]

---

## filter

* 讓元素增添視覺效果

* 各種屬性的單位都不太一樣，要注意！

* blur(px)：

* brightness(%)：

---

## text-transform

* 文字改變

  * capitalize：首字大寫

  * uppercase：全部變大寫

  * lowercase：全部變小寫

## text-decoration

* 文字裝飾，包含以下幾項

  * text-decoration-line：線的位置

  * text-decoration-color：線的顏色

  * text-decoration-style：線的樣式（虛線、波浪線等等）

  * text-decoration-thickness：線的厚度

## text-align

* 調整文字排版：

  * justify：左右對齊（齊行）

  * left：靠左對齊

  * right：靠右對齊

* 如果使用在inline element的話要調整display的形式才可以使用

## text-indent

* 調整文字的縮排與凸排

  * 正數代表縮排、負數代表凸排

* 與padding不同，縮排凸排只有套用在第一排，padding整個內容都會縮。

## letter-spacing

* 調整字母之間的距離

## word-spacing

* 調整單詞之間的距離

  * 偵測的是空白前後，所以CJK字體中單字之間不會被拆開，除非中間有空白

---

## line-height

* 調整文字行高

  * 跟調整內邊距的padding不同，調整padding時文字中間的行距不會改變

## cursor 滑鼠樣式

## 單位

### 相對單位

* rem：根元素(root element)當基準的倍數大小

  * 3rem就是根元素設定的三倍大

* em：依照parent element當基準的倍數
