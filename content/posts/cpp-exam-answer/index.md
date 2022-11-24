---
title: "高一C++期中考詳解"
date: 2022-11-17
description: "西苑高中鄭傑的高一C++期中考考題詳解"
categories: ["Coding"]
dropCap: true
displayInMenu: false
displayInList: true
draft: true
---

這裡提供了我的解題思路，僅供參考，任何能算出解答的都是好方法。因為是期末考所以我是等所有人都考完才發，且因為這只是給西苑的朋友看所以發在這裡就沒有發在資訊密技了。



> 偷吃步:右鍵，使用Google Lens搜尋圖片，複製文字，貼到隨便一個C++編譯器即可。只有`#include`那行一定要換行，其他有分號的都可以不用管。

## 輸入2 3 4 5，輸出為何?

A:3

帶入  val=3/2+4/3+5/3; 記得先乘除後加減，且都是int只會算出整數  
 var=1+1+1=3

```c++
#include<iostream>
using namespace std;
int main(){
    int a,b,c,d,val=1;
    cin>>a>>b>>c>>d;
    val=b/a+c/b+d/b;
    cout<<val;
    return 0;
}  
```

## 輸入8，輸出為何?

A:14

`pow(a,b)`是a的b次方。8*8=64大於50所以是要輸出8+2\*3=14

```c++
#include<iostream>
#include<cmath>
using namespace std;
int main(){
    int a;
    cin>>a;
    if(pow(a,2)<50){
        cout<<a*2+3;
    }
    else{
        cout<<a+2*3;
    }
    return 0;
}  
```

## 輸入8 7，輸出為何?

A:7

if裡面是一個交換，如果a>b就交換。8>7所以原本的a從8換成7。

```c++
#include<iostream>
using namespace std;
int main(){
    int a,b,c=5;
    cin>>a>>b;
    if(a > b){
        c = a;
        a = b;
        b = c;
    }
    cout<<a;
    return 0;
}  
```

## 輸入10，輸出為何?

A:16

* 10>0所以count會變成11
* 接著11大於10所以變成12。12除以4整除沒有餘數所以變0
* 最後count 0沒有大於0所以會改成16

```c++
#include<iostream>
using namespace std;
int main(){
    int count;
    cin>>count;
    if(count > 0){
        count = 11;
    }
    if(count > 10){
        count = 12;
        if(count % 4 == 3){
            count = 1;
        }
        else{
            count = 0;
        }
    }
    else if(count > 11){
        count = 13;
    }
    else{
        count = 14;
    }
    if(count > 0){
        count = 15;
    }
    else{
        count = 16;
    }
    cout<<count;
    return 0;
}  
```

## 輸入31 69，輸出為何?

A:1000

經過一番輸入a=31,b=69,i=a=31,sum=0

迴圈會從3加到69，公差為2。
{{< raw >}}
\frac{(31+69)[(69-31)\div2+1]}{2}=1000
{{< /raw >}}

```c++
#include<iostream>
using namespace std;
int main(){
    int i,a,b,sum=0;
    cin>>a>>b;
    for(i=a; i<=b; i=i+2){
        sum=sum+i;
    }
    cout<<sum;
    return 0;
}
```

## 輸入10，輸出為何?

A:85

n=10，重複10次
先看abc變化
a=1，b=2，c=3  
第一次:a=2，b=3，c=4  
第二次:a=3，b=4，c=5...  
第十次:a=11，b=12，c=13

接著是sum變化。每次sum加了  
第一次:-1+2+3=4  
第二次:-2+3+4=5  
第十次:-10+11+12=13  

注意每一次加的是上一次加的數字，因為是先加才改變。觀察發現其實就是4加到13的等差數列

{{< raw >}}
\frac{(4+13)\times10}{2}=85
{{< /raw >}}

```c++
#include<iostream>
using namespace std;
int main(){
    int n,i,a=1,b=2,c=3,sum=0;
    cin>>n;
    for(i=1; i<=n; i++){
        sum=sum-a+b+c;
        a=b;
        b=c;
        c++;
    }
    cout<<sum;
    return 0;
}
```

## 輸入100，輸出為何?

A:100

迴圈從1到100重複100次。每次都是+b-a

先看ab變化  
a=0，b=1  
第一次:a=1，b=2  
第二次:a=2，b=3...  
第十次:a=100，b=101

接著是sum變化  
第一次:0-1+2=1  
第二次:1-2+3=2...  
第100次:99-100+101=100

觀察發現不就是每次加一。零加一一百次就是一百

```c++
#include<iostream>
using namespace std;
int main(){
    int n,i,a=0,b=1,sum=0;
    cin>>n;
    for(i=1; i<=n; i++){
        sum=sum-a+b;
        a=b;
        b++;
    }
    cout<<sum;
    return 0;
}
```

## 輸入9，輸出為何?

A:19

當n>1時,將會一直執行第7~13行程式碼

n=100
1100除以2沒有餘數變50  
50除以2沒有餘數變25  
25除以2餘1變76  
76除以2沒有餘數變38  
38除以2沒有餘數變19  
19除以2餘1變58  
58除以2沒有餘數變29  
29除以2餘1變88  
88除以2沒有餘數變44  
44除以2沒有餘數變22  
22除以2沒有餘數變11  
11除以2餘1變34  
34除以2沒有餘數變17  
17除以2餘1變52  
52除以2沒有餘數變26  
26除以2沒有餘數變13  
13除以2餘1變40  
40除以2沒有餘數變20  
20除以2沒有餘數變10  
10除以2沒有餘數變5  
5除以2餘1變16  
16除以2沒有餘數變8  
8除以2沒有餘數變4  
4除以2沒有餘數變2  
1除以2沒有餘數變1 
1除以2=0.5

數一下沒有餘數的有19次

```c++
#include<iostream>
using namespace std;
int main(){
    int n,count=0;
    cin>>n;
    while(n>1){
        if(n%2==1){
            n=3*n+1;
        }
        else{
            n=n/2;
        }
        count++;
    }
    cout<<count;
    return 0;
}  
```

## 輸入20，輸出為何?

A:210

裡面的迴圈第一次重複1(+1)，第二次重複2(+2)，共20次

{{< raw >}}
\frac{(1+20)\times20}{2}=210
{{< /raw >}}

```c++
#include<iostream>
using namespace std;
int main(){
    int i,j,n,a=0;
    cin>>n;
    for(i=1; i<=n; i++){
        for(j=1; j<=i; j++){
            a++;
        }
    }
    cout<<a;
    return 0;
}  
```

## 輸入13，輸出為何?

A:20

就是

```c++
#include<iostream>
using namespace std;
int main(){
    int n,i,j,x=0;
    cin>>n;
    for(i=1; i<=n; i++){
        for(j=1; j<=n; j++){
            if((i+j)==2){
                x=x+2;
            }
            if((i+j)==3){
                x=x+3;
            }
            if((i+j)==4){
                x=x+4;
            }
        }
    }
    cout<<x;
    return 0;
}  
```
