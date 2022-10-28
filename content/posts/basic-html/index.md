---

title: "基本HTML語法整理"
date: 2022-10-28
description: "HTML語法整理! 3分鐘快速弄懂常用語法！"
categories: ["Web Design"]
dropCap: true
displayInMenu: false
displayInList: true
draft: false

---

先讓大家看一下一個基本的HTML文件格式為：
```html
<html>
  <head>
    <title>標題</title>
  </head>
  <body>
  網站內容
  </body>
</html>
```
 
你可以看到網頁就是由一堆標籤(所謂標籤就是指被<>包起來的語法)集合起來的，透過瀏覽器的消化整理，就是我們所看到的網頁了。簡單而言，通常一份完整的網頁包含了二個部份：抬頭(HEAD)、文件本體(BODY)。而打在`<TITLE></TITLE>`這裡面的文字會出現在瀏覽器視窗最上頭藍色部份，當作一篇網頁的主題。而最上方及下方的HTML標籤，是為了告訴瀏覽器說這是一份HTML，但這個標籤不是必須的，不過通常都包在網頁的最上下兩端，將所有的原始碼都包起來。

看過上述內容你已經瞭解了一個最基本的HTML檔案格式是什麼樣子，接下來為各位整理了HTML基本語法，讓各位在開發時能更快速查詢自己想要的語法。

Html語法整理：

|	屬性名稱	|	說明	|
|	 -------------------------------------- 	|	 -------------------------------------- 	|
| `	<! - -與 - ->	` |	註解	|
| `	<a href target>	` |	指定超連結的分割視窗	|
| `	<a href>	` |	指定超連結	|
| `	<b>	` |	粗體字	|
| `	<br />	` |	換行	|
| `	<caption align>	` |	設定表格標題位置	|
| `	<caption>...</caption>	` |	為表格加上標題	|
| `	<center>	` |	向中對齊	|
| `	<cite>...<cite>	` |	用於引經據典的文字	|
| `	<code>...</code>	` |	用於列出一段程式碼	|
| `	<comment>...</comment>	` |	加上註解	|
| `	<dd>	` |	設定定義列表的項目解說	|
| `	<dfn>...</dfn>	` |	顯示"定義"文字	|
| `	<dir>...</dir>	` |	列表文字標籤	|
| `	<dl>...</dl>	` |	設定定義列表的標籤	|
| `	<dt>	` |	設定定義列表的項目	|
| `	<em>	` |	強調之用	|
| `	<font face>	` |	任意指定所用的字形	|
| `	<font size>	` |	設定字體大小	|
| `	<form action>	` |	設定戶動式表單的處理方式	|
| `	<form method>	` |	設定戶動式表單之資料傳送方式	|
| `	<frame marginheight>	` |	設定視窗的上下邊界	|
| `	<frame marginwidth>	` |	設定視窗的左右邊界	|
| `	<frame name>	` |	為分割視窗命名	|
| `	<frame noresize>	` |	鎖住分割視窗的大小	|
| `	<frame scrolling>	` |	設定分割視窗的捲軸	|
| `	<frame src>	` |	將HTML檔加入視窗	|
| `	<frameset cols>	` |	將視窗分割成左右的子視窗	|
| `	<frameset rows>	` |	將視窗分割成上下的子視窗	|
| `	<frameset>...</frameset>	` |	劃分分割視窗(不能在body內)	|
| `	<h1>~<h6>	` |	設定文字大小(H1為最大)	|
| `	<hr>	` |	加上分格線	|
| `	<i>	` |	斜體字	|
| `	<img align>	` |	調整圖形影像的位置	|
| `	<img alt>	` |	為你的圖形影像加註	|
| `	<img dynsrc loop>	` |	加入影片	|
| `	<img height width>	` |	插入圖片並預設圖形大小	|
| `	<img hspace>	` |	插入圖片並預設圖形的左右邊界	|
| `	<img lowsrc>	` |	預載圖片功能	|
| `	<img src border>	` |	設定圖片邊界	|
| `	<img src>	` |	插入圖片	|
| `	<img vspace>	` |	插入圖片並預設圖形的上下邊界	|
| `	<input type name value>	` |	在表單中加入輸入欄位	|
| `	<isindex>	` |	定義查詢用表單	|
| `	<kbd>...</kbd>	` |	表示使用者輸入文字	|
| `	<li type>...</li>	` |	列表的項目 ( 可指定符號 )	|
| `	<marquee>	` |	跑馬燈效果	|
| `	<menu>...</menu>	` |	條列文字標籤	|
| `	<meta name="refresh" content url>	` |	自動更新文件內容	|
| `	<multiple>	` |	可同時選擇多項的列表欄	|
| `	<noframe>	` |	定義不出現分割視窗的文字	|
| `	<ol>...</ol>	` |	有序號的列表	|
| `	<option>	` |	定義表單中列表欄的項目	|
| `	<p align>	` |	設定對齊方向	|
| `	<p>	` |	分段	|
| `	<person>...</person>	` |	顯示人名	|
| `	<pre>	` |	使用原有排列	|
| `	<samp>...</samp>	` |	用於引用字	|
| `	<select>...</select>	` |	在表單中定義列表欄	|
| `	<small>	` |	顯示小字體	|
| `	<strike>	` |	文字加橫線	|
| `	<strong>	` |	用於加強語氣	|
| `	<sub>	` |	下標字	|
| `	<sup>	` |	上標字	|
| `	<table border=n>	` |	調整表格的寬線高度	|
| `	<table cellpadding>	` |	調整資料欄位之邊界	|
| `	<table cellspacing>	` |	調整表格線的寬度	|
| `	<table height>	` |	調整表格的高度	|
| `	<table width>	` |	調整表格的寬度	|
| `	<table>...</table>	` |	產生表格的標籤	|
| `	<td align>	` |	調整表格欄位之左右對齊	|
| `	<td bgcolor>	` |	設定表格欄位之背景顏色	|
| `	<td colspan rowspan>	` |	表格欄位的合併	|
| `	<td nowrap>	` |	設定表格欄位不換行	|
| `	<td valign>	` |	調整表格欄位之上下對齊	|
| `	<td width>	` |	調整表格欄位寬度	|
| `	<td>...</td>	` |	定義表格的資料欄位	|
| `	<textarea name rows cols>	` |	表單中加入多少列的文字輸入欄	|
| `	<textarea wrap>	` |	決定文字輸入欄是自動否換行	|
| `	<th>...</th>	` |	定義表格的標頭欄位	|
| `	<tr>...</tr>	` |	定義表格美一行	|
| `	<tt>	` |	打字機字體	|
| `	<u>	` |	文字加底線	|
| `	<ul type>...</ul>	` |	無序號的列表 ( 可指定符號 )	|
| `	<var>...</var>	` |	用於顯示變數	|
![image](https://user-images.githubusercontent.com/61068739/198489664-87b1a473-869f-4219-8728-1c3b25bfe121.png)
