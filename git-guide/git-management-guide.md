# Git管理ガイド

**作成日:** 2025-04-04  
**最終更新:** 2025-04-04  
**バージョン:** 1.0.0

## 1. はじめに

本ガイドは、複数プロジェクトの効率的な管理のためのGit/GitHub活用方法をまとめたものです。ADHD特性に配慮し、シンプルでありながら必要十分な運用ルールを提供します。

## 2. ブランチ戦略

### 2.1 ブランチの種類
- **mainブランチ**: 安定したリリースバージョンのみを含む
- **featureブランチ**: 新機能や修正を開発するためのブランチ
- **hotfixブランチ**: 緊急のバグ修正用（必要時のみ）

### 2.2 ブランチの命名規則
- `feature/` + 機能名: 新機能の開発や修正（例: `feature/satellite-data-fetcher`）
- `hotfix/` + 修正名: 緊急修正（例: `hotfix/api-authentication-fix`）

### 2.3 GitHub Flowの採用
本プロジェクトでは、シンプルで効率的なGitHub Flowブランチモデルを採用しています：

1. **mainブランチからfeatureブランチを作成**
2. **機能実装・コミット**
3. **プルリクエスト作成**
4. **セルフレビュー**
5. **mainブランチにマージ**

### 2.4 安定版リリースと緊急バグ修正の対応
1. **安定版リリース**:
   - 安定版リリースごとに明確なタグ（例: v1.0.0）を使い、リリース時点を明示します
   - リリース時の品質チェックをGitHub Actionsなどで自動化することで、品質を維持します

2. **緊急バグ修正**:
   - 必要に応じて臨時で「hotfix/XXX」ブランチを作成して対応
   - 修正後は通常のプルリクエストプロセスを経てmainにマージ

## 3. コミットメッセージの一貫性

### 3.1 Conventional Commits形式
以下の形式に従ったコミットメッセージを使用します：

```
<type>: <description>

[optional body]

[optional footer]
```

主なタイプ:
- `feat`: 新機能
- `fix`: バグ修正
- `docs`: ドキュメントのみの変更
- `style`: フォーマットの変更（コードの動作に影響しない）
- `refactor`: リファクタリング
- `test`: テストの追加や修正
- `chore`: その他の変更（ビルドプロセスや依存関係の管理など）

### 3.2 コミットメッセージの例
```
feat: Add new satellite data fetcher module

Add functionality to fetch and parse Sentinel-2 satellite data
using Google Earth Engine API.

Closes #42
```

```
fix: Correct authentication error in Google Earth Engine API

Updated authentication flow to handle token refresh properly.
```

```
docs: Update progress report with latest test results

Added precision metrics and example outputs.
```

### 3.3 ADHD特性に配慮したコミット戦略
- 小さな単位での頻繁なコミット（15-30分ごと）
- 作業中断時には必ずコミット
- WIP（Work In Progress）コミットも許容（例: `chore: WIP on data preprocessing`）
- コミットメッセージをGitHub Copilotに提案させる活用法

## 4. プルリクエスト（PR）の活用

### 4.1 PRの作成
- コードレビューを通じて品質を確保
- 自動テストをPRに統合
- PRテンプレートを使用して必要な情報を提供

### 4.2 セルフレビュープロセス
1. コードの変更点を俯瞰的に確認
2. 以下の観点からセルフレビュー:
   - 機能性: 要件を満たしているか
   - パフォーマンス: 効率的な実装か
   - 可読性: 他者（将来の自分）が理解できるか
   - エラー処理: 例外的な状況に対応しているか
3. GitHub Copilotを活用したレビュー支援

### 4.3 PRテンプレートの例
```
## 概要
- 変更内容の概要を記述

## 関連Issue
- 関連するIssue番号を記述

## 変更内容
- 具体的な変更点を記述

## テスト結果
- テストの実行結果を記述

## スクリーンショット（必要に応じて）
- UI変更などがある場合は追加
```

