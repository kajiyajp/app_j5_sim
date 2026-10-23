<!-- 作成: 2026-10-23 / 目的: コントリビュータを迎えるための GitHub 側の設定（ラベル・トピック）の案と、反映するコマンドを残す -->

# GitHub の設定案（ラベル・トピック）

ラベルとトピックは、リポジトリのファイルではなく GitHub 側の設定です。ここに案と、反映する `gh` コマンドを残します。

## ラベル

### 新しく作るラベル

| ラベル | 色 | 意味 |
|---|---|---|
| `hardware-check` | `#0E8A16` 緑 | 実機・マニュアルとの違いの報告（「実機確認」フォームで自動で付く） |
| `needs-hardware` | `#FBCA04` 黄 | 実機を持っている人の確認が必要 |
| `verified` | `#2EA44F` 濃い緑 | 実機またはマニュアルで確認済み |
| `ladder` | `#1D76DB` 青 | ラダー・ニーモニック・命令 |
| `servo-model` | `#5319E7` 紫 | サーボ・機械のモデル、状態遷移 |
| `ui` | `#C5DEF5` 薄い青 | 画面の配置・操作・表示 |

### 今あるラベル（そのまま使う）

| ラベル | 使いどころ |
|---|---|
| `bug` | 不具合（「不具合」フォームで自動で付く） |
| `enhancement` | 要望（「要望」フォームで自動で付く） |
| `documentation` | README・CONTRIBUTING などの文書 |
| `good first issue` | 初めての人に向く、小さめの Issue |
| `help wanted` | 手伝ってほしい Issue |
| `question` | 質問 |
| `duplicate`・`invalid`・`wontfix` | 重複・対象外・対応しない |

`accessibility` は今は使い道が少ないので、残しても消してもかまいません。

### 反映するコマンド

```bash
gh label create hardware-check --color 0E8A16 --description "実機・マニュアルとの違いの報告" --repo kajiyajp/app_j5_sim
gh label create needs-hardware --color FBCA04 --description "実機を持っている人の確認が必要" --repo kajiyajp/app_j5_sim
gh label create verified --color 2EA44F --description "実機またはマニュアルで確認済み" --repo kajiyajp/app_j5_sim
gh label create ladder --color 1D76DB --description "ラダー・ニーモニック・命令" --repo kajiyajp/app_j5_sim
gh label create servo-model --color 5319E7 --description "サーボ・機械のモデル、状態遷移" --repo kajiyajp/app_j5_sim
gh label create ui --color C5DEF5 --description "画面の配置・操作・表示" --repo kajiyajp/app_j5_sim
```

## トピック（検索用のタグ）

リポジトリのトップに表示され、GitHub の検索で見つけてもらいやすくなります（最大 20 個、英小文字とハイフン）。

| 分類 | トピック |
|---|---|
| PLC・ラダー | `plc`、`ladder-logic`、`ladder-diagram`、`melsec` |
| サーボ・通信 | `servo`、`servo-motor`、`motion-control`、`cia402`、`cc-link` |
| 分野 | `factory-automation`、`industrial-automation` |
| 種類 | `simulator`、`education`、`learning` |
| 技術 | `javascript`、`html`、`github-pages` |

### 反映するコマンド

```bash
gh repo edit kajiyajp/app_j5_sim --add-topic plc,ladder-logic,ladder-diagram,melsec,servo,servo-motor,motion-control,cia402,cc-link,factory-automation,industrial-automation,simulator,education,learning,javascript,html,github-pages
```

## そのほか（必要になったら）

- **Discussions**（質問や雑談の場）を有効にする: リポジトリの Settings → General → Features → Discussions
- **確かめてほしい Issue を立てる**: README の「実機で確かめていない例」を 1 件ずつ Issue にし、`needs-hardware` と `help wanted` を付ける
