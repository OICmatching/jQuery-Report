# jQuery
___


* jQueryライブラリの準備
* JavaScriptの約束事


### jQueryライブラリの準備
___
* jQueryライブラリをダウンロードして使用する。
  * 各サイトにjQueryを（ダウンロードして）フォルダに設置する必要がある。
* http://jQuery.comからjQueryライブラリを読み込む。   
  * 常にインターネットに接続出来る状態である必要がある。

```
<head>
<meta charset=” ”>
<title></title>
<script src=”  jQueryライブラリファイル( or URL) ” ></script>
</head>
```

jQueryのライセンスは、ライブラリの著作権表示を消さない限り、商用・非商用問わずに誰でも制約なしに利用することが可能。


###  JavaScriptの約束事
___

* ブラウザはHTMLを上から下へ読み込む    
  * 通常HTMLやCSSの記載された内容はjQueryやJavaScriptの記載された内容の後に読み込まれるためHTMLやCSSで記載した内容を操作できない。     
  　→「$(document).ready」を使用すると、HTMLを全て読み込んだあとにjQueryやJavaScripが読み込まれる。

```
<script>
$(document).ready(function({
  //この中に書かれた記述は、HTMLを全て読み込んだ後に読み込まれる。
  })；
</script>
```

（jQueryレッスンブック　Cherpter2参照）
