# laravel_dev
laravel開発用
これをフォークすることによりプロジェクトを作成してください。

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
password: secret

が予め作成されています。

どちらを使うにせよ
簡単のため、
```
# useradd homestead
```
としてGuestOS側にもホームディレクトリを作成せず、ユーザーだけ作成することをおすすめします。

## submoduleについて
submodule側のレポジトリが更新された場合は下のコマンドで追随します。
```
$ git submodule foreach git pull origin master
```
