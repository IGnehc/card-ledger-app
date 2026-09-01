卡牌直播账本 V2

GitHub Pages 更新方法：
1. 打开 card-ledger-app 仓库。
2. 删除或覆盖旧的 index.html、manifest.webmanifest、sw.js、icons 文件夹。
3. 上传本压缩包解压后的全部文件。
4. Commit changes。
5. 等待 Actions -> pages build and deployment 变成绿色。
6. 原来的网址不变。

V2 功能：
- 今日收货 / 今日销售 / 今日毛利润 / 待收款
- 库存数量、平均成本、库存金额
- 移动加权平均成本
- 本月销售和本月毛利润
- 收货 / 卖货快速录入
- 已付款 / 未付款
- 常用商品与默认买卖价格
- 流水查询、CSV 导出、JSON 备份恢复
- 同浏览器旧版 V1 数据迁移

注意：
数据仍然只保存在当前浏览器本机 localStorage。