## 5. タグとリリースの管理

### 5.1 バージョン番号の付け方
- メジャー.マイナー.パッチの形式を採用（例: v1.0.0）
  - **メジャー**: 互換性を破壊する変更
  - **マイナー**: 後方互換性のある機能追加
  - **パッチ**: 後方互換性のあるバグ修正

### 5.2 タグ付けの手順
```bash
# 注釈付きタグの作成
git tag -a v1.0.0 -m "Version 1.0.0 - Initial release"

# タグをリモートにプッシュ
git push origin v1.0.0
```

### 5.3 リリースノートの作成
- 変更点を以下のカテゴリで明確に記述:
  - 新機能
  - 改善点
  - バグ修正
  - 非推奨化
  - 削除された機能
- スクリーンショットや図解を必要に応じて追加
- リリース日と対象バージョンを明記

## 6. GitHub Issuesの活用

### 6.1 Issue活用の基本
- 各タスクをIssueとして作成
- 適切なラベル付けで分類
- マイルストーンでグループ化
- Issueテンプレートの活用

### 6.2 Issueテンプレート例
```
## 概要
[タスクの簡潔な説明]

## 目的
[このタスクを完了することで得られる価値]

## 受け入れ基準
- [ ] [基準1]
- [ ] [基準2]

## 追加情報
[関連する技術的な詳細や参考情報]
```

### 6.3 ADHD特性に配慮したIssue管理
- 視覚的な進捗管理（GitHub Projects活用）
- 小さな単位への分割（2時間以内で完了可能なサイズ）
- 依存関係の明示
- 優先順位の視覚化（ラベルや順序で）

## 7. プロジェクト管理との統合

### 7.1 GitHub Projectsの活用
- カンバンボードスタイルの進捗管理
- 以下の列構成を推奨:
  - Backlog（未着手）
  - Ready（準備完了）
  - In Progress（作業中）
  - Review（レビュー中）
  - Done（完了）

### 7.2 マイルストーンの設定
- 2週間〜1ヶ月の適切な期間で設定
- 達成可能な範囲に限定
- 明確な成功基準を含める

### 7.3 過集中・休息サイクルとの連携
- 過集中期に向けたIssueのバッチ準備
- 休息期のメンテナンスタスク管理
- 進捗の可視化によるモチベーション維持

## 8. Git/GitHubの効率的な学習・活用リソース

### 8.1 参考リソース
- [GitHub Skills](https://skills.github.com/) - インタラクティブな学習コース
- [GitHub Docs](https://docs.github.com/) - 公式ドキュメント
- [Oh Shit, Git!?!](https://ohshitgit.com/) - 一般的な問題と解決策

### 8.2 便利なGitコマンド集
```bash
# 作業状態の確認
git status

# 変更の確認
git diff

# ステージングに追加
git add .

# コミット
git commit -m "type: description"

# ブランチ作成と切り替え
git checkout -b feature/new-feature

# リモートへのプッシュ
git push origin feature/new-feature

# メインブランチの最新化
git checkout main
git pull

# 変更を退避
git stash

# 退避した変更を復元
git stash pop
```

### 8.3 トラブルシューティング
- コンフリクト解決手順
- 誤ったコミットの修正方法
- ブランチ操作の失敗からの回復

## 9. GitHub Copilotとの連携

### 9.1 コード生成の効率化
- 関数やクラスの雛形生成
- テストケースの自動生成
- ドキュメントの生成

### 9.2 コメントを活用した指示
```python
# Sentinel-2衛星画像からNDVIを計算し、閾値0.2以下の領域を
# 太陽光パネルの候補として検出する関数を実装
def detect_panel_candidates(image_data, threshold=0.2):
    # Copilotがここから実装を提案
```

### 9.3 VSCode統合の最適化
- GitHub Copilot Chatの活用
- @workspaceコマンドによるコンテキスト提供
- ドキュメントとコードの一貫性維持

---

**変更履歴:**
- 2025-04-04: 初版作成