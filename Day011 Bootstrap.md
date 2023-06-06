# 06\.05 Day 11 Bootstrap

## Bootstrap 介紹

- 功用：穩定、快速打造RWD網站

- 上課版本使用5.2.x，一定要確認版本，不同版本的寫法有可能不一樣

- 官網有詳列不同bootstrap css檔的差異，可以只取所需要功能的css檔就好

   JS檔也是

### 使用Bootstrap

- 一定要有<meta name="viewport">這行，使用link跟script去取用網路上或電腦上的css和js檔。

   ```html
   <!doctype html>
   <html lang="en">
     <head>
       <meta charset="utf-8">
       <meta name="viewport" content="width=device-width, initial-scale=1">
       <title>Bootstrap demo</title>
       <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
     </head>
     <body>
       <h1>Hello, world!</h1>
       <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4" crossorigin="anonymous"></script>
     </body>
   </html>
   ```

- 在引用Bootstrap檔案時要注意順序，如果出錯可以先查閱官方文件

   - Bootstrap link的CSS檔順序很重要，先設定樣式再link css的話可能會失效

- 是否使用Bootstrap最好一開始就決定，不然到一半才使用，原本的版面很可能會跑掉。

- 每個版本的優先權重設定不同，可以用!important試錯看看是不是優先權問題，如果是的話要嘗試使用例如類別選擇器或以上優先權重較重的，才能夠順利更改樣式。

- 在v5.中很少看到left或right，會用start取代左邊，end取代右邊

### Icon

- [https://icons.getbootstrap.com/](https://icons.getbootstrap.com/#install)

- 可以透過Icon font的方式（可套用自己的字型）或svg（圖片）

### breaking points

- bootstrap有預設類別對應到的斷點，大部分用到幾個類別詞會對應島這些斷點，如md對應到大於等於768px



### containers

- `.container` ：有設定max-width，當螢幕畫面達到設定的breakpoint的時候

- `.container-{breakpoint}`：一般狀況是`width: 100%` ，只有當螢幕畫面達到特定設定的breakpoint的時候才會設定max-width

- `.container-fluid`：所有的breakpoint下都是`width: 100%`


### Bootstrap Grids

- Bootstrap預設12等分，可以自訂要怎麼分配這12等分

- 使用網格系統時，一定要有parent element的display是flex屬性值（Bootstrap中包含在.row的class裡面）才會生效

- 用`.row`和`.col`去分配元素的大小

   ```html
   <div class="row">
     <div class="col-4">col-4</div>
     <div class="col-4">col-4</div>
     <div class="col-4">col-4</div>
   </div>
   ```

   - 雖然預設是12等分，但如果用的是`.col`而已，那還是會硬加下去，例如有13個col，就會硬拆分成13等分

      ```html
      <div class="row">
            <div class="col">1</div>
            <div class="col">2</div>
            <div class="col">3</div>
            <div class="col">4</div>
            <div class="col">5</div>
            <div class="col">6</div>
            <div class="col">7</div>
            <div class="col">8</div>
            <div class="col">9</div>
            <div class="col">10</div>
            <div class="col">11</div>
            <div class="col">12</div>
            <div class="col">13</div>
          </div>
      ```


   - 如果`.col`後面有數字指定分配等分，**超過12等分的元素就會被放到下一列去**。**建議都指定清楚要分配的等分，好讓別人理解也不會搞混**

      ```html
          <div class="row">
            <div class="col-4">1</div>
            <div class="col-4">2</div>
            <div class="col-4">3</div>
            <div class="col-4">4</div>
          </div>
      ```


      - 也有可能一排不滿12等分

         ```html
         <div class="row">
               <div class="col-5">1</div>
               <div class="col-8">2</div>
               <div class="col-12">3</div>
             </div>
         ```

- `.col-{斷點}-{數字}`：要滿出斷點才會指定分配到該數字

   - .col-md-6：在畫面滿足md（>=768px）的時候，指定元素分配6等分

- `.row-cols-{數字}`：從parent元素的角度下去寫

   - .row-cols-2：一列要有兩欄

      ```html
      <div class="container text-center">
        <div class="row row-cols-2">
          <div class="col">Column</div>
          <div class="col">Column</div>
          <div class="col">Column</div>
          <div class="col">Column</div>
        </div>
      </div>
      ```

- Nesting：巢壯結構，可以在被等分的欄位中再等分12等分，再下去分割空間

   - Bootstrap官網例子：

      ```html
      <div class="container text-center">
        <div class="row">
          <div class="col-sm-3">
            Level 1: .col-sm-3
          </div>
          <div class="col-sm-9">
            <div class="row">
              <div class="col-8 col-sm-6">
                Level 2: .col-8 .col-sm-6
              </div>
              <div class="col-4 col-sm-6">
                Level 2: .col-4 .col-sm-6
              </div>
            </div>
          </div>
        </div>
      </div>
      ```

---

### Typography

- Bootstrap有幾種預設語意且具備樣式的標籤如下：

- `h1`到`h6`：Bootstrap的h1到h6跟原本html預設的樣式一樣，但是可以透過將其他文字套用該class標籤來達到，跟h1到h6一樣的樣式，可是標籤元素的語意不同。

   ```html
   <head>
       <link rel="stylesheet" href="../_css/bootstrap.css" />
       <script src="../_js/bootstrap.bundle.js"></script>
   </head>
   <body>
         <h1>Apple</h1>
         <p class="h1">Apple</p>
         <!-- 這裡的p跟h1呈現出來的樣式一樣，但是兩者在網頁架構上的語意不同  -->
   </body>
   ```

- `display-{數字}`：有1到6的層級，表示文字大小

- `small`：要來標示註解、版權等小字

- `mark`：淡黃色的highlight標示文字

- `abbr`：Abbreviations，讓文字變成有需底線，當使用者把遊標移動到上面時，遊標會變成問號，然後會顯示出title屬性設定的值（說明）

- `blockquote`：用來標示引用的段落，配合figure、figcaption、.blockquote、.blockquote-footer、cite

   ```html
        <figure>
           <blockquote class="blockquote">
             <p>A well-known quote, contained in a blockquote element.</p>
           </blockquote>
           <figcaption class="blockquote-footer">
             Someone famous in <cite title="Source Title">Source Title</cite>
           </figcaption>
         </figure>
   ```
- `code`：用來highlight程式碼段落的標籤

- `kbd`：keyboard用來標示鍵盤輸入的段落
