# グッズ取引リスト

Twitter（X）でのグッズ取引（譲・求）用の一覧ページです。アカウントごとに HTML 1枚で動き、GitHub Pages で公開します。

## ページのURL

| アカウント | URL |
|---|---|
| yawayawara | `https://trade-list.github.io/page/yawayawara/` |
| sell___oooo | `https://trade-list.github.io/page/sell___oooo/` |

## 公開手順（初回のみ）

1. リポジトリの **Settings → Pages** を開く
2. Source を「Deploy from a branch」、Branch を `main` / `(root)` にして保存

## アカウントの追加・削除

- 追加：既存のフォルダ（例 `yawayawara/`）をコピーして新しいアカウント名にし、
  中の `index.html` の `const ACCOUNT = '...'` を書き換える。
  `data/<アカウント名>.json` は、既存ファイルをコピーするか、管理者がログインして「公開する」を押すと自動で作成されます。
- 削除：`<アカウント名>/`、`data/<アカウント名>.json`、`images/<アカウント名>/` を削除。

`theme` は `sage`（セージグリーン）/ `blue`（スモーキーブルー）/ `brown`（ブラウン）/ `pink`（ローズピンク）から選べます（管理モードからも変更可）。

## 管理者（2名）

管理者は GitHub アカウントでログインします（ページ下の小さな「管理者」リンク）。

1. 管理者それぞれの GitHub アカウントを、このリポジトリの Collaborator（Write 権限）に追加
2. 各管理者が Fine-grained token を発行
   - Repository access: このリポジトリのみ
   - Permissions → Contents: Read and write
3. `data/<アカウント名>.json` の `admins` に、そのページを管理する GitHub ユーザー名を入れる
   ```json
   "admins": ["github-user-name"]
   ```
   空 `[]` の場合は、書き込み権限を持つ人なら誰でも管理できます。

「管理モード」で行った変更は、画面下の「公開する」を押すと GitHub にコミットされ、1〜2分でサイトに反映されます。押さずにページを閉じると変更は消えます。

## データ構成

```
<アカウント>/index.html     … 各アカウントのページ
data/<アカウント>.json      … タイトル・プロフィール・グッズ一覧
images/<アカウント>/*.jpg   … グッズ画像（アップロード時に自動で縮小）
```
