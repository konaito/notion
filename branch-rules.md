# ブランチ命名規則

## 概要
このドキュメントでは、プロジェクトにおけるGitブランチの命名規則について説明します。一貫したブランチ名を使用することで、チーム間のコラボレーションを円滑にし、プロジェクトの管理を効率化します。

## 基本原則

### 1. 小文字とハイフンを使用
- ブランチ名は小文字のみを使用する
- 単語の区切りには ハイフン (`-`) を使用する
- アンダースコア (`_`) やスペースは使用しない

### 2. 簡潔で分かりやすい名前
- ブランチの目的が明確に分かる名前にする
- 不必要に長い名前は避ける
- 略語よりも完全な単語を優先する

## ブランチタイプ別命名規則

### メインブランチ
- `main` - プロダクション用のメインブランチ
- `develop` - 開発用のメインブランチ（使用する場合）

### 機能ブランチ (Feature Branches)
**フォーマット:** `feature/[機能名]` または `feat/[機能名]`

**例:**
```
feature/user-authentication
feature/dashboard-redesign
feat/payment-integration
feat/search-functionality
```

### バグ修正ブランチ (Bug Fix Branches)
**フォーマット:** `bugfix/[バグの説明]` または `fix/[バグの説明]`

**例:**
```
bugfix/login-error-handling
fix/memory-leak-in-cache
fix/incorrect-date-display
bugfix/api-timeout-issue
```

### ホットフィックスブランチ (Hotfix Branches)
**フォーマット:** `hotfix/[緊急修正の説明]`

**例:**
```
hotfix/security-vulnerability
hotfix/critical-payment-bug
hotfix/server-crash-fix
```

### リリースブランチ (Release Branches)
**フォーマット:** `release/[バージョン番号]`

**例:**
```
release/v1.2.0
release/v2.0.0-beta
release/1.5.3
```

### 実験・検証ブランチ (Experimental Branches)
**フォーマット:** `experiment/[実験内容]` または `spike/[調査内容]`

**例:**
```
experiment/new-ui-framework
spike/performance-optimization
experiment/ai-integration
```

### リファクタリングブランチ (Refactoring Branches)
**フォーマット:** `refactor/[リファクタリング対象]`

**例:**
```
refactor/user-service
refactor/database-queries
refactor/component-structure
```

### ドキュメントブランチ (Documentation Branches)
**フォーマット:** `docs/[ドキュメント内容]`

**例:**
```
docs/api-documentation
docs/setup-guide
docs/deployment-instructions
```

## Issue番号を含む場合
Issue番号がある場合は、ブランチ名の末尾に含めることができます。

**フォーマット:** `[タイプ]/[説明]-[issue番号]`

**例:**
```
feature/user-login-123
fix/button-alignment-456
docs/readme-update-789
```

## 個人ブランチ
個人的な作業や実験的な変更の場合は、ユーザー名を含めることができます。

**フォーマット:** `[ユーザー名]/[作業内容]`

**例:**
```
alice/prototype-feature
bob/code-review-fixes
```

## 禁止事項

### 使用してはいけない文字・パターン
- 日本語文字（ひらがな、カタカナ、漢字）
- 大文字
- スペース
- 特殊文字（`@`, `#`, `$`, `%` など）
- 数字のみのブランチ名
- 既存のGitコマンドと同じ名前（`HEAD`, `master` など）

### 避けるべき名前の例
```
# 悪い例
Feature/UserLogin        # 大文字を含む
fix_button_bug          # アンダースコア使用
feature/ユーザー認証     # 日本語文字
temp                    # 内容が不明
123                     # 数字のみ
bug fix                 # スペース含む
```

## ブランチの削除
作業が完了し、メインブランチにマージされたブランチは定期的に削除します。

```bash
# ローカルブランチの削除
git branch -d feature/completed-feature

# リモートブランチの削除
git push origin --delete feature/completed-feature
```

## チームでの運用

### レビュープロセス
- 機能ブランチは必ずプルリクエスト経由でマージする
- レビュー完了後、ブランチ作成者が削除責任を持つ

### 長期ブランチの管理
- 長期間使用するブランチは定期的にメインブランチからマージする
- 不要になったブランチは速やかに削除する

## まとめ
この命名規則に従うことで、以下のメリットが得られます：

- **可読性の向上** - ブランチの目的が名前から明確に分かる
- **検索性の向上** - 規則的な名前により、必要なブランチを素早く見つけられる
- **自動化の促進** - CI/CDパイプラインでのブランチ判定が容易になる
- **チーム協力の円滑化** - 一貫したルールにより、誰でも理解しやすい

このドキュメントは必要に応じて更新し、プロジェクトの成長とともに改善していきます。