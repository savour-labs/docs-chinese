## NFT 数据监控和NFT推荐产品设计文档

### 一. 概述

本产品主要是对 NFT 的合约地址创建，合约 mint NFT 和交易的数据进行抓取，做数据统计分析，给用户推荐高价值的 NFT。业务规则包含，巨鲸钱包地址监控，NFT 项目监控，NFT 价值分析，NFT 稀有度分析等。

### 二. 架构设计

整个项目设计架构图如下：

![nft-1.png](https://github.com/savour-labs/savour-docs-chinese/blob/main/images/nft-1.png)

#### 1.规则组件详细逻辑

##### 1.1.巨鲸钱包规则

- 巨鲸钱包地址的评判依据规则一：根据 NFT 持有者的 NFT + Token 价值做判断，大于每一个值就算是巨鲸钱包，评断为巨鲸钱包的地址，自动监控，一旦这个钱包的价值小于规定值，自动解除监控
- 巨鲸钱包地址的评判依据规则二：交易所热钱包地址，大户地址，知名圈内投资机构和投资地址直接监控。

判断为巨鲸钱包的地址需要监控所有相关的数据，将清洗过的数据推到数据清洗中心，供给业务中台使用。

##### 1.2.有价值的 NFT 项目判断规则

- NFT 集合的总价值高于某个值
- NFT 的流转次数大于某个值
- NFT 持有地址的数量大于某个值

同时达到以上三个条件的 NFT 项目，需要监控他们 NFT 的 mint 和 NFT 交易情况，以及判断出新开启的 NFT 项目，将清洗过的数据推到数据清洗中心，供给业务中台使用。

##### 1.3.单个有价值的 NFT 判断依据

- NFT 的流转次数大于某个值
- NFT 最近 N 次交易交易金额大于某个值

同时达到以上两个个条件的 NFT 项目，需要监控 NFT 交易情况，将数据推到数据清洗中心，供给业务中台使用。


### 三. 细节逻辑

待补充

### 四.总结

待补充


### 五.附录

Oklink: https://www.oklink.com/docs/en/#rest-api-address-top-100-richest-addresses
巨鲸地址抓取网站一：https://dune.com/0xBi/0xBi
钱包查询功能参考：https://pro.nansen.ai/wallet-profiler
巨鲸地址判断参考：https://nftgo.io/whale-tracking/list
