# 06\.13 Day 017 JavaScript

## 運算子

- `a + b`：a、b是運算元，+是運算子

- `+-*/`：加減乘除，要注意兩邊都要是數字才能運算

- `%`：取餘數，`a%b`，a除以b後的餘數

   - 常用在判斷奇偶數

- `變數++`和`++變數`：變數+1

   - `b+=1`、`b++`都是等於b=b+1

   - `b+=2` 就是 b=b+2

   - 注意變數++和++變數的處理先後會有不同：\
      變數++會先給出變數之後再處理++；\
      \++變數是先處理完變數+1再整個回傳

   ```javascript
         var b = 3;
         var c = 3;
         console.log(b++);//印出3
         console.log(b);//印出4
   
         console.log(++c);//印出4
         console.log(c);//印出4
   ```

### = vs. == vs. ===

- =：賦值

- ==：寬鬆比較，判斷**運算元的值**是否相同

   > **「==」 寬鬆比較**
   >
   > 如果運算元相同型別，就使用嚴格比較去檢驗。
   >
   > null跟undefined相同。
   >
   > 運算元一個是數值，一個是字串，會將字串轉數字，再進行比較。
   >
   > **其中一個是true或false會轉成數字的1或0，再進行比較。**
   >
   > 其中一個是物件，另一個是字串或數值，物件會先轉成基型值，再進行比較。\
   > \
   > 參考：<https://ithelp.ithome.com.tw/articles/10204290>

- ===：嚴格比較，判斷**運算元的值還有資料形態**是否相同

   ```javascript
         var x = 10;
         var y = "10";
         var temp = x == y;
         console.log(temp);//true，JS會先試著轉換字串再比較
   
         var temp = x === y;
         console.log(temp);//false，雖然值相同但是兩邊的資料形態不相同
   ```

   > **「===」 嚴格比較**
   >
   > 先判斷運算元的型別是否相同，若不相同，結果為false。
   >
   > null與undefined都跟自己相等。
   >
   > true與false都跟自己相等。
   >
   > NaN不等於任何值，包括自己。
   >
   > 只要是number型別的值一樣，他們就相等。
   >
   > 0跟-0相等。
   >
   > string長度跟內容不一樣，包括空白，它們就不相等。
   >
   > **如果參考至同一個物件、陣列、函式，相同的記憶體位置，他們就相等，若無，就算內容的值一樣，它們也不相等，不同的記憶體位置存相同的值。\
   > **\
   > 參考：<https://ithelp.ithome.com.tw/articles/10204290>

### \>、<

- a>b 兩個運算元比較：得到true或false

- a>b>c 連續比較：會先處理a>b是true還是false，再用true或false的值去跟c比較得到true或false

   ```javascript
         console.log(1 < 2 < 3);//true
         console.log(3 > 2 > 1);//false
   ```

   - 建議兩兩比較就好，不然可能容易搞混

### !=

- 不等於，比較後回傳true或false

### 邏輯運算子 &&、||

- 常常與if條件句配合使用

- && ：and，條件需要同時成立的時候

- ||：or，條件擇一成立

```javascript
      var apple = 10;
      var bee = 5;
      console.log(apple == 10 && bee == 5); //true
      console.log(apple == 10 || bee != 5); //true
```

### 條件（三元）運算子

- (condition) ? value1:value2：當條件成立時回傳value1，條件不成立時回傳value2

   ```javascript
         var temp = "PM";
         var apple = 0;
   
   //原本的條件式
         if (temp == "AM") {
           apple = 100;
         } else {
           apple = 80;
         }
         console.log(apple);
   
   //用條件運算子改寫
        var apple= (temp=="AM")?100:80
   ```

## 日期

- new Date()：使用new來生成日期物件，預設回傳星期、年月日 時間 時區

   ```javascript
         var d = new Date();
         console.log(d);
   //Tue Jun 13 2023 10:23:31 GMT+0800 (台北標準時間)
   ```

