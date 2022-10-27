---

title: "網頁設計課程大綱"
date: 2012-10-27
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

## 網頁原理

### 寄包裹

- **網路連線**
- **TCP/IP**：傳輸控制協定和網際網路協定（Transmission Control Protocol and Internet Protocol）車子、腳踏車
- **DNS**：網域名稱系統（Domain Name Servers）就像是網站的電話簿。當你在瀏覽器輸入網址時，瀏覽器會在取得網站前，先去看 DNS 以查到網站的真實地址。瀏覽器需要找到哪個伺服器在託管指定的網站、這樣才能把 HTTP 訊息傳送到對的地方（可以參考下文）。這就像你在去商店前會先翻開電話簿，才好去商店一般。
- **HTTP**超文本傳輸協定（Hypertext Transfer Protocol）是定義用戶端語言，和伺服器如何對話的應用[協議](https://developer.mozilla.org/zh-TW/docs/Glossary/Protocol)。可以想成你買東西時會用來溝通的語言。
- **Component files**：網站由許多不同的文件組成，如同商店內許多不同的商品。這些檔案分為以下類型：
  - **程式檔**：網站主要是由 HTML、CSS、JavaScript 建立，雖然你知會看到其他工具或技術。
  - **Asset**：這是構成網站其他內容的集體名稱，裡面可能包含圖像、音樂、影片、Word、PDF……之類的。

## [所以我說到底發生了啥？](https://developer.mozilla.org/zh-TW/docs/Learn/Getting_started_with_the_web/How_the_Web_works#%E6%89%80%E4%BB%A5%E6%88%91%E8%AA%AA%E5%88%B0%E5%BA%95%E7%99%BC%E7%94%9F%E4%BA%86%E5%95%A5%EF%BC%9F "Permalink to 所以我說到底發生了啥？")

當你在瀏覽器輸入網址時（你可以想像說自己要走去商店時）：

1. 瀏覽器會先去 DNS 伺服器尋找託管網站的伺服器，其真實位置所在（如同你去尋找商店的地址）
2. 瀏覽器向伺服器傳送 HTTP 訊息，請求伺服器向用戶端傳送網站的複本（如同去商店下訂單）。在用戶端及伺服器的之間，請求訊息與其他資訊，會使用 TCP/IP 在網路連線之間傳送。
3. 伺服器如果允許用戶端請求，伺服器就會傳送「200 OK」訊息，意味著「好，你可以閱覽這個網站，那我給你網站資料囉～」並開始對瀏覽器以一小串稱作「資料封包」的組合形式，傳送網站的檔案。這就像是商店給你商品，你接著把它們都帶回家一樣
4. 瀏覽器把一小塊一小塊的東西，組合成完整的網站，並把它呈現起來－－商品送到家門口後，閃亮亮的新貨在你眼前，超棒的啦！

## [講講 DNS](https://developer.mozilla.org/zh-TW/docs/Learn/Getting_started_with_the_web/How_the_Web_works#%E8%AC%9B%E8%AC%9B_dns "Permalink to 講講 DNS")

真正的網址，並不是在瀏覽器的網址列上，輸入好記好讀的字串，就能找到你最愛的網站。它們其實是一串特殊的數字，看起來就像是這樣：63.245.215.20

這叫做 [IP 地址](https://developer.mozilla.org/zh-TW/docs/Glossary/IP_Address)，網路上它擁有獨一無二的位置。不過，記數字果然不簡單吧？這就是要發明域名伺服器的原因。他們會把你在瀏覽器輸入的網址（例如 mozilla.org）和網站的真實位置（IP）相匹配

網站能直接透過其 IP 位置訪問之：在瀏覽器的網址列輸入 `63.245.215.20` 的話，可以走到 Mozilla 的網站。

## [再講講封包](https://developer.mozilla.org/zh-TW/docs/Learn/Getting_started_with_the_web/How_the_Web_works#%E5%86%8D%E8%AC%9B%E8%AC%9B%E5%B0%81%E5%8C%85 "Permalink to 再講講封包")

稍早我們用了「封包」來描述從伺服器傳到用戶端的資料格式。這裡的「封包」是什麼意思呢？通常資料在網路傳送時，會傳送上千個小資料，這樣在同一時間和同一網站，才能有很多用戶下載內容。如果網站只傳送一個大傢伙過去，那在同一時間就只能有一個用戶能下載，網路會變得很慢、很無聊...

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

### 認識Json

到這裡你就可以去一個月3 4萬找工作

## 後端

### 使用Google App Script串接Google Sheet

## 前端-串接