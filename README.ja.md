# FuelPHP Vagrant Development setup (CentOS6)

**このリポジトリは保守されていますが、積極的には開発されていません。新しい Vagrant CentOS6 PHP リポジトリを作成しました。[vagrant-centos6-php](https://github.com/kenjis/vagrant-centos6-php)を参照してください。**

このプロジェクトは、あなたのFuelPHPプロジェクトを含むCentOS 6.5 (64bit) 仮想マシンをセットアップします。FuelPHPプロジェクトのディレクトリを仮想マシンからマウントするため、ホスト側でお好みのエディタを使って作業できます。

## 必要なソフトウェア

* VirtualBox - フリーな仮想化ソフトウェア [ダウンロード](https://www.virtualbox.org/wiki/Downloads)
* Vagrant 1.3+ - VirtualBoxのイメージを操作するツール [ダウンロード](http://downloads.vagrantup.com/)
* Git - バージョン管理システム [ダウンロード](http://git-scm.com/downloads)

### テストされた環境

* Ubuntu 14.04     - VirtualBox 4.3.18 & Vagrant 1.6.5 & Git 1.9.1
* Mac OS X 10.10.1 - VirtualBox 4.3.18 & Vagrant 1.6.5 & Git 1.9.3

## この開発環境に含まれるもの

以下のいくつかは、Chef Opscodeリポジトリを使ってインストールされます。

* PHP 5.5
  * Xdebug
  * Zend OPcache
  * APCu
* Apache 2.2
  * FuelPHPプロジェクト用のバーチャルホスト設定
* MySQL 5.1
  * データベース **fuel_dev** および **fuel_test**
* phpMyAdmin 4.0
* PHPUnit 3.7
* Git 1.7.1

(オプション)

* MongoDB 2.6
* Redis 2.4

## 推奨されるセットアップ方法とディレクトリ構成

vagrant-fuelphp-centos6をあなたのプロジェクトに追加します:

	$ git submodule add git@github.com:kenjis/vagrant-fuelphp-centos6.git vagrant
	$ git submodule update --init --recursive
	$ cd vagrant
	$ vagrant up

ディレクトリ構成は以下のようになります:

	project/
	├── docs/
	├── fuel/
	├── public/
	└── vagrant/

## FuelPHPプロジェクトへのアクセス方法

* **ブラウザ(ポート転送)**: [http://localhost:8000](http://localhost:8000)
* **ブラウザ(IPアドレス直接)**: [http://192.168.33.33](http://192.168.33.33)
* **MySQL**: mysql:host=192.168.33.33;dbname=fuel_dev (rootユーザのpasswordはVagrantfileに設定されています)

### Vagrant

よく使うコマンド:

* `vagrant up` 仮想マシンを起動しプロビジョンします
* `vagrant suspend` 仮想マシンの状態を保存して停止します
* `vagrant halt` 仮想マシンを停止 (シャットダウン) します
* `vagrant ssh` 仮想マシンへのSSHアクセスを提供します
* `vagrant destroy` 仮想マシンを破棄します
* `vagrant status` 仮想マシンの状態を表示します
* `vagrant global-status` すべての仮想マシンの状態を表示します

もっと知りたい場合は、http://docs.vagrantup.com/v2/

## Thanks to

* https://github.com/iturgeon/vagrant-fuelphp
