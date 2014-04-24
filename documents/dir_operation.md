ディレクトリ操作
====

ディレクトリを作る
----

* `mkdir kenshu`と入力してください
    * `ls`で`~`の中を表示してみてください
* `mkdir kenshu2`と入力してください
    * `ls`で`~`の中を表示してみてください

```
macmini-ssuzuki:~ ssuzuki$ mkdir kenshu
macmini-ssuzuki:~ ssuzuki$ ls
Desktop       kenshu
Documents
Downloads
Library
Movies
Music
Pictures
Public
macmini-ssuzuki:~ ssuzuki$ mkdir kenshu2
macmini-ssuzuki:~ ssuzuki$ ls
Desktop       kenshu
Documents     kenshu2
Downloads
Library
Movies
Music
Pictures
Public
macmini-ssuzuki:~ ssuzuki$ 
```

* `mkdir`は、新しいディレクトリを作成するコマンドです
    * make directoryの略
* 今`~`の下に`kenshu`と`kenshu2`というディレクトリが作成されました

ディレクトリを移動する
----

* `cd kenshu`と入力してください
    * そして`pwd`や`ls`をしてみてください

```
macmini-ssuzuki:~ ssuzuki$ cd kenshu
macmini-ssuzuki:kenshu ssuzuki$ pwd
/Users/ssuzuki/kenshu
macmini-ssuzuki:kenshu ssuzuki$ ls
macmini-ssuzuki:kenshu ssuzuki$
```

* `cd`は、指定したディレクトリに移動するコマンドです
    * change directory
* 移動したことによって、カレントディレクトリは`/Users/ssuzuki/kenshu`になりました
    * これからはここで作業をすることになります
* 今作ったばかりのディレクトリなので、中身は何もありません

上のディレクトリに戻る
----

* `cd ..`(ドット2つ)と入力してください

```
macmini-ssuzuki:kenshu ssuzuki$ cd ..
macmini-ssuzuki:~ ssuzuki$ pwd
/Users/ssuzuki
macmini-ssuzuki:~ ssuzuki$
```

* `..`は、「1つ上のディレクトリ」を意味します
    * `/Users/ssuzuki/kenshu`の場合は`/Users/ssuzuki`
* 基本的に下に移動するときは名前を直接指定し、上に戻るときは`..`を使うことになります

ディレクトリを削除する
----

* `rmdir kenshu2`と入力してください
    * `ls`で`~`の中を表示してみてください

```
macmini-ssuzuki:~ ssuzuki$ rmdir kenshu2
macmini-ssuzuki:~ ssuzuki$ ls
Desktop       kenshu
Documents
Downloads
Library
Movies
Music
Pictures
Public
macmini-ssuzuki:~ ssuzuki$
```

* `rmdir`は、指定したディレクトリを削除するコマンドです
    * remove directoryの略
    * 空のディレクトリでない場合は削除できません
* 今`~`の下の`kenshu2`というディレクトリが削除されました

ホームディレクトリに戻る
----

* 一旦ルートディレクトリに移動してから、単に`cd`と入力してください

```
macmini-ssuzuki:~ ssuzuki$ cd ..
macmini-ssuzuki:Users ssuzuki$ cd ..
macmini-ssuzuki:/ ssuzuki$ pwd
/
macmini-ssuzuki:/ ssuzuki$ cd
macmini-ssuzuki:~ ssuzuki$ pwd
/Users/ssuzuki
macmini-ssuzuki:~ ssuzuki$
```

* 単に`cd`と入力すると、ホームディレクトリに戻ります
    * もちろん`cd ~`でもOK
