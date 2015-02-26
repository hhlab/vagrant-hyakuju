vagrant-hyakuju
--

健康長寿プロジェクトのローカル開発環境仮想マシンのリポジトリ

## 事前にインストールが必要なもの
- [VirtualBox](https://www.virtualbox.org/) :  仮想マシン実行のため
- [Vagrant](https://www.vagrantup.com/) : 仮想マシン立ち上げの自動化のため

公式サイトを見ればインストールできるはず

### インストール確認
    $ vagrant --version
    Vagrant 1.6.5

## ローカル環境構築手順
1. 開発環境構築用のリポジトリをクローン
1. 仮想マシンの立ち上げ
1. SSH設定
1. 疎通確認

### リポジトリのクローン
    $ cd your_workspace
    $ git clone git@github.com:hhlab/vagrant-hyakuju.git

### 仮想マシンの立ち上げ
    $ cd vagrant-hyakuju
    $ vagrant up

### SSH設定
    $ vagrant ssh-config web --host 192.168.110.10 >> ~/.ssh/config
    $ vagrant ssh-config db --host 192.168.110.20 >> ~/.ssh/config

### 疎通確認
    $ ansible -i stage all -m ping
    192.168.110.20 | success >> {
        "changed": false,
        "ping": "pong"
    }

    192.168.110.10 | success >> {
        "changed": false,
        "ping": "pong"
    }

以上。
