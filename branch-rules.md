# ブランチ命名規則

## 概要

このドキュメントでは、プロジェクトにおけるGitブランチの命名規則を定義します。一貫した命名規則により、チーム間のコラボレーションが円滑になり、プロジェクト管理が効率化されます。

## 基本原則

### 1. 文字の使用
- **小文字とハイフンのみ使用**：`kebab-case`形式を採用
- **日本語使用禁止**：英語のみでブランチ名を作成
- **特殊文字使用禁止**：アルファベット、数字、ハイフン（`-`）のみ許可

### 2. 長さの制限
- **最大50文字以内**：簡潔で分かりやすい名前を心がける
- **略語の使用**：必要に応じて一般的な略語を使用（例：`fix`、`feat`、`doc`）

### 3. 一意性
- **重複回避**：既存のブランチ名と重複しないこと
- **意味のある名前**：ブランチの目的が明確に分かること

## ブランチタイプ別命名規則

### 1. 機能開発（Feature）
```
feature/<機能名>[-issue番号]
```

**例：**
- `feature/user-authentication`
- `feature/payment-integration-123`
- `feature/dashboard-redesign`

### 2. バグ修正（Bugfix）
```
bugfix/<バグの内容>[-issue番号]
```

**例：**
- `bugfix/login-error`
- `bugfix/memory-leak-456`
- `bugfix/responsive-layout`

### 3. ホットフィックス（Hotfix）
```
hotfix/<緊急修正内容>[-issue番号]
```

**例：**
- `hotfix/security-vulnerability`
- `hotfix/payment-failure-789`
- `hotfix/data-corruption`

### 4. リリース（Release）
```
release/<バージョン番号>
```

**例：**
- `release/v1.2.0`
- `release/v2.0.0-beta`
- `release/v1.1.3`

### 5. 実験的機能（Experiment）
```
experiment/<実験内容>
```

**例：**
- `experiment/new-ui-framework`
- `experiment/performance-optimization`
- `experiment/ai-integration`

### 6. リファクタリング（Refactor）
```
refactor/<対象コンポーネント>
```

**例：**
- `refactor/database-layer`
- `refactor/api-endpoints`
- `refactor/authentication-service`

### 7. ドキュメント（Documentation）
```
docs/<ドキュメント内容>
```

**例：**
- `docs/api-documentation`
- `docs/installation-guide`
- `docs/coding-standards`

## Issue番号の扱い

### Issue連携がある場合
- ブランチ名の末尾にハイフンとissue番号を追加
- 例：`feature/user-profile-123`（issue #123に対応）

### Issue連携がない場合
- issue番号は省略可能
- 例：`feature/user-profile`

## 個人作業ブランチ

### 個人的な作業や実験の場合
```
<ユーザー名>/<作業内容>
```

**例：**
- `yamada/prototype-testing`
- `tanaka/research-new-library`
- `suzuki/personal-experiments`

## 禁止事項

### 使用してはいけない文字
- 大文字（A-Z）
- スペース
- アンダースコア（`_`）
- スラッシュの連続（`//`）
- 特殊文字（`@`, `#`, `$`, `%`, `&`, `*`, 等）

### 避けるべき名前
- `main`, `master`, `develop` などの予約語
- `test`, `tmp`, `temp` などの一時的な名前
- 数字のみの名前（例：`123`）
- 意味不明な略語や暗号的な名前

## 運用ガイドライン

### 1. ブランチ作成前の確認
- 同じ名前のブランチが存在しないか確認
- 作業内容に適したプレフィックスを選択
- Issue番号がある場合は必ず含める

### 2. レビュープロセス
- プルリクエスト作成時にブランチ名の妥当性を確認
- レビュアーは命名規則の遵守をチェック
- 不適切な場合は修正を依頼

### 3. 長期間のブランチ管理
- 30日以上更新がないブランチは定期的に確認
- マージ済みブランチは速やかに削除
- 作業が中断したブランチは適切にドキュメント化

## まとめ

この命名規則を遵守することで、以下のメリットが得られます：

1. **可読性の向上**：ブランチの目的が一目で分かる
2. **検索性の向上**：一貫した命名によりブランチを見つけやすい
3. **自動化の促進**：規則的な名前によりCI/CDの設定が容易
4. **チーム協力の促進**：統一されたルールによるスムーズなコラボレーション

---

*最終更新：2025年8月23日*