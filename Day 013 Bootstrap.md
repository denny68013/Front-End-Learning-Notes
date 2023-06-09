# 06\.07 Day 013 Bootstrap

### fixed-top

- .fixed-top：將元素固定在畫面最上方

### sticky-top

- .sticky-top：當捲動後碰到視窗上方的時候，會固定4在視窗上方

### float 與 clearfix

- .float-{start｜end｜none}：飄到左右或不飄

- .clearfix：如果元素後面有東西，記得加上.clearfix，才能清楚掉因為float導致的跑版

### nav 與 nav-link、nav-fill

- 設置導覽列樣式，通常搭配ul和li一起用

- .nav：導覽列的parent element需要放置

- .nav-item：導覽列各子元素樣式調整

- .nav-fill：在parent element上設定，可將子元素的空間平均分配

- .nav-pills：在parent element上設定，將子元素的樣式調整成pills-like

- 可以搭配.tab-conten、.tab-pane，透過href="#id“的選取方式，讓導覽列的元素顯示（需搭配data-bs-toggle=”pill”）

### navbar、carousel、form

- 按照官網的案例和class下去修改調整

### button

- .btn：套用按鈕樣式

   - .btn-{sm｜md｜lg}：這裡的sm、md、lg不是斷點是指按鈕大小

### popover

- 用bootstrap寫好的js語法與class下去調整

```html
<button
        class="btn btn-danger"
        title="cat"
        data-bs-toggle="popover"
        data-bs-content="dogggggg"
        data-bs-placement="bottom"
        data-bs-trigger="hover"
      >
        apple
      </button>
```

- 有以下屬性

   - data-bs-toggle=”popover”：不能調，屬於彈出框的屬性

   - title=””：跳出的訊息標題

   - data-bs-content=””：跳出的訊息

   - data-bs-placement="“：跳出的位置

   - data-bs-trigger="hover"：跳出提示框的方法，hover是只要滑鼠移動到button上面就會跳出，不用點

### collapse

- .collapse：用來隱藏一開始不想出現的元素，可以跟其他東西配合在滿足條件的時候跑出來

- 要注意button因為沒有超連結的導向（href）屬性，所以屬性要使用data-bs-target來指向要作用的元素

```html
<div class="collapse" id="demo">apple</div>

<!--按鈕開啓-->
<button class="btn btn-info text-white" 
        data-bs-toggle="collapse"
        data-bs-target="#demo">click
</button>

<!--超連結開啓-->
<a href="#demo" class="btn btn-info text-white" data-bs-toggle="collapse">click</a>
```

### modal

- 互動視窗，例如跳出來的通知登出訊息或購物車

- 參照官網範例下去修改，一開始沒出現，需要用.show .d-block把他弄出來

```html
 <button
        class="btn btn-info"
        data-bs-toggle="modal"
        data-bs-target="#demo"
      >
        登出
      </button>

      <div data-bs-backdrop="static" class="modal fade" tabindex="-1" id="demo">
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title">Modal title</h5>
              <button
                type="button"
                class="btn-close"
                data-bs-dismiss="modal"
                aria-label="Close"
              ></button>
            </div>
            <div class="modal-body">
              <p>Modal body text goes here.</p>
            </div>
            <div class="modal-footer">
              <button
                type="button"
                class="btn btn-secondary"
                data-bs-dismiss="modal"
              >
                Close
              </button>
              <button type="button" class="btn btn-primary">
                Save changes
              </button>
            </div>
          </div>
        </div>
      </div>
```

### card

- 用Bootstrap來做卡片樣式

```html
 <div class="card">
      <div class="card-header">one piece</div>
      <div class="card-body">
        <img src="../_image/sunny.jpg" class="img-fluid" />
        <h5 class="card-title">Sunny</h5>
        <p class="card-text">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Similique,
          enim amet ducimus placeat nihil voluptatibus deserunt cum! Quae,
          officia iure. In nesciunt nobis inventore provident quaerat molestiae
          pariatur rem ut.
        </p>
      </div>
      <div class="card-footer text-end">
        <a href="#" class="stretched-link btn btn-primary">點我看更多</a>
      </div>
    </div>
```

- .stretched-link：將連結的點擊範圍延伸到整張卡片

### progress bar

- 用Bootstrap的.progress和.progress-bar設定進度條

```html
     <div class="progress" style="height: 50px">
        <div
          class="progress-bar w-75 progress-bar-striped progress-bar-animated"
        ></div>
      </div>
```

### toast

- 用Bootstrap樣式出現吐司訊息（用來告知的通知框）

```html
      <button type="button" class="btn btn-primary" id="liveToastBtn">
        Show live toast
      </button>
      <div class="toast-container position-fixed bottom-0 end-0 p-3">
        <div id="liveToast" class="toast bg-warning">
          <div class="toast-header">
            <span class="me-auto">cat</span>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="toast"
            ></button>
          </div>

          <div class="toast-body">dog</div>
        </div>
      </div>

    <script>
      const toastTrigger = document.getElementById("liveToastBtn");
      const toastLiveExample = document.getElementById("liveToast");
      if (toastTrigger) {
        toastTrigger.addEventListener("click", () => {
          const toast = new bootstrap.Toast(toastLiveExample);

          toast.show();
        });
      }
    </script>
```
