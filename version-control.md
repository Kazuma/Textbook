# バージョン管理

## この講義の目的

* バージョン管理について知る
* 実際にバージョン管理システムに触れる

## 目次

* バージョン管理について
* バージョン管理システムの種類
* 管理方法


## バージョン管理について

バージョン管理(バージョン管理システム)とは


    プロジェクト内のさまざまなファイルの変更履歴を管理すること。また、そのシステム
    たとえば、ソースコードやドキュメント、 ウェブページなどがバージョン管理の対象となる。 

バージョン管理の基本的な機能

    バージョン管理システムの最も基本的な機能は、ファイルの作成日時、変更日時、変更点などの履歴を保管することである。
    これにより、何度も変更を加えたファイルであっても、過去の状態や変更内容を確認したり、変更前の状態を復元することが容易になる。
    更に、多くのバージョン管理システムでは、複数の人間がファイルの編集に関わる状況を想定している。
    商業的なソフトウェア開発やオープンソースプロジェクトなどでは、複数の人間が複数のファイルを各々編集するため、それぞれのファイルの最新の状態が分からなくなったり、同一ファイルに対する変更が競合するなどの問題が生じやすいが、バージョン管理システムは、このような問題を解決する仕組みを提供する。

バージョン管理の利点

* ファイルを過去のバージョンへ簡単に戻せる
* 過去のコミット履歴を閲覧できる


## バージョン管理システムの種類

バージョン管理システムには **中央集中型** と **分散型** がある

### 中央集中型

**CVS (Concurrent Versions System)**

    複数人が同時に同じファイルを編集することができ、編集した内容が競合していなければ両方の変更を自動的に統合できる
    また、1つのバージョンに対して別々の変更を加えるためにバージョンを分岐させることも可能

**SVN (Subversion)**

    CVS を参考に開発されたバージョン管理システム
    CVS から変更された点は、リビジョンの番号のつけ方、メタデータを付与できるようになった点、Webブラウザなどとの連携を図ることが可能になっている点などがある

### 分散型

**Git**

    Linuxカーネルのソースコード管理を目的として作られたバージョン管理システム
    ワーキングディレクトリがリポジトリの全ての履歴を含んでいるため、中央サーバへのアクセスが不可能な状態であってもリビジョン間の履歴を調査することができる

**Mercurial**

    Python で実装されたクロスプラットフォームのバージョン管理システム


## 管理方法

Subversion(中央集中型)、Git(分散型) それぞれの管理方法

### Subversion

* 中央リポジトリからコピーする
* コピーしたリポジトリを編集し、コンテンツの修正、追加、削除を行う
* 中央リポジトリへコミットする

#### インストール方法

`apt-get install subversion`

#### リポジトリをローカルへコピー

`svn checkout http://hoge.co.jp/repos/hoge hoge/`

#### ファイルを追加

`svn add hoge.txt`

#### ファイルをコミット

`svn commit -m 'add hoge.txt' hoge.txt`

#### リポジトリの更新

`svn update`

### Git

* 中央リポジトリからコピーする
* コピーしたリポジトリを編集し、コンテンツの修正、追加、削除を行う
* ローカルへコミットする
* 中央リポジトリへ変更内容を反映させる

#### インストール方法

`apt-get install git`

#### リポジトリをローカルリポジトリへコピー

`git clone git://hoge.co.jp/hoge`

#### ファイルを追加

`git add hoge.txt`

#### ファイルをコミット

`git commit -m 'add hoge.txt'`

#### 中央リポジトリへ変更を適用

`git push`

#### リポジトリの更新

`git pull`

### おまけ

[@naotos](https://twitter.com/#!/naotos) さんがすすめる [Manual Version Control](http://d.hatena.ne.jp/naoSora/20110317/1300323187) もあるよ！


<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="http://i.creativecommons.org/l/by-nc-sa/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/2.1/jp/">クリエイティブ・コモンズ 表示 - 非営利 - 継承 2.1 日本 ライセンス</a> の下に提供されています。