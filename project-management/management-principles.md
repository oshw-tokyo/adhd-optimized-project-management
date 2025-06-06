# プロジェクト管理原則

**作成日:** 2025-04-04  
**最終更新:** 2025-04-04  
**バージョン:** 1.0.0

## 1. 基本的な管理原則

### 1.1 不確定要素の優先的解消
- **リスク先行型アプローチ**: 最も不確実性の高い要素から着手する習慣
- **仮説検証サイクル**: 小さな実験で大きなリスクを早期に検証する習慣
- **決断の遅延コスト認識**: 不確実性を放置することの実際のコストを意識
- **前進感の確保**: 不確定要素を解消することで得られる「進んでいる感覚」によるモチベーション維持

### 1.2 前倒し作業による余裕の創出
- **締切前倒しの原則**: 実際の締切よりも20-30%早く完了するよう計画する
- **バッファ確保の習慣化**: 予想外の問題に対処するための時間的余裕を常に確保
- **ストレスのない状態の維持**: スケジュールに追われるのではなく、余裕を持って取り組む環境作り
- **良いサイクルの構築**: 前倒し→余裕→高品質→自信→モチベーション向上の好循環を意識
- **自己嫌悪の防止**: ギリギリの納期や遅延による自己批判の連鎖を予防

### 1.3 パーキンソンの法則と期限設定
- **短期期限の明示的設定**: 作業前に具体的な期限を必ず設定（「今日17時まで」など）
- **暫定解の許容**: 完璧を求めず期限内での暫定解を重視し次のステップに進む
- **見積もりの継続的改善**: 実際の所要時間と予測のギャップを記録し学習に活用
- **タイムブロッキング**: カレンダーに作業時間を事前予約し視覚化する習慣

### 1.4 結果と成果の区別
- **成果(outcome)の明確化**: 全活動の前に「これにより何が改善されるのか」を定義
- **意味のある指標**: 単なる活動量ではなく価値創出に関連する指標での進捗測定
- **コミュニケーション構造の最適化**: 「目的→成果→結論」の順序での情報共有

### 1.5 構造整理の徹底
- **思考の外部化**: 頭の中のアイデアをまず書き出し俯瞰する習慣
- **整理のための一時停止**: 行動前に「本当にこれが最適か」と問い直す習慣
- **構造化ツールの活用**: マインドマップや階層リストなどの視覚的整理ツールの活用

### 1.6 プロジェクト完了優先の原則
- **完了の価値最大化**: 80%完了した3つのプロジェクトより、100%完了した1つのプロジェクトを優先
- **適切な完了基準の設定**: 「理想的な完了」ではなく「価値提供可能な完了」の基準採用
- **完了ファーストの選択**: リソース配分やタスク優先順位付けで、完了に近いプロジェクトを優先
- **完了までの道筋の明確化**: 全プロジェクトで「ここから完了までの具体的なステップ」を常に明確化
- **新規着手の抑制**: 進行中プロジェクトの完了前に新プロジェクトへの大規模なリソース投入を避ける

## 2. フォルダ構造と命名規則

### 2.1 全体フォルダ構造
```
Projects/
├── _Archive         # 完了または休止中のプロジェクト
├── Main             # 主力プロジェクト
│   ├── refurbish
│   ├── satellite_solar_scan
│   └── ...
├── _Management      # 全体管理用フォルダ（このフォルダ）
├── Sub              # 副次的なプロジェクト
│   └── ...
└── Support          # 運営支援プロジェクト
    └── ...
```

### 2.2 各プロジェクトフォルダの標準構造
```
[プロジェクト名]/
├── README.md        # プロジェクト概要
├── SPECS.md         # 技術仕様書（技術プロジェクトの場合）
├── PROJECT.md       # プロジェクト管理情報
├── src/             # ソースコード（技術プロジェクトの場合）
├── docs/            # ドキュメント
│   ├── technical/   # 技術ドキュメント
│   ├── business/    # 事業関連ドキュメント
│   └── planning/    # 計画関連ドキュメント
└── notes/           # 作業メモ、アイデア
    ├── ideas/       # アイデア集
    ├── meetings/    # ミーティングノート
    └── research/    # 調査メモ
```

