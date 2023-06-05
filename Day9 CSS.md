# 06\.01 Day 9 CSS

# Display

- div的display區塊預設值為block

- **display:block** 區塊，元素的寬度預設會撐到最大。

- **display:inline-block：**在一列裡面的區塊。

   - div 的 display:inline-block 會有預設空格在元素之間，建議使用flexbox去調整

      - 也可以在parent元素中用style="font-size: 0px;或letter-spacing: 0px;或word-spacing: 0px;或直接調整元素的margin

- **display:inline**：變成inline元素，無法設定寬高。

   - 使用inline寬高的設定會失效，因為把block element變成inline element，而inline element 的寬高是由元素中的內容決定

- **display:flex：**必須要在parent元素上使用，套用到child元素，元素之間會沒有空格

- **display:grid：**在parent元素上使用，搭配grid的其他屬性

- **display:none**：讓元素消失在畫面呈現上，像是沒有存在過

## flex

- **parent元素必須要有display:flex，不然會沒有效果**

- flex:number：設定flex屬性後，會依照等分的概念下去分配各元素在列中的大小

   - 以圖為例：紅色是6等分中的3等分、綠色是2等分、藍色是1等分

## grid

- **parent元素必須要有display:grid，不然會沒有效果**

- grid-template-columns：設定grid的行寬（如果只有這個屬性，會自動幫你分配好行數）

- grid-template-row：設定grid的列高（如果只有這個屬性，會按照順序往下設定，不會自動分配列數）

```css
  display: grid;
    grid-template-columns: auto auto auto;
    grid-template-rows: 100px 200px 300px;
```

- grid-template-areas：用代號或名稱去配置不同元素的位置

-  grid-area：用代號或名稱定義區塊或元素，配合grid-template-areas使用

```css
.grid-container {
            display: grid;
            grid-template-areas:
                'header header header header header header'
                'menu main main main right right'
                'menu footer footer footer footer footer';
            gap: 10px;
            background-color: #2196F3;
            padding: 10px;
        }
        .item1 {
            grid-area: header;
        }

        .item2 {
            grid-area: menu;
        }

        .item3 {
            grid-area: main;
        }

        .item4 {
            grid-area: right;
        }

        .item5 {
            grid-area: footer;
        }
```

## **visibility**

- **visibility:visible**：預設呈現

- **visibility:hidden：**讓元素隱藏在畫面呈現上，但是一樣會佔用原本的空間，只是元素不見，如果不想影響版面就可以使用這個

- **已經消失的元素是無法透過hover互動的**：如果一個元素display:none或visibility:hidden，hover過去想要讓他呈現出來（display:block或visibility:visible），以下選擇會沒有效果，我們無法經過消失的元素

```
  #reddiv_B {
    display: none;
  }

  #reddiv_C {
    visibility: hidden;
  }
 
  #reddiv_B:hover {
    display: block;
  }
  #reddiv_C:hover {
    visibility: visible;
  }
```

## Position

- **position:static**：預設值，加上 top、bottom、left、right 屬性不會造成任何影響

- **position:fixed**：固定在畫面的某處，沒有設定 top、bottom、left、right時，預設的位置為 扣除【parent容器】元素內容，

   -  top、bottom、left、right為**元素跟上下左右方的距離（不是往上下左右移），而且必須要跟position一起使用，position的值不能是static**

- **position:relative**：相對位置，相對原本的位置。如果沒有設定 top、bottom、left、right；表現會和 static 一樣。

   - top、bottom、left、right一樣是跟元素的距離，但是relative的話是**相對於原本的位置，而且不會影響到後面的元素**

- **position:absolute**：會依據上一層元素的position設定值去計算，**若為static則會被忽略**；若沒有（找不到非static的parent元素），則會對應到body元素，以**視窗位置**當起始點

   - top、bottom、left、right一樣是跟元素的距離，但是沒找到非static的parent元素就會對應到body元素，以視窗為起始點
   
- background也有background-position可以調整 05.29 Day6 CSS

## z-index

- z-index：預設為0，用來調整元素前後的z軸深度

## float、clear

- float 浮動，可以讓元素往特定方向飄，會影響到後面的元素

   - 如圖，float:left會一個一個從順序開始往右飄，所以直的1234會變成橫的4321。

- float如果讓div裡面的元素飄走，則div本身就不會再有內容，有可能設定好的如background-color之類就不會呈現、而且也會影響到後面的元素。為了避免跑版，有三種方法：

   - **clear：清楚float屬性**

      - left、right、both：清楚左邊、右邊或左右兩邊的float屬性（看float的屬性）

      - 屬性值還有：inherit（IE不支援）、none

      - backgorund-color如果有套用的話在這個例子

   - **overflow:hidden：會因為這個屬性建立一個BFC**（Block Formatting Context，確保裡面的元素不會被外面影響的空間），BFC建立的高度會把浮動元素下去算，所以如果parent元素沒有設定高度的話，就會建立一個空間。

   - **::after+clear+display：在parent元素中透過新增虛擬的空白元素，創造一個空間解除跑版。**

   ```css
   .clearfix:after {
     content: “”;
     display: block;
     clear: both;
   }
   /* display的屬性值也可以換成table，
   更穩定，如果你有需要包含top-margin的child元素 */
   ```

   - **display: flow-root**：如果child元素有float性質不要影響到parent元素以外的空間

   - 參考：<https://medium.com/ui-ux%E7%B7%B4%E5%8A%9F%E5%9D%8A/%E8%A7%A3%E9%99%A4-float-%E5%B1%AC%E6%80%A7%E7%9A%84%E6%96%B9%E6%B3%95-5e29cc30777d>
