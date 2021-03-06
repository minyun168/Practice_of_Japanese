# HTMLの記述
## HTML説明
HTMLファイルはテキストファイルであり、タグ([<]と[>]で)により、文章の構造を定義します。
HTMLファイルは以下のような構成にする必要があります。

ヘッダ要素にはこのHTMLファイルに関する情報を記述し、ボディ要素には画面の構成に関する情報を記述します。

## ヘッダ要素
head要素以下には、以下のようなタグを記述することができます。
なお、これら以外にも様々なタグを記述することができますが、詳しくはWEBに多くのリファレンスがありますので、各自で調べるようにしてください。

## ボディ要素
ボディ要素以下に記述可能なタグに関しては、ログイン画面を例に説明します。
ログイン画面の場合、以下のようなHTMLタグで構成することが考えられます。

それぞれのタグの意味は以下の通りです。
これ以外にも様々なタグを記述することができます。詳しくはWEBに多くのリファレンスがありますので、各自で調べるようにしてください。

## ログイン画面HTMLの記述
実際に、ログイン画面のHTMLを記述してみましょう。
HTMLは以下のようになります。

```
code省略
```
### 3~4行目：

ヘッダ要素の記述。
titleタグでページタイトルを、metaタグで文字セットを明示しています。

###  7~36行目：

ボディ要素の記述。
ログイン画面の構成例に従ってタグを組み合わせています。
上記のファイルを適当な場所にダウンローダし、ブラウザで表示を確認してください。ブラウザには以下のように表示されます。


# CSSの記述
HTMLを書いただけの場合、各タグの表示スタイル（文字色、背景色、サイズなど）はブラウザのデフォルト定義によって決定されます。
この表示スタイルを変更したい場合は、CSSを記述する必要があります。

CSSはテキストファイルで、以下のような形式で記述します。

```
スタイルを定義したい要素 {
    プロパティ名: プロパティ値;
    ...
}
...(上記の繰り返し)
```

スタイルを定義したい要素（タグなど）を明示し、プロパティの名前と値の組を記述しています。
なお、ここでは簡単にしか説明しません。詳しくはWEBなどで調べるようにしてください。

スタイルを定義したい要素には以下のような記述をすることができます。
* 「タグ名」と書き、タグすべてに対してスタイルを指定
* 「タグ名.class名」と書き、特定のclass属性を持つタグのみに対してスタイルを指定クラス属性は、「」のようにタグに対して記述します。

また、プロパティに指定可能な値には以下のようなものがあります。

## ログイン画面CSSの記述
では、先ほどのHTMLファイルにCSSを書きくわえてみましょう。
なお、今回はCSSファイル名はtodo.cssとします。具体的には、以下のスタイルを設定することにします。

## HTMLファイルに対する変更
HTMLファイルに対する変更点は以下の通りです。

###  5行目

cssファイルへの参照を追加。
CSSファイルへの参照はlinkタグにより記述します。

各要素にclass属性を追加。
このclass 属性に対応するようにCSSファイルを記述します。
ここでは、th,tdタグなどに無条件にスタイルを設定するのではなく、画面ごとにclass属性を用いる設定することを想定しています。

## CSSファイルの記述
CSSファイルは以下のように記述します。
上記のファイルを適当な場所にダウンロードし、ブラウザで表示を確認してください。ブラウザには以下のように表示されます。


# JavaScriptの記述
ユーザの入力内容によって動的にボタンの無効/有効を切り替えたい場合があります。
このような処理はJavaScriptを記述することで実現できます。

ここでは、以下のように「ユーザID」と「パスワード」の両方に字列が入力されないと「ログイン」ボタンを無効にするようなロジックを追加してみましょう。
JavaScriptのファイル名はlogin.jsとします。

JavaScriptの記述は、部分的にはJavaによく似てはいますが、Javaとは別の言語です。

記述方法について、詳しくはWEBで調べるようにしてください。
っここではサンプルの実装に必要な最低限の項目について説明します。

## ログイン画面のJavaScript実装
では、先ほどのHTMLファイルにJavaScriptを書き加えれ見ましょう。

## HTMLファイルに対する変更
HTMLに対する重要な変更点は以下の通りです。
```
<script type="text/javascript" src="login.js">
</script>
```
JavaScriptファイルへの参照を追加。
JavaScriptファイルへの参照はscriptタグにより記述します。

### 9行目

bodyタグにonloadハンドラを追加。
読み込み完了時にfieldChanged関数を呼び出し、ボタンを無効化するようにします。

### 20~23行目

inputタグに変更時ハンドラとIDを追加。

### 31~34行目

inputタグに変更時ハンドラとIDを追加。

# JavaScriptファイルの記述
JavaScriptファイルは以下のように記述します。
フィールド変更時の処理を行うためのfieldChanged関数、およびその関数から呼び出されるgetField関数を定義しています。

ブラウザには以下のように表示されます。
「ユーザ」IDと「パスワード」に文字を入力すると、「ログイン」ボタンが有効になります。

# 一覧画面の記述
ログイン画面と同じ要領で、一覧画面を記述してみましょう。
なお、ここでは作業項目は一つとして作成していき、Servletの実装時にデータべースの内容を反映するものとします。

上記のファイルを適当な場所にダウンロードし、ブラウザで表示を確認してください。ブラウザには以下のように表示されます。ブラウザには以下のように表示されます。

# Javaプログラムの作成
Javaプログラムからデータベースに対してアクセスするためには、JDBCを利用します。
JDBCとは、Javaからデータベースに対してアクセスするための標準APIです。
パッケージjava.sqlにインタフェースおよび抽象クラスが用意してあり、データベース付属のライブラリからその実装が提供されます。

## JDBCコードの基本
JDBCは基本的に以下のように処理を記述します。

データベース付属のJDBCドライバを初期化し、java.sql.Connectionオブジェクトを取得します。
ここで指定するパラメータは接続対象のデータベースにより異なります。
H2 Databaseの場合は以下のようになります。

java.sql.ConnectionオブジェクトからStatementオブジェクトを取得し、SQL文を実行します。

一般的にはデータを取得する場合はexecuteQueryメソッドを、データを操作する場合はexecuteUpdateメソッドを呼び出します。

データベースの操作が完了したら、各オブジェクトのcloseメソッドを呼び出し、処理を完了します。

