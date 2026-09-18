# 📔 Git・GitHub 基本チートシート（虎の巻）

このファイルは、GitとGitHubの基本操作をいつでも確認できるようにまとめたものです。

---

## 1. 導入時の一時的なセットアップ（環境構築）
新しいPCで最初に一度だけ行う設定です。
- **Gitのインストール**:
  ```powershell
  winget install Git.Git
  ```
- **日本語文字化け防止**:
  ```powershell
  git config --global core.quotepath false
  ```
- **ユーザー名の設定**:
  ```powershell
  git config user.name "takanit"
  ```
- **メールアドレスの設定**:
  ```powershell
  git config user.email "takanit@example.com"
  ```

---

## 2. 日常の3ステップ（超基本・1日に何回も使う）
何かファイルを新しく作ったり、書き換えて保存・アップロードする際のお決まりの順番です。

1. **追加（ステージング）**：変更ファイルをGitの登録リストに載せる
   ```powershell
   git add .
   ```
2. **記録（コミット）**：メッセージ（作業のメモ）をつけてPC内にセーブする
   ```powershell
   git commit -m "何をしたかのメモ（例：◯◯ファイルを追加）"
   ```
3. **送信（プッシュ）**：ローカルのセーブデータをGitHub（ネット上）にアップロードする
   ```powershell
   git push
   ```

---

## 3. 状態・履歴の確認（迷ったらいつでも打つ）
- **今の状態を見る**：「変更されたファイル」や「登録されたファイル」がわかります。
   ```powershell
   git status
   ```
- **過去の履歴を見る**：これまでのセーブポイント（コミット）の一覧が古い順から並びます。
   ```powershell
   git log --oneline
   ```

---

## 4. タイムトラベルと復旧（安全のためのセーブポイント機能）
- **誤消去からの復活**：ゴミ箱から消してしまったファイルも一瞬で戻せます。
   ```powershell
   git restore <ファイル名>
   ```
- **過去へのタイムトラベル**：一時的に過去のコミット時点にフォルダ全体を戻します。
   ```powershell
   git checkout <コミット識別番号（例: 0db1607）>
   ```
- **現代への帰還**：タイムトラベルを終えて最新のメインブランチに戻ります。
   ```powershell
   git checkout main
   ```

---

## 5. 複数PC間のやりとり（ダウンロード・同期）
- **クローン（最初の1回）**：GitHub上のデータを新PCにフォルダごと丸ごとコピーします。
   ```powershell
   git clone <GitHubのリポジトリURL>
   ```
- **プル（2回目以降の同期）**：他のPCでプッシュした最新状態を、手元のフォルダに取り込みます。
   ```powershell
   git pull
   ```
