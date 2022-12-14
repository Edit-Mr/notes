---

title: "HTML Form"
date: 2022-10-31
description: "HTML表單"
categories: ["Web Design"]
dropCap: true
displayInMenu: false
displayInList: true
draft: false
toc: true

---

HTML 表單 (form) 是用來讓使用者輸入資料，這些資料可以用來和使用者互動，例如表單內容填完後可以傳回遠端伺服器 (web server)，像常見的連絡表單。

## 一個完整的 HTML 表單範例
```
<form action="/formprocess.php" method="post">

    <p>Name:</p>
    <p><input type="text" name="name" value="你的名字"></p>

    <p>Email:</p>
    <p><input name="species" type="text"></p>

    <p>Comments: </p>
    <p><textarea name="comments" rows="5" cols="20">你的留言</textarea></p>

    <p>請問你最有興趣學習的技術:</p>
    <p><input type="radio" name="interest" value="html"> HTML</p>
    <p><input type="radio" name="interest" value="css"> CSS</p>
    <p><input type="radio" name="interest" value="js"> JavaScript</p>

    <p><input type="submit" value="送出資料"></p>

</form>
```
## input
### `<input>` 標籤的屬性 (attributes)
#### name: 欄位名稱
<input> 的 name 屬性用來指定送出去的該筆資料要用什麼名稱，目的是讓遠端伺服器才能透過明確定義好的名稱去取出對應的欄位值。

```html
<input name="myfield">
```
<input name="myfield">

可以想像當表單送出時，這個欄位會以類似 "myfield=輸入內容" 的形式傳給遠端伺服器。

#### value: 指定初始值 (default value)

```html
<input value="我的初始值">
```
<input value="我的初始值">

#### disabled: 將元件設定為禁用狀態
```html
<input disabled>
```
<input disabled>

#### readonly: 將元件設為唯獨不可更改內容的狀態

```html
<input value="點我看看可否編輯" readonly>
```
<input value="點我看看可否編輯" readonly>

#### autocomplete: 是否啟用瀏覽器自動完成功能

值有 on 和 off，預設是 on。
```html
<input autocomplete="off">
```
<input autocomplete="off">


#### autofocus: 當頁面載入後，自動聚焦在此欄位上

如果有設定 autofocus，當頁面載入後，瀏覽器會自動將畫面聚焦 (focus) 在該欄位上，但要注意，整個頁面所有的表單元件中只能有一個 autofocus 而已喔。
```html
<input autofocus>
```
<input autofocus>

#### required: 指定為必填欄位

當送出表單時，如果聲明為 required 的欄位內容沒有填寫，會被瀏覽器提醒必填。

```html
<input required>
```
<input required>

#### `<input>` 的 type 屬性: 建立不同類型的表單元件

```html
<input type="text">
```
<input type="text">

`<input>` 的 type 預設上就是 text，所以也可以省略不寫，沒 type 時其實就是 text：

輸入類型的 input 欄位還有這些屬性可以運用：

* maxlength: 指定最多能輸入多少字
* minlength: 指定最少需要輸入多少字
* size: 一個數字指定欄位顯示寬度 (characters wide)
* text input 的 placeholder 屬性: 輸入的提示訊息

```html
<input placeholder="請輸入帳號">
```

<input placeholder="請輸入帳號">

#### `<input type="password"> `
密碼輸入欄位

密碼文字輸入欄位和 text 的差別是，使用者輸入的內容不會被明碼顯示在螢幕畫面中。

#### `<input type="checkbox">` 核取方塊
核取方塊 (check box / tick box) 用來讓使用者勾選某個選項是否成立，可以再搭配 value 屬性 (預設值是 "on") 來指定當使用者勾選此方塊時要傳送給遠端伺服器什麼值。

```html
<input type="checkbox" name="subscribe" value="html-newsletter"> Subscribe to HTML newsletter?<br>
<input type="checkbox" name="subscribe" value="js-newsletter"> Subscribe to JavaScript newsletter?
```
<input type="checkbox" name="subscribe" value="html-newsletter"> Subscribe to HTML newsletter?<br>
<input type="checkbox" name="subscribe" value="js-newsletter"> Subscribe to JavaScript newsletter?