## Javaプロジェクトの作成
では実際にデータベース操作アプリケーションのコードを記述し、デバッグ·動作確認してみましょう。
ここでは以下のような動作をするアプリケーションを作成します。
* アプリケーション種別：コンソールアプリケーション
* データの取得·追加·更新·削除機能を実装します。
* 操作の種類、パラメータはコマンドライン引数として与える。

コマンドライン引数の意味は以下の通り。(実験用コードのため、引数のエラーチェックなどはしない。)

1. まずEclipseワークスペース内にプロジェクトを作成します。プロジェクトは、Eclipse上でのアプリケーションの単位です。Eclipsの「Package Exporer」上で右クリックし、「New]-「Projet...」を選択します。

2. 以下のようなダイアログが表示されるので、[Java]-[Java Project]を選択します。

3. 以下のようなダイアログが表示されるので、[Project name]に[userdb]と入力し、[Next]を押します。

4. [Libraries]タブを選択し、[Add External JARs]を押します。
5. ファイルダイアログでディレクトリ内「」を選択し、「finish」ボタンを押します。この作業により、H2　Database二アクセスするためのクラス群をuserdbプロジェクトから呼び出せるようになります。

## Javaクラスの作成
データベースにアクセスするプログラムをtest.Userクラスとして作成してみましょう。
1. testパッケージにUserDBクラスを作成します。
2. UserDB.javaとして以下のようなコードを作成します。コードのうち、重要な部分をいくつか抜粋すると以下のようになります。コンソールアプリケーションとして実行するため、main関数を定義。

JDBD接続を初期化するコードを定義。

テーブルの内容を取得するコードを定義。

テーブルにデータを追加するコードを定義。

## ここまでのファイル
ここまででプロジェクトディレクトリの内容は以下のようになります。正しく作成できているか、確認してください。

## デバッグ·動作確認
では、UserDB.javaをデバッグしましょう。
1. [Package Explorer]の[UserDB.java]アイコン上で右クリックし、[Debug As] - [Java Application]を選択します。

まだコマンドラインオプションを指定していないので、以下のようなエラーが出力されるはずです。

異なるエラーメッセージが出力された場合は、ソースコード（特にUserDB.create())が間違っていないか、H2 Dateabase が起動しているかどうかを確認してください。

2. 次に、コマンドラインオプションを指定します。[Package Explorer]の[UserDB.java]アイコン上で右クリックし、[Debug As]-[Debug Configurations...]を選択します。

3. 以下のようなダイアログボックスが表示されますので、[Arguments]タブを選択し、[Program Arguments]に[select]と入力してください。
4. [Apply]ボタンを押し入力内容を保存した後、[Close]ボタンを押しダイアログを閉じます。
5. コードの動作確認のために、ブレークポイントを設定しましょう。コードを停止したい行の左端を左ダブルクリックすると、以下のようにブレークポイントを示す印が表示されます。
6. では、改めてUserDB.javaをデバッグしましょう。
[Package Explorer]の[UserDB.java]アイコン上で右クリックし、[Debug As-[Java Applicatio]を選択します。
7. 以下のようなデバッグ画面が表示されますので、各機能を利用して順次実行します。変数ビューでの変数確認も行うようにしてください。
各機能の役割は以下の通りです。
以下のような出力が行われればデバッグ成功です。同じ要領で、insert、update、deleteも動作確認をしてください。

# 演習：作業テーブルの作成
ユーザ情報テーブルと同じ要領で、作業を格納するテーブルを記述し、データを操作するようなコンソールアプリケーションを作成してみましょう。
データ構造は以下のようにするものとします。
なお、ここまで使用したSQL文以外の知識が必要となります。WEBなどで調べながら作業してください。以下が模範解答です。コンソールアプリケーションの仕様は以下のようにしてください。

（修正されたファイルは個別にダウンロード）
（プロジェクト全体をまとめてダウンロード）

## ログイン画面の作成
まず、ログイン画面の実装を通じて、Servletの基本要素を学習していきましょう。

### プロジェクトの作成

まず、Tomcatプロジェクトを作成します。Tomcatプロジェクトを作成することで、コンテキストバ以下のファイル構造を作成し、容易にTomcatに配備することができます。コンテキストパス以下のファイル構造は以下のようにする必要があります。

WEB-INFディレクトリはWEBアプリケーションの構成情報やクラスファイルなどを格納するために利用されます。WEB-INFディレクトリ以ファイルは直接ブラウザから参照することはできません。WEB-INFディレクトリ以外のファイルは、CSSファイル、JSファイルなど、ブラウザから参照する必要がある場合に配置します。ここに配置されたファイルは、http://(サーバ名):(ポート番号)/(コンテキストパス)(コンテキストパス内でのパス
)の形で参照することができます。ログイン画面は、以下のようなファイル構造とします。

では、Tomcatプロジェクトを作成し、ログイン画面を実装していきましょう。
Eclipseの[Package Explorer]上で右クリックし、[New]-[Project...]を選択します。[Java]-[Tomcatプロジェクト]を選択します。

[Project name]に[todotest]と入力し、[Finish]を押します。

以下のようなプロジェクトがPackage Explorer上に現れれば成功です。

### Servletクラスの作成

Servletクラスを作成していきましょう。
Servletクラスはjavax.servlet.http.HttpServletクラスを継承する必要があり、目的に応じて以下のメソッドをオーバーライドします。（ほかにもいくつかのメソッドがあります。）

Servletのメソッドの処理の中で、リクエストに関する情報を取得したい場合にはjavax.servlet.http.HttpServletRequestオブジェクトを使用します。ここではサンプルに使用するメソッドのみ説明します。

Servletのメソッドの処理の中で、レスポンスに関する情報を設定したい場合にはHttpServletResponseオブジェクトを使用します。ここでは、JSPファイルによってレスポンスの内容を生成しますので、Servletの処理内では特に操作しません。Servletクラスを作成します。[WEB-INF/src]上で右クリックし、[New..]-[Class]を選択します。以下のダイアログが表示されたら、[Package][Name][Superclass]のフィールドに、以下のように値を設定します。TodoServletクラスを作成します。ここでは、GETリクエストに対する処理として、以下のような処理を記述します。

 ### パラメータの解析処理

getParameter("action")によりactionパラメータに指定された値を取得し、loginが指定された場合に転送先としてWEB-INF/jsp/login.jspを指定しています。(実際の転送処理は後述)

また、actionパラメータが指定されていない場合や、認識できないactionパラメータが指定された場合、ServletException例外をスローしてエラー終了しています。（この場合、Tomcatのエラー画面が表示されてしまいます。次のセクションで自分が作成したエラー画面へと差し替えます。

