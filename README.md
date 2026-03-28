# versus-log

OBS Studio 用の勝敗カウンターウィジェットです。

## 機能

- WIN / LOSS カウント表示
- 勝率・ゲージバー表示
- 連勝 / 連敗ストリーク表示
- 直近10試合の履歴表示（LAST 10）
- 2パネルの自動スライド切り替え

## 使い方

### OBSへの追加

1. OBS Studio を起動
2. ソースに「ブラウザ」を追加
3. URLに `https://tAI-HMB.github.io/versus-log` を入力
4. 幅: `900` / 高さ: `200` に設定

### 勝敗の記録

OBS WebSocket（ポート `4455`）経由でメッセージを送信します。

| メッセージ | 動作 |
|---|---|
| `win` | 勝利を記録 |
| `loss` | 敗北を記録 |

### Advanced Scene Switcher との併用

[Advanced Scene Switcher](https://obsproject.com/forum/resources/advanced-scene-switcher.395/) のマクロ機能を使うことで、ゲーム画面の自動認識と連動した勝敗送信が可能です。

**マクロの設定例（勝利の場合）**

1. Advanced Scene Switcher のマクロ画面を開く
2. 条件（If）に「動画 → ソース → パターンに一致」を設定し、勝利画面の画像を指定
3. アクションに「WebSocket → イベント → シーンスイッチャーメッセージ」を追加
4. メッセージに `win` と入力
5. 敗北用も同様に `loss` で作成

> 閾値は環境によって調整してください。

## 参考

- [OBS配信修業僧 - Advanced Scene Switcherの使い方](https://pc.watch.impress.co.jp/docs/column/haishin_shugyousou/2029483.html)
- [おれ主夫 - OBSの画像認識Tips](https://oreshufu.com/blog/tipsmemo/obsimage)

## 動作環境

- OBS Studio（WebSocket機能が必要）
- WebSocketポート: `4455`（認証なし）

## 利用規約

### 免責事項

本ソフトウェアは**現状のまま（AS IS）**提供されます。使用によって生じたいかなる損害・不具合についても、作者は一切の責任を負いません。

### 改変・再配布について

- 改変・カスタマイズは自由に行っていただいて構いません。
- ただし、本ソフトウェアを**改変せずにそのまま別の場所で公開すること（無改変での再配布）は禁止**します。
- 改変版を公開する場合は、元のリポジトリ（本リポジトリ）へのリンクを明記してください。
