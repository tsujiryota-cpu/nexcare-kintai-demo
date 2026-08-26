# ニコライフ勤怠アプリ（公開デモ） — 作業ルール

ネクスケア（辻さん）の勤怠管理Webアプリのたたき台。ここは公開デモの配信用リポジトリです。
**作業前に必ず `docs/仕様書_再生成プロンプト.md` を読むこと**（全仕様・業務ルールが書いてある）。

- `index.html` … アプリ本体（単一HTML＋localStorage・外部ライブラリなし）
- main に push すると GitHub Pages（https://tsujiryota-cpu.github.io/nexcare-kintai-demo/）に自動反映される

## 変更のしかた
1. 仕様書を読む → `index.html` を編集
2. 動作確認（シフト自動作成の制約を壊さない: 常勤176〜177h・公休9日・夜勤月6回まで・連日夜勤禁止・夜勤明け翌日休み・最大5連勤）
3. **仕様書の該当箇所も更新**してから、日本語のコミットメッセージ「vNN: 変更内容」で push
4. 応答の最後に「PCセッションで他の保存先への同期が必要」と辻さんに伝えること
   （開発本体 NEXCAREjapan/nexcare-kintai・OneDrive・Googleドライブ・Claude Artifact への反映は辻さんのPCセッションが行う）

## 守ること
- 日本語UI・専門用語を避けた文言。localStorageのキーは `nl_` プレフィックス
- 職員名簿は実名。名簿の初期データ（STAFF_SEED）やシードガードの変更は慎重に
- スマホ幅460px基準＋PC対応（1000px以上でシフト表全幅）。ダークモード対応（CSS変数は素の:root・@media dark・[data-theme=dark]・[data-theme=light]の4か所に定義）
- confirm()/prompt()は使わない（アプリ内モーダル askConfirm を使う）
