# 06\.06 Day 12 Bootstrap

### image

- .img-fluid：將圖片設定會`max-width: 100%;` and `height: auto;`

- .img-thumbnail：將圖片設定會`max-width: 100%;` and `height: auto;`，將圖片加上圓角邊框

- .rounded：將圖片設為圓角

### picture

```html
     <picture>
        <source
          media="(min-width: 1200px)"
          srcset="
            https://dummyimage.com/1200x300/f7cff7/544954&text=Whatever+I+like,+if+it's+wrong+or+right,+it's+alright
          "
        />
        <source
          media="(min-width: 800px)"
          srcset="
            https://dummyimage.com/800x600/f7cff7/544954&text=Whatever+I+choose,+and+I'll+sing+the+blues+if+I+want
          "
        />
        <img
          src="https://dummyimage.com/600x400/f7cff7/544954&text=I'm+free+to+be+whatever+I"
          alt=""
        />
      </picture>
```

- 在picture元素下，用source的media屬性去設定條件，srcset設定要出現的圖片

- **圖片的順序會有影響！瀏覽器會先挑第一個符合設定的！**

### figure

- .figure .figure-img .figure-caption：微小調整圖片跟圖片說明設定

### table

- 在最外層的table元素中，一定要有.table的

- 屬性scope：標示範圍是col還是row

- .table-striped、.table-striped-columns：奇偶列（或行）不同顏色

- .table-hover：滑鼠放上去的時候該列會呈現不同顏色

### color

- Bootstrap有自定義一些常見的標籤代表常用顏色，有黑底的是Bootstrap為了方便辨識顏色而加

- primary：

- secondary

- success

- danger

- warning

- info

- light

- dark

- muted

- white

- 在文字或背景上就可以加上text-或bg-來改變顏色

### text

- text-{start｜center｜end}：靠左、中、右對齊，注意如果是inline element就會沒效

   - 中間也可以加斷點

- .text-truncate：當文字溢出時，呈現…的符號，直接將05.29 Day6 CSS中一定要搭配的CSS語法先定義好

- .text-{lowercase｜uppercase｜capitalize}：文字的小寫、大寫、首字大寫

- .fs-{數字}：font size

   - 數字有1到6

- .fw-{粗細}：font-weight

- .fst-{normal｜italic}：font-style，有兩種調整

### width、height

- {w｜h}-{百分比｜auto}：寬高的大小，數值不用加%，直接是百分比單位

   - 數值預設只有25、50、75、100、auto

### margin、padding

- {m｜p}{t｜b｜s｜e｜x｜y｜空白}-{breakpoint}-{size}

   - t：top

   - b：bottom

   - s：start

   - e：end

   - x：左右

   - y：上下

   - 空白：上下左右

   - size：0-5和auto

      - 0：距離為0

      - 1：$spacer \* 0.25

      - 2：$spacer \* 0.5

      - 3：$spacer \* 1

      - 4：$spacer \* 1.5

      - 5：$spacer \* 3

      - **auto：只有margin才能使用auto，自動調整外邊距**

      - **$spacer：就是1 rem，預設是16px**

### margin-collapse

- margin 在垂直方向會在某些情況下出現bug

   - 當你的外層是block，內層也是block的時候，你對有直接接觸的子元素新增margin，就有可能造成產生崩塌。

   - 解法：

      - 外層容器加入 padding

      - 外層容器加入 border

      - 內層或外層容器改變為 display: inline-block（）

   > It turns out that many of us have **a misconception about how margins work.**
   >
   > Margin is meant to increase the distance between siblings. It is *not* meant to increase the gap between a child and its parent's bounding box; that's what padding is for.
   >
   > Margin will always try and increase distance between siblings, **even if it means *transferring* margin to the parent element!** In this case, the effect is the same as if we had applied the margin to the parent `<div>`, not the child `<p>`.
   >
   > “But that can't be!”, I can hear you saying. “I've used margin before to increase the distance between the parent and the first child!”
   >
   > Margins only collapse when they're *touching*. If there's any sort of gap or barrier between margins, they won't collapse.

- 參考網站：<https://www.joshwcomeau.com/css/rules-of-margin-collapse/>

### border

- .border-{top｜bottom｜start｜end}：預設邊線

- .border-{數字}：0-5

### flex

- .d-flex：將子元素轉變為flex屬性，但parent element為block

- .d-inline-flex：將子元素轉變為flex，但parent element為inline block

   - .flex-wrap：溢出的元素排列會換行

   - .flex-nowrap：溢出的元素排列不會換行


- .flex-grow-{0｜1}：參與.d-flex底下的空間分配

   - .flex-grow-0：不會參與空間分配，原本的東西有多寬就多寬

   - .flex-grow-1：會平均分配空間

   - 只有0跟1兩個數字，如果設定2以上會等於沒有設定

- .order-{數字}：數字代表排列的先後順序，預設數字最到5，1最先排列

- .flex-row、.flex-row-reverse：設定橫列排列的方向

- .flex-column、.flex-column-reverse：設定直列排列的方向

### justify-content

- 按照主軸的方向對齊，預設是row（左到右），有以下屬性（parent element 需要有.d-flex）

   - .justify-content-start

   - .justify-content-end

   - .justify-content-center

   - .justify-content-between

   - .justify-content-around

   - .justify-content-evenly

### align-items

- 按照交錯軸的方向對齊，預設是row的交錯軸（上到下，要垂直高度夠才表現得出來），有以下屬性（parent element 需要有.d-flex）

   - .align-items-start

   - .align-items-end

   - .align-items-center

   - .align-items-baseline

   - .align-items-stretch

### align-self

- 調整特定子元素的對齊方式，按照交錯軸的方向對齊，預設是row的交錯軸（上到下，要垂直高度夠才表現得出來），有以下屬性（parent element 需要有.d-flex）

   - .align-self-start

   - .align-self-end

   - .align-self-center

   - .align-self-baseline

   - .align-self-stretch

### align-content

- 按照交錯軸有多行時的方向對齊，預設是row的交錯軸（上到下，多行指的就是多列，要垂直高度夠才表現得出來），有以下屬性（parent element 需要有.d-flex）

   - .align-content-start

   - .align-content-end

   - .align-content-center

   - .align-content-between：第一項元素跟最後一項元素與container的邊緣齊平

   - .align-content-around：第一個元素前跟最後一個元素後的空白是每個元素之間相等空白的一半。

   - .align-content-stretch

### align-items vs. align-content vs. align-self

- 兩者都是以交錯軸為對齊方向，align-items是交錯軸的單行對齊，align-content是交錯軸有多行時的多行對齊（spacing between lines，多行中的單行不歸align-content管，當元素排列只有單一行時align-content也沒有效果）

- align-self調整單一子元素，跟另外兩者差異比較大

- 參考：

   - <https://stackoverflow.com/questions/27539262/whats-the-difference-between-align-content-and-align-items>

      <https://blog.csdn.net/sinat_27088253/article/details/51532992>


