# HTML を学ぼう

## この講義の目的

* HTML を知る
* HTML5 に触れる

## 目次

* HTML について
* HTML の書き方
* HTML5
* 実際に書いてみよう

# HTML について

HTML とは

    HTML (HyperText Markup Language) とは、 Web ページを記述するためのマークアップ言語の略称

で、この **HyperText** と **Markup** は

    HyperText とは、ある文章を読んでいる最中に別の文章を参照することを表す
    Markup とは、文章の構造や要素を表す

という意味

## HTML の歴史

* 1993年に IETF のワーキンググループによりインターネット・ドラフトが提出された (HTML 1.0)
* 1995年に IETF の HTML ワーキンググループにより RFC 1866 として使用が発表された (HTML 2.0)
* 1997年1月に W3C 勧告として使用が発表された (HTML 3.2)
* 1997年12月に W3C 勧告として HTML 4.0 の使用が発表された (HTML 4.0)
* 2008年に W3C よりドラフトが発表された (HTML 5) 

### どこで決めてるの？

W3C (World Wide Web Consortium)

    HTML や XML をはじめとする WWW (World Wide Web) で利用される様々な技術の標準化を推進することを目的とした非営利団体の名称である

## HTML の特徴

HTML の特徴として

* 要素を使用して書く
* 柔軟な表現が出来る

などが挙げられる。  
そして、良い HTML の条件として

> アクセシビリティ

    ユーザーがどこに何があるかを直感で理解できる

> 保守性

    メンテナンスしやすい構造

# HTML の基本

## DTD 宣言

HTML を書く時には先頭に DTD 宣言(文書宣言) を書く

    DTD 宣言とは、文書が HTML であり、この HTML がどのバージョンで記述されているかを宣言すること

```html
<!DOCTYPE HTML>
```

## 要素

HTML は要素を使用して記述していく

```html
<!DOCTYPE html>
<html>                                                                                                                                
  <head>
  </head>
  <body>
  </body>
</html>
```

要素 (element) は、開始タグ (Start-tag)・内容 (Content)・終了タグ (End-tag) の3つから構成される

* 要素は < と > で囲まれる開始タグで始まり、</ と > で囲まれる終了タグで終わる
* 開始タグと終了タグではさまれた部分が内容となる

上記に書かれている要素を順番に説明していく

### \<HTML>

DTD 宣言では文書の HTML のバージョンが宣言されていたが、 html 要素では HTML 文書であることを示すために記述する

```html
<!DOCTYPE html>
<html>

</html>
```

html 開始タグに lnag="ja" を加えると、この文書が日本語であることを宣言できる

```html
<html lang="ja">
```

\<html> ~ \</html> の間には \<head> と \<body> が必ず1つは必要となる

### \<head>

head 要素は、この文書のヘッダ情報を表す際に使用する。正確には文書のメタデータを表すために記述する

\<head> ~ \</head> の中に

* \<title> (タイトル)
* \<base> (基準 URL)
* \<link>(リンク情報)
* \<style>(スタイルシート)
* \<meta> (メタデータ)

などの要素を配置することで、この文書の情報(メタデータ)を表すことができる

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="UTF-8">
    <title>Let's HTML</title>
  </head>
</html>
```

### \<body>

body 要素は、文書の本体を表す際に使用する。 文書の本体とはブラウザ上に表示されるメインコンテンツのこと

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="UTF-8">
    <title>Let's HTML</title>
  </head>
  <body>
    <p>hogehoge fugafuga</p>
  </body>
</html>
```

# HTML5

HTML5 は現在、2014年までの正式勧告を目指して W3C にて策定が行われている

## HTML5 でできること

HTML5 では HTML4 でできなかったことができるようになる

### 文書構造をより明確に示せる

HTML5 では、文書構造を表す新しい要素が加わることで文書構造がより強化された

例えば

* header - ヘッダを示す 
* footer - フッタを示す 
* section - セクションを示す 
* article - 記事であることを示す 
* nav - ナビゲーションであることを示す 

など、それぞれの役割に応じて適切な要素に割り当てることができるようになる

### 動画・音声が簡単に扱える

