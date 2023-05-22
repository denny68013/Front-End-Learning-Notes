
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
<!--註解-->
```

### 屬性

- 屬性會加在開始標籤（角括弧）裡面，在標籤名稱之後，用一個空白隔開，如下圖：


- 不同元素可能有不同屬性：例如 a 標籤（超連結）中的 href 屬性

  ```html
  <a href=""></a>
  ```

- 元素能有多個屬性，屬性位置不影響功能

- 同一個元素不能有多個相同的屬性（如兩個 id 或兩個 href 等等）

- 元素如果使用不支援的屬性則沒有效果

  - 如 href 就是 a 標籤才有，放在其他如 h1 標籤，都不會有效果

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
<a href=""></a>
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

<https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes>

---
# HTML 文件結構

### &lt;!DOCTYPE html&gt;

- 是 HTML 文件的宣告（declaration），不是標籤（tag）

- 不區分大小寫

### html 元素

- html 元素就是 HTML 文件的根元素（root element），用來標示網頁的範圍

- lang=”en-US”：用來告訴瀏覽器這份文件要以什麼語言閱讀\
  HTML 的 ISO Language Codes\
  <https://www.w3schools.com/tags/ref_language_codes.asp>\
  HTML 的 ISO Country Codes\
  <https://www.w3schools.com/tags/ref_language_codes.asp>

### head 元素

- &lt;meta&gt;元素：用來定義一些資訊給搜尋引擎與瀏覽器看

  - 只有開始標籤沒有結束標籤

  - chartset=”UTF-8”：編碼使用 UTF-8 格式

  - name=”description”：網頁資訊的形容（只能使用 description，不能使用 description2）

    - 不能寫成如下圖，有既定寫法

    ```html
    &lt;meta description="對網頁的說明"&gt;
    ```

  - name=”keywords”：網頁的關鍵字，一樣放在 content 裡去定義

    - Google 不會用這個關鍵字標記在搜尋排名上

    [https://www.youtube.com/watch?v=jK7IPbnmvVU](https://www.youtube.com/watch?v=jK7IPbnmvVU)

    - 但是可能有其他家搜尋引擎會使用 keywords，所以你依然可以放進去

  - name=”author”：網頁作者

  - name=”viewport”：網頁的可見區域，當有設定好的時候在不同的視窗中被觀看的方式就會不一樣，跟 RWD（Responsive Web Design）響應式網站設計有關

    - **width=device-width**

      因為目前手機尺寸非常多，因此，我們就只要設定為 width=device-width 就可以自動符合所有不同手機螢幕他們自己的預設最佳解析度。

      ### **initial-scale=1**

      設定手機螢幕畫面的初始縮放比例為 100%。

      ### **user-scalable=no**

      有時候網站會有特殊設定，或者業主有指定不允許使用者改變縮放比例，則會將值設為 no。\
      \
      來源：<https://ithelp.ithome.com.tw/articles/10195279>

- &lt;title&gt;元素：網頁標題

- &lt;link&gt;元素：文件之間的關聯

  - rel：relationship

  - type：後方的種類是固定的，不能寫成 png2

  - 這段是在連結網頁標題旁的縮圖要使用什麼圖片

  - 連結到某個地方的 css 檔

  - **CSS 檔的語法（在 HTML 文件中都寫在&lt;head&gt;元素裡）：**

    - 選擇器：選擇哪些元素作為套用對象\
      p{}：只要元素的標籤是&lt;p&gt;就會被選擇

    - 屬性名稱：屬性值 → 選擇樣式要以怎麼樣呈現\
      （與 HTML 的「屬性名稱=屬性值」寫法不同）

    - 多種屬性之間以「;」分開，如果只有一種屬性也會習慣加上一個分號\
      （與 HTML 的多種屬性是以「空格」分開不同）

  - CSS 語法也可以寫在 HTML 裡，以&lt;style&gt;標籤包起來，如下圖，選擇&lt;div&gt;標籤後指定他的背景顏色屬性值為 aquamarine

- &lt;style&gt;元素

### body 元素

- 網站上的內容都是寫在這個裡面

**常用標籤**

- 特殊的保留符號（指在 HTML 文件中已經被預設有公用的符號），需要參考 HTML Entity Code 來表現：

  - 空格 → 換成&nbsp;或&#160;

  - 大於&gt; → &gt; 或 &#62;

  - 小於&lt; → &lt; 或 &#60;

  - 參考符號列表：<https://oinam.github.io/entities/&gt;

- **區塊元素（block level）前後會換行，不是透過&lt;br&gt;來換行，就是區塊元素，反之不換行的的就是行內元素（inline level）**

- &lt;h1&gt;\~&lt;h6&gt;：標題大小

- &lt;p&gt;：定義段落

- &lt;hr&gt;：分隔網頁段落（沒有結束標籤）

- &lt;br&gt;：換行（沒有結束標籤）

- &lt;pre&gt;：preformatted，該元素中的文本會按照原本的格式做排列，比如空白或換行。

- &lt;div&gt;：division，為分割區塊使用，是**區塊元素（block level），前後會換行**，常用在網站的元素佈局規劃，像是一個袋子，可以用來做各層級分類。

  - 區塊元素可以包含區塊元素

  - &lt;div&gt;不會被包含在一些功能特定的元素中（如&lt;h1&gt;、&lt;p&gt;，因為每個標籤有設計出來的用途與目的）

- &lt;span&gt;：行內元素（inline level）前後不會換行

  - 區塊元素可以包含行內元素，但行內元素不能包含區塊元素

- &lt;b&gt;：粗體 bold

- &lt;i&gt;：斜體

- &lt;s&gt;：刪除線 strikethrough

- &lt;u&gt;：底線 underline

- &lt;strong&gt;：粗體，語氣強烈

- &lt;em&gt;：斜體，強調

- &lt;del&gt;：被刪除的文字

- &lt;ins&gt;：插入的文字 insert（瀏覽器通常會畫底線）

- 有些標籤雖然在瀏覽器上顯示一樣，但是一個是風格上改變，一個是語氣上不同，兩者在使用朗讀網站文章功能時可能會出現變化

-

## 為什麼寫 HTML 的時候會有這些屬於 CSS 的樣式設定？

→HTML CSS JS 彼此能夠互相做一些簡單的設定

- HTML 的 Element 呈現出來的預設 CSS 樣式對照表：<https://www.w3schools.com/cssref/css_default_values.php>


