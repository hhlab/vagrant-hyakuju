# vagrant-hyakuju
健康長寿プロジェクトのローカル開発環境仮想マシンのリポジトリ

## 事前にインストールが必要なもの
- [VirtualBox](https://www.virtualbox.org/) :  仮想マシン実行のため
- [Vagrant](https://www.vagrantup.com/) : 仮想マシン立ち上げの自動化のため

公式サイトを見ればインストールできるはず

### vagrant-vbguestのインストール
    $ vagrant plugin install vagrant-vbguest

### インストール確認
    $ vagrant --version
    Vagrant 1.6.5

    $ vagrant plugin list
    vagrant-login (1.0.1, system)
    vagrant-share (1.1.3, system)
    vagrant-vbguest (0.10.0)

## ローカル環境構築手順
1. 開発環境構築用のリポジトリをクローン
1. 仮想マシンの立ち上げ
1. 疎通確認

### リポジトリのクローン
    $ cd your_workspace
    $ git clone git@github.com:hhlab/vagrant-hyakuju.git

### 仮想マシンの立ち上げ
    $ cd vagrant-hyakuju
    $ vagrant up

### 疎通確認
    $ vagrant ssh web
    Last login: Fri Aug  1 09:45:51 2014 from 10.0.2.2
    [vagrant@www ~]$ exit
    ログアウト
    Connection to 127.0.0.1 closed.

    $ vagrant ssh db
    Last login: Fri Aug  1 09:45:51 2014 from 10.0.2.2
    [vagrant@db ~]$ exit
    ログアウト
    Connection to 127.0.0.1 closed.

以上。
