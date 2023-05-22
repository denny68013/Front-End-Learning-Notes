
* 數字命名是為了上課需求，在寫程式的時候不是一個好的寫法。

* HTML5：Hyper Text Markup Language

* HTML主要用途是**定義網頁內容**，用標籤進行標記和定義

  * 副檔名是.html

* HTML文件是由元素(Element)組成的

  * 元素 element：透過標籤(tags)建立

  * 標籤 opening tag & closing tag：<>（角括弧）加上英文數字字串建立，通常成對（有單一成立的標籤），元素是由**開始標籤**跟**結束標籤**建立，結束標籤會有一個 “/” 符號

  * 內容：放在開始與結束標籤中間的東西

* HTML5 提供比起前代更多元素：

  * 語意化區塊：	&lt;section>、	&lt;nav&gt;、	&lt;header&gt;

  * 多媒體區塊：	&lt;video>、&lt;audio&gt;、&lt;canvas&gt;

* HTML & CSS & JavaScript：

  * HTML(.html)：定義網頁**內容**

  * CSS(.css)：階層樣式表，定義網頁**外觀（美化）**

  * JavaScript(.js)：網頁與使用者**互動**

---
# Visual Studio Code

* 左鍵點兩下，頁籤上的標題不是斜體的話代表檔案不會被蓋掉（左鍵點一下就會出現斜體）

* vscode套件擴充：

  * Chinese (Traditional) Language Pack for Visual Studio Code 

  * Bracket Pair Colorization Toggler：把各組括號用不同的顏色標示

  * Auto Rename Tag：建立一個local server，在隨時存檔的時候更新html頁面

  * Live server：它會幫使用者自動開啟一個服務器，保存的時候便自動刷新瀏覽器頁面

  * open in browser：快速鍵開啓當前網頁

* 快速鍵：

  * Move line up/down：Alt+ ↑ / ↓（⌥↓ / ⌥↑）

  * Copy line down/up：Shift+Alt + ↓ / ↑（⇧⌥↓ / ⇧⌥↑ ）

---
# HTML 標籤與語法

- 註解：Ctrl(Command)+/

```html
&lt;!--註解--&gt;
```

### 屬性

- 屬性會加在開始標籤（角括弧）裡面，在標籤名稱之後，用一個空白隔開，如下圖：

  ![image.png](./HTML標籤與語法-assets/image.png)

- 不同元素可能有不同屬性：例如 a 標籤（超連結）中的 href 屬性

  ```html
  &lt;a href=""&gt;&lt;/a&gt;
  ```

- 元素能有多個屬性，屬性位置不影響功能

- 同一個元素不能有多個相同的屬性（如兩個 id 或兩個 href 等等）

- 元素如果使用不支援的屬性則沒有效果

  - 如 href 就是 a 標籤才有，放在其他如 h1 標籤，都不會有效果

    ![image 1.png](./HTML標籤與語法-assets/image%201.png)

### id 屬性

- id 是屬性用來識別元素、content 是屬性值（用=和””雙引號賦予），下圖為 Hello,World 的 h1 元素是有一個屬性 id，這個 id 的屬性值是 content

  - id 的屬性值要注意

    1. 有區分大小寫

    2. 至少包含一個字元

    3. **不能以數字開頭：**會與 CSS 的語法衝突**\
       &lt;https://stackoverflow.com/questions/22141358/why-can-an-element-id-not-start-with-an-integer&gt;**

    4. **不能包含空格：**一樣會與 CSS 的語法衝突

    5. **id 的屬性值是唯一**

### a 標籤超連結

```html
&lt;a href=""&gt;&lt;/a&gt;
```

- href：hypertext reference

### on 開頭屬性

- 為 JavaScript 相關的屬性，稱作**事件屬性**

- 可與函式功能搭配，要觸發的時候要在 function 的名字後面加上()

```javascript
funtion name (){
功能;
}
```
- 在 HTML 文件裡看到 on 屬性就是跟 JS 有關

- 在 HTML 文件裡看到&lt;script&gt;&lt;/script&gt;標籤也是跟 JS 有關

## HTML 的屬性一覽表

&lt;https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes&gt;

