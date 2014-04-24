ファイルの詳細
====

ファイルの詳細情報
----

* `~/kenshu/test1/test11`を再度作ってください
* `ls -l ~/kenshu/test1`と入力してください

```
macmini-ssuzuki:~ ssuzuki$ mkdir ~/test1/test11
macmini-ssuzuki:~ ssuzuki$ ls -l ~/test1
total 8
-rw-r--r--@ 1 ssuzuki  staff  495  3 22 21:54 renshu1.txt
drwxr-xr-x  2 ssuzuki  staff   68  3 26 20:00 test11
macmini-ssuzuki:~ ssuzuki$
```

* `ls`コマンドに`-l`オプションを付けると、ファイルやディレクトリの詳細な情報が表示されます
    * `l`はLong Formatの略
* ちなみに、ファイルやディレクトリのパスを指定すると、そのファイルやディレクトリの中身についての情報を表示します
    * 指定しない場合は、`ls .`と指定しているのと同じと言う方が近い
* ファイルの所有ユーザやサイズ、最終更新日時などが表示されます
    * 1文字目が`d`になっている場合はディレクトリ、`-`の場合は普通のファイルです
* `rw-r--r--`とか書いてあるところも重要ですが、とりあえず後回し
    * パーミッション(権限)に関するものです

隠しファイルの表示
----

* `~`で`ls -a`と入力してください
    * 以下の出力例は細かくいろいろと違うかもしれませんが気にしないでください

```
macmini-ssuzuki:~ ssuzuki$ ls -a
.              Music
..             Pictures
.bash_profile  Public
Desktop        kenshu
Documents
Downloads
Library
Movies
macmini-ssuzuki:~ ssuzuki$
```

* `ls`コマンドに`-a`オプションを付けると、隠しファイルを含めた全てのファイルを表示します
* ファイル名の1文字目が`.`(ドット)で始まるものが隠しファイル(または隠しディレクトリ)です
    * 設定ファイルなどに利用されます
* ちなみに、`ls -la`と入力すると、`-l`と`-a`の両方のオプションが適用されます
