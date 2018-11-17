# リングバッファの演習

# 進め方
## はじめてのとき
* [GitHub](https://github.com/)のアカウントを作成してください
* [Travis CI](https://travis-ci.org/) のアカウントを作成してください
* GitHubのアカウントを[こちらのフォーム](https://goo.gl/forms/anAdoxqPKVt8sJGZ2)から教えてください。
## 毎回の進め方
* このリポジトリをforkしてください
* Travis CI を設定して、自動ビルドが通るようにしてください
   * Travis CI のGitHubアカウントでの登録とforkしたリポジトリをTravisCI側で許可する
   * 参考サイト：[Travis CI入門 Travis CIとGitHubでCIを実現する方法(Change the World!)](http://changesworlds.com/2014/09/introduction-to-travis-ci-and-github-001/)
* forkしたリポジトリの README.md ファイルの「t-kougei-game-comp-2018」の部分を自分のGitHubアカウント名に差し替えてください(2箇所)
* 問題を解いて、テストを通るようにしてください。
* fork 元の master ブランチにプルリクエストを投げてください

# テスト結果

[![Build Status](https://travis-ci.org/oonuki1030/07_ring_buffer.svg?branch=master)](https://travis-ci.org/oonuki1030/07_ring_buffer)

# 今回の問題

リングバッファの勉強です。

入力される数字を順次格納して、取り出すように指示されたら、要素をFIFOで取り出してください。取り出す際に取り出したデータの値を出力してください。

input?.txt ファイルを標準入力として読み込んで、標準出力の結果を output?.txt ファイルと一致するか比較するテストをします。

main.c ファイルだけを書き換えて下さい。

## 入力される値
入力は以下のフォーマットで与えられます。
~~~
n
n
n
n
~~~

nの値に応じて、処理を変えてください。
* 0: 現在のバッファに格納されている全てのデータを古い順に「,」で区切って表示する
* -1: リングバッファからデータを取り出す
* それ以外の値: バッファにデータを追加する

## 期待する出力

取り出された際に、取り出されたデータの値を表示するか、0が入力された際に、その時点のリストを表示します。

最後は改行し、余計な文字、空行を含んではいけません。

## 条件
すべてのテストケースで以下の条件を満たします。
* -1 <= n <= 100

リングバッファが格納できるデータ個数は10個とします。それ以上に格納しようとしても何も処理されないものとします。

リングバッファに送られていない状態で取り出そうとする場合は、改行を出力します。

## 入力例1
~~~
100
-1
~~~
* 1行目の数字は正で、リングバッファにデータが積まれることを期待します
* 2行目の値は「-1」なので、古いデータが取り出され、取り出されたデータ(100)を出力します。

## 出力例1
~~~
100
~~~

## 入力例2
~~~
1
2
3
0
-1
4
0
~~~

## 出力例2
~~~
1,2,3
1
2,3,4
~~~
