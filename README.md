# himawari-live

気象衛星ひまわり9号の公開タイル画像を10分間隔で144枚取得し、直近24時間をなめらかにループ再生する単一HTMLのビューア。ドラッグ移動・ピンチ/ホイールズームで台風の渦を自由に追える。

A single-page viewer that replays the last 24 hours of Himawari-9 weather-satellite imagery as a smooth loop (144 frames at 10-minute intervals). Drag to pan, pinch or scroll to zoom in on a typhoon's spiral.

Earth Sensing Technologies 制作。

## データソース / Data source

| 項目 | 内容 |
|---|---|
| 提供元 | 情報通信研究機構（NICT）「ひまわりリアルタイムWeb」 |
| 取得元エンドポイント | `https://himawari8.nict.go.jp/img/D531106/` (`latest.json` + タイル画像 `{level}d/550/...png`) |
| 更新間隔 | 10分（ひまわり9号の観測間隔と同期） |
| 必須クレジット表記 | 「提供：情報通信研究機構（NICT）」 |
| 利用範囲 | 気象庁データ公開ポリシーに準拠。非営利（研究・教育）が原則だが、報道・出版・インターネット上での掲載、および営利活動の前段階の研究開発は可能とされている。継続的な商用埋め込み公開は個別に要相談（下記「残課題」参照） |
| 参照ページ | https://himawari8.nict.go.jp/ja/himawari8-about.htm |

外部依存ライブラリなし。ページ内のロゴ（EstMark）・フォントはすべて自前実装/システムフォントで、追加のCDN読み込みは行っていない。

## 起動方法 / Run locally

```bash
python3 -m http.server 8000
# http://localhost:8000/ を開く
```

ビルド不要の単一 `index.html`。

## デプロイ先 / Deployment

Vercel: https://himawari-live.vercel.app/ （個人アカウント配下、Git連携で自動デプロイ）

## 残課題 / Known follow-ups

- リポジトリ/デプロイの帰属: 現状 GitHub 個人アカウント (`kosuke-matsushima/himawari-live`) ＋ 個人 Vercel プロジェクト。EST org への移管は未実施（本タスクのスコープ外）。
- NICTデータの継続的な商用埋め込みについて、正式な利用申請/相談が必要かどうかは NICT サイエンスクラウド事務局への確認が未了。ページ内クレジットは規定の文言（「提供：情報通信研究機構（NICT）」)を明記済みだが、事業として継続公開する前に一度問い合わせることを推奨。
