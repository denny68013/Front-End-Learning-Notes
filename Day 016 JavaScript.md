# 06\.12 Day 016 JavaScript

## VScode的提示

- VScode的提示參數後面接一個?代表可有可無

- 不同參數之間用,分開

- VScode的提示中如果沒有回傳值，會寫void

## String

- 如果想要印出引號，要同時使用到單引號和雙引號或使用\\”（跳脫字元）

- 如果沒有先給值，直接讓變數=變數，會出錯 not defined.

### String Method

- `indexOf(searchString:string,position?)`：搜尋子字串的位置，index從0開始算，有match到的話回傳第一個字match到的數字，如果找不到回傳-1

- `lastIndexOf(searchString:string,position?)`：搜尋子字串的位置，index從0開始算，有match到的話回傳最後一個字match到的數字

- `split(``separator``,`` limit``)`：切割字串，以separator為目標，切割目標作字串，limit可以限制數量，回傳array

   ```javascript
    var fruits = "apple,bubble,lemon";
         temp = fruits.split(",b", 1);
         console.log(temp);
   //印出['apple']　
   ```

- `padStart(maxLength,fillString?)`：開頭補字元

   - maxLength目標字串長度

   - fillString是想在前面加的字元，如果沒有填會以空白代替

   - `padEnd()`：結尾補字元方法同padStart()

- `substring(indexStart, indexEnd?)`：截取後**回傳字串**，indexStart填入開始的index（有包含），indexEnd填入結束的index（不包含該index值！），

   - 如果indexEnd沒有填則預設截取到最後面

   - 如果indexEnd小於indexStart，substring會自動對調數字，由小截到大

   - 如果有負數，則substring()會將其視為0

- `slice(indexStart?, indexEnd?)`：截取後**回傳字串，**indexStart和indexEnd可同時不填，傳回整串字串，與substring()不同，indexEnd需大於indexStart，如果indexEnd小於indexStart則不會回傳東西。

   - 如果有負數，則slice()會從後面數過來

   ```javascript
   var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
   console.log(`str.slice(5,3)：${str.slice(5, 3)}`);
   //str.slice(5,3)：　　　　　　　　　　　　　
   
   console.log(`str.slice(-5)：${str.slice(-5)}`);
   //印出str.slice(-5)：VWXYZ
   ```

- `toString()`：字串化

### Escape Character

- 跳脫字元，以反斜線開頭+英文或符號，如果在引號中會成爲另外一種表示：

   - 例如：\\t 會成為 換行 會印出C:\\temp

   ```javascript
   var str1 = "C:\temp";
         console.log(str2);　　　　　　　　　　　　　　　　　　　　　　
   // 會印出C: emp　　　　　　
   　　　　　　　　　　　
   var str2 = "C:\\temp"　　　　　　　　;
         console.log(str2);　　　　
   // 會印出C:\temp　　　　　　　　　　　　
   ```

- 詳細的跳脫字元參考：<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Character_escape>

## Template Literals

- 模板字串，用\`\`包起字串，就可以在字串中用${}包含變數，變數就會在處理的時候代入變數被給予的值

```javascript
 var food = "小籠包"; 
 var store = "鼎泰豐";

//原本的寫法
 var str3 = "3.我想來點" + store + "的" + food;
 console.log(str3);

//更方便的寫法
 var str4 = `4.我想來點${store}的${food}`;
 console.log(str4);
