# HEM-7271T V24 修正版2

今回の解析エラーの原因は認識エンジンではなく、
解析終了時の詳細ログ表示部分でした。

## 原因
`fmt()` でSYS/DIA/PULSEのログ文字列を作るコードは存在していましたが、
それをまとめる `const log = ...` がV24編集時に抜け落ちていました。

そのため解析自体が終わったあと、
`$("debug").textContent = log;`
で ReferenceError になっていました。

## 修正
- `const log=fmt("SYS",S)+"\n"+fmt("DIA",D)+"\n"+fmt("PULSE",P);` を復旧
- 認識方式、自動トリミング、1/7/0強化は変更なし
- Service Workerキャッシュ名を再変更