###  JSPファイルへの転送処理

先の処理で転送先として指定さてたJSPファイルへと転送を行います。

###  JSPファイルの作成

次に、JSPファイルを作成していきましょう。先に作成したlogin.js.htmlをベースとし、JSPファイルとして処理するために必要ないくつかの記述を追加していきます。

todotestプロジェクト/WEB-INFディレクトリ以下にjspディレクトリを作成します。

###  JSPファイルを作成します

先に作ったindex.js.htmlをlogin.jspにリネームし、WEB-INF/jspディレクトリにコピーします。先に作ったCSS,JavaScriptファイルをstruts2todoプロジェクト直下にコピーします。JSPファイルに以下の修正を加えます。

JSPファイルの１行目にJSPファイルに関する属性情報を追加。

フォームの送信先がServletになるように変更。また、送信メソッドとactionパラメータを設定します。

## 設定ファイルの作成
最後に、WEB-INFフォルダ以下にweb.xmlファイルを作成します。

###  7~13行目

Servletクラスの情報を定義します。

###  15~22行目

Servletクラスのパスを定義します。servlet要素の定義とはservlet-name要素の値を通じて関連付けられます。

###  ここまでのファイル

ここまででプロジェクトディレクトリの内容は以下のようになります。正しく作成で来ているか、確認してください。

###  デバッグ·動作確認

[Tomcat起動]ボタンを押します。ます、何もクエリを指定せず、意図的にエラーを起こしてみましょう。Servletは何もクエリを指定しなければ、action名が取得できず、エラーが発生するはずです。ブラウザで以下ンURLを開きます。
http://localhost:8080/todotest/todo
以下のエラー画面が現れればただしくServletは動作しています。

次に、デバッガの使用方法の確認もかねて、パラメータを指定して実行してみましょう。コンソールアプリケーションと同じ要領で、TodoServlet.javaおdoGetの初めにブレークポイントを設定します。ブラウザで以下のURLを開きます。
http://localhost:8080/todotest/todo?action=login
以下のようにEclipseのデバッガが起動します。（以下の画面構成にならない場合は、Eclipseメニューの[Window]-[Open Perspective]-[Debug]を実行してください。

デバッグ実行完了後、ブラウザに以下の画面が現れれば成功です。

## 一覧画面とエラー画面の作成
次に、一覧画面とエラー画面を実装します。修正内容は以下の通りです。

## H2 Database ライブラリのクラスパスへの追加
WEBアプリケーションからJARファイル中のクラスを参照するためには、JARファイルをWEB-INF/lib以下に配置する必要があります。H2 DatabaseライブラリをWEBアプリケーションから参照できるようにしましょう。ログイン処理及び一覧画面はデータベースアクセスを必要とするため、まず、WEB-INF/libにH2 DatabaseのJARをコピーします。C:￥Program Files\H2\bin\h2-10jarを、(todotestプロジェクト)/WEB-INF/libにコーピします。次に、todotestプロジェクトのクラスパスにH2 DatabaseのJARを登録します。todotestプロジェクト上で右クリックし、[Properties]を選択します。ダイアログが表示されたら、[Java Build Path]の[Libraries]タブを選択します。

Add JARS...ボタンを押し、（todotestプロジェクト）/WEB-INF/lib/h2-10jarを選択します。これでWEBアプリケーションからH2 Databaseのクラスを参照できるようになります。

## Javaクラスの記述

次に、Javaクラスを作成していきましょう。まず、データベースのデータを格納するための値オブジェクトを作成します。これらのクラスには、テーブルのカラム事に以下のようなメンバ変数、メソッドを実装します。

値を格納するためのメンバ変数の宣言。

値を取得するためのメソッドの宣言。JSPファイルはこのメソッドを呼び出すことで、HTMLに出力すべき値を取得します。

値を設定するためのメソッドの宣言。Servletファイルはこのメソッドを呼び出すことで、このインスタンスに値を設定します。次に。Servletクラスを記述します。postメソッド要求時の処理として、actionパラメータがlogin_actionだっだ場合の処理を記述します。

POSTメソッドの処理の実装。login_actionパラメータが要求された場合の処理、および不正なパラメータが指定された場合の処理を記述します。

ログイン処理。user_id,passwordパラメータからデータベースの内容を検索し、ユーザ情報が正しい場合はTODO_ITEMテーブルの亜内容を取得し、JSPで参照できるようにします。ItemオブジェクトはHttpServletRequest.setAttributeにより、リクエストオブジェクト内に格納します。このメソッドを呼びだすことで、JSPファイル内でHttpServletRequest.getAttributeを呼びだすことでItemオブジェクトを参照できるようになります。これは、同一のリクエスト処理中にのみ参照可能です。UserオブジェクトはHttpSession.setAttributeメソッドによりセッションオブジェクト内に格納します。セッションとはブラウザとサーバ間の一連のやりとりを識別するためのものです。セッションオブジェクトにオブジェクトを設定することで、リクエストを発行したブラウザとのやり取りの中で常にオブジェクトを参照可能です。ここで設定されたオブジェクトは後述するlist.jspによって参照されます。

エラーが発生時の処理。HttpServletRequest.setAttributeメソッドによりエラーメッセージを設定しています。ここで設定されたエラーメッセージは後述するerror.jsp似よって参照されます。

JDBC接続の初期化処理。今回は一度JDBCとの接続を確立したらそのオブジェクトを使いまわすような実装としています。接続確立は通信処理やオブジェクト生成処理をともなう非常にコストの高い処理であるため、このように回数を減らす工夫を行っています。

ユーザ情報の取得処理。取得した内容はUserオブジェクトに格納しています。Itemオブジェクトの取得も同様の手順で行っています。

## JSPファイルの記述
次に、JSPファイルを記述します。先ほどンログイン画面とは異なり、TodoServletがっ生成したオブジェクトをHttpServletRequest経由で取得し、画面表示に反映しています。先に作成したlist.htmlの拡張子をjspにリネームし、WEB-INF/jspディレクトリにコピーした後、JSPコードを追加します。

import 宣言の記述。Javaプログラムと同様、JSPコード内でクラスを参照する場合、import宣言を記述する必要があります。

Javaプログラムの記述。Javaプログラムを記述する場合、<%と%>で囲みます。ここでは、HttpServletRequestオブジェクト(変数名requestで参照可能)からセッションオブジェクトを取得し、getAttributeメソッドを使用して現在ログインしているユーザ情報を取得しています。

