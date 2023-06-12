# 06\.09 Day 015 Javascript

- Javascript是定義互動05.22 Day1 HTML

- Java是Sun的產品；JavaScript是Netscape的產品 \*(Oracle於2009年收購Sun)

- 優點是可以在client端執行部分運算，減少server端的負荷

- 缺點是若client端的JavaScript功能關閉，若網頁有使用JavaScript的功能，將無法運作。

## 物件

- 物件=「屬性（特徵）+方法（會動的）」的集合

- 萬物皆物件

- 瀏覽器提供的內建物件

   ![Pasted 2023-06-09T02!34!11.596Z](./06.09%20Day%20015%20Javascript-assets/Pasted%202023-06-09T02!34!11.596Z)

   - **Browser Object Model （BOM）瀏覽器物件模型**

      - 核心是window物件，可以用來操控瀏覽器本身底下的各種物件如：screen、history

         ![Pasted 2023-06-09T02!35!32.688Z](./06.09%20Day%20015%20Javascript-assets/Pasted%202023-06-09T02!35!32.688Z)

   - **Document Object Model （DOM）文件物件模型**

      ![Pasted 2023-06-09T02!35!21.999Z](./06.09%20Day%20015%20Javascript-assets/Pasted%202023-06-09T02!35!21.999Z)

      - 當html被瀏覽器載入時，會將html底下的所有元素轉成物件，用Javascript的語法去操控各種元素的內容或屬性

      > **HTML DOM 規範中定義了這些類型 API：**
      >
      > 1. 可將 HTML 的元素 (element) 當作是 JavaScript 物件 (object) 來操作
      >
      > 2. 定義 HTML 元素有哪些屬性可被操作
      >
      > 3. 能存取所有 HTML 元素的方法
      >
      > 4. 元素事件，可針對元素來做事件的綁定
      >
      > \
      > 參考：<https://ithelp.ithome.com.tw/articles/10235746>

### <script> 標籤

- 使用JavaScript語法的方法

   - 將Javascript寫在<script>開始和結束標籤內

      - <script type="text/javascript">這個寫法是舊版標籤，並沒有錯，只是現在已經很少人在用

   - 用<script src=”” > 標籤連結到外部JS檔

      - **如果使用<script src=”” > 載入外部J　檔案，那開始跟結束標籤之間就無法撰寫JavaScript的語法！**

   ```html
    <script src="./index.js"></script>
   ```

### 使用物件

- 物件名稱.方法()、物件名稱.方法(資料)

   - 用句點去取用DOM的功能，後面有接括號的才是功能，括號裡面有可能不需要有東西

```javascript
document.write("100")
```

- 單/雙引內是字串，以這個例子來說就是會呈現「100」

   - 如果write功能後字串中放的是html的元素，則會呈現渲染過後的元素（等於新增一個html元素）

### 取得物件屬性

- 物件名稱.屬性名稱

### console

console原本是指外接終端，在這裡是指client端的Javascript命令介面

- console.log()：最常用，印出訊息

- console.error()：跳出錯誤訊息，呈現紅色

- console.warn()：跳出警告訊息，呈現黃色

- console.clear()：清楚console上的訊息

- console.table(\[array\])：用陣列呈現表格

- console.time()：計時開始

   - console.timeEnd() 計時結束（搭配使用）

- console.group()：建立一個群組（預設是展開狀態）

   - console.groupCollapsed()：一樣建立一個群組（預設是收合狀態）

   - console.groupEnd()：群組的結束點（搭配使用）

### document object

- 當html文件被瀏覽器載入時，他就會變成一個document object。

- window.document或document都可以

- console.log(document)：會印出document的所有東西

   - console.log(document.head)、console.log(document.body)：在chrome瀏覽器上有可能會出現兩種，端看瀏覽器每次重新整理都不同\
      參考：<https://stackoverflow.com/questions/12736679/console-logdocument-head-results-alternate-with-each-refresh>　
      
### getElementsBy

- document.getElementsByTagName()：用標籤名稱去取得元素

- document.getElementsById()：用#id去取得元素

- 可以如圖用.去進一步取得更裡面的元素

- document.getElementsByName()：用name屬性去取得元素

### 順序很重要

- 因為電腦是由上往下讀，所以如果Js檔的某一行出錯，後面就不會繼續執行下去（除非有使用其他條件式）

- 因此<script>寫在<head>還是<body>會有差，在<head>中要找<body>裡面的元素就會找不到

- 所以建議把<script>放在<body>的最後，除了是先後順序的功能外，在使用者端也不會因為先讀入大JS檔造成卡住延遲，讓網頁的內容很慢才顯示出來。

### function 函式

