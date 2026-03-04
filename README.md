# .github

a-d-systems 組織共通のGitHub設定リポジトリ。

個別リポジトリに同名のテンプレートがある場合はそちらが優先されます。

## 含まれるもの

### Issue Templates

- **機能改善・新機能** (`feature.yml`) — プロダクト改善や新機能の実装リクエスト
- **バグ報告** (`bug.yml`) — 不具合の報告

### PR Template

- `pull_request_template.md` — 全リポ共通のPRテンプレート

### Reusable Workflows

- **Codex Review** (`.github/workflows/codex-review.yml`) — PRに対してCodex CLIで自動コードレビューを実行
  - 規模判定（small/medium/large）に応じたレビュー戦略
  - arch review + diff review の2段階レビュー
  - 結果をPRコメントとして投稿、blockingがあればCIを失敗に

### セットアップ

#### Codex Review を各リポに導入する

1. Organization Secrets に `OPENAI_API_KEY` を設定
2. `codex-review-caller.yml` の内容を対象リポの `.github/workflows/codex-review.yml` にコピー
3. 必要に応じて `review_focus` パラメータでリポ固有の重点観点を設定

## 運用

詳細は [サービスチーム開発ワークフロー](https://github.com/a-d-systems/backlog/wiki/サービスチーム開発ワークフロー) を参照。