これまで動画や音声をウェブページに埋め込む際には Flash などのプラグインを利用するのが一般的だったが、 HTML5 では新しく追加される video 要素や audio 要素を使用することで動画や音声をシンプルに扱えるようになる

> video

```html
<video width="640" height="360" preload="auto" poster="hoge.png" controls autoplay>
  <source src="hoge.webm" type='video/webm; codecs="vp8, vorbis"'>
</video>  
```

> audio

```html
<audio controls loop>
  <source src="hoge.mp3">
</audio>
```

### フォームの入力補助やチェック機能が強化されている

今まで JavaScript で作成するのが一般的だったことが、フォーム要素に追加される新しい属性で簡単に指定できるようになる

> input 要素の属性を書き換える

```html
<input name="text" type="text"> /* 文字をチェック */
<input name="email" type="email"> /* メールアドレスをチェック */
<input name="url" type="url"> /* URL をチェック */
```

> 入力項目を必須にする

```html
<input name="text" type="text" require> /* text 項目は必須 */
```

> input が未フォーカス時に文字を表示させる

```html
<input name="text" type="text" placeholder="例）東京都"> /* "例）東京都" が薄く表示される */
```

### 記述が簡潔に書ける

HTML4 で長かった記述が簡潔に書けるようになる

> HTML4

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN">
<html>
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>Let's HTML</title>
  </head>
  <body>
  </body>
</html>
```

> HTML5

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset=UTF-8">
    <title>Let's HTML</title>
  </head>
  <body>
  </body>
</html>
```

## HTML5 で追加される要素・廃止される要素

HTML5 では HTML4 になかった新たな要素が追加され、また、HTML4 にあった要素の一部が HTML5 では廃止される(現段階では予定)

### HTML5 で新たに追加される予定の要素

* \<article>  -  記事であることを示す
* \<aside>  -  余談であることを示す
* \<audio>  -  音声を再生する
* \<canvas>  -  図形を描く
* \<command>  操作メニューの各コマンドを指定する
* \<datalist>  -  入力候補となるデータリストを定義する
* \<details>  -  備考や操作手段などの詳細情報を示す
* \<embed>  -  プラグインデータを埋め込む
* \<figcaption>  -  図表のキャプションを示す
* \<figure>  -  図表であることを示す
* \<footer>  -  フッタであることを示す
* \<header>  - ヘッダであることを示す
* \<hgroup>  -  セクションの見出しを表す、見出しをまとめる
* \<keygen>  -  フォーム送信時にキーを発行する
* \<mark>  -  文書内の該当テキストを目立たせる
* \<menu>  -  操作メニューを作成する
* \<meter>  -  規定範囲内の測定値を表す
* \<nav>  -  ナビゲーションであることを示す
* \<output>  -  計算結果を示す
* \<progress>  タスク完了までの進行状況を示す
* \<section>  -  一つのセクションであることを示す
* \<source>  -  動画や音声などのURLや種類を指定する
* \<summary>  -  \<details> の内容の要約を示す 
* \<time>  -  日付や時刻を正確に示す
* \<video>  -  動画を再生する
* \<rp>  -  ルビを囲む記号を指定する
* \<rt>  -  ルビのテキストを指定する
* \<ruby>  -  ルビをふる
* \<wbr>  -  改行しても良い位置を示す

### HTML5 では廃止される予定の要素

> これらの要素は、別の要素に置き換えられるか CSS に置き換えられる

* \<acronym>  -  略語（頭字語）であることを表す
* \<applet>  -  JAVAアプレットを挿入する
* \<basefont>  -  テキストの基準サイズ・基準色・基準フォントを指定する
* \<bgsound>  -  効果音・BGMを鳴らす（IE独自の仕様）
* \<big>  -  テキストのサイズをひとまわり大きくする 
* \<blink>  -  文字を点滅させる（NN独自）
* \<center>  -  センタリングする
* \<dir>  -  リストを表示する
* \<font>  -  フォントの種類・大きさ・色を指定する
* \<frame>  -  フレームに表示するファイルを指定する
* \<frameset>  -  ウィンドウをフレームに分割する
* \<isindex>  -  検索キーワードの入力欄を作る
* \<listing>  -  ソースをそのまま表示する（タグは解釈される）
* \<marquee>  -  文字をスクロールさせる（IE独自）
* \<nobr>  -  改行なしで表示する（NN独自）
* \<noembed>  -  プラグインが利用できない環境用の表示内容を指定する（NN独自）
* \<noframes>  -  フレームが表示できない環境用の表示内容を指定する
* \<plaintext>  -  ソースをそのまま表示する
* \<rb>  -  ルビをふる文字を指定する（IE独自）
* \<spacer>  -  スペースを挿入する（NN独自）
* \<strike>  -  打ち消し線を引く
* \<tt>  -  等幅フォントで表示する
* \<u>  -  テキストに下線（アンダーライン）を引く
* \<xmp>  -  ソースをそのまま表示する

