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
## 選擇器
* 所有後代:`*`
* 後代選擇器: `nav a`
* 群組選擇器: `nav, a`
* 親代選擇器: ` ol > li` (只能在裡面一層)
* 相鄰兄弟: ` h1 + p`(後面的第一個)
* 一般兄弟: ` h1 ~ p`(後面的)
* 屬性選擇器: `a[href="https://twitter.com"]`
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




  * :``
  * :``
  * :``
  * :``


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

### overflow
```css
/* Keyword values */
overflow: visible;/* 可突出 */
overflow: hidden;
overflow: clip;/* 禁止所有滾動 */
overflow: scroll;
overflow: auto;
overflow: overlay;/* 不佔空間的auto */
overflow: hidden visible;
```
### display
```css