変数の埋め込み。変数を埋め込む場合、<%=と%>で囲みます。

制御構造の記述。Javaプロジェクトと同様に制御構造を設けて、条件文が成立した場合のみ文字列を出力することが可能です。forループ、whileループなどについても同様です。ここでは、HttpServletRequestオブジェクトからアイテムリストを取得し、その内容に応じてHTMLを生成しています。先に作成したerror.htmlの拡張子をjspにリネームし、WEB-INF/jspディレクトリにコピーした後、JSPコードを追加します。

変数の埋め込み。ここでは、HttpServletRequestオブジェクトからエラーメッセージを取得しています。

###  ここまでのファイル

ここまででプロジェクトディレクトリの内容は以下のようになります。正しく作成できているか、確認してください。

## デッバグ·動作確認
ブラウザで以下のURLを開き、動作確認を行います。

http://localhost:8080/todotest/todo?action=login

TODO_USERテーブルに登録したユーザIDとパスワードでログインし、以下のような画面が表示されれば成功です。なお、TODO_ITEMテーブルには、先に作成したItemDBコマンドラインアプリケーションを用いてあらかじめデータを登録しておきましょう。（作業項目登録画面はこの次で実装します。）

# 登録画面の作成
これまでの作業を踏まえて、登録画面を作成してみましょう。
先の実装に対して、以下のファイルを加えていきます。

## Servletクラスの追加
Servletクラスに処理を追加します。
postメソッド要求時の処理として、actionパラメータがadd,add_action,listだった場合の処理を記述します。

アクションの処理を追加

add, add_action, listパラメータが要求された場合の処理を追記します。一覧処理と同じ要領でJSPに渡すデータを設定していきます。

add-actionの処理を記述。

日本語を含むパラメータをServletで正しく受け取るためには、new String(name.getBytes("iso-8859-1"),"utf-8")のようにして、一度、文字コード[iso-8859-1]でバイト列に変換した後、改めて文字コード[UTF-8]で文字列オブジェクトに変換する必要があります。

## JSPファイルの記述
次に、JSPファイルを記述します。
先に作成したadd.htmlの拡張子をjspにリネームし、WEB-INF/jspディレクトリにコピーした後、javaコードを追加します。
一覧画面と同じ要領で変数埋め込みと繰り返す·条件分岐を埋め込みます。

### ここまでのファイル
ここまででプロジェクトディレクトリの内容は以下のようになります。正しく作成できているか、確認してください。

## デバッグ·動作確認
ブラウザで以下のURLを開き、動作確認を行います。http://localhost:8080/todotest/todo?action=login TODO_USERテーブルに登録したユーザIDとパスワードでログインし、「作業登録」ボタンを押した後、以下のような画面が表示されれば成功です。

実際に入力欄に文字を入力し、作業を登録してみましょう。エラーが表示される場合は、デバッガでどこに問題があるのか調べてみてください。

# 演習：Servletの残り機能の実装
これまでの作業を踏まえて、以下の機能を追加してみましょう。
* 完了·未完了の切り替え機能
* 更新機能
* 削除機能
* 検索機能

模範解答は以下からダウンロードしてください。
(プロジェクト全体をまとめてダウンロード)

# SQL Injection
SQL Injectionとは、以下のようにパラメータにSQLの演算子を挿入して、不正な操作を実行することを指します。
## 問題
まずは不正操作が実行できることを試してみましょう。ログイン画面で以下のようなユーザID、パスワードを入力してみてください。
* ユーザID['or("=']
* パスワード[') or "=']
これらの文字列はユーザID、パスワードとして不正であるのにも関わらず、ログインできてしまいます。 

これは、TodoServletクラスのgetUser(String userID, String password)メソッドで以下のようなSQL文を発行してしまうことに起因します。

SELECT ID, NAME FROM TODO_USER WHERE ID='' OR (''='' AND PASSWORD='') OR "="

WHERE節の末尾の条件が常に成立してしまうために、このSELECT文が常にユーザ情報を返してしまいます。

### 回避方法
この問題を回避するためには、SQL文に設定するパラメータが不正なものでないかをチェックする必要があります。
例えば、以下のようにユーザID、パスワードそれぞれに半角英数字のみを許容することで、このような問題の発生を防ぐことができます。

## Cross Site Scripting
Cross Site Scriptingとは、以下のようにパラメータにScriptタグなどのブラウザで実行可能なスクリプトを挿入して、不正な操作を実行することを指します。

### 問題
まずは不正操作が実行できることを試してみましょう。
作業登録画面で以下のようなコードを入力してみてください。
<Script>alert("Script")</Script>

この作業を登録すると、以降一覧画面を表示するたびに以下のようなダイアログが表示されてしまいます。

作業項目名として常にHTMLタグが出力されてしまうためにこのような現象が発生してしまいます。

### 回避方法
この問題を回避するためには、HTMLとして出力されることになるパラメータが不正なものでないかをチェックする必要があります。

例えば、以下のように作業項目名にHTML上意味がある文字を、HTMLとして解釈されない文字に置換することで、このような問題の発生を防ぐことができます。

## 高度なテクニック
WEBアプリケーションを作成する場合、先に説明したようなServlet、JSPを単純に作成する方法以外にも、開発を効率化したり、アプリケーションに高度な機能を付加するための様々なテクニックがあります。
ここでは、そのうちいくつかのテクニックを紹介していきます。
1. WEBアプリケーション開発フレームワーク
2. O/Rマッパーに要るデータベース操作
3. DIコンテナ
4. JavaScriptの活用(Ajax)

## WEBアプリケーション開発フレームワーク
アプリケーションの開発は、フレームワークを利用することで効率化することができます。
フレームワークとアプリケーションの土台となるソフトウェアです。
フレームワークは亜pリケーションの枠組みを定義し、その枠組みに合わせたクラス·群を提供します。
アプリケーションの開発者はフレームワークが提供するクラス·インタフェースを実装することでアプリケーションを実現します。
このように枠組みを定義し、アプリケーションごとに共通の部分をフレームワークが提供することにより、開発者が記述すべきコード量を減らすことができるなどのメリットがあります。世の中には王区のフレームワークがあり、開発したいアプリケーションの構造に応じてフレームワークを選択することが重要です。
今回は、有名なWEBアプリケーション開発フレームワークの一つであるStructs2について説明します。

### Struts2の概要

