---

title: "CSS複習"
date: 2022-12-19
description: "CSS複習一些重要或容易忘記的語法"
categories: ["Web Design"]
dropCap: true
displayInMenu: false
displayInList: true
draft: false
toc: true

---

> 這是我自主學習計畫整理的一些CSS重要或容易忘記的語法。如果你對科技有興趣歡迎在[Instagram](https://www.instagram.com/em.tec.blog/)和[Google新聞](https://news.google.com/publications/CAAqBwgKMKXLvgswsubVAw)追蹤我的部落格:[毛哥EM資訊密技](https://em-tec.github.io/)
> 
> 當然也歡迎追蹤[我的Instagram](https://www.instagram.com/elvisdragonmao/)


## 假圖產生

我們在練習排版時通常會想要隨便放點圖和文字來方便操控。文字大家習慣使用這一段沒有意義的文字:

> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptas, similique eos? Voluptates corrupti est autem ducimus eaque. Voluptates asperiores debitis libero, dolore quis eaque voluptate tempore. Cum natus fugit expedita.

而圖片則會使用這種網站:

* https://fakeimg.pl/

```html
<img src="https://fakeimg.pl/300/">
<img src="https://fakeimg.pl/250x100/">
<img src="https://fakeimg.pl/250x100/ff0000/">
<img src="https://fakeimg.pl/350x200/ff0000/000">
<img src="https://fakeimg.pl/350x200/ff0000,128/000,255">
<img src="https://fakeimg.pl/350x200/?text=Hello">
<img src="https://fakeimg.pl/200x100/?retina=1&text=こんにちは&font=noto">
<img src="https://fakeimg.pl/350x200/?text=World&font=lobster">
```
* https://picsum.photos/
```
https://picsum.photos/200/300
```


## 選擇器

CSS可以用來控制元素，但要先用選擇器來選擇要誰控制

> 後代是指裡面的東西。如超連結在文章裡面，超連結就是文章的後代，

* 所有後代:`*`
* 後代選擇器: `nav a`
* 群組選擇器: `nav, a`
* 親代選擇器: ` ol > li` (只能在裡面一層)
* 相鄰兄弟: ` h1 + p`(後面的第一個)
* 一般兄弟: ` h1 ~ p`(後面的)
* 屬性選擇器: `a[href="https://twitter.com"]`
  * 屬性某個地方: `a[href*="tuts"]` (nettuts.com、net.tutsplus.com、tutsplus.com)
  * 屬性開頭: `a[href^="http"]`
  * 屬性結尾: `[href$=".jpg"]`

### 偽類 Pseuedo-classes

偽類之所以叫作偽，簡單來說它的選擇器所選的不是真正存在的類別（class屬性值），它的選擇符為：冒號，它可以用來幫元素的“狀態”套樣式，或是用順序來指定元素等，通常在基本選擇器或是組合方式的選擇器無法選到、或選擇起來不夠方便時，就會用到偽類。很多時候使用偽類，可以省下幫很多元素做class的命名。

  * 未被訪問: `:link`
  * 已被訪問:`:visited`
  * 懸浮:`:hover`
  * 按下去/右鍵:`:active`
  * 被鍵盤輸入鎖定:`:focus`
  * 根元素偽類:`:root`(權重比較高)
  * 兄弟結構偽類:`:nth-child()`
    * 第一個:`nth-child(1)`
    * 奇數個:`nth-child(even)`
    * 偶數個:`:nth-child(odd)`
  * 用算式:`:nth=child(an+b)`(如每三列第一則:`:nth-child(3n+1)`)

### Pseudo-elements 偽元素

偽元素跟偽類的差異在於，偽類是基於真實存在的元素去選取不存在的class ; 而偽類則是基於存在的元素，創出一個虛擬的元素。它的選擇符是`::`雙冒號。

```html
<p>大家好</p>
```

```css
p::before {
  content: "哈囉";
  color: red;
}
```

<span style=color:red>哈囉</span>大家好

### 權重

> 你女朋友說你很醜，早餐店阿姨說你是帥哥，你就是很醜，因為女朋友權重比較重。

從上比下來。這裡有一個[計算機](https://specificity.keegan.st/)
* `!important`
* ID 選擇器
* 類別選擇器、屬性選擇器、偽類選擇器(如:`root`)
* 元素選擇器、偽元素選擇器
* 任何元素選擇符`*`沒有權級

權重如果相等，後寫的樣式宣告會蓋過先前的樣式宣告

## 單位

### 顏色

RGB 是以「直視光」的方式理解色域，可以說是光本身，與光的混合來理解顏色。

HSL 是以「反射光」的方式理解色域，可以說是物體本身的顏色與環境光的結果，來理解顏色。

### 大小

* `px`:相對顯示器的解析度
* `em`:相對父元素的m寬度(預設16px)
* `rem`:相對根元素的m寬度(預設16px)
* `vw`/`vh`: viewport（視口）寬/長度
* `%`
  * width跟height的`%`基準是父層
  * line-height以本身文字行高為基準

## 裝飾文字

語法直接全上!

<p style="color:rgb(252, 3, 3, 0.8);
  font-size:1em;
  letter-spacing: 10px;
  line-height: 20px;
  font-weight: 500;
  text-decoration:underline;
  font-style:italic;
  Opacity:0.5;
  text-align:left;
  font-family:arial, sans-serif;">毛哥EM Elvis Dragon Mao</p>

```css
color:rgb(252, 3, 3, 0.8);
  font-size:1em;
  letter-spacing: 10px;
  line-height: 20px;
  font-weight: 500;
  text-decoration:underline;
  font-style:italic;
  opacity: 0.5;
  text-align:left;
  font-family:arial, sans-serif;
  ```

### font-weight

```css
/* 關鍵字 */
font-weight: normal;
font-weight: bold;

/* 比較級關鍵字 */
font-weight: lighter;
font-weight: bolder;

/* 絕對的數值 */
font-weight: 100;
font-weight: 400; /* 正常 */
font-weight: 700; /* 粗 */
font-weight: 900;
```
### text-decoration

```css
text-decoration: underline;
text-decoration: overline red;
text-decoration: none;
text-decoration-color: #ff00ff;
```

## background

### background-image

```css
background-image: url(./image/cloud.png);
background-repeat: no-repeat;
background-size: cover; /* 寬填滿 */
background-size: contain; /* 高填滿 */
height: 300px;

background-position: top left;
background-position: 20% 40%; /* 從左上開始算 */

background-attachment: scroll; /* 不動但可以往下滾 */
background-attachment: fixed; /* 卡住不動 */
background-attachment: local; /* 一起動 */
```

### 漸層

漸層的邏輯可以參考我的[網頁漸層指引](https://www.instagram.com/p/Cn99VUIvbLf/)(然後你可以順便按讚追蹤)

<blockquote class="instagram-media" data-instgrm-captioned data-instgrm-permalink="https://www.instagram.com/p/Cn99VUIvbLf/?utm_source=ig_embed&amp;utm_campaign=loading" data-instgrm-version="14" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:540px; min-width:326px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:16px;"> <a href="https://www.instagram.com/p/Cn99VUIvbLf/?utm_source=ig_embed&amp;utm_campaign=loading" style=" background:#FFFFFF; line-height:0; padding:0 0; text-align:center; text-decoration:none; width:100%;" target="_blank"> <div style=" display: flex; flex-direction: row; align-items: center;"> <div style="background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 40px; margin-right: 14px; width: 40px;"></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 100px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 60px;"></div></div></div><div style="padding: 19% 0;"></div> <div style="display:block; height:50px; margin:0 auto 12px; width:50px;"><svg width="50px" height="50px" viewBox="0 0 60 60" version="1.1" xmlns="https://www.w3.org/2000/svg" xmlns:xlink="https://www.w3.org/1999/xlink"><g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"><g transform="translate(-511.000000, -20.000000)" fill="#000000"><g><path d="M556.869,30.41 C554.814,30.41 553.148,32.076 553.148,34.131 C553.148,36.186 554.814,37.852 556.869,37.852 C558.924,37.852 560.59,36.186 560.59,34.131 C560.59,32.076 558.924,30.41 556.869,30.41 M541,60.657 C535.114,60.657 530.342,55.887 530.342,50 C530.342,44.114 535.114,39.342 541,39.342 C546.887,39.342 551.658,44.114 551.658,50 C551.658,55.887 546.887,60.657 541,60.657 M541,33.886 C532.1,33.886 524.886,41.1 524.886,50 C524.886,58.899 532.1,66.113 541,66.113 C549.9,66.113 557.115,58.899 557.115,50 C557.115,41.1 549.9,33.886 541,33.886 M565.378,62.101 C565.244,65.022 564.756,66.606 564.346,67.663 C563.803,69.06 563.154,70.057 562.106,71.106 C561.058,72.155 560.06,72.803 558.662,73.347 C557.607,73.757 556.021,74.244 553.102,74.378 C549.944,74.521 548.997,74.552 541,74.552 C533.003,74.552 532.056,74.521 528.898,74.378 C525.979,74.244 524.393,73.757 523.338,73.347 C521.94,72.803 520.942,72.155 519.894,71.106 C518.846,70.057 518.197,69.06 517.654,67.663 C517.244,66.606 516.755,65.022 516.623,62.101 C516.479,58.943 516.448,57.996 516.448,50 C516.448,42.003 516.479,41.056 516.623,37.899 C516.755,34.978 517.244,33.391 517.654,32.338 C518.197,30.938 518.846,29.942 519.894,28.894 C520.942,27.846 521.94,27.196 523.338,26.654 C524.393,26.244 525.979,25.756 528.898,25.623 C532.057,25.479 533.004,25.448 541,25.448 C548.997,25.448 549.943,25.479 553.102,25.623 C556.021,25.756 557.607,26.244 558.662,26.654 C560.06,27.196 561.058,27.846 562.106,28.894 C563.154,29.942 563.803,30.938 564.346,32.338 C564.756,33.391 565.244,34.978 565.378,37.899 C565.522,41.056 565.552,42.003 565.552,50 C565.552,57.996 565.522,58.943 565.378,62.101 M570.82,37.631 C570.674,34.438 570.167,32.258 569.425,30.349 C568.659,28.377 567.633,26.702 565.965,25.035 C564.297,23.368 562.623,22.342 560.652,21.575 C558.743,20.834 556.562,20.326 553.369,20.18 C550.169,20.033 549.148,20 541,20 C532.853,20 531.831,20.033 528.631,20.18 C525.438,20.326 523.257,20.834 521.349,21.575 C519.376,22.342 517.703,23.368 516.035,25.035 C514.368,26.702 513.342,28.377 512.574,30.349 C511.834,32.258 511.326,34.438 511.181,37.631 C511.035,40.831 511,41.851 511,50 C511,58.147 511.035,59.17 511.181,62.369 C511.326,65.562 511.834,67.743 512.574,69.651 C513.342,71.625 514.368,73.296 516.035,74.965 C517.703,76.634 519.376,77.658 521.349,78.425 C523.257,79.167 525.438,79.673 528.631,79.82 C531.831,79.965 532.853,80.001 541,80.001 C549.148,80.001 550.169,79.965 553.369,79.82 C556.562,79.673 558.743,79.167 560.652,78.425 C562.623,77.658 564.297,76.634 565.965,74.965 C567.633,73.296 568.659,71.625 569.425,69.651 C570.167,67.743 570.674,65.562 570.82,62.369 C570.966,59.17 571,58.147 571,50 C571,41.851 570.966,40.831 570.82,37.631"></path></g></g></g></svg></div><div style="padding-top: 8px;"> <div style=" color:#3897f0; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:550; line-height:18px;">在 Instagram 查看這則貼文</div></div><div style="padding: 12.5% 0;"></div> <div style="display: flex; flex-direction: row; margin-bottom: 14px; align-items: center;"><div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(0px) translateY(7px);"></div> <div style="background-color: #F4F4F4; height: 12.5px; transform: rotate(-45deg) translateX(3px) translateY(1px); width: 12.5px; flex-grow: 0; margin-right: 14px; margin-left: 2px;"></div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(9px) translateY(-18px);"></div></div><div style="margin-left: 8px;"> <div style=" background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 20px; width: 20px;"></div> <div style=" width: 0; height: 0; border-top: 2px solid transparent; border-left: 6px solid #f4f4f4; border-bottom: 2px solid transparent; transform: translateX(16px) translateY(-4px) rotate(30deg)"></div></div><div style="margin-left: auto;"> <div style=" width: 0px; border-top: 8px solid #F4F4F4; border-right: 8px solid transparent; transform: translateY(16px);"></div> <div style=" background-color: #F4F4F4; flex-grow: 0; height: 12px; width: 16px; transform: translateY(-4px);"></div> <div style=" width: 0; height: 0; border-top: 8px solid #F4F4F4; border-left: 8px solid transparent; transform: translateY(-4px) translateX(8px);"></div></div></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center; margin-bottom: 24px;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 224px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 144px;"></div></div></a><p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;"><a href="https://www.instagram.com/p/Cn99VUIvbLf/?utm_source=ig_embed&amp;utm_campaign=loading" style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none;" target="_blank">毛哥EM資訊密技（@em.tec.blog）分享的貼文</a></p></div></blockquote> <script async src="//www.instagram.com/embed.js"></script>

```css
background: linear-gradius(degree, color);
background: linear-gradient(#e66465, #9198e5);
background: linear-gradient(0.25turn, #3f87a6, #ebf8e1, #f69d3c);
background: linear-gradient(to left, #333, #333 50%, #eee 75%, #333 75%);
background: linear-gradient(217deg, rgba(255,0,0,.8), rgba(255,0,0,0) 70.71%),
            linear-gradient(127deg, rgba(0,255,0,.8), rgba(0,255,0,0) 70.71%),
            linear-gradient(336deg, rgba(0,0,255,.8), rgba(0,0,255,0) 70.71%);
```
<img src=https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient/linear-gradient.png style="width:300px;display:inline;" />
<img src=https://i.imgur.com/XUupJaf.png style="width:300px;display:inline;" />

## border

```css
border-style: solid; /* 花邊很醜 相信我 */
border-width: 10px;
border-color: #00ff00;
border: solid 10px hsl(0 ,100%, 100%);
```
### border-radius
```css
border-radius: 四個角;
border-radius: 左上角與右下角 右上角與左下角;
border-radius: 左上角 右上角 右下角 左下角;
border-top-left-radius: BJ4;
```
### outline

outline位置在border的外緣，但不佔用元素的任何空間。  
outline不能夠聲明單邊樣式，它一定是圍繞呈現的。  
outline的形狀可以不規則，它會順著border邊緣顯示，不一定得是矩形。可是目前大多數的瀏覽器不支援該特性。實際上驗證之下會發現outline並不會去適應border-radius的圓弧
```css
outline-style | outline-width | outline-color | outline-offset
```
## Box-sizing
```
box-sizing:content-box;  // 把寬度範圍指定給內容物的空間
box-sizing:border-box;  // 把寬度範圍指定給邊框到邊框之間的空間
```
所以在 block 元素中只要設定 box-sizing:border-box; 就不用另外再計算padding、border 的寬度造成 width 賦予的值不直覺。
假設 width:300px, padding 就算加了 20px, border 加了4px，寬度依舊是300px。
### box
![box](https://i.imgur.com/vxm8vFhm.png)
## display

CSS的Display屬性可以改變元素對外所參與的佈局環境（outer display type），例如：

- `inline`: 參與IFC
- `block`: 佔滿`<body>`作為block container的寬度
- `contents`: 只有contents area的box，只顯示內容文字。
- `inline-block`: 對外參與IFC佈局，對內創建了BFC佈局
- `display: none` Bang不見

* block 是有面積的，可以設定寬跟高
* inline 設定寬高無效，可以設定 padding 的左右值，上下值無效，無法被撐開。
* inline-block 同時擁有兩種 display 的特性，可以設定寬高，但也可以與其他元素並排

> 如果使用 inline-block(像是 a 或 li 設定)，標籤之間會有空白字元約 4~5px

也可以為元素創造內部的佈局環境，提供後代元素佈局的規則（inner display type）。對內創造的佈局例如：

- `flow layout`  
  block container的佈局環境，等於normal flow佈局：IFC水平佈局+BFC垂直佈局。
- `flow root`  
  創建一個新的BFC時，其內部的佈局叫做`flow root`，一個新的`normal flow`佈局。
- `flex`  
  彈性盒佈局，該屬性值的元素本身對外仍參與normal flow，可是內部環境為獨立的flex formatting context。
- `grid`  
  格線佈局，該屬性值的元素本身對外仍參與normal flow，可是內部環境為獨立的彈性盒佈局grid formatting context。

## float
### 用法
#### none
![](https://i.imgur.com/wHErd2k.png)
#### left
![](https://i.imgur.com/Yz6bJ16.png)
### 問題
### float collapse
![](https://i.imgur.com/Zdntd5z.png)
解決方法很多，列幾個
* 元素的float參數不為none
* 元素的position參數為absolute或fixed
* 元素的display為inline-block
* overflow參數不為visible的block元素
* display參數為flow-root的元素
### Clear
```css
clear: left|right|both;
```
會讓左/右不會重疊到
```html
<div></div><div></div><div></div>
```
![](https://i.imgur.com/KJsAt0K.png)
![](https://i.imgur.com/In4DqWf.png)

## Position
讓我最頭痛的。功能是設定**物件定位時所要的參考對像**
```css 
position:static | relative | absolute | fixed | sticky;
top | right | bottom | left: 10px;
```
### static 原始定位
inline往右，block往下
### reletive 相對定位
我原本該在哪裡位置就佔著，但我看起來要往右/下...。
![](https://i.imgur.com/H1Vru7P.png)

### absolute 絕對定位
貼到最近的reletive祖先元素。口決:父相子絕
### fixed
貼著視窗，卡在那裡，原本位置不再佔據
# sticky
以自己為基準，卡在那裡，但sticky元素仍然in flow，元素佔位會保留
![](https://media.giphy.com/media/LRs2BIsDx1WjzSdIAJ/giphy.gif)
## Transform: translate
```css
transform: translate(單位或百分比, 單位或百分比);
transform: translateX(單位或百分比);
transform: translateY(單位或百分比);
```
單位值為多少就平移多少，然後transform支援負值
```css
.translate {
  background-color: pink;
  transform: translate(100px, -50px);
}
```
![](https://i.imgur.com/IFdDGiC.png)

translate的百分比基準是自己的width跟height
![](https://i.imgur.com/jM1Hazt.png)
來一個推方塊範例
```css
.outer  {
  position: relative;
}

img {
  position: absolute;
  top:50%;
  left: 50%;
}
```
![](https://i.imgur.com/Gswm945.png)

再來往左上推: `transform: translate(-50%, -50%);`

![](https://i.imgur.com/YeDUST3.png)
## transition 轉場
``` css
transition: 屬性 轉換時間 延遲執行動畫的時間 速度;

transition:all .3s 0s ease;// 設定全部 0.3秒轉換 沒有延遲 ease為預設值
transition: padding .3s 0s, background-color 1s 1s; // 可以各別設定，用逗號分開，並用延遲時間設定出現的先後順序
// ** 任何標籤都可以設定hover e.g. 文字段落滑過要變色
```
## overflow
```css
/* Keyword values */
overflow: visible; /* 可突出 */
overflow: hidden;
overflow: clip; /* 禁止所有滾動 */
overflow: scroll;
overflow: auto;
overflow: overlay; /* 不佔空間的auto */
overflow: hidden visible;
```
## Media
```css
@media screen and (條件) and (條件)...{ // 判斷式，用在screen螢幕的媒體
}

// 舉例
@media screen and (min-width: 768px){ // why 設定768px?  i pad 的解析度1024*768
    // 表768px以上的尺寸 樣式如何呈現(桌機)
}
```
```html
// head 裡要加上 "設定裝置縮放的模式"
//     視窗大小/解析度  視窗內容:寬度 = 裝置寬度 
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
##   圖片不放背景也可以占滿寬的寫法

```html
<div style="width: 400px;height: 400px;border: blue solid;">
    <img style="width: 100%;height: 100%;object-fit: cover;"src="https://picsum.photos/500/300/?random=1">
</div>
```

<div style="width: 400px;height: 400px;border: blue solid;">
    <img style="width: 100%;height: 100%;object-fit: cover;"src="https://picsum.photos/500/300/?random=1">
</div>

## label for

加了for屬性，點到 label上的文字，input也會打勾

```html
<input type="checkbox" name="" id="aa">
<label for="aa">勾選a</label>
<input type="checkbox" name="" id="bb">
<label for="bb">勾選b</label>
```

<!-- 加了for屬性，點到 label上的文字，input也會打勾 -->
<input type="checkbox" name="" id="aa">
<label for="aa">勾選a</label>
<input type="checkbox" name="" id="bb">
<label for="bb">勾選b</label>



差不就這樣啦!


> 參考資料:MSN，[從門外漢到前端新手](https://ithelp.ithome.com.tw/users/20120683/ironman/2609?page=3)，