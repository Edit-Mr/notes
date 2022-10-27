---

title: "網頁設計課程大綱"
date: 2022-10-27
description: "網頁設計課程大綱"
categories: ["Coding"]
dropCap: true
displayInMenu: false
displayInList: true
draft: false
resources:

- name: featuredImage
  src: "mdd-iphone.jpg"
  params:
    description: "An iphone with a website featuring the aether theme"

---

要我講網頁設計大概就是講這些

看不懂沒關係，聽我講就懂了

## 網頁原理


### 寄包裹

- **網路連線**
- **TCP/IP**（傳輸控制協定和網際網路協定 Transmission Control Protocol and Internet Protocol）：車子、腳踏車
- **DNS**：電話簿
- **HTTP**超文本傳輸協定（Hypertext Transfer Protocol）：交通規則
- **Component files**：網站由許多不同的文件組成
  - **程式檔**：HTML、CSS、JavaScript...
  - **Asset**：附件

#### 所以我說到底發生了啥？

當你在瀏覽器輸入網址時（你可以想像說自己要走去商店時）：

1. 瀏覽器會先去 DNS 伺服器尋找託管網站的伺服器，其真實位置所在（如同你去尋找商店的地址）
2. 瀏覽器向伺服器傳送 HTTP 訊息，請求伺服器向用戶端傳送網站的複本（如同去商店下訂單）。在用戶端及伺服器的之間，請求訊息與其他資訊，會使用 TCP/IP 在網路連線之間傳送。
3. 伺服器如果允許用戶端請求，伺服器就會傳送「200 OK」訊息，意味著「好，你可以閱覽這個網站，那我給你網站資料囉～」並開始對瀏覽器以一小串稱作「資料封包」的組合形式，傳送網站的檔案。這就像是商店給你商品，你接著把它們都帶回家一樣
4. 瀏覽器把一小塊一小塊的東西，組合成完整的網站，並把它呈現起來－－商品送到家門口後，閃亮亮的新貨在你眼前，超棒的啦！

### 前後端

## 前端

### 註冊Github 下載VSCode

Github可以說是程式的雲端硬碟或IG。註冊帳號就可以上傳檔案，可以自己決定要不要讓別人看到。當然也可以留言、按讚（星星）、或轉發改編。 上傳檔案除了可以像社群一樣用網頁版直接傳之外，因為通常一個專案裡面會有很多資料夾和檔案，所以通常會用一個叫做git的技術來實現同步檔案。

Visual Studio Code是一款由微軟開發且跨平台的免費原始碼編輯器。該軟體支援語法突顯、程式碼自動補全、程式碼重構功能，並且內建了命令列工具和 Git 版本控制系統。使用者可以更改佈景主題和鍵盤捷徑實現個人化設定，也可以透過內建的擴充元件程式商店安裝擴充元件以加強軟體功能。

### HTML語法

讓網站不只是純文字，有標題、表格、超連結等

### CSS語法

改變顏色、排版

到這裡就可以建立一個好看的網站了

### 認識Markdown

讓寫筆記/文章更快速方便

Markdown的語法有個主要的目的：用來作為一種網路內容的*寫作*用語言。

Markdown不是要來取代HTML，甚至也沒有要和它相似，它的語法種類不多，只和HTML的一部分有關係，重點*不是*要創造一種更容易寫作HTML文件的語法，我認為HTML已經很容易寫了，Markdow的重點在於，它能讓文件更容易閱讀、編寫。HTML 是一種*發佈*的格式，Markdown是一種*編寫*的格式，因此，Markdown的格式語法只涵蓋純文字可以涵蓋的範圍。

### 基本Git

你也可以想像Github是物流中心，而git就是物流。我們透過物流來傳資料到Github的倉庫合獲取檔案。git厲害的地方是每次上傳或下載時它會比較差異，只傳送不同的檔案。除了節省時間流量之外，因為記錄了每一次的更動，所以可以進行版本控制。包括釋出不同版本，和復原到指定版本。

### JavaScript

跟網站互動起來

### 認識Json

一種很讚的物件儲存格式

到這裡你就可以去一個月3 4萬找工作

## 後端

### 使用Google App Script串接Google Sheet

使用`doGet` `doPost`和`spreadsheet`功能做一個api

## 前端-串接

讓網站能用你的api

## 連上Line

通知，群發消息，收回覆

### Line Notify

### Line Bot

#### 對話-Message API

##### Flex Message

### Line Liff

#### 建立Liff網站

大概就醬