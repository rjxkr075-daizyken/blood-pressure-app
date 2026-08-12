# HEM-7271T V24 修正版

V24で発生した解析エラーを修正しました。

原因:
- V24で追加した 1 / 7 / 0 強化判定が、extractShapeFeatures() の返す
  `rel[]` を named field として直接参照していました。
- V23側のデータ構造との接続が不足していました。

修正:
- `rel[0..6]` を top / mid / bot / leftTop / rightTop / leftBot / rightBot に明示マッピング
- 判定値に defensive guard を追加
- NaN が発生しても解析全体を停止しない保護を追加
- Service Worker のキャッシュ名を変更

認識方式そのものはV24のままです。