- Date物件底下的功能

   - getFullYear()：回傳四位數的年份數字

   - getMonth()：回傳月份的數字，**編號從0開始到11！**

   - getDate()：回傳日期的數字，編號從1到31

   - getDay()：回傳星期的數字，**編號從0=星期日開始到6=星期六！**

   - geyHours()：回傳小時的數字，編號從0到23，也就是24小時制

   - getMinutes()：回傳分鐘的數字，編號從0到59

   ```javascript
         // 宣告一個時間物件
         var d = new Date();
         console.log(d); //Tue Jun 13 2023 10:32:41 GMT+0800 (台北標準時間)
         // 取得年份
         console.log(d.getFullYear()); //2023
         // 取得月份 (請注意這裡)
         console.log(d.getMonth() + 1); // 6
         // 取得日期
         console.log(d.getDate()); //13
         // 取得星期 (請注意這裡)
         console.log(d.getDay()); //2
         // 取得時間
         console.log(d.getHours()); //10
         // 取得分鐘
         console.log(d.getMinutes()); //32
   ```

   - setDate()：設定物件的日期

      - 這個月最後一天=下個月第0天

- 日期相加減：JS中可以直接兩個日期相加減，會被轉成毫秒的答案，如果要轉換成日期或小時，可以將答案除以1000 \* 60 \* 60 \* 24（日期）或 1000 \* 60 \* 60（小時）

   - 一天的毫秒 millisecond = 86400000 = 1000*60*60\*24

## Math

- `Math.random()`：取亂數，會隨機取0到1之前的數值（包含0，不包含1）

   - 

- 進位捨去：

   - `Math``.round()`：回傳最接近的整數四捨五入到整數

   - `Math.ceil()`：回傳大於或等於的最小整數

   - `Math.floor()`：回傳小於或等於的最大整數

   - `Math.trunc()`：無條件捨去小數以後的部分

## Window

- `window.alert()`：跳出警告視窗，只有一個確定選項，括號裡面不限定資料形態

   - 可以直接寫`alert()`，一樣的功能

- `window.confirm()`：跳出確認視窗，有確定或取消選項，回傳布林值，確定回傳true，取消會回傳false

## prompt

- prompt()：跳出輸入視窗，有確定和取消兩個選項，按下確定會回傳使用者輸入的值（沒有輸入則為空白），按下取消會回傳null

## setInterval、setTimeout

- `setInterval(handler,time?,arg1,arg2…)`：在固定的間隔時間下執行指定function（handler），時間以毫秒為單位，會回傳一個ID值

   - handler的function寫法要注意：

      - `setInterval(func,1000)`：每一秒會執行一次func()

      - `setInterval(“func”,1000)`：每一秒會執行一次func()

      - `setInterval(func(),1000)`：**一開始執行一次func()後就不會再執行！（因為第一次執行完後會變成undefined）**

   - `clearInterval(intervalId)`：括號裡面放回傳的ID值，清除setInterval的執行

- `setTimeout(handler,time?,arg1,arg2…)`：指定時間到了後執行指定function（handler），時間以毫秒為單位，會回傳一個ID值

   - 寫法跟setInterval一樣要注意，用法同上

   - `clearTimeout(timeoutId)`：括號裡面放回傳的ID值，清除setTimeout的執行

### 補充跳轉網頁寫法

- `<meta http-equiv="refresh" content="0;url=`[`https://www.google.com`](www.google.com)`" />`

   - 在meta標籤寫，content指定時間，單位是毫秒

- `document.location.href = "`[`https://www.google.com`](https://www.google.com)`";`

   - 用JS指定網頁屬性

## getComputedStyle

- `window.getComputedStyle(element)`：取回CSS樣式的值，取到的是最終套用在該元素上所有CSS的效果，沒有特別寫的也會把默認的都寫出來

   - 可以用`getPropertyValue(“property“)`：去得到該元素底下特定的CSS設定

   - 跟使用`element.style`的方法不同的是，如果style中沒有套用屬性就不會回傳東西，而`getComputedStyle` 只能讀取不能改變，`element.style`可以讀取跟改變




