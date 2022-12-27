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

這裡會複習一些CSS重要或容易忘記的語法，不太適合因手閱讀。

## 假圖產生
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
* *https://picsum.photos/
```
https://picsum.photos/200/300
```


## 選擇器

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
+
```css
p::before {
  content: "哈囉";
  color: red;
}
```
=<span style=color:red>哈囉</span>大家好
### 權重
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
* px:相對顯示器的解析度
* em:相對父元素的m寬度(預設16px)
* rem:相對根元素的m寬度(預設16px)
* vw/vh: viewport（視口）寬/長度
* %
  * width跟height的%基準是父層
  * line-height以本身文字行高為基準
## 裝飾文字

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
/* Keyword values */
font-weight: normal;
font-weight: bold;

/* Keyword values relative to the parent */
font-weight: lighter;
font-weight: bolder;

/* Numeric keyword values */
font-weight: 100;
font-weight: 400; /* normal */
font-weight: 700; /* bold */
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