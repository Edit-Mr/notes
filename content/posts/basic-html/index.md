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

HTML叫做超文本標記語言(Hyper Text Markup Language)。故名思義就是標記一下文字，目的是讓**瀏覽器知道這個是什麼**。比如說Google想知道網站標題會去找裡面的`<h1>`；而給盲人用的語音閱讀器在看到`<stronge>`會加重語氣。主要功能不是為了裝飾文字喔，裝飾文字是CSS的工作（下禮拜就來講）

我們今天在桌面建立了一個html文件並用瀏覽器打開。可以看看這篇文章認識更多html標籤

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
 
看過上述內容你已經瞭解了一個最基本的HTML檔案格式是什麼樣子，接下來這裡整理了HTML基本語法，讓各位在開發時能更快速查詢自己想要的語法。你可以建立一個html檔並直接全選貼上。查看實際效果

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <title>標題</title>
    <meta name="description" content="網頁描述">
    <meta name="keywords" content="關鍵字">
    <meta name="author" content="作者">
    <!-- 下面兩個是網頁縮圖 -->
    <link rel="apple-touch-icon" sizes="180x180" href="https://EM-Tec.github.io/icons/apple-touch-icon.png">
    <link rel="icon" type="image/png" sizes="32x32" href="https://EM-Tec.github.io/icons/favicon-32x32.png">
</head>

<body>
    <!-- 註解，瀏覽器不會管這一段文字 -->

    <h1>一級標題</h1>
    <h2>二級標題</h2>
    <h3>三級標題</h3>
    <h4>四級標題</h4>
    <h5>五級標題</h5>
    <h6>六級標題</h6>

    <p>這是一段說長不長說短不短的一個文章段落</p>

    <a href="">超連結</a>
    <a href="" target="_blank">新視窗超連結</a>
    <b>粗體字</b> <s>槓掉</s> <i>斜體字</i> <u>底線</u>
    換行<br />

    插入分格線
    <hr />

    底下我每個元素都會換行方便閱讀<br />
  <br />
    以上幾個對盲人很有幫助，不過每個瀏覽器對他們的處理方式不太相同。有的瀏覽器用斜體，有的用粗體。比較少用<br />
  
    <em>強調</em><br />
    <cite>用於引經據典的文字</cite><br />
    <code>用於列出一段程式碼</code><br />
    <comment>...</comment> 加上註解<br />
    <dfn>顯示"定義"文字</dfn><br />
    <person>顯示人名</person><br />
    <pre>使用原有排列</pre><br />
    <samp>...</samp> 用於引用字<br />
    <strong> 用於加強語氣</strong><br />
  
  以上幾個對盲人很有幫助，不過每個瀏覽器對他們的處理方式不太相同。比較少用<br />
  
    H<sub>2</sub>O
    2<sup>10</sup>

    <ul>
        <li>無序號的列表</li>
        <li>無序號的列表</li>
        <li>無序號的列表</li>
    </ul>

    <ol>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
    </ol>

    <!-- 交叉排序 -->
    <dl>
        <dt>項目一</dt>
        <dd>描述一有很多內容說明</dd>
        <dt>項目二</dt>
        <dd>描述二有很多內容說明</dd>
    </dl>
    <!-- 多個項目+單一描述 -->
    <dl>
        <dt>項目一</dt>
        <dt>項目二</dt>
        <dd>只有一個描述也可以哦</dd>
    </dl>
    <!-- 單一項目+多個描述 -->
    <dl>
        <dt>項目一</dt>
        <dd>很多個描述也可以哦</dd>
        <dd>很多個描述也可以哦</dd>
    </dl>

    <img src="圖片網址" alt="圖片敘述 沒載入成功顯示文字 閱讀器會唸給盲人" />
    <br />
    輸入欄位很多種，之後慢慢講
    <input value="我的初始值">
    <br />
    <marquee>跑馬燈效果</marquee>
    <menu>條列文字標籤</menu>
    <meta name="refresh" content url> 自動更新文件內容

    <select>
        <option>請選擇你最愛的寵物</option>
        <option>Dog</option>
        <option>Cat</option>
        <option>Hamster</option>
        <option>Parrot</option>
        <option>Spider</option>
        <option>Goldfish</option>
    </select>
    <br />

    <textarea>輸入文字框</textarea> <br />

    底下是表格<br />
    <table>
        <thead>
            <tr>
                <th colspan="2">The table header</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>The table body</td>
                <td>with two columns</td>
            </tr>
            <tr>
                <td>The table body</td>
                <td>with two columns</td>
            </tr>
            <tr>
                <td>The table body</td>
                <td>with two columns</td>
            </tr>
        </tbody>
    </table>

    <caption>為表格加上標題</caption>
</body>

</html>
```

整個網站都沒有裝飾，表格連框都沒有很醜對吧，之後我們來用CSS裝飾它吧！
