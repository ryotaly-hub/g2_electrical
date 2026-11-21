# CLAUDE.md

このファイルは、このリポジトリで作業する Claude Code (claude.ai/code) への指針を提供する。

## プロジェクト概要

2級電気工事施工管理技士 第一次検定の学習アプリ（静的サイト）。`index.html` 1ファイルに HTML/CSS/JS がすべて収まった構成で、外部ライブラリやビルドチェーンは無い。

`build-app` という個人ワークスペース内の1プロジェクトとして管理されているが、それ自体は独立した git リポジトリ。ワークスペース横断の共通事項は親フォルダの `CLAUDE.md` を参照。

## コマンド

- **ローカル確認**: `index.html` をブラウザで直接開く。
- **デプロイ**: GitHub Pages（https://ryotaly-hub.github.io/g2_electrical/ ）。`main` に push すると `.github/workflows/pages.yml` がリポジトリ直下をビルド無しでそのまま公開する。Vercel は使わない。
- **ビルド／lint／テスト**: 該当コマンド無し。

## ディレクトリ構造

```
index.html                          画面・スタイル・ロジックをすべて含む単一ファイル
design/                              デザイン案・実装スクリーンショット（アイコン案、ヘッダー案、模擬試験画面など）
icon-192.png / icon-512.png / apple-touch-icon.png / favicon-*.png   アプリアイコン各種
manifest.webmanifest
電気工事施工管理技士とは.txt         資格制度の説明テキスト（出題内容の参考元）
.github/workflows/pages.yml          GitHub Pages への公開ワークフロー
```

## 注意事項

- `index.html` が唯一のソースファイル。新機能を追加する際も、単一HTML構成を踏襲するか、分割するなら意図的な判断としてその理由を明確にすること。
- 資格制度・出題内容に関する記述を変更する場合は、`電気工事施工管理技士とは.txt` や参照元サイト（`https://www.kssk.info/denkikoujiseko`）との整合を確認する。
