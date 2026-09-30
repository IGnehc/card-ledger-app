V4 Firebase 云端同步版。旧版 cardLedgerUsers 只读；新版 cardLedgerV4Users 独立存储。先下载云端原始备份再初始化。需要 Firebase Authentication 启用邮箱密码或 Google 登录，并允许 GitHub Pages 域名；Firestore 规则需允许本人 UID 读取旧集合、读写新集合。首次登录读取后，手动确认初始化。此版本未在线连接真实 Firebase 测试，请先备份并核对库存利润。

V2.1：恢复实时 CNY→JPY 汇率；进入卖货自动获取，30分钟缓存，可手动刷新；交易保存当时汇率、获取时间和来源。
