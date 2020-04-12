# laral_manegement_site
laravel開発用
これをフォークすることによりプロジェクトを作成してください。

homestead,vagrant,virtualboxな環境です。
あらかじめ
vagrant,virtualbox,vagrant-vbguest
はインストールしてください。
フォークしたプロジェクトは
```
$ cd laravel_dev
$ git submodule init homestead_vagrant/
$ git submodule update homestead_vagrant/
$ cd homestead_vagrant
$ vagrant up
```
で簡単にvagrant環境を作成することができ、

vagrant guestOS側で
```
vagrant@vagrant:~/projects/:$ laravel new your_project
```

という形でlaravel環境を作成することができます。

host側からみると
laravel_dev/projects/
配下にプロジェクトが作成されます。

vscodeなどでホスト側から
ファイルを修正することができます。

コマンドを打つときはguest側の
osからコマンドを入力してください。

## visual studiocodeでの開発について
ほぼ必須なプラグイン一覧

```
$ code --install-extension onecentlin.laravel5-snippets # Laravel Snippets
$ code --install-extension onecentlin.laravel-blade # Laravel Blade Snippets
$ code --install-extension thekalinga.bootstrap4-vscode # Bootstrap 4, Font awesome 4, Font Awesome 5 Free & Pro snippets
```

## データベースについて
homesteadを使っているため、
mysqlは
user: homestead
password: secret

user: root
password: secret

postgresqlは
user: homestead
password: secret

user: postgres
password: postgres

が予め作成されています。

どちらを使うにせよ
簡単のため、
```
# useradd homestead
```
としてGuestOS側にもホームディレクトリを作成せず、ユーザーだけ作成することをおすすめします。

また、使わない方のデータベースを
```
# systemctl disable [RDB to want to stop]
```

としてデータベースを止めておくこと。
初期設定では、laravelはmysqlが
config/database.php
に書かれているので、迷ったらmysqlの方がいいかも。

## dataディレクトリについて
プロジェクトの内容以外の
GuestOS,HostOS間のデータのやりとりに利用してください。
.gitignoreにdataフォルダ配下のファイルは無視するように
書かれているので、それぞれの開発用PCで共有したいファイルに使うと
いい感じです。

## submoduleについて
submodule側のレポジトリが更新された場合は下のコマンドで追随します。
```
$ git submodule foreach git pull origin master
```
