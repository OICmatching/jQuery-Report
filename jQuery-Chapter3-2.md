# jQuery

* 要素と属性の指定



### 代表的なセレクタの紹介

```
$( セレクタ ).メソッド名();
```
のセレクタ部分に対応する属性や要素ので代表的なものを紹介。   
ＣＳＳセレクタと記述方法はほぼ同等。

#### $(”要素名”).メソッド名( )
要素名で指定した全ての要素に対して実行される。

```
<html>
  <head>
    <meta charset="UTF-8">
    <title></title>
  <script src="https://code.jquery.com/jquery-2.2.4.min.js" integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44=" crossorigin="anonymous"></script>
    <script>
      $(document).ready(function(){

        $("div").css("color","#f00");
        //全てのdiv要素にstyle = #f00を指定。

        });
      </script>
  </head>
  <body>
    <div>
      div要素内の文字
      <p>
        divの子要素のp要素内の文字
      </p>
    </div>
    <div id="testId">
        div（id=testId）要素内の文字
    </div>
    <p>
    div要素外の文字
    </p>
  </body>
</head>
```


#### $(”[name = name属性値]”).メソッド名( )
指定したname名に実行される。

```
      $(document).ready(function(){

        $("[name=test]").css("color","#f00");
        //指定したname名にstyle = #f00を指定。

        });
      </script>

・・・省略・・・

    <div name="test">
        div（name=test）要素内の文字<br>
        div（name=test）要素内の文字<br>
    </div>
    <div>
        div要素内の文字
    </div>

```

#### $("#id名").メソッド名( )
指定したid名に実行される。

```
      $(document).ready(function(){

        $("#test").css("color","#f00");
        //指定したid名にstyle = #f00を指定。

        });
      </script>

・・・省略・・・

    <div id="test">
        div（id=test）要素内の文字<br>
    </div>

```

#### $(".class名").メソッド名( )
指定したclass名に実行される。

```
      $(document).ready(function(){

        $(".test").css("color","#f00");
        //指定したclass名にstyle = #f00を指定。

        });
      </script>

・・・省略・・・

    <div class="test">
        div（class=test）要素内の文字<br>
    </div>
    <div id="test">
        div（id=test）要素内の文字<br>
    </div>

```

#### $(" * ").メソッド名( )
全ての要素に実行される。

```
      $(document).ready(function(){

        $("*").css("color","#f00");
        //全要素にstyle = #f00を指定。

        });
      </script>

・・・省略・・・

    <div class="test">
        div（class=test）要素内の文字<br>
    </div>
    <div id="test">
        div（id=test）要素内の文字<br>
    </div>

```

#### $("要素名,#id名").メソッド名( )　or　$("要素名,.class名").メソッド名( )
指定した要素名　or　id名に実行される。   
※　,「カンマ」区切りで、複数指定可能。    
※　 $(".class名(要素名),.class名")の場合、class名の間のカンマを省略できる。   
※　ｊＱｕｅｒｙ上から下へ読み込まれるので内容が上書きされる事がある。   

```
      $(document).ready(function(){

        $("div,#test").css("color","#f00");
        //指定した要素かid名にstyle = #f00を指定。
        $("div,#test,.test").css("color","#0000FF");
        //指定した要素かclass名にstyle = #0000FFを指定。

        });
      </script>

・・・省略・・・

    <div class="test">
        div（class=test）要素内の文字<br>
    </div>
    <div id="test1">
        div（id=test）要素内の文字<br>
    </div>
    <p id="test">
        p(id=test)要素内の文字
    </p>
    <p>
        p要素内の文字
    </p>

```

#### $("#id名 要素名").メソッド名( )　or　$(".class名 要素名").メソッド名( )
指定したidの子要素である指定した要素を指定する（孫要素も対象）。   
※　「空白」区切りで、さらに細かく特定して指定できる。

```
      $(document).ready(function(){

        $("#test1 div p").css("color","#f00");
        //指定した要素かid名にstyle = #f00を指定。
        $(".test div").css("color","#0000FF");
        //指定した要素かclass名にstyle = #0000FFを指定。

        });
      </script>

・・・省略・・・

<div id="test1">
 div（id=test1）要素内の文字<br>
  <div id="test2">
    <p>
      div（id=test1）要素内のdiv（id=test2）要素内のp要素内の文字<br>
    </p>
  </div>
</div>
<div class="test">
  <div>
    <p>
      div（class=test）要素内のdiv要素内のp要素内の文字<br>
    </p>
  </div>
</div>

```

#### $("#id名 > 要素名").メソッド名( )　or　$(".class名 > 要素名").メソッド名( )
指定したidの子要素である指定した要素を指定する（孫要素は非対象）。   
※　> 「」区切りで、さらに細かく特定して指定できる。   
※　孫要素が指定できちゃうため保留。

```
      $(document).ready(function(){

        $("#test1 > div >  p").css("color","#f00");
        //指定した要素かid名にstyle = #f00を指定。
        $(".test > div").css("color","#0000FF");
        //指定した要素かclass名にstyle = #0000FFを指定。

        });
      </script>

・・・省略・・・

<div id="test1">
 div（id=test1）要素内の文字<br>
  <div id="test2">
    <p>
      div（id=test1）要素内のdiv（id=test2）要素内のp要素内の文字<br>
    </p>
  </div>
</div>
<div class="test">
  <div>
    <p>
      div（class=test）要素内のdiv要素内のp要素内の文字<br>
    </p>
  </div>
</div>

```

#### $("要素名(or class名　or id名):first").メソッド名( )
対象要素名が複数ある場合、指定した要素名の一番最初に対して

```
      $(document).ready(function(){

        $(".p:first").css("color","#f00");
        //指定したclass名にstyle = #f00を指定。

        });
      </script>

・・・省略・・・

    <p>
      １番目のp要素内の文字
    </p>
    <p>
      ２番目のp要素内の文字
    </p>
    <p>
      ３番目のp要素内の文字
    </p>

```
#### $("要素名(or class名　or id名):last").メソッド名( )
対象要素名が複数ある場合、指定した要素名の一番最後に対して。

```
      $(document).ready(function(){

        $("p:last").css("color","#f00");
        //指定したclass名にstyle = #f00を指定。

        });
      </script>

・・・省略・・・

    <p>
      １番目のp要素内の文字
    </p>
    <p>
      ２番目のp要素内の文字
    </p>
    <p>
      ３番目のp要素内の文字
    </p>

```

#### $("要素名(or class名　or id名):even").メソッド名( )
指定した要素名が複数ある場合、対象要素のindex（0番目から始まる）で偶数番目に対して。

```
      $(document).ready(function(){

        $("p:even").css("color","#f00");
        //指定したclass名にstyle = #f00を指定。

        });
      </script>

・・・省略・・・

    <p>
      １番目のp要素内の文字
    </p>
    <p>
      ２番目のp要素内の文字
    </p>
    <p>
      ３番目のp要素内の文字
    </p>
    <p>
      ４番目のp要素内の文字
    </p>

```
#### $("要素名(or class名　or id名):odd").メソッド名( )
指定した要素名が複数ある場合、対象要素のindex（0番目から始まる）で偶数番目に対して。

```
      $(document).ready(function(){

        $("p:odd").css("color","#f00");
        //指定したclass名にstyle = #f00を指定。

        });
      </script>

・・・省略・・・

    <p>
      １番目のp要素内の文字
    </p>
    <p>
      ２番目のp要素内の文字
    </p>
    <p>
      ３番目のp要素内の文字
    </p>
    <p>
      ４番目のp要素内の文字
    </p>

```
