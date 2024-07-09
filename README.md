[Click to view the English version tutorial～～～](https://github.com/zklion-miner/Aleo-miner/blob/master/README_en.md)


## 1、準備挖礦設備

操作系統：推薦使用如下系统

 HiveOS [点击查看HiveOS配置教程～～～](https://github.com/zklion-miner/Aleo-miner/blob/master/HiveOS/README.md)

 Ubuntu 20.04 server
 
 Ubuntu 22.04 server


ubuntu系統下載地址：https://releases.ubuntu.com/focal/ubuntu-20.04.6-live-server-amd64.iso


## 2、註冊zklion礦池帳戶
礦池地址：https://pool.zklion.com

zklion ALEO挖礦方式為用戶名挖礦，需註冊礦池帳戶後根據引導創建挖礦用戶。

訪問zklion官網，根據指引完成註冊即可獲取用戶名，登錄帳戶後，點擊用戶頭像賬戶設置創建挖礦用戶，用於配置挖礦參數。

開始挖礦後，挖礦收益會自動累計在各自帳戶中



## 3、下載挖礦程序

[点击进入挖矿程序下載地址～～～](https://github.com/zklion-miner/Aleo-miner/releases)
```shell
aleo-pool-prover-zklion-v0.x          //Ubuntu系統礦池挖礦程序

aleo-solo-prover.tar.gz  //Ubuntu系統solo挖礦程序

zklion_miner.tar.gz      //HiveOS系統礦池挖礦程序

#一键脚本
curl -sSf -L http://dl.zklion.com/zklion-miner/join.sh|sudo bash -s -- --worker-name 矿机名称 --account 矿池用户名
```



## 4、程序參數解釋

```shell
#礦池挖礦程序
./aleo-pool-prover-zklion-v0.x --help
ZKLION-pool-prover 0.1.0 (c5f1287 2024-06-30)

USAGE:
    aleo-pool-prover [OPTIONS] --pool <POOL> --account <ACCOUNT> --worker-name <WORKER_NAME>

OPTIONS:
        --account <ACCOUNT>            //礦池中生成的挖礦用戶名
    -h, --help                         //打印幫助信息
        --pool <POOL>                  //礦池連接地址、wss://aleo.zklion.com:3777
        --rest <REST>                  //本地監聽端口、默認0.0.0.0:9988
    -v, --version                      //程序版本
        --worker-name <WORKER_NAME>    //輸入你的礦機名稱

```

```shell
#solo挖礦程序
./aleo-solo-prover --help
ZKLION-solo-prover 0.1.0 (c5f1287 2024-06-30)

USAGE:
    aleo-solo-prover [OPTIONS] --proxy <PROXY> --address <ADDRESS>

OPTIONS:
        --address <ADDRESS>            //你的aleo錢包地址
    -h, --help                         //打印幫助信息
        --proxy <PROXY>                //礦池連接地址、wss://aleo.zklion.com:3666
        --rest <REST>                  //本地監聽端口、默認0.0.0.0:9988
    -v, --version                      //程序版本
        --worker-name <WORKER_NAME>    //輸入你的礦機名稱
```

## 5、示例 

```shell
#下載後首先添加可執行權限
chmod +x aleo-pool-prover-zklion-v0.x
#礦池程序啟動示例
./aleo-pool-prover-zklion-v0.x --account test01 --pool wss://aleo.zklion.com:3777 --worker-name 192-168-100-101

#一键脚本
curl -sSf -L http://dl.zklion.com/zklion-miner/join.sh|sudo bash -s -- --worker-name 矿机名称 --account 矿池用户名

#solo程序啟動示例
1、解壓縮
tar -zxvf aleo-solo-prover.tar.gz
2、進入解壓後的目錄
cd aleo-solo-prover/
3、添加可執行權限
chmod +x aleo-solo-prover
4、啟動
./aleo-solo-prover --address aleo1308gq2pfn0y3xxxx --proxy wss://aleo.zklion.com:3666 --worker-name x99-01
```

## 6、后台運行挖礦程序、如下为示例、实际运行时请将参数替换为自己的

矿池程序后台运行：
```shell
nohup ./aleo-pool-prover-zklion-v0.x --account test01 --pool wss://aleo.zklion.com:3777 --worker-name 192-168-100-101 &> /root/zklion-pool-prover.log &
```

solo程序后台运行：
```shell
nohup ./aleo-solo-prover --address aleo1308gq2pfn0y3xxxx --proxy wss://aleo.zklion.com:3666 --worker-name 192-168-100-102 &> /root/zklion-solo-prover.log &
```

======查看zklion-pool-prover.log日誌======
```shell
tail -f /root/zklion-pool-prover.log
```
<img width="734" alt="image" src="https://github.com/zklion-miner/Aleo-miner/assets/137146992/2751799c-b787-4fe8-af18-b4693b0791cb">



