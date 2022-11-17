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

根據老師說法各班題目數字不一樣，順序依樣。

> 偷吃步:右鍵，使用Google Lens搜尋圖片，複製文字，貼到隨便一個C++編譯器即可。只有`#include`那行一定要換行，其他有分號的都可以不用管。

## 輸入2 3 4 5，輸出為何?

A:3

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
## 輸入12，輸出為何?
A:144
```c++
#include<iostream>
using namespace std;
int main(){
    int n,i,a=1,b=1,c;
    cin>>n;
    for(i=3; i<=n; i++){
        c=a+b;
        a=b;
        b=c;
    }
    cout<<c;
    return 0;
}
```
## 輸入100，輸出為何?
A:100
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

(註：當n>1時,將會一直執行第7~13行程式碼)

A:19
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
