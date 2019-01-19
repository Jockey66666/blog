---
title: Linker error，找不到SetPortW()
date: 2019-01-19 07:58:04
tags: cpp
categories: [cpp]
---

## 問題

寫一個class，有一個function叫做SetPort，結果在link的期間linker error出現找不到SetPortW()的實作

``` cpp	
class Socket {
public:
    void SetPort(size_t port){
        // implementation
    }
};
```

為什麼function name明明是SetPort卻要link SetPortW ?

## 原因
看到link的時候名字不一樣了那一定是preprocessor搞的鬼，先找[SetPort MSDN](https://docs.microsoft.com/en-us/windows/desktop/printdocs/setport)，看到Winspool.h裡面有一段code

``` cpp
#ifdef UNICODE
#define SetPort SetPortW
#else
#define SetPort SetPortA
#endif // !UNICODE
```

## 解法

1. 直接rename function，快又有效
2. 確保include windows.h的順序，盡一切可能放在最後include，有點麻煩，隨著時間過去這件事會被淡忘

## 結論

這種windows上的坑絕對不只一個，在MFC內尤其多，每個function都要A跟W，能早點脫離這個坑就早點放棄吧…XD

## 參考資料
* https://docs.microsoft.com/en-us/windows/desktop/printdocs/setport
* https://social.msdn.microsoft.com/Forums/vstudio/en-US/8afda048-96d6-4c87-8895-acfddcff1731/linker-problem-with-setport?forum=vcgeneral