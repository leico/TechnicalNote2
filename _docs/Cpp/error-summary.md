---
layout : post
title  : "エラー処理: まとめ"
date   : 2019/08/13
lastchange : 2019-08-14 07:49:59.
tags   :
  - C++
  - C++11
  - Error
  - try
  - catch
---

## ここまでの試行錯誤から

* C++ 例外処理
  * 遅い
  * 正常動作時には余分なリソースを食わない
  * 後始末は全く簡単になってない
  * 文法も複雑
  * 煩雑なコードはそこまで改善しないと思う
  * 戻り値や余分な引数は無くなる
  * `std :: exception` やスマートポインタを利用できるのは楽
* Cから引き続き
  * 動作は早い
  * 正常動作時にもリソースが割かれる
  * 煩雑なコードになる
  * 文法はまぁ、いつもの感じ
    * 読みづらいと言えば読みづらい
  * 戻り値や余分な引数などの犠牲が生じる
  * こちらでも別に `std :: exception` やスマートポインタを利用することはできる
    ```cpp
      void fx( const int a, const int b, std :: runtime_error& err);
    ```
* C系まともに例外処理する気があるのだろうか