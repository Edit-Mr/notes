---

title: "SecurityFoscusOnline2023"
date: 2023-02-05
description: "SecurityFoscusOnline2023"
categories: ["Coding"]
dropCap: true
displayInMenu: false
displayInList: true
draft: false
toc: true

---

這是我的個人筆記，因此只有紀錄不會或需要反覆搜尋的內容。[原始markdown在這裡](https://github.com/Edit-Mr/notes/tree/main/content/posts/SecurityFoscusOnline2023)

## 三大主要CTF資安攻防賽類型
1. 解謎式（Jeopardy） 本次教學使用的類型
2. 攻防模式（Attack and Defense）
3. King of The Hill(類似搶灘遊戲)

## 解謎式CTF常見5種題型 

### Reverse逆向工程類型  

通常由主辦方給一個或多個Binary， 過關所需要的Key通常加密藏在執行檔裡，要將程式逆向分析出後才能找出。

### Pwnabl弱點或漏洞分析類型  

主辦方會給一個有弱點的程式或 Server 執行檔，主辦方自己會開一台伺服器跑該服務，參賽者要透過靜態分析與動態分析來找出該程式的弱點。例如： Buffer overflow、命令注入等，在遠端伺服器利用漏洞來執行任意指令，進一步取得存在遠端伺服器的金鑰。

### Crypto加解密類型  

主辦方會給加密過的密文、加密程式，參賽者必須分析加解密演算法甚至需要找出演算法的弱點來破解出真正的明文。

### Forensics鑑識類型  

主辦方會要求參賽者從封包、Log、 Memory Dump、Disk Image、VM image等鑑識出隱藏在之中的金鑰。

### Misc綜合類型  

沒有較明確的分類：像是給個遊戲要想辦法作弊破到幾百萬分、給一個壞掉的 QR code 嘗試修復，或是給張圖片要找出相關的人事物等。
## 隱寫術
### Word

字型>隱藏

### PDF

`Ctrl + A`

### 影像

* [顏色工具](https://stegonline.georgeom.net/upload)
* HxD 軟體檢視二進位
* `type`查看檔案類型(是否為`.gz`,`.zip`...)

#### Linux
* 查看檔案格式:`file just_open_it.jpg`
* 查看檔案內藏的字串
第一次測試 ==> strings just_open_it.jpg

第二次測試 ==> 再多使用pipeline | 及超強的grep指令
     strings just_open_it.jpg | grep ABCTF
     strings /root/Downloads/just_open_it.jpg | grep CTF


## 編碼

電腦只看得懂0和1(至少目前是)，所以我們用數字來代表字元。常見如UTF-8,BIG5

### 線上解密工具
* [頻率分析](https://quipqiup.com/)
* [凱薩](https://planetcalc.com/1434/)
* [維吉尼亞密碼](https://www.dcode.fr/vigenere-cipher)
* [Hex/Binary](https://cryptii.com/pipes/hex-decoder)
* [Base64](https://www.base64decode.org/)
* [ASCII](https://www.dcode.fr/ascii-code)

> 可參考 https://ithelp.ithome.com.tw/users/20121059/ironman/2810

## Python整理

以下是常用的 Python 語法：

### 基本數據類型
* `int`：整數
* `float`：浮點數
* `str`：字符串
* `bool`：布爾

### 變量定義
`variable_name = value`

### 運算符
`+`：加法
`-`：減法
`*`：乘法
`/`：除法
`%`：餘數
`==`：等于
`!=`：不等于
`<`：小于

`>`：大于
`<=`：小于等于
`>=`：大于等于

### 控制結構
* `if-elif-else`：判斷式
* `for`：迴圈
* `while`：迴圈

### 函數定義
```python
def function_name(arguments):
```

### 列表
```python
list = [item1, item2, item3, ...]
```

### 字典
```python
dictionary = {key1: value1, key2: value2, key3: value3, ...}
```

### 集合
```python
set = {item1, item2, item3, ...}
```

模塊：
```python
import module_name
```

輸入輸出：
```python
print(expression)
input(prompt)
```

## CMD解題

這裡只列出幾題，把各個會用到的邏輯記錄下來

### Python 一次100題

> VSCode 記得先安裝pwn(pip install)
```
===== Welcome =====
I need you to transform from Fahrenheit to Celsius
----- wave : example -----
Fahrenheit : 10 (guarantee to be integer)
Celsius : -110/9
----- wave : 1/100 -----
Fahrenheit : 95
Celsius :
```

```python
from pwn import *
from fractions import Fraction

r = remote("120.114.62.215", 5127)

r.recvlines(5)

for _ in range(100):
    r.recvuntil("Fahrenheit : ")
    C = (Fraction(int(r.recvline().strip()), 1) - 32) * 5 / 9
    r.sendline(str(C.numerator) + '/' + str(C.denominator))

r.interactive()
```
這段代碼是一個使用 Python 實現的黑客程式，其目的是連接到遠程服務器（120.114.62.215，埠5127），然後在服務器上執行一些操作。

代碼首先使用了 pwn 庫，它是一個用於編寫黑客程式的庫。然後，使用了 fractions 模組中的 Fraction 類，它可以把整數轉換為分數。

接下來，代碼通過 remote 函式連接到遠程服務器。然後，代碼使用 recvlines 函數接收了服務器的五行數據。

接下來，代碼進入了一個 for 循環，其運行 100 次。在每次循環中，代碼使用 recvuntil 函數等待並接收特定字串 「Fahrenheit : 」，然後使用 recvline 函數接收相應的攝氏溫度。

然後，代碼將攝氏溫度轉換為華氏溫度，並使用 sendline 函數將轉換后的結果發送回服務器。

最後，代碼使用 interactive 函數進入互動模式，以便與遠程服務器進行互動。

> `.strip()` 它的作用是刪除字串開頭和結尾的空白字元（例如空格，回車，換行符等）

### SSH連線

以下是指令步驟

語法: `ssh lab@120.114.62.215 -p 2200`
```
lab@6efabf09ad73:~$ ssh lab@120.114.62.215 -p 3700
Could not create directory '/home/lab/.ssh'.
The authenticity of host '[120.114.62.215]:3700 ([120.114.62.215]:3700)' can't be established.
ECDSA key fingerprint is SHA256:ganPFCO6alrpyTd6mukU27rlrz35PIAcMG1itPFDdqQ.
Are you sure you want to continue connecting (yes/no)? yes
Failed to add the host to the list of known hosts (/home/lab/.ssh/known_hosts).
lab@120.114.62.215's password:
Last login: Sat Feb  4 13:42:13 2023 from 203.204.208.96
lab@c74b487c2253:~$ ls
base64.txt  flag  hex.txt
lab@c74b487c2253:~$ flag
BreakALLCTF{YUA7D5D0k4elbQ1XqH14}
```