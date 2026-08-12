# HEM-7271T V25 チェック済み版

V25の認識ロジック自体は変更していません。

チェック・修正内容:
- JavaScript構文チェック: OK
- JavaScriptから参照するDOM ID: 欠落なし
- Service Worker: V25専用キャッシュへ更新
- title / manifest の旧V23表記をV25へ修正
- 桁位置保存時の旧V21表記をV25へ修正
- V25構造補正が働いた場合、ログに override / base を表示
- 既に取得済みの121/71/80用ログでV25補正規則を再計算し、
  SYS1=1, SYS3=1, DIA1=7, DIA2=1, PULSE2=0 になることを確認

V24の自動トリミングは使用していません。