```

## Number

- 數字，能處理的最大範圍 -2^53到2^53之間（不含兩個端點），如果超出這個最大數，則計算結果會有誤

- Infinity、-Infinity：正數除以0會得到到值Infinity、負數除以0則會得到-Infinity

- NaN：Not a Number的縮寫，如果遇到數字除以字串，JS會先把字串轉換成數字，但如果無法相除，就會得到NaN，形態上是數字（用`typeof`去檢驗的話） 

   ```javascript
   var x = 100 / 10;
   var y = 100 / "10";
   var z = 100 / "apple";
   console.log(x,y,z);
   //印出 10 10 NaN
   ```

### Number Method

- isNaN(number)：判斷是否是NaN，回傳true或false

- 「數字字串」與數字的加減法：

   - 數字字串+數字：得到字串，因為+是JS的字串連結符號，所以JS會把後面的數字自動變成字串。

   - 數字字串-數字：得到數字，因為JS不能使用-號來拆減字串，所以會把第一個字串轉換成數字相減。

   ```javascript
         var a1 = "11" + 1;
         console.log(a1);
   //印出111
   
         var a2 = "11" - 1;
         console.log(a2);
   //印出10　　
   ```

- `parseInt(string,radix)`：把文字轉換成數值

   - radix：要轉換目標進位系統，如果沒有填，預設不是十進位

      - 如果字串開頭是0x或0X，預設是轉換成16進位

      - 如果字串是其他數字開頭，預設轉換成10進位

## array

- 當你需要很多儲存相同的資料型態時，可以使用陣列儲存並透過index取值，不同形態的資料不建議存在同一個陣列裡面

- \[a,b,c\]：陣列的資料就是元素（與html的元素不同），中間用,分開

- 透過index放入取出或修改儲存的值

- 巢狀陣列：陣列中放入陣列

   ```javascript
         apple[0] = "皮卡球";
         apple[1] = 85;
         apple[2] = ["cat", "dog"];
         console.log(apple);
   //印出['皮卡球', 85, Array(2)]　　
   ```

- 如果用const，不能一開始不指派陣列給他，事後也不能重新指派整個陣列，但是如果要一項一項調整是可以的。

   ```javascript
   const cars ;
   cars = ["Saab", "Volvo", "BMW"];
   //Missing initializer in const declaration
   
   const cars = ["Saab", "Volvo", "BMW"];
   const cars = ["a", "b"];
   console.log(cars);
   //entifier 'cars' has already been declared
   
   const cars = ["Saab", "Volvo", "BMW"];
   cars[0] = "a";
   cars[1] = "b";
   cars[2] = "c";
   console.log(cars);　　
   //印出 ['a', 'b', 'c']　　
   ```

- `array.length`：回傳陣列有幾個值

- 二維陣列的長度：以選擇到的那層陣列為基準，不管裡面的單一陣列有多少元素，都只算一個陣列一個元素

   ```javascript
         var poker = [];
         poker[0] = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13];
         console.clear();
         console.log(poker);
         console.log(poker.length);
         console.log(poker[0].length);
   // output:[Array(13)]　　
   // output:1
   // output:13
   ```

### Array Method

- `join()`：用指定的字串把陣列內容串起來，合併成一個字串。

   - 在不帶參數的狀況下，會跟toString()呈現一樣的結果

   ```javascript
   var weekList = [
           "sunday",
           "monday",
           "tuesday",
           "wednesday",
           "thursday",
           "friday",
           "saturday",
         ];
         var x = weekList.join();
         console.log(x);
         // output:sunday,monday,tuesday,wednesday,thursday,friday,saturday
         var y = weekList.join("#");
         console.log(y);
         // output:sunday#monday#tuesday#wednesday#thursday#friday#saturday　　
   ```

- `shift()`：移除並**回傳陣列的第一個元素**，會改變原陣列的長度。

- `pop()`：移除並**回傳陣列的最後一個元素**，會改變原陣列的長度。

- `push()`：新增一個或多個元素到陣列的最後面，回傳新陣列的**長度**

- `unshift()`：新增一個或多個元素到陣列的最前面，回傳新陣列的**長度**

## call by value vs. call by reference

- 當參數傳入時，call by value是把值傳給另一個變數，call by reference是把參考位置傳給另一個變數，所以如果原本位置的值有改，另一個得到該位置的變數裡的值也會改。

   - 在JavaScript中為了怕像是陣列的元素過多，保護記憶體空間，因此陣列採用的是call by reference

## Object

- {}用大括號定義物件，可以包含屬性和方法。

- 當你有許多相關連結且不同形態的資料。

   - {key1:value1,key2:value2…}

```javascript

      // 10. 使用 {} create object；object 可以包含屬性和方法
      //     { key1:value1, key2:value2.. }
      var pikachu = {
        name: "皮卡丘",
        chinese: 80,
        math: 90,
      };
      var puli = {
        name: "胖丁",
        chinese: 100,
        math: 60,
      };
      // 20. 透過 .  可以 取得 | 新增 object 的屬性

      console.log(pikachu);
      //{name: '皮卡丘', chinese: 80, math: 90}

      console.log(pikachu.math);
      // 90

      pikachu.english = 100;
      console.log(pikachu);
      //{name: '皮卡丘', chinese: 80, math: 90, english: 100}

      pikachu.chinese = 85;
      console.log(pikachu);
      // {name: '皮卡丘', chinese: 85, math: 90, english: 100}

      // 可以先建立一個空物件
      var nb = {};
      console.log(nb);
      // {}
      nb.name = "acer";
      console.log(nb);
      // {name: 'acer'}

      // 30. 透過 [] 可以 取得 | 新增 object 的屬性
      console.log(pikachu.chinese);
      // 85
      console.log(pikachu["chinese"]);
      // 85

      //  修改
      pikachu["chinese"] = 60;
      console.log(pikachu);
      // {name: '皮卡丘', chinese: 60, math: 90, english: 100}

      //  新增
      pikachu["science"] = 70;
      console.log(pikachu);
      // {name: '皮卡丘', chinese: 60, math: 90, english: 100, science: 70}
```

## Boolean

- true或false兩個關鍵字

   - 可以在等號右邊用比較運算方式賦值

## typeof

- `typeof`：檢驗資料的形態方法，會回傳該資料是屬於哪一種類別（如數字、字串、布林值等）
