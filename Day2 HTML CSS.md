# 05\.23 Day2 HTML CSS

- 使用 style 屬性能夠在 html 的標籤內完成 CSS 樣式設定。

```html
<span style="color：red">紅</span>
```

# 清單

### unordered list：無排序清單：

- 裡面要用&lt;li&gt;標籤去包

- &lt;ul&gt;和&lt;li&gt;是有結構的元素，&lt;ul&gt;的下一層只能放&lt;li&gt;

- 可以使用 list-style-type 的 CSS 樣式來更改前面的圖標（none、或圓形方形等）

```html
<ul>
  <li>item1</li>
  <li>item2</li>
</ul>
```

### ordered list：排序清單：

- 裡面一樣要用&lt;li&gt;標籤去包

- **編碼格式可以更改**：可以使用 start="5" type="A" reversed 等來改變前面項目的清單編號

- 也可以用 value 來指定單一項前面的編號（但是注意：後面的 list item 的清單編號也會隨著更改，而且只能使用數字來作為編號！）


### description list 描述清單：

- &lt;dl&gt;底下有兩個標籤：

  - &lt;dt&gt;：description list term 描述的東西名

  - &lt;dd&gt;：description descriptions 描述 item

```html
<dl>
  <dt>item</dt>
  <dd>item description</dd>
</ul>
```
---
# a href 超連結

- 屬性

  - target：指定要在哪裡打開連結的網頁

    - targe=”\_blank”能夠變成開啓新分頁

  - download：會啓動下載行為

    - download=”name.副檔名” 會以指定的名稱下載

  - 連結信箱

    - 以&lt;mailto:連結信箱，以;增加多個信箱&gt;

 
  ```html
  <a href=”mailto:abc@gmail.com;efg@gmail.com”
  
  >Contact Me</a>
  ```

  - 連結至網頁內元素（如跳轉文章內章節等）

    - href=”#id”

    - **需要用#標示該元素的 id 名稱（與 CSS 相同）**

    - 如果要回到頁面最上方有兩種方式：

      - href=”#” 加上#字號

      - href=”#top” 指定#top

### 要如何開啓內部檔案？

- 絕對路徑

  - 如網路上的路徑（https 開頭）

  - 如本機上的路徑（&lt;file://開頭&gt;)

    - **如果使用 live server 外掛功能，因為通訊協定不同（file://開頭和 https 開頭，架在 live server 走的是網路上的 https 通訊協定，如果讀得到的話，代表是網路上的任何網頁都可以存取到你的本機檔案，會有資安問題）**

- 相對路徑

  - .目前的目錄

  - /根目錄（root directory）

    - 如果是用 live server 執行，那根目錄就會是 VS Code 打開的資料夾

  - ..上一層目錄

  參考：&lt;https://ithelp.ithome.com.tw/articles/10268186&gt;
---
# img

```html
<img src="" alt="">
```

* 屬性

  * src：圖片路徑，路徑寫法參考a href 超連結

  * alt：替代文字，圖片讀不出來或者朗讀文章時會展現的文字

  * width、height：寬高像素設定，如果只設定一種，另外一個會等比例縮放。

    * 如果使用CSS語法去寫，數值跟單位之間是不是能有空白的。

    * %：為相對單位，會以父元素（parent element）的大小下去計算，如果img放在body下面，body就會是父元素，所以就會按照body的寬度下去計算（隨著視窗大小而改變）

      * height的%設置如果沒有作用，代表你沒有給父元素先定義一個height。（因為height有分視窗高度和網頁高度）

---
# figure 群組

* 是一個containter，可以用來表達self-contained的內容區塊，以&lt;figcaption&gt;標籤說明該區塊的標題

```html
    <figure>
      <img style="width: 100%" src="media/cat.jpg" alt="cat" />
      <figcaption>Fig1. - Cat</figcaption>
    </figure>
```
---
# CSS

* padding：元素的內邊距（元素內離自己邊邊的距離）

* margin：元素的外邊距（離其他元素的邊距）
---
# Audio

```html
    <audio src="./media/Mess_Call.mp3" controls muted loop autoplay>
      Audio
    </audio>
```

* 需要給一個controls才看得到操控面板

* muted：靜音

* loop：循環播放

* autoplay：在不同的瀏覽器下有限制

  * 如Chrome的限制：要靜音，或使用者有互動等

  * 參考：[Autoplay policy in Chrome - Chrome Developers ](https://developer.chrome.com/blog/autoplay/)

# Video

```html
    <video
      controls
      muted
      loop
      poster="./media/poster.png"
      src="./media/sayhi.mp4"
    >
      Video
    </video>
```

* 屬性大部分同audio

* poster：可以設定影片封面

  * source可以獨立寫在video標籤裡面

---
# iframe

* inline frame內嵌框架，嵌入如Youtube影片、Google地圖等

> 但一般如果不是用來嵌入外站的內容，還是盡量少用 iframe，因為 iframe 還是對網頁效能、維護性和 SEO 有非正面的影響。\
> \
> 出處：[fooish.com/html/iframe-tag.html](fooish.com/html/iframe-tag.html)
