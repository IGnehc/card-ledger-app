V2.4 手机/电脑云同步版

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
