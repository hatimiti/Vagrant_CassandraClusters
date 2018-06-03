https://qiita.com/48hands/items/05c2ad0ea89fe13afd57 を参考に、複数データセンターの Cassandra 設定

```
# VirtualBoxに6つのインスタンスを作成する
$ git clone https://github.com/hatimiti/Vagrant_CassandraClusters.git
$ cd Vagrant_CassandraClusters
$ vagrant up
$ vagrant ssh-config >> ~/.ssh/config

# 1つ目のデータセンター
$ itamae ssh -h itamae ssh -h nosql1 cookbooks/cassandra.rb -y node-cluster1.yml
$ itamae ssh -h itamae ssh -h nosql2 cookbooks/cassandra.rb -y node-cluster1.yml
$ itamae ssh -h itamae ssh -h nosql3 cookbooks/cassandra.rb -y node-cluster1.yml
# 2つ目のデータセンター
$ itamae ssh -h itamae ssh -h nosql4 cookbooks/cassandra.rb -y node-cluster2.yml
$ itamae ssh -h itamae ssh -h nosql5 cookbooks/cassandra.rb -y node-cluster2.yml
$ itamae ssh -h itamae ssh -h nosql6 cookbooks/cassandra.rb -y node-cluster2.yml

# 下記を nosql1〜nosql6 まで繰り返す
$ ssh nosql1
$ cassandra
```

