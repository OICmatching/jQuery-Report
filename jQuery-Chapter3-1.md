
# jQuery

* jQueryで覚えておく用語の理解
  * どの箇所に対して
  * 何をさせるか
  * どのタイミングで


* jQueryの基本的な記述方法                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              

### jQueryで覚えておく用語の理解
___

1. どの箇所に対して(セレクタ)  
    HTMLやCSSの要素やプロパティ名を記述する。

2. 何をさせる（メソッド）    
   「1.」で指定した要素やプロパティ等の対象物に対して何をさせたいか動作を記述する。    
   CSSのような装飾部分だけでなく、HTML要素を操作することも可能。

3. どのタイミングで（イベント）   
  「1.」で指定した要素やプロパティ等の対象物に対して「2.」で指定した何をさせたいか動作をいつ実行させるかを記述する。     
  ｊQueryの処理を開始する合図。


### jQueryの基本的な記述方法
___

* JavaScript　や　ｊQuery　は< script >で囲んだ中で記述しないとブラウザがJavascriptとに意識せず読み込めない。

```
<script>
  //  JavaScrip や　ｊQuery　の内容を記述する。
</script>

```


* コメント以外に行末に、「 ;(セミコロン) 」 がないとエラーが起こり実行が出来ない。


```
alert(”　”);
```

* セレクタ　と　メソッド　の間は、「 .（ドット） 」でつなぐ。

```
$( セレクタ ).メソッド名();
```

* コメント　は、2つの方法がある。    
    * 行頭に「 //（ダブルスラッシュ） 」で1行をコメントにする方法
    * 「/＊　･･･　＊/（半角文字で）　」 の中で記述された複数行をコメントにする方法

  ```
  //alert(”コメントとして認識される。”);
  ```
  ```
  /*　
  　　　alert(”コメントとして認識されます。”);
  　　　alert(”「/*　… */」囲まれた内容はコメントとして認識される。”);
  */
  ```



（jQueryレッスンブック　Cherpter3 Lesson1とLesson2参照）
