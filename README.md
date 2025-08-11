# Metadata-generator (Fork)

> This repository is a fork of the original project: https://github.com/multi-nono/Metadata-generator

## English

### What It Is
A single-page, offline HTML tool to compose structured metadata blocks (e.g., YAML/JSON/Markdown fragments) that you can copy or download and reuse in knowledge bases, blogs, catalogs, and library tools.

### When To Use
- Preparing front matter for Markdown posts (Hugo, Jekyll, Zola).
- Creating book/article metadata for Calibre, Zotero, or Obsidian/Notion templates.
- Standardizing product or project notes with consistent fields and tags.
- Generating shareable metadata for tickets, design docs, or research logs.
- Quickly producing JSON/YAML snippets to paste into scripts or APIs.

### Files
- `EN v2.html`: English interface
- `JA v2.html`: Japanese interface

### Quick Start
1. Open `EN v2.html` or `JA v2.html` in a modern browser (Chrome/Edge recommended).
2. If clipboard features do not work on `file://`, serve the folder locally (secure context): `python -m http.server 8080` and open `http://localhost:8080/`.
3. Fill out the form, click Generate, then Copy or Download the result.

### Buttons and Tools
Note: Exact labels may vary slightly by version. Use the closest match.

- Generate: Build the metadata from current form values and show it in the output area.
- Copy: Copy the generated metadata to the clipboard.
- Download: Save the generated metadata as a file (e.g., `.txt`, `.md`, `.json`).
- Clear Output: Clear only the output area; keep your current inputs.
- Reset Form: Reset all input fields to default/empty values.
- Load Sample: Prefill the form with example values to try the tool quickly.
- Import: Load form values from a supported file or pasted text (e.g., JSON/YAML) when available.
- Export: Save current form values/settings so you can reuse them later.
- Theme/Language: If shown, toggles theme or language. For language, use `EN v2.html` or `JA v2.html`.

### License and Credits
- Upstream: https://github.com/multi-nono/Metadata-generator
- Credits: Thanks to the upstream authors and contributors.
- License: See `LICENSE`. Unless otherwise noted, terms follow the upstream project.

---

## 日本語 (Japanese)

### ツール概要
単一の HTML ページで動作するオフラインのメタデータ生成ツールです。フォームに入力した値から、再利用しやすい構造化メタデータ（例：YAML/JSON/Markdown 断片）を生成し、コピーやダウンロードで他のツール・文書へ転用できます。

### 想定ユースケース（どのような場面で使えるか）
- Markdown 記事のフロントマター作成（Hugo / Jekyll / Zola など）。
- 書籍・記事のメタデータ作成（Calibre / Zotero / Obsidian・Notion 用テンプレート）。
- 製品・プロジェクトメモの標準化（共通フィールドやタグの付与）。
- チケット、設計資料、リサーチログ向けの共有用メタデータ生成。
- スクリプトや API に貼り付ける JSON/YAML スニペットの素早い作成。

### 同梱ファイル
- `EN v2.html`：英語 UI
- `JA v2.html`：日本語 UI

### かんたん手順
1. お使いのブラウザ（Chrome/Edge 推奨）で `EN v2.html` または `JA v2.html` を開きます。
2. `file://` でクリップボードが使えない場合は、ローカルサーバーで配信してください：`python -m http.server 8080` を実行し、`http://localhost:8080/` を開きます。
3. フォームに入力し、「Generate」等のボタンで生成。結果を「Copy」または「Download」で取得します。

### ボタン・ツールの説明（主要操作）
※ バージョンによりラベルが異なる場合があります。近い名称をご確認ください。

- Generate：現在の入力値からメタデータを生成し、出力欄に表示します。
- Copy：生成されたメタデータをクリップボードへコピーします。
- Download：生成されたメタデータをファイル（例：`.txt`、`.md`、`.json`）として保存します。
- Clear Output：出力欄のみをクリアし、入力値はそのまま残します。
- Reset Form：すべての入力項目を初期状態（空）に戻します。
- Load Sample：サンプル値を自動入力し、動作を素早く試せます。
- Import：対応形式（例：JSON/YAML）のファイルや貼り付けたテキストから入力値を読み込みます（機能がある場合）。
- Export：現在の入力値・設定を保存し、後で再利用できます（機能がある場合）。
- Theme/Language：表示テーマや言語を切り替えます。言語は `EN v2.html` / `JA v2.html` をご利用ください。

### ライセンス・クレジット
- フォーク元（Upstream）：https://github.com/multi-nono/Metadata-generator
- クレジット：オリジナルの作者・コントリビューターの皆様に感謝します。
- ライセンス：`LICENSE` を参照。特に明記がない場合、フォーク元に準拠します。

---

Questions or issues? Please open an issue or pull request in this repository. / ご質問・不具合は本リポジトリの Issue / Pull Request にてお知らせください。

