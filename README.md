# laravel_dev
laravel開発用
これをフォークすることによりプロジェクトを作成してください。

フォークしたプロジェクトは
```
$ cd homstead_vagrant
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
