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
/home/vagrant/projects/:$ laravel new your_project
```

という形でlaravel環境を作成することができます。

host側からみると
laravel_dev/projects/
配下にプロジェクトが作成されます。

submodule側のレポジトリが更新された場合は下のコマンドで追随します。
```
$ git submodule foreach git pull origin master
```