### 2.3 ファイル命名規則
- すべてのドキュメントファイルは拡張子 `.md`（マークダウン）を使用
- 日付を含めるファイルは `YYYY-MM-DD-[内容].md` の形式（例: `2025-04-04-weekly-review.md`）
- 単語の区切りはハイフン（`-`）を使用
- すべて小文字を使用（特殊な固有名詞を除く）

## 3. プロジェクトライフサイクル

### 3.1 プロジェクト分類と移行基準
- **Main**: 月20時間以上を投資する主要プロジェクト（最大2つまで）
- **Sub**: 週2-5時間程度を投資する副次的プロジェクト（最大3つまで）
- **Support**: 運営を支援するプロジェクト（必要最小限に維持）
- **_Archive**: 完了、休止、または保留中のプロジェクト

### 3.2 新規プロジェクト開始プロセス
1. プロジェクト提案書の作成（`PROJECT.md`の初版）
2. リソース見積もりと投資判断
3. プロジェクトフォルダの作成と初期化
4. キックオフと初期マイルストーンの設定

### 3.3 プロジェクト終了/アーカイブプロセス
1. 最終レビューと学びの記録
2. 成果物の整理とドキュメント化
3. `_Archive`フォルダへの移動
4. プロジェクト終了報告書の作成

## 4. 複数プロジェクトの並行管理

### 4.1 時間・エネルギー配分の原則
- 主力プロジェクトには全リソースの60-70%を配分
- 副次的プロジェクトには全リソースの20-30%を配分
- 運営支援には全リソースの10-20%を配分
- 過集中期には特定プロジェクトに80%以上を集中投資

### 4.2 プロジェクト間の切り替え方法
- 作業の中断/再開時には「次回の自分への引継ぎノート」を必ず作成
- プロジェクト切り替え前に5-10分の「クロージング儀式」を行う
- 各プロジェクトの「再開儀式」を定義し、素早く集中状態に入れるようにする

### 4.3 コンテキストスイッチのコスト最小化
- 関連性の高いタスクをグループ化して取り組む
- 1日のうちでプロジェクト切り替えは最大2回までに制限
- 切り替え時には前後15分のバッファ時間を設定

## 5. レビューと振り返りの体系

### 5.1 日次振り返り
- 1日の終わりに10分以内で完了
- 達成したこと、学んだこと、次の日のToDo確認
- `templates/daily-checkin.md`を使用

### 5.2 週次振り返り
- 週末に30分程度で実施
- 週の成果、課題、学び、次週の計画を整理
- `templates/weekly-review.md`を使用

### 5.3 月次統合レビュー
- 月末に1-2時間かけて実施
- 全プロジェクトの進捗、リソース配分の最適化、方向性の調整
- `templates/integrated-report-template.md`を使用

### 5.4 四半期戦略レビュー
- 3ヶ月毎に半日程度かけて実施
- 大きな方向性の確認、プロジェクトポートフォリオの見直し
- 長期目標との整合性確認

## 6. 生成AIを活用した管理最適化

### 6.1 日常的なAI活用ポイント
- 毎日の計画と振り返りに生成AIを対話パートナーとして活用
- プロジェクト間の優先順位付けや意思決定の支援に活用
- 構造化した問いかけで具体的なアドバイスを引き出す

### 6.2 プロジェクト管理におけるAI活用
- プロジェクト計画の妥当性検証
- リスク要因の特定と対策の検討
- 進捗報告書のレビューと改善提案

### 6.3 管理システム自体の継続的改善
- 月に一度、この管理システム自体の有効性をAIと共に評価
- 使用していないテンプレートや過剰に複雑な部分を特定し簡素化
- 新たに必要となったガイドラインやテンプレートの追加

---

**変更履歴:**
- 2025-04-04: 初版作成