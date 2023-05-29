# 05\.25 Day 5 CSS

# 連結CSS的方式：

* External CSS：外部樣式連結至HTML文件，將<link>放在<head>元素中

```html
  <head>
    <meta charset="UTF-8" />
<link rel="stylesheet" href="./style.css">
  </head>
```

* Internal CSS：在 <head> 元素裡使用 <style> 元素嵌入樣式表

```html
 <head>   
    <style>
      p {
        color: red;
      }
    </style>
  </head>
```

* Inline CSS：使用 HTML 元素的 style 屬性

```html
  <body>
    <p style="color:red;">Apple</p>
  </body>
```

---

## selector 選擇器

### Type selector 類型選擇器

* 使用標籤(tag name)挑選元素並設定樣式

```css
h1{ color: red;}
```

### ID selector ID選擇器

* 使用 #id 挑選元素並設定樣式

```css
#pikachu { color: yellow　;}
```

### Class selector 類別選擇器

* 使用 .class 挑選元素並設定樣式

* 要表達兩個以上的class類別，要用空格隔開，不能寫超過一個class屬性在一個標籤元素中

```html
<h1 class="pokemon fire">小火龍</h1>
```

```css
.pokemon { background-color: lightblue;}
.fire{border: 2px solid red;}
```

### Universal selector 萬用選擇器

* 用\*字號設定樣式

```css
* {background-color: aquamarine;}
```

### Attribute selector 屬性選擇器

* 將屬性條件寫在\[\]（中括號）裡面

* 權重等於.class，一樣是10分

```css
a[href^="https"] {font-size: 2rem;}

a[href*="pseudo"] {color: tomato;}

a[href$="https"] {background-color: lightblue;}

a[target="_blank"] {text-decoration: none;}
```

* \[attribute=”value”\]：屬性要完全等於value

* \[attribute^=”value”\]：屬性要以value開頭

* \[attribute$=”value”\]：屬性以value結尾

* \[attribute\*=”value”\]：屬性要包含value

### **Groups of selectors 群組選擇器**

* 用逗號,隔開：逗號前後可以使用不同選擇器

* 一次選取多種元素套用相同以上

```css
  h1,#pikachu,.pokemon{font-size: 72px;}
```

### Child combinator  子選擇器

* 用parent > child 來選擇直接底下的元素

```css
  div>h1 {color: red;}
/* <div>下一層的<h1>會被選到*/
```

### Descendant combinator 後代選擇器

* 用空白來選擇元素包含在內的所有元素

```css
  div h1 {color: red;}
/* <div>包含在內的所有<h1>都會被選到*/
```

### Adjacent Sibling combinator  同層相鄰選擇器

* 用+來選擇**同層**內緊鄰的元素

```css
  div+h1 {color: red;}
/* 跟<div>同一層並且與之相鄰的<h1>會被選到*/
```

### General Sibling combinator  同層全體選擇器

* 用～來選擇同層內**後面**的所有其他元素

```css
  div~h1 {color: red;}
/* 跟<div>同一層且在其後面的所有<h1>會被選到*/
```

## Pseudo-classes 虛擬類別

* 元素存在，且元素的樣式會隨使用者操作改變或元素存在，但無法透過 "simple selectors" 的方法選取的

* 用「:」冒號來選擇

* 與pseudo-element的「::」的不同

* 優先權重同 .class，一樣是10分

  ### 選取html標籤有兩種方法

  1. 用:root{}：選到的是HTML文件的根元素也就是<html>，跟第2種方法選到的方式一樣，但是這個方法優先權比較高

  2. html{}

  ```css
    :root {color: orange;}
    html {color: gray;}
  ```

#### 常見的pseudo classes

* :link：設定超連結未連結時的顏色

* :visited：設定超連結已連結過的顏色

* :hover：設定滑鼠移至連結上方時的顏色

* :active：設定超連結點選連結當下的顏色

* :nth-child(n)：符合本身是第幾個子元素的標籤，有以下幾種變化

  * :nth-child(2n+3)

  * :nth-child(odd/even)

  * :nth-child(3n)

  * :nth-last-child(n)：倒數第幾個子元素

* :nth-of-type：符合本身**該類型元素**是第幾個元素的標籤，變化

  * :nth-of-type(2n+3)

  * :nth-of-type(odd/even)

  * :nth-of-type(3n)

  * :nth-of-type(n)：倒數第幾個該類型元素

  * :valid

  * :invalid

