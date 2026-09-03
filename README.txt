V2.6 手机/电脑云同步 + 人民币汇率 + 单位换算版

需要 Firebase：
1. Authentication 开启 Email/Password
2. Firestore Database 已创建
3. 设置页填写 apiKey、authDomain、projectId、appId
4. 电脑和手机使用同一个邮箱账号登录
5. 第一次先在电脑“上传本机数据到云端”，手机再“从云端恢复到本机”
6. 之后自动同步

建议 Firestore Rules：
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /cardLedgerUsers/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}

启用同步前请先备份 JSON。


新增功能：卖货时输入人民币单价，联网获取最新 CNY/JPY 汇率，自动换算成日元。保存时同时记录人民币单价、成交汇率、汇率获取时间、日元单价。汇率缓存 30 分钟，也可手动刷新。

新增单位换算：
- 包（1包）
- 手（24包）
- 盒（1盒）
- 个（1个）
- 选择“手”时库存统一按包换算，例如 2手 = 48包。
- 计价方式可选“按当前单位计价”或“按基础单位计价（手自动×24）”。
