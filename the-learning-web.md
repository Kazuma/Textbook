# Web 基礎

## この講義の目的

* 普段利用している Web を知る

## 目次

* Web について
* HTTP について

# Web について

## Web ってなに?

Web を直訳すると **蜘蛛の巣**

    正式名称は World Wide Web (略称:WWW) 
    現在のインターネットを築いているハイパーテキストシステム

## Web と Internet

**Web** と **Internet** はよく混同されがちだが、実際は違う。

> Web

    インターネット上で提供されているハイパーテキストシステム

> Internet

    コンピュータネットワーク自体を指す言葉

Web は Internet を応用した技術なのである！！１！

## URI

> Web といえば URL, URL といえば URI

普段ブラウザ等から何気なく URL を入力して検索しているが、その URL にもちゃんとした意味がある。

    URI とは、インターネット上に存在する情報資源の場所を指し示す記述方式

そして、

    URL とは、URI の機能の一部を具体的に仕様化したもの

つまり、URI/URL はネットワーク上の「住所」のこと。この「住所」を辿って様々なものを検索してる。

<img src="https://cacoo.com/diagrams/Qk926fUQkzvxRlYj-ABE04.png" align="center">

上の URI は3つから構成されている

* スキーム - 資源(リソース)に到達するための方法/手段
* ホスト名 - 資源(リソース)を提供するホストマシン名/IP アドレス
* ファイル名 - 資源(リソース)自身のパス

## URI スキーム

ホスト名は住所、ファイル名はホストマシンの中にあるファイルということがわかった。はず。

じゃあ、スキームってなに？

URI スキーム

    インターネット上の資源の所在を表す URI(URL) の先頭部分で、資源に到達するための手段を表したもの

まとめると、http という手段でホストマシンを検索し、ホストマシン内のファイルにアクセスするということ。

## ポート番号

    インターネット上の通信において、複数の相手と同時に接続を行うための IP アドレスの下に設けられたサブ(補助)アドレス。
    単にポートと略されることもある。

# HTTP について

## HTTP とは

<pre>
HTTP とは HyperText Transfar Protocol, ハイパーテキスト(HTML で記述されたテキスト)を転送するためのプロトコル。
現在では リクエストメソッド, ステータスコード, HTTP ヘッダ などが拡張され、ハイパーテキスト以外にも利用出来るようになった。
</pre>

    WWW を支える重要な技術

HTTP で送受信出来るもの

* 画像ファイル (jpg, png, gif など)
* 音声ファイル (wave, mp3 など)
* 動画ファイル (mpeg, mp4, avi など)

## Web ブラウザ

HTTP クライアントとして最もよく使用されているのが Web ブラウザ。

主な Web ブラウザ

* Internet Explorer
* Mozilla Firefox
* Google Chrome
* Safari
* Opera

## HTTP 通信の流れ

1. Web ブラウザ等から URI を指定
2. URI を DNS サーバ へ送り、対応する IP アドレスを調べてもらう
3. 対応する IP アドレスを答える
4. 受け取った IP アドレスに対してリクエストを送る (SET, GET)
5. Web サーバ側でリクエストに対して処理を行う
6. 処理結果をクライアントへ返す
7. クライアントの Web ブラウザ等で処理結果を画面に表示する

ブラウザの拡張機能を使うと流れがわかるよ！設定しよう！

> 使い方は [Google](http://www.google.co.jp) 先生で調べてね♪

* Firefox - [Firebug](https://addons.mozilla.org/ja/firefox/addon/firebug/)
* Firefox - [Live HTTP Headers](https://addons.mozilla.org/ja/firefox/addon/live-http-headers/)
* Chrome - [Google Chrome Developer Tools](https://developers.google.com/chrome-developer-tools/?hl=ja)
* Safari - [Safari Developer Tools](https://developer.apple.com/jp/technologies/safari/developer-tools.html)

## プロトコルとは

    ネットワークを介してコンピュータ同士が通信を行う上で、相互に決められた約束事の集合。
    通信手順、通信規約などと呼ばれることもある。 

### HTTP 以外でよく利用されるプロトコル

* FTP (File Transfar Protocol)
* SMTP (Simple Mail Transfar Protocol)
* POP (Post Office Protocol)
* IMAP (Internet Message Access Protocol)

#### FTP

FTP (File Transfar Protocol) はファイル転送に使われるプロトコル

#### SMTP

SMTP (Simple Mail Transfar Protocol) は電子メールを送信するためのプロトコル

    [Mail Client] --> [Mail Server]

#### POP

POP/POP3 (Post Office Protocol) は電子メールを保存しているサーバからメールを受信するためのプロトコル

    [Mail Client] <-- [Mail Server]

#### IMAP

IMAP (Internet Message Access Protocol) は電子メールを保存しているサーバからメールを受信するためのプロトコル

POP との違いは

* メールはサーバ上のメールボックスで管理
* タイトルや発信者を見て受信するかしないかを決める
* オンライン・オフライン両方で利用できる
* 複数端末から接続できる

[GMail](http://mail.google.com/mail) や [MobileMe](http://www.apple.com/jp/mobileme/) などで採用されている。

## OSI 参照モデル

OSI 参照モデルとは

    国際標準化機構(ISO)によって策定された、コンピュータの持つべき通信機能を階層構造に分割したモデルである。
    OSI基本参照モデル、OSIモデルなどとも呼ばれ、通信機能（通信プロトコル）を7つの階層に分けて定義している。

## OSI 参照モデル7階層

<img src="https://cacoo.com/diagrams/6f3p1xNvmOy69a0b-AAF42.png" align="center">

### アプリケーション層

    アプリケーション層は、アプリケーションプロセスのための共通アプリケーションサービスへ直接接続して実行する。またプレゼンテーション層に対して要求も行う。


## どこで決めてるの？

IETF (Internet Engineering Task Force)

    インターネットに関連する技術の標準化を促し、インターネットの円滑な運用を図っている国際的組織の名称である。
    インターネットに関連する多種多様な技術の標準的仕様について議論、策定を行い、主にRFC（Request for Comment）と呼ばれる文書として公開している。TCP、POP3、UTF-8など、多数の重要な技術規格の仕様がRFCにおいて策定されている。

ちなみに、Web 関連技術の標準化は W3C が行なっている。

W3C (World Wide Web Consortium)

    HTMLやXMLをはじめとする WWW(World Wide Web) で利用される様々な技術の標準化を推進することを目的とした非営利団体の名称である。

# 詳しくは Web で検索！

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="http://i.creativecommons.org/l/by-nc-sa/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/2.1/jp/">クリエイティブ・コモンズ 表示 - 非営利 - 継承 2.1 日本 ライセンス</a> の下に提供されています。