## HTML5 を使う際に注意すること

HTML5 に追加される機能はこれ以外にもあり、さらに増えるだろう  
HTML5 を使う際に以下の注意が必要

#### 1. HTML5 はまだ草案段階であること

仕様が固まってないため、これからどんどん仕様が変わっていく可能性がある

#### 2. ブラウザによって挙動が変わる

すべてのブラウザが HTML5 に対応しているわけではない

## HTML5 をもっと知るには

このスライドがとてもわかりやすくて参考になるので1回は見よう

[HTML5, きちんと。](http://www.slideshare.net/myakura/html5-2480964)

# 実際に書いてみよう

HTML5 を使って Web システムでよく目にする「ユーザー登録画面」を作ってみる

### 設計

画面レイアウト、項目は以下の通りに作成する

> 画面レイアウト

<img src="https://cacoo.com/diagrams/y1NPzlszhEgN7yyM-51DA5.png" align="center">

> section 部に表示する項目

* 氏名(必須)
* メールアドレス(必須)
* パスワード(必須, 入力時にパスワードは *** で表示)
* 都道府県(セレクトボックスから選択する)
* 性別(ラジオボタン)
* 関心のあるジャンル(チェックボックス)
* ご要望(複数行書けるように)

注意点

* ブラウザは Chrome を使用すること
* 文字コードは **UTF-8** で保存すること
* 拡張子は **.html* にすること
* デスクトップに **regist.html** という名前でファイルを作成する

## header 部

header にはセクションの目次や検索フォーム、あるいはロゴなどを入力する

>  文書のヘッダ情報を表す \<head> タグとは異なるので注意

```html
<header>
  <ol>
    <li>TOP</li>
    <li><a href="#">ユーザー登録画面</a></li>
  </ol>
  <h1>ユーザー登録画面</h1>
</header>
```

## section 部

section はウェブページ内のその部分が、一つのセクションであることを示す際に使用する  
article は内容が単体で完結するセクションであることを示す際に使用する

## nav 部

nav はウェブサイト内の他のページへのリンクや、ページ内リンクなどのナビゲーションを示す際に使用する

```html
<nav>
  <ul>
    <li><a href="../index.html">TOP 画面</a></li>
    <li><a href="../show.html">一覧画面</a></li>
    <li><a href="../delete.html">削除画面</a></li>
  </ul>
</nav>
```

## footer 部

footer はそのセクションに関する情報を扱う時に使用し、一般的には、誰が書いたのか、関連文書へのリンク、著作権などの情報が含まれる

```html
<footer>
  <p>
  Copyright© 2012 hoge All Rights Reserved.
  </p>
</footer>
```

HTML でページを作れたら、次は CSS を使って見た目をよくしよう！

[HTML の次は CSS を学ぶ](https://github.com/Kazuma/Textbook/blob/master/regist.html)

# 参考リンク

* [HTML5とは何かを簡単にまとめてみた](http://techblog.yahoo.co.jp/html5/html5/)
* [HTML クイックリファレンス - HTML5 リファレンス](http://www.htmq.com/html5/index.shtml)
* [Wikipedia - HyperText Markup Language](http://ja.wikipedia.org/wiki/HyperText_Markup_Language)

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="http://i.creativecommons.org/l/by-nc-sa/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/2.1/jp/">クリエイティブ・コモンズ 表示 - 非営利 - 継承 2.1 日本 ライセンス</a> の下に提供されています。