### not()

* 用pseudo classes方法排除不想被套用的元素

```css
      td:not(:first-child) {
        background-color: lightgreen;
      }
```

## Pseudo Elements 虛擬元素

* 代表不直接存在於 document tree 中的元素。\
  參考：[https://titangene.github.io/article/css-selector-pseudo-element.html](https://titangene.github.io/article/css-selector-pseudo-element.html)

* 用「::」雙冒號來選擇

* 可以用CSS對html內的元素選擇指定的部分，因為這些指定的元素難以使用html寫法完成，因此這些

* 優先權重同標籤，一樣是1分

#### 常用pseudo elements

* ::before

* ::after

* ::first-letter

* ::first-line

---
# CSS 要注意的事

* CSS會區分文字大小寫 

* CSS註解方式為 /\* \*/ 

* 如果屬性值包含空白，記得將屬性值前後加上雙引號或者單引號

## CSS失效可能原因

* 打錯字、大小寫寫錯

* 語法錯誤

* 路徑錯誤（引用外部CSS檔的時候，路徑錯誤會讀不到檔案）

* 優先權（權重）沒有注意

* 宣告順序（後蓋前）

## CSS選擇器如何選擇滿足多種不同類型的標籤元素？

* 「標籤.class」：**注意中間沒有空白**

  ```html
    <h1>小火龍</h1>
    <h2 id="pikachu">皮卡丘</h2>
    <h3 class="pokemon">卡比受</h3>
    <h4 class="pokemon">卡比</h4>
    <h4>卡比攻</h4>
  ```

  ```css
    h4.pokemon {background-color: antiquewhite;}
  ```

## CSS的優先權

* **如果CSS衝突的話會以最後寫的，最有針對性的優先**（相同的選擇器中先處理完前面，處理後面的程式碼把前面覆蓋掉了，並不是前面沒有執行）

* 如果同樣的文字先設定為紅色，再設定為綠色，則執行完紅色後會再執行綠色將它覆蓋

* !important：最高的優先權，但是不建議實際使用，會造成無法分辨CSS優先順序，可以在測試使用，以找出問題是否在優先權的設定上

* 優先權（越前面越先）：**!important > inline CSS > #id > .class = :（pseudo class）= \[\] （屬性選擇器） > type 標籤 = :: （pseudo element）> \* （萬用選擇器）**

  > Selector types: The following list of selector types increases by specificity:
  >
  > 1. Type selector (e.g., h1) and pseudo-elements (e.g., ::before).
  > 2. Class selectors (e.g., .example), attributes selectors (e.g., \[type="radio"\]) and pseudo-classes (e.g., :hover).
  > 3. ID selectors (e.g., #example).
  >
  > 
  >
  > 文字跟具體CSS的優先權計算方法可參考<https://blogs.halodoc.io/best-practices-that-we-follow-to-avoid-specificity-issues/>

  * 優先權是用十進位的算法計算，單一class就是010→10分

    ![image.png](./CSS%20要注意的事-assets/image.png)

    CSS 權重計算

## HTML中標籤的多個class順序是否有影響？

* 如果你使用的選擇器是Attribute selectors的話，會

* 具體參考這篇stackoverflow上的貼文：\
  <https://stackoverflow.com/questions/15670631/does-the-order-of-classes-listed-on-an-item-affect-the-css>
    
---
# Semantic Elements

HTML 中有一些具有語義的 container，在網頁呈現上跟&lt;div id=”article”&gt;這種，沒有區別，但是在別人看程式碼的時候會因為這些語義元素讓理解的速度加快，元素包含但不限於如下：

- &lt;article&gt;

- &lt;aside&gt;

- &lt;details&gt;

- &lt;figcaption&gt;

- &lt;figure&gt;

- &lt;footer&gt;

- &lt;header&gt;

- &lt;main&gt;

- &lt;mark&gt;

- &lt;nav&gt;

- &lt;section&gt;

- &lt;summary&gt;

- &lt;time&gt;

![HTML Semantic Elements](https://www.w3schools.com/html/img_sem_elements.gif)

圖片與列舉出自：&lt;https://www.w3schools.com/html/html5_semantic_elements.asp&gt;

