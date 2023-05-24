# 05\.23 Day3 HTML CSS

# 表單

```html
<form>
 <!--form elements-->
</form>
```

## form element

- &lt;form&gt;的屬性：

  - action：定義表單送出後傳給後端的動作

- form element 的屬性：

  - name：表單的定義名稱（手機名稱），每個表單需要唯一的 name

  - value：選項的值（型號），不一定跟使用者看到的 option 名稱一樣。

    - 所以選擇完後，送到後端的會是 name=value（手機是 XX 型號）
    - value預先給定一個值，就會在載入網頁時該欄位有預先設定的值。
    - <datalist>的<option>中的value屬性是指選項呈現出來的名稱

  - selected：可以預設表單要選擇的選項。

```html
<!--簡單的下拉式選單-->
    <label for="phone">選擇手機型號：</label>
    <select name="phone" id="phone">
      <option value="i13">iPhone13</option>
      <option value="i14">iPhone14</option>
      <option value="p6">Pixel 6</option>
      <option value="p7">Pixel 7</option>
    </select>
<br>
<!--下拉式分組選單-->
    <label for="phone2">選擇手機型號：</label>
    <select id="phone2">
      <optgroup label="Apple">
        <option>iPhone13</option>
        <option>iPhone14</option>
      </optgroup>
      <optgroup label="Google">
        <option>Pixel 6</option>
        <option>Pixel 7</option>
      </optgroup>
    </select>
<br>
<!--datalist 可建議輸入選單-->

    <label for="food">請輸入喜歡的食物</label>
    <input type="text" id="food" list="foodList" />
    <datalist id="foodList">
      <option value="小籠包"></option>
      <option value="白菜魯"></option>
      <option value="雞肉飯"></option>
    </datalist>
```

- &lt;select&gt;：

  - 用來表現可選擇的元素，底下用&lt;option&gt;來標示選項。

- &lt;option&gt;：表單的選項，可用&lt;optgroup&gt;做分組

  - 如果是配合&lt;datalist&gt;使用，不需要結束標籤，將要呈現的名稱放在 value 屬性裡面

- &lt;optgroup&gt;：&lt;option&gt;的分組，**可使用 label 屬性來選擇呈現分組名稱（屬性的 label≠ 標籤&lt;label&gt;）**

- &lt;label&gt;：表單標籤，**用 for 屬性對應表單的 id 值（id 值需為唯一）**，將表單的 caption 跟表單連結起來，用以解釋某個表單的形式與文字說明。

  - 可以點擊 label 標籤的文字就直接 autofocus 在表單上

- &lt;input&gt;：

  - &lt;datalist&gt;：用 input 的屬性 list 去跟 datalist 的 id 連結，才會呈現，底下選項用&lt;option&gt;（但要注意不用結束標籤，把名稱放在 value 裡面）

    - 使用時機：在有建議選項可以提供給使用者，但是還是開放式問答（指定答案還是使用&lt;select&gt;，比較合適）

  - input 的 type 屬性（輸入的種類）：

  - radio：圓圈單選

    - **需用 name 屬性來將不同的 input 分類到同一組**

    - 用來做單選，無法拿來多選

  - date：日期輸入／選擇

  - number：限定輸入數字

    - number 可以搭配的其他屬性

      - max、min：最大、最小值

      - step：每個數字的級距

      - value：給定一個預設值

  - text：文字輸入框

  - tel：電話輸入框

    - 雖然電腦上還是可以輸入其他非數字，但是在行動裝置上跳出來的鍵盤會是電話鍵盤

  - email：信箱輸入框（會驗證是否有@符號，以及@符號前後是否有文字）

    - 行動裝置上跳出來會是英文鍵盤

  - checkbox：多選框

    - 用 checked 屬性來預設選取

- &lt;fieldset&gt;：用來分組表單內的不同控制組合。

  - &lt;legend&gt;：用來呈現&lt;fieldset&gt;的說明

  &gt; legend 的意思：\
  &gt; \
  &gt; the words written on or next to a picture, map, coin, etc. that explain what it is about or what the symbols on it mean
  &gt;
  &gt; 來源：&lt;https://dictionary.cambridge.org/dictionary/english/legend&gt;

-