Struts２は以下のような構造のフレームワークです。（なお、Structs1とStruct2は全く違う構造です。以下の説明はStructs1には適用できませんのでご注意ください。）
Struts２はMVCという考え方に基ついて設計されています。
MVCとは、以下のようにアプリケーションをModel, View, Controllerの３種類に分割して考えるモデルです。

Struct2においては、Controllerのうち基本的なクラスはStructs２から提供されます。したがって、アプリケーション開発者はModel、Viewのみを実装すればアプリケーションを実現することができます。

これらのクラスおよびファイルを実装し、Struts2の規約に従った設定ファイルによって関連付けることでアプリケーションを実現することができます。

## Struts2によるサンプルWEBアプリケーションの仕様
では、具体できにTODO管理アプリケーションをStructs2上に再構築することでStructs2での開発作業を確認していきましょう。
この中で、実際に書くべきコードの量が減ったり、アプリケーションの柔軟性が向上することを実感してください。

サンプルは以下のような構造とします。

ActionクラスおよびJSPファイルは以下のものを用意するものとします。原則として、各アクションはServletの実装に示した仕様に従います。

### ログイン一覧画面のStrut2による実装
まず、ログイン-一覧画面の一連の流れを実装してみましょう。

## 演習：その他の機能の実装
ログイン画面·一覧画面以外をStruts2上で実装してみましょう。

演習：その他の機能の実装

# ログイン-一覧画面のStruts2による実装
では、具体的にTODO管理アプリケーションをStrut2上に再構築することでStruts2での開発を確認していきましょう。
まず、ログイン画面から一覧画面までを実装してみましょう。

## プロジェクトの作成
strutstodoアプリケーションを作成するため、Eclipseワークスペース上にプロジェクトを作成しましょう。なお、プロジェクト名はコンテキストパスに対応して、struts2todo とします。
また、Struts2を利用するためにはStruts2によって提供されるライブラリファイルをクラスパス上に配置する必要があります。以下の手順で作業を行ってください。

1. struts2todoプロジェクトを作成します。ログイン画面の作成と同じ要領でTomcatプロジェクトを作成してください。
2. 以下のファイルをダウンロードし、適当なディレクトリに展開してください。
3. Struts2に関するJARファイルをWEB-INF/libにコピーします。zipファイルのstruts-2.1.6/libディレクトリから以下のファイルをWEB-INF/libにコピーしてください。
4. WEB-INF/libにH2　DatabaseのJARをコピーします。
5. struts2todoプロジェクトを右クリックし[Properties]を選択し、[Java Build Path]にWEB-INF/lib以下のJARファイルを設定してください。これで、JavaプログラムからJARファイル内にあるクラスを参照可能になります。

### Action クラスの実装
以下のようなクラス構成で実装します。
1. データを保持するためのUser,Itemクラスを記述します。WEB-INF/src以下に[test]パッケージを作成し、以下のようなクラスを作成します。
2. 抽象actionクラスを記述します。ここでは、全アクションに共通、JDBC接続の確立処理とセッション情報の管理処理を実装します。インタフェースorg.apache.struts2.interceptor.SessionAwareを実装することの宣言。セッション情報を格納·取得するためにはこのインタフェースを実装する必要があります。

SessionAwareインタフェースのメソッドの実装。
セッション情報を格納·取得するためのMapオブジェクトが設定されます。
現在ログインしているユーザ情報を取得する処理。セッション情報を格納したMapからUserオブジェクトを取得しています。
JDBC接続の確立処理。

3. Actionクラスを記述します。
先ほどの抽象Actionクラスを継承し、Action固有の処理を実装します。アクションとクラス·メドッドの対応関係は以下のようにします。また、パラメータにかんしてはServlet実装と同じにします。

リクエスト中のuser_idパラメータ受付処理。
リクエストパラメータはsetterメソッドにより受け入れることが可能です。ActionクラスではHttpServletRequestなどのクラスを考慮する必要はありません。
リクエスト中のpasswordパラメータ受け処理。

loginアクションの処理。

戻り値はアクション処理後にどのJSPファイルへ転送するかを示します。

login_actionアクションの処理。

戻り値はアクション処理後にどの処理へ転送するかを示します。
ユーザIDとパスワードが不正などのエラーが発生した場合はerrorを、ログイン成功した場合はsuccessを返します。
この戻り値はStruts2で解釈され、このご記述するstruts.xmlに従って別の処理に転送されます。

4. 同じ要領でListActionクラスを作成します。

### JSPファイルの実装
JSPファイルを実装します。
ここでは、以下のファイルを実装します。

1. ログイン画面のJSPファイルを記述します。WEB-INF/jsp以下に以下のようなファイルを作成します。

Struts2ではタグライブラリが用意されており、開発者は直接Javaコードを記述しなくても簡単にJSPが記述できるようになっています。
タグは以下のようなものが記述可能です。

Struts2のタグライブラリを使用することの宣言。

タグライブラリを使用したform定義。

formを簡単に定義するためのs:formタグを使用することで、table定義など面倒なHTML記述をすることなくシンプルにformを定義することができます。

2. エラー画面のJSPファイルを記述します。

Actionの値をJSP中に出力。

s:propertyタグを記述することで、転送元のActionのgetterを呼び出し、JSP中に埋め込んでいます。

3. 一覧画面のJSPファイルを記述します。

転送元のActionの値による条件分岐。
s:ifタグによって条件分岐を行います。条件文中の値は、s:propertyと同様に転送元のActionのgetterを呼び出すことで取得しています。

転送元のActionの値による繰り返しと変数の管理処理。
s:iteratorタグによって繰り返しをおこないます。また、s:setタグにより変数に値を設定しています。

4. 先に作ったCSS,JavaScriptファイルをstruts2todoプロジェクト直下にコピーします。CSSについてはStruts2のformタグに合わせて一部修正しています。

## 設定ファイルの記述
1. WEB-INF以下にweb.xmlを作成します。ここでは、Struts2が提供するクラスをパラメータに指定します。
2. WEB-INF/src以下にstruts.xmlを作成します。ここでは、これから記述するActionとJSPの定義をパラメータに指定します。

loginアクションの定義。

アクションクラス名とメソッド名、結果文字列によってどのJSPファイルに転送するかを設定します。
別のアクションへの転送定義。result要素にtype="chain"と記述することで別のアクションに転送することも可能です。
 
###  ここまでのファイル
ここまででプロジェクトディレクトリの内容は以下のようになります。正しく作成できているか、確認してください。

### デバッグ
ブラウザで以下のURLを開きます。
http://localhost:8080/struts2todo/login.action

