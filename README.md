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

## 動作環境

- OBS Studio（WebSocket機能が必要）
- WebSocketポート: `4455`（認証なし）
