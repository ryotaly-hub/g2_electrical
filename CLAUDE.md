# CLAUDE.md

このファイルは、このリポジトリで作業する Claude Code (claude.ai/code) への指針を提供する。

## プロジェクト概要

2級電気工事施工管理技士 第一次検定の学習アプリ（静的サイト）。`index.html` 1ファイルに HTML/CSS/JS がすべて収まった構成で、外部ライブラリやビルドチェーンは無い。

`build-app` という個人ワークスペース内の1プロジェクトとして管理されているが、それ自体は独立した git リポジトリ。ワークスペース横断の共通事項は親フォルダの `CLAUDE.md` を参照。

## コマンド

- **ローカル確認**: `index.html` をブラウザで直接開く。
- **デプロイ**: Vercel。`vercel.json` で `framework: null` / `buildCommand: null` / `outputDirectory: "."` を明示しており、ビルドステップ無しでそのまま配信される。
- **ビルド／lint／テスト**: 該当コマンド無し。

## ディレクトリ構造

```
index.html                          画面・スタイル・ロジックをすべて含む単一ファイル
design/                              デザイン案・実装スクリーンショット（アイコン案、ヘッダー案、模擬試験画面など）
icon-192.png / icon-512.png / apple-touch-icon.png / favicon-*.png   アプリアイコン各種
manifest.webmanifest
電気工事施工管理技士とは.txt         資格制度の説明テキスト（出題内容の参考元）
vercel.json
```

## 注意事項

- `index.html` が唯一のソースファイル。新機能を追加する際も、単一HTML構成を踏襲するか、分割するなら意図的な判断としてその理由を明確にすること。
- 資格制度・出題内容に関する記述を変更する場合は、`電気工事施工管理技士とは.txt` や参照元サイト（`https://www.kssk.info/denkikoujiseko`）との整合を確認する。
- 新しいアイコン・図版が必要な場合は、手描きやストック画像ではなく `generate-illustration` スキル（PC全体・`~/.claude/skills/generate-illustration/` に導入済み）で生成する。