Servletから実装する場合に比べて、アクション事に分配する処理などを記述する必要がなくなり、個々の機能の独立性が高くなっていることがわかると思います。

このようにWEBアプリケーションフレームワークを活用することで、モジュール化、再利用を促進することができるようになります。

# 演習:　その他の機能の実装
ログイン画面·一覧画面以外をStruts2上で実装してみましょう。
実装するアクションおよびJSPファイルの対応関係は以下のようにしてください。

模範解答は以下からダウンロードしてください。
（修正されたファイルを個別にダウンロード）

# O/Rマッパーによるデータベース操作

O/Rマッパーとは、オブジェクトとデータベースの間の関係を定義するだけで、データベースアクセスが行えるシステムです。

ここまでの作業では、データベースアクセス処理は、以下のようにサーバ処理内に直接開発者が手作業で記述していました。JDBC接続の初期化からSQLの発行、必要な値の取得などをすべて開発者が記述しています。

O/Rマッパーを使用すると、開発者はアノテーションや設定ファイルの形でデータベースとクラスのかんけーを定義するだけで、O/Rマッパーが接続に必要な処理を自動的に生成します。開発者がDBアクセス処理を記述する必要はありません。

設定ファイルとアノテーションの記述方法はJPA(Java Persistence API）として標準化されています。

今回はO/RマッパーであるHibernateを使って、JPAを使用してみます。

# JPAの概要
JPAは、データベースとJavaオブジェクト間のマッピングを実現する規格です。

JPAはいあkの要素から構成されています。

## ユーザ情報テーブルでのHibernate利用
ユーザ情報テーブルに関する処理をHibernateで実装してみましょう。

## 演習：作業項目テーブルアクセス実装の実装
作業項目テーブルをHibernateで実装してみましょう。

# ユーザ情報テーブルでのHibernate利用
はじめに、ユーザ情報テーブルに対して、Hibernateを利用してO/Rマッピングを作成してみましょう。

JPAにおいては、基本的には、一つのJavaクラスを一つのテーブルに対応させ、そのクラス内のプロパティ、setterメソッド(set(プロパティ名))、getterメソッド(get(プロパティ名))をテーブル内のカラムと対応させる必要があります。

WEBアプリケーション開発フレームワークで作成したstruts2todoプロジェクトに対して、以下のような構造で作成するものとします。
* Javaオブジェクト：test.User
* テーブル：TODO_USER
* メソッド-カラムの関係付け

## Hibernateを使用可能にする
まず、Hibernate関連のファイルをダウンロードし、プロジェクトのクラスパスに追加しましょう。

1. 以下のファイルをダウンロードし、適当なディレクトリに展開してください。

2. Struts2に関連するJARファイルをWEB-INF/libにコピーします。先ほど展開したzipファイルから以下のファイルをWEB-INF/libにコピーしてください。

3. struts2todoプロジェクトを右クリックし[Properties]を選択し、[Java Build Path]に前記で追加したWEB-INF/lib以下のJARファイルを設定してください。これで、JavaプログラムからJARファイル内にあるクラスを参照可能になります。

これで、JavaプログラムからJARファイル内にあるクラスを参照可能になります。

## アノテーションの追加
Javaクラスにアノテーションを追加していきます。アノテーションとは、@から始まる文字列をクラスb定義やメンバ定義に付加することで、クラスやメンバに追加譲情報を定義する手法です。

JPAでは、以下のようなアノテーションを定義することができます。
test.Userクラスを以下のように修正します。

UserクラスがTODO_USERと関連づいたクラスであることの宣言。JPAのアノテーションルールに従って、[@(アノテーション情報)]の形式で情報を付加します。

IdプロパティがIDであることと、カラム名がIDであることの宣言。

 Nameプロパティに対応するカラム名がNAMEであることの宣言。同様に、Passwordプロパティに関しても定義をおこないます。
 
 ### Actionクラスの修正
 データベースからおd－多取得処理をJPAを利用する形に修正していきます。
 データベースからデータを取得するためには、Hibernateが提供するjavax.persistence.EntityManagerオブジェクトを利用します。
 
 具体的には、以下のメソッドを使用してデータベースからオブジェクトを取得する処理を実装します。
 
 また、JPQLは以下のような形式で記述することができます。
 
 Actionクラスを、JPAが提供するjavax.persistene.EntityManagerクラスを利用するように修正します。
 
 EntityManagerを取得する処理。
 後述する設定ファイルに記述された設定名(今回は"sample")をキーとしてEntityManagerを取得します。
 
 EntityManagerから特定のIDを持つUserを取得する処理。JPQLをクエリとしてUserオブジェクトの取得を行います。
 EntityManagerから全Userを取得する処理
 
 ## 設定ファイルの作成
 設定ファイルを作成します。
 WEB-INF/src/META-INF以下にpersistence.xmlを作成します。ここでは、データベースの情報などを指定します。
 
 Userクラスを永続化すルことの宣言。
 
 接続対象のデータベースに関する宣言。
 H2　Databaseに接続することを指定しています。dialectとは、データベース間のSQLにおける方言を吸収するためのクラスです。接続するデータベースにより、この指定を変更する必要があります。
 
 ###　ここまでのファイル
 ここまででプロジェクトディレクトリの内容は以下のようになります。正しく作成できているか、確認してください。
 
 ### デバッグ
 ブラウザで以下のURLを開きます。
 
 http://localhost:8080/struts2todo/login.action
 
### 作業項目テーブルアクセス実装の実装

作業項目テーブルをHibernateで実装してみましょう。

クラスの定義は以下のようにします。
* Javaオブジェクト: test.Item
* テーブル：TODO_ITEM
* メソッド-カラムの関係付け

javax.persistence.GenerationType.AUTOで定義可能。

模範解答は以下からダウンロードしてください。
(修正されたファイルを個別にダウンロード)
(プロジェクト全体をまとめてダウンロード)

## DIコンテナ
DIコンテナとは、アプリケーションにDI(Dependency Injection: 依存性注入)機能を提供するフレームワークです。

依存性注入とはソフトウェアのうち、外部の環境などに依存する部分(データへのアクセスなど)を切り離し、ソフトウェアの外部から提供できるようにするという考え方です。

共有型TODO管理アプリケーションを例にすると、これまでは以下のようにActionがEntityManagerに直接アクセスしていました。。この構造の場合、開発中など、データベースアクセスせず、仮のオブジェクトにアクセスするようにしたい場合はActionを修正しなければなりません。

### ここまでの処理
DIコンテナを使用する場合、以下のように、インタフェースRepositoryを追加し、Actionはそのインタフェスにたいしてアクセスするように処理を実装します。DIコンテナは、インタフェースに対する実装の選択機能を提供します。

これにより、開発中はテスト用にデータはメモリ上に格納、参照するようなMockRepositoryクラスを使用し、運用時には実際にデータベースにアクセスするようなDBRepositoryクラスを使用することができ、実際のデータベースにアクセスできない環境でも開発をおこなえるようになります。

DIコンテナには以下のようなものがあります。
ここでは、Guiceを例にDIコンテナを使用してみましょう。
* Spring
* Seaasar
* Guiceを例にDIコンテナを使用してみましょう。

### Guiceの概要
Guiceは、Googleが開発·配布しているDIコンテナです。
非常にシンプルな構造が特徴です。

Guiceでオブジェクトを実装する場合、以下のようなクラスを作成する必要があります。

以下の手順でGuiceの処理を呼び出すことで、クライアントクラスとサーバスの実装カラスの関連付けを行うことができます。
1. Binderにサービスのインタフェースとサービスの実装クラスの対応付けを登録する。
2. Injectorにクライアントクラスのインスタンス化を依頼する。この時、クライアントクラスにはサービスの実装クラスのインスタンスが渡されます。

### Guiceを使った依存オブジェクト切り離し
では、実際にGuiceを利用してDIコンテナを利用したアプリケーションを実装してみましょう。

Guiceを使った依存オブジェクト切り離し 

## 演習：作業項目テーブルアクセス部分の分離
作業項目テーブルにアクセスしている部分を依存部分として切り離してみましょう。

演習：作業項目テーブルアクセス部分の分離

## Guiceを使った依存オブジェクト切り離し
では、実際にユーザ処理を依存部分としてきりはなしてみましょう。以下のようにインタフェースおよびクラスを追加·修正することにします。以下のようにインタフェースおよびクラスを追加·修正することにします。

### Guiceを使用可能にする
1. 以下のファイルをダウンロードし、適当なディレクトリに展開してください。
2. Guiceに関連するJARファイルをWEB-INF/libにコピーします。zipファイルから以下のファイルをWEB-INF/libにコピーしてください。
3. struts2todoプロジェクトを右クリックし[Properties]を選択し、[Java Build Path]にWEB-INF/lib以下のJARファイルを設定してください。

これで、JavaプログラムからJARファイル内にあるクラスを参照可能になります。

## サービスとクライアントの実装
依存部分のインタフェース、および実装クラスを記述します。

サービスのインタフェースの宣言。
アノテーションにより、test.mock.MockRepositoryをサービスの実装として使用することを宣言します。サービスの実装を変更したい場合はアノテーションの内容を変更します。

ユーザ情報を定数として宣言。
この実装では、ユーザ情報チェック時の処理はこの定数に基づいて行います。

ユーザ情報の取得処理の実装。
この実装では、JPAによってデータベースの内容を参照しています。
ActionクラスをRepositoryインタフェースを使用するように修正します。

設定ファイルの記述

WEB-INF/web.xmlを以下のように修正します。
ここでは、GuiceをWEBアプリケーションに組み込むことを指定します。

Guice　Servlet Filterの宣言。

Guice Servlet　Filterの呼び出し条件。
struts2todo以下のすべてのパスに対するリクエストに対して、Guice　Servlet　Filterを呼び出します。

### ここまでのファイル
ここまででプロジェクトディレクトリの内容は以下のようになります。正しく作成できているか、確認してください。

### デバッグ
1. まず、MockRepositoryサービスで動作確認を行います。ブラウザで以下のURLを開きます。

http://localhost:8080/struts2todo/login.action
2. 次に、RepositoryインタフェースのImplementedByアノテーションの値をDBRepositoryに変更し、動作確認を行います。
ブラウザで以下のURLを開きます。

# JavaScriptの活用　
Ajax(Asynchronous JavaScript+XML)とは、JavaScriptを活用したWEBアプリケーション作成手法です。

これまで作成してきた画面は、以下のように画面を遷移するたびにformタグからリクエストし、レスポンスとして受け取ったHTMLをブラウザ画面に反映することで実現してきました。

### ここまでの処理
このやり方はシンプルですが、画面遷移ごとに毎回画面全体のHTMLを書き換えることになります。これには以下のような問題があります。
* フォームへの入力途中でサーバとのやり取りができない...項目の入力ごとに値をチェックしたり、項目に入力された値によって別の項目の内容を変化させるなどができない。（フォームの内容をすべて入力しないとリクエストできない）
* 画面の部分更新ができない...変化させたい部分だけを更新することができない。（サーバへのリクエスト発行時はブラウザで表示しているすべてのHTMLを置き換えなければならない。）

そこで、Ajaxでは、JavaScriptからサーバに対してリクエストを発行し、そのレスポンスをJavaScriptが解釈して画面に表示している内容を変更することで画面遷移を行います。

JavaScriptを使い、クライアントで動作するロジックを作成することで、これまでの作成方法と比べより対話的なWEBアプリケーションを作成することができるようになります。

## Ajaxに使用される技術
### リクエストの発行·レスポンスの受け取り
リクエストの発行とレスポンスの受け取りにはXMLHttpRequestを利用します。
XMLHttpRequestとは、JavaScriptから利用可能なオブジェクトで、多くのブラウザで提供されています。

このオブジェクトを利用することで、任意のHTTPリクエストを発行し、そのレスポンスを取得することができます。XMLと名前がついていますが、XML以外のデータのやり取りも可能です。

XMLHttpRequestをはじめとするJavaScriptオブジェクト、関数にはブラウザ間の互換性の問題があるため、注意が必要です。

これは、ブラウザ、JavaScriptオブジェクトの実装がばらばらに行われ、単一の明確な仕様に基づいて実装されてこなかったことに起因しています。

今回は、ライブラリprototype.jsを利用し演習を行います。
prototype.jsはブラウザ菅の互換性を吸収するよう名実装となっているため、XMLHttpRequestなどのブラウザ間の互換性の問題を気にすることなく処理を実装することができます。

### レスポンスの解析
JavaScriptがレスポンスを解析する場合には、以下の二つの方法がよく利用されます。

### XML
XML(Extensible Markup Language)とは、タグ付け(<タグ>...)によりツリー形式でデータを表現する方法です。XMLによって表現されたデータの構造をJavaScriptで解析し、処理を行います。今回はXMLを使わず、以下のJSONを使用します。

### JSON
JSON(JavaScript Object Notation)とは、JavaScriptの値定義記述(配列、ハッシュなど)によって構造をもったデータを表現する方法です。JSONによって表現されたデータをJavaScript式として評価することでレスポンスの内容を変数に取り込み、処理を行います。

### 画面の更新
レスポンスから処理された情報を画面に反映するには、DOMを利用します。DOM(Document Object Model)とは、JavaScriptから表示中のHTMLのオブジェクト構造を操作するための規格です。

HTML文書ははNodeオブジェクトのツリーとして表現され、タグ(DOMにおいては要素と呼びます)はElementオブジェクト、テキストはTextオブジェクトとして表現されます。いずれもNodeオブジェクトのサブクラスです。

文書のルートはdocumentグローバル変数で取得することができ、HTML文書の内容に応じて以下のような構想となります。

Ajaxでは、レスポンスの内容に応じて、DOMを通じてHTML文書の構造を操作します。

## Ajaxを利用した機能の仕様
ここでは、演習として、以下のような機能を実装してみましょう。

### ソート機能の実装
ソート機能の実装を行ってみましょう。

### 演習：追加·編集·削除画面のAjax化
追加·編集·削除画面のAjax化を行ってみましょう。

# 演習：作業項目テーブルアクセス部分の分離

作業項目テーブルにアクセスしている部分を依存部分として切り離してみましょう。

Repositoryインタフェースに対して、以下のメソッドを追加し、各アクションの処理をRepositoryインタフェースを使った処理に修正してみてください。

* アイテムの一覧取得
* 指定されたIDを持つアイテムの取得
* 指定されたIDを持つアイテムの削除
* 指定されたアイテムの追加
* 指定されたIDを持つアイテムの更新

模範解答は以下からダウンロードしてください。
（修正）されたファイルを個別にダウンロード）

## ソート機能の実装
Ajaxを利用してソートソート機能を実装してみましょう。以下のようにファイルを修正していきます。
## サーバプログラムの修正
### JSON出力プラグインの追加とlist_jsonアクションんの追加
サーバの処理にlist_jsonアクションを追加します。

Struts2には、JSON出力を簡単に実現できるプラグインが存在します。ここでは、プラグインを利用し、アプリケーションにJSON出力機能を付加します。また、ListAction.javaにソート用のパラメータおよび処理を追加します。
1. 以下のファイルをダウンロードし、WEB-INF/libにコーピしてください。
2. struts2todoプロジェクトを右クリックし[Properties]を選択し、[Java Buil Path]にWEB-INF/lib以下のJARファイルを設定してください。

これで、JavaプログラムからJARファイル内にあるクラスを参照可能になります。

3. WEB-INF/src/struts.xmlを以下のように修正します。ここでは、ブラウザからの要求に応じてソートした作業一覧をJSONで送信することを設定します。

JSONパッケージを利用するために、パッケージをjson-defaultパッケージをベースとしたパッケージに変更。この宣言により、パッケージ内でJSON出力機能を利用することができるようになります。

JSON出力をおこなうアクションlist_jsonの宣言。
result要素のtype属性に"json"を指定することで、アクションの持つgetterメソッドから取得可能なプロパティを自動的にJSONデータ化することができます。ここでは、セキュリティの観点から、パスワード情報はJSONデータに含めないように宣言しています。

### Javaクラスの修正
Javaクラスに対してソート機能を追加していきます。
1. Repositoryインタフェースおよびその実装クラスにソート機能を実装します。アイテムリストを取得するためのメソッドItem[] queryItems(String keywords)にたいしてソート用のカラム名を設定します。以下のようにコードを修正してください。

queryItemsメソッドに引数orderByを追加。
MockRepositoryクラスでは、orderByが指定されても特に処理はおこなわないものとします。
引数orderByが指定された場合、JPQL文字列内にORDER BYを加え、クエル発行時にソートするようにします。
2. アクションクラスを修正します。以下のようにコードを修正してください。

orderByプロパティの宣言。
orderByプロパティのsetter,getterメソッドの宣言。
currentUserプロパティの宣言。
JSONかする際にListActionクラスで宣言された全getterからオブジェクトが取得されます。
queryItemsメソッド呼び出しの修正。
SearchActionクラスも同様の修正を実施します。

## クライアントの修正
ブラウザ側でユーザの入力を受けつけ、処理を行うJavaScriptプログラムを一覧画面に追加します。
JavaScriptで記述する処理のうち、主要なものは以下のとおりです。

1. 以下のファイルをダウンロードし、struts2todoプロジェクト以下にコピーしてください。
2. ブラウザ部分のプログラムを作成します。以下のようなコードを作成してください。

ロードするJavaScriptファイルの定義。
前の手順で配置したprototype.jsとこれから作成するlist.jsを配置します。

テーブルに関するID定義。
スクリプトによるテーブルの操作は、このIDを介しておこないます。

ソートボタンの定義。
スタイルシートによりカーソル形状を定義し、マウス移動、クリック時にスクリプトの関数を呼び出すように設定しています。

サーバに対するリクエスト·レスポンス処理。prototype.jsのAjaxRequest関数を利用しています。成功時にはレスポンスをJSONとみなしオブジェクトに変換し、Updateオブジェクトのupdate関数を呼び出します。

レスポンスのDOMへの反映処理。
レスポンスの解析によって作成されたオブジェクトの値をテーブルの各要素へと反映していきます。

ソートボタンに関するスタイル宣言。

cursorプロパティを定義することで、オブジェクト上にマウスポインタがある場合のカーソル形状をカスタマイズすることが可能です。  

### ここまでのファイル
ここまででプロジェクトディレクトリの内容は以下のようになります。正しく作成できているか、確認してください。正しく作成できているか、確認してください。

ダウンロード struts2todo 1.zip

### デバッグ
ブラウザで以下のURLを開きます。
一覧画面の各カラムのソートボタンを押したときに、テーブルの順序が入れ替われば成功です。

http://localhost:8080/struts2todo/login.action

## 演習：追加·編集·削除画面のAjax化
ソート機能の実装を参考に、JavaScriptを用いて追加·編集·削除画面をajax化してみましょう。
モーダルダイアログボックスの処理は煩雑であるため、以下のライブラリを使用してください。

ダウンロード windows js 1.3.zip

模範解答は以下からダウンロードしてください。

(修正されたファイルを個別にダウンロード)　ダウンロード　...

(プロジェクト全体をまとめてダウンロード) ダウンロード　...