當使用者勾選時，就會隨著表單送出像是 "subscribe=newsletter" 的資料；相反的，如果 checkbox 沒有被勾選，就不會有任何資料被送出。

對於不同的 checkbox 你可以用一樣的 name 也可以用不一樣，一樣的話，會送出像是 "subscribe=html-newsletter&subscribe=js-newsletter" 格式的資料。

#### `<input type="radio">` 選項按鈕

radio (radio button) 是選項按鈕，用來處理表單中有多選一時的情況，搭配 value 屬性 (預設值是 "on") 來指定當使用者選取此選項時要傳送給遠端伺服器什麼值。

同一組 radio button 的選項，需要都是一樣的 name。

```html
請選擇你最喜歡的顏色：<br>
<input type="radio" name="color" value="red"> red<br>
<input type="radio" name="color" value="green"> green<br>
<input type="radio" name="color" value="blue"> blue

```
請選擇你最喜歡的顏色：<br>
<input type="radio" name="color" value="red"> red<br>
<input type="radio" name="color" value="green"> green<br>
<input type="radio" name="color" value="blue"> blue

checkbox 和 radio 的 checked 屬性: 預設勾選
checked 可以將該 checkbox / radio 的初始狀態設定為已選取。

```html
<input type="checkbox" checked> Subscribe to newsletter?
```

<input type="checkbox" checked> Subscribe to newsletter?

#### `<input type="submit">` 表單的送出按鈕 (submit button)

當使用者點了 submit button 就會送出表單給遠端的伺服器，用 value 屬性可以設定按鈕名稱。
```html
<input type="submit" value="Send Request">
```

<input type="submit" value="Send Request">

#### `<input type="reset">` 重設表單狀態
reset 用來讓使用者點了可以重設表單內容回到初始狀態，而 value 屬性可以設定 reset 按鈕的名稱。

```html
<input type="reset" value="Reset">
```

<input type="reset" value="Reset">

#### `<input type="hidden">` 隱藏資料欄位
hidden 是用來當你想傳送一些值回遠端 server，但你不想或不需要讓使用者看見這些內容。

```html
<input name="itemid" type="hidden" value="fwoxla">
```
<input name="itemid" type="hidden" value="fwoxla">

#### `<input type="image">` 圖片送出按鈕
送出按鈕除了可以用前面提到的文字按鈕，也可以是圖片按鈕。

圖片按鈕可以搭配這些屬性使用：

* src: 指定圖片位址
* alt: 指定當圖片下載失敗時的替代文字
* width: 指定圖片顯示寬度
* height: 指定圖片顯示高度

```html
<input type="image"
       src="https://em-tec.github.io/icons/EMprofile.png"
       alt="Login"
       width="100" height="100">
```
       
<input type="image"
       src="https://em-tec.github.io/icons/EMprofile.png"
       alt="Login"
       width="100" height="100">

圖片送出按鈕還有一個特性是當送出表單時，會同時送出座標點 (coordinates) (x, y) 的額外資訊，表示使用者點擊了圖片中的哪個位置，座標軸是以圖片的左上角為 (0, 0)。送出的資料格式會像是 "x=52&y=55"，如果你有設定 name 名稱，例如 name="position"，則送出去的資料格式會像是 "position.x=52&position.y=55"。


#### `<input type="file">` 檔案上傳 (file upload)

type="file" 用來讓使用者可以從本機端選擇檔案上傳。

搭配 accept 屬性可以限制允許上傳的檔案類型 (file type)，可以用逗點分隔開多種允許類型，accept 可以設定的值有：

.檔案類型: 例如 .jpg, .pdf, .doc
明確指定 MIME type: 例如 image/jpeg, image/png