- function 函式名稱(變數){函式功能}

### onclick

- onclick=””：元素被點擊的時候產生互動，如果裡面又有引號的話使用單引號，避免電腦誤讀引號順序

## 宣告變數

- JavaScript的變數名稱有以下命名規則

   - 英文大小寫（JS有區分大小寫）

   - \_ 底線、$符號（比較特殊用途）

   - 數字0-9**（但是數字不能放開頭！！！）**

- 多個名詞組合不要使用-號，因為電腦會誤判成減號運算，可以用底線或小駝峰式寫法

   - first-name（X）：不能用-

   - first name（X）：不能用空白

   - first_name（O）：常用

   - firstName（O）：小駝峰，最常用

   - FirstName（O）：大駝峰，可以用但是比較少

   - firstname（O）：可以用但是很少

- JavaScript Reserved Words：JavaScript的保留字，在做變數或函式命名的時候不能跟這些名稱衝突，不然功能可能會出錯\
   參考：<https://www.w3schools.com/js/js_reserved.asp>

### var、let、const

- 三個都是宣告變數使用的詞，let、const 是在ES6版本之後才出現，解決一些var的問題。

- const：

   - const 的變數宣告並給予值之後，無法再給予其他值，並且const也沒辦法事後指派值，必須要在宣告的時候就指派。

   - **不能改值、不能事後指派！**

      ```javascript
      
          //   以下產生碼會出錯
            const PI;
            PI=3.14
            console.log(PI);
      ```

- var：

   - var宣告是全局宣告，不管是在條件式的大括號裡還是限定作用域，都可以在其他地方取得該變數值。

      ```javascript
            if (2 > 1) {
              var cat = 100;
            }
            console.log(dog);
      // dog會被印出顯示100
      ```

   - var可以重新宣告，重新宣告後，後面賦予的值會蓋過前面，但是這個寫法在其他程式語言中通常是錯的。

      ```javascript
            var apple = 1;
            var apple = 2;
            console.log(apple);
      
      //apple會顯示2，但這個寫法在其他語言中是錯誤的
      ```

- let：

   - let宣告有限定作用的區域，如果在區域外取用，會顯示not defined，

      ```javascript
            if (2 > 1) {
              let dog = 200;
            }
            console.log(dog);
      //會跳出錯誤訊息：dog is not defined
      ```

   - let不能重新再宣告一次相同的變數名稱，但是可以被改值，賦予一個新的值。

      ```javascript
            let bee = 3;
            let bee = 4;
            console.log(bee);
      //跳出錯誤訊息Identifier 'bee' has already been declared (
      ```

      ```javascript
            let bee = 3;
            bee = 4;
            console.log(bee);
      //會印出4
      ```

### not defined、undefined

- not defined：變數還沒被定義（宣告）

   - XXX is not defined是錯誤訊息，語法有錯

- undefined：未定義，變數存在但未被定義。

### hoisting

- 提升，JavaScript會預設將變數宣告移到作用域的最前面。

- 以下不同案例宣告變數情況

   ```javascript
        console.log(x);
   //caught ReferenceError: x is not defined
   ```

   ```javascript
         var y;
         console.log(y);
   //呈現undefined
   ```

   ```javascript
         var y;
         y = 10;
         console.log(y);
   // 呈現是10
   ```

   ```javascript
         console.log(z);
         var z = 20;
   //呈現undefined
   //因為hoisting的關係所以跟以下幾行的結果一樣
        　//var z;
         //console.log(z);
         //z = 20;
   ```

   - var會hoisting，在宣告的時候往前提

   ```javascript
         console.log(z);
         let z = 20;
   //出現錯誤訊息ReferenceError: Cannot access 'z' before initialization
   ```

   - let和const其實有hoist，但是不會被初始化（宣告），因此會產生reference error，實際上是因為在TDZ（Temporal Dead Zone）的關係產生reference錯誤

   > The variable is in a “temporal dead zone” from the start of the block until the initialization is processed.\
   > \
   > 在變數完成初始化之前呼叫的話，是會處於暫時性死區 (TDZ)，這也就是為什麼會出現 `ReferenceError` 錯誤，而實際上 `let` 運作模式有變嗎？其實並沒有，只是會變成 `ReferenceError` 暫時性死區錯誤\
   > \
   > 參考：[JavaScript 核心觀念(61) - ES6 章節：Let 及 Const - Let 有沒有 Hoisting？暫時性死區介紹 | 是 Ray 不是 Array ](https://israynotarray.com/javascript/20210718/956160363/)

   > 參考另外一篇文章：[我知道你懂 hoisting，可是你了解到多深？](https://blog.techbridge.cc/2018/11/10/javascript-hoisting/)