* audio/*: 指任何聲音檔
* video/*: 指任何影片檔
* image/*: 指任何圖檔
舉個例子：
```html
<input type="file" accept="image/*,.pdf">
```

<input type="file" accept="image/*,.pdf">

搭配 multiple 屬性，一次可同時選多個檔案上傳：

```html
<input type="file" accept="image/*,.pdf" multiple>
```

<input type="file" accept="image/*,.pdf" multiple>

搭配 capture 屬性，可以用來開啟使用手機的照相機鏡頭：

```html
<input type="file" capture>
```

<input type="file" capture>

再搭配 accept 使用會有不同效果：

拍照上傳
```html
<input type="file" accept="image/*" capture>
```
<input type="file" accept="image/*" capture>

拍影片上傳

```html
<input type="file" accept="video/*" capture>
```
<input type="file" accept="video/*" capture>
用麥克風錄音上傳
```html
<input type="file" accept="audio/*" capture>
```
<input type="file" accept="audio/*" capture>
還可以指定要開啟手機的前鏡頭或後鏡頭，設定 capture 的屬性值：

* user: 指定要開啟前鏡頭
* environment: 指定要開啟後鏡頭
* front (user) - 前鏡頭
```html
<input type="file" accept="video/*" capture="user">
```
<input type="file" accept="video/*" capture="user">

* back (environment) - 後鏡頭

```html
<input type="file" accept="video/*" capture="environment">
```

<input type="file" accept="video/*" capture="environment">

#### `<input type="button">` 表單按鈕

button 通常用來搭配 JavaScript 來動態操作表單內容。
```html
<input type="button" value="Click Me">
```

<input type="button" value="Click Me">

#### `<input type="search">` 搜尋欄位
搜尋的文字輸入框，和 type="text" 主要的差異是欄位用途在語意上更明確，有些瀏覽器可能也會針對搜尋框顯示不同的樣式。

```html
<input type="search" name="q">
```

<input type="search" name="q">

#### `<input type="tel">` 電話號碼輸入欄位
type="tel" 和 type="text" 主要的差異是欄位用途在語意上更明確，且在特定的裝置像是手機上會顯示針對電話號碼輸入的界面。
```html
<input type="tel">
```

<input type="tel">

#### `<input type="url">` 網址輸入欄位

type="url" 和 type="text" 主要的差異是欄位用途在語意上更明確，且在送出表單之前，有支援的瀏覽器也會自動驗證 (validate) 使用者輸入的內容是不是合法的 URL。

```html
<input type="url">
```

<input type="url">

<input type="email"> 電子郵件輸入欄位
type="email" 和 type="text" 主要的差異是欄位用途在語意上更明確，且在送出表單之前，有支援的瀏覽器也會自動驗證 (validate) 使用者輸入的內容是不是合法的 email。
```html
<input type="email">
```

<input type="email">

multiple 屬性用來聲明此欄位可以用逗號 , 分開輸入多組 email：
```html
<input type="email" multiple>
```

<input type="email" multiple>

#### `<input type="date">` 日期輸入欄位
type="date" 用來建立一個日期輸入欄位，日期的格式為 yyyy-mm-dd。

可以再搭配這些屬性使用：

* max: 可以輸入的最晚日期
* min: 可以輸入的最早日期
* step: 設定一個數字，用來控制日期元件一次跳動的幅度；或在送出表單之前，瀏覽器會對日期欄位做驗證，日期需要符合 step 設定的跳動區間

例子：

```html
<input type="date"
       value="2020-04-20"
       min="2020-04-01"
       max="2022-04-30"
       step="5">
```
       
<input type="date"
       value="2020-04-20"
       min="2020-04-01"
       max="2022-04-30"
       step="5">
       
#### `<input type="time">` 時間輸入欄位
type="time" 用來建立一個時間輸入欄位，時間的格式為 24 小時制的 hh:mm。

可以再搭配這些屬性使用：

* max: 可以輸入的最晚時間
* min: 可以輸入的最早時間
* step: 設定一個數字，用來控制時間元件一次跳動的幅度；或在送出表單之前，瀏覽器會對時間欄位做驗證，時間需要符合 step 設定的跳動區間
例子：
```html
<input type="time"
       value="06:00"
       min="02:00"
       max="22:00"
       step="5">
       ```
       
<input type="time"
       value="06:00"
       min="02:00"
       max="22:00"
       step="5">
       
#### `<input type="number">` 數字輸入欄位
數字輸入欄位只允許輸入數字。

可以再搭配這些屬性使用：

* max: 可以輸入的最大值
* min: 可以輸入的最小值
* step: 設定一個數字，用來控制數字元件一次跳動的幅度；或在送出表單之前，瀏覽器會對欄位做驗證，數字需要符合 step 設定的跳動區間

```html
<input type="number"
       step="10"
       min="0"
       max="1000">
       ```
       
<input type="number"
       step="10"
       min="0"
       max="1000">
       
number 欄位在預設上，只能輸入整數，如果你想要能夠輸入小數點需要去調整 step 的屬性值，例如設定 step="0.1" 表示能輸入到小數點第一位；step="0.01" 表示能輸入到小數點第二位，依此類推；step="any" 則是用來表示可以輸入任何數字。

#### `<input type="range">` 數字範圍滑動選取欄位
type="range" 可以讓使用者用滑動的方式在一個數字區間內選擇出一個值，可以應用在對數字精準度要求不高的場景，像是調整音量大小。

可以再搭配這些屬性使用：

* max: 範圍中可選的最大值
* min: 範圍中可選的最小值
* step: 設定一個數字，用來控制元件數字一次跳動的幅度；或在送出表單之前，瀏覽器會對欄位做驗證，數字需要符合 step 設定的跳動區間
```html
<input type="range" min="-10" max="10">
```

<input type="range" min="-10" max="10">

#### `<input type="color">` 顏色選擇器 (color picker)
type="color" 用來讓使用者挑選顏色，顏色的格式為 #rrggbb。

```html
<input type="color" value="#ff0000">
```

<input type="color" value="#ff0000">

### 表單欄位驗證 (pattern validation) - pattern 屬性

text, date, search, url, tel, email 和 password 等輸入欄位可以利用 pattern 屬性搭配正規表達式 (regular expression) 來做表單欄位驗證。

語法：

```html
<input pattern="正規表達式">
```

範例：

```html
<input type="text" pattern="[a-z]{4,8}">

<input type="time" pattern="[0-9]{2}:[0-9]{2}">

<input type="email" pattern=".+@beststartupever.com">
```

<input type="text" pattern="[a-z]{4,8}">

<input type="time" pattern="[0-9]{2}:[0-9]{2}">

<input type="email" pattern=".+@beststartupever.com">

如果使用者輸入的內容不符合 pattern，在表單送出去之前就會被瀏覽器驗證錯誤而擋下。

## textarea

`<textarea>` 可以用來在表單 (form) 中，建立一個可以輸入多行文字的輸入框 (multi-line textbox)。

`<textarea>` 標籤上有這些屬性 (attributes)：

* name: 聲明欄位名稱
* rows: 一個數字，設定輸入框的高度是幾行文字 (lines)，預設是 2
* cols: 一個數字，設定輸入框的寬度是多少文字 (characters)，預設是 20
* maxlength: 一個數字，限定輸入的文字長度上限是幾個字
* minlength: 一個數字，限定輸入的文字長度最少是幾個字
* placeholder: 輸入欄位中的提示訊息
* disabled: 將欄位設定為禁用的狀態，是一個布林 (boolean) 屬性
* readonly: 將欄位設定為唯讀不可編輯的狀態，是一個布林 (boolean) 屬性
* required: 將欄位設定為必填，是一個布林 (boolean) 屬性
如果要在 textarea 中設定預設文字，不是像 `<input>` 一樣用 value 屬性喔，是直接將文字放在 `<textarea>`內容`</textarea>` 標籤之間，而內容文字的換行是使用一般的文字換行符號 `\n`，不是用 `<br>` 喔。

textarea 使用範例：

```html
<textarea name="mytext"
          rows="6"
          cols="40"
          required>
我是...
多行....
輸入框....
</textarea>
```
    
<textarea name="mytext"
          rows="6"
          cols="40"
          required>
我是...
多行....
輸入框....
</textarea>

## button
  
`<button>` 標籤 (tag) 是用來建立一個按鈕，而按鈕文字是放在 `<button></button>` 之間。

`<button>` 有下面這些屬性 (attributes)：

* name: 按鈕名稱
* type: 按鈕的形式，有三種選項：
* submit: 表單送出按鈕，預設值
* reset: 表單內容重置按鈕
* button: 沒任何特殊功能的一般按鈕，通常配合 JavaScript 使用
* value: 當 type="submit" 時，隨表單送出給遠端 server 的值
* disabled: 禁用此按鈕
使用範例：

```html
<button type="button">Push Me</button>
```

<button type="button">Push Me</button>