# Dependabot PR調査ツール

## 使用方法

### Dependabot PR調査の依頼

Claude Codeに以下のプロンプトを送信してください：

```
https://github.com/[org]/[repo_name]/pull/[PR番号]
このPRはdependabotによって作成されたものです。
approveしてよいのか、次に示す手順に従って調査/確認をお願いします。
[配置場所フォルダパス]/ai-prompts/review-dependabot-pr/review-general.md
[配置場所フォルダパス]/ai-prompts/review-dependabot-pr/review-[任意の言語].md

結果は指示に従ってファイル出力してください。
```

### 言語別テンプレート

- **Python (uv)**: `review-python-uv.md`
- **Next.js**: `review-nextjs.md`
- **Rails**: `review-rails.md`  
- **Terraform (AWS)**: `review-terraform-aws.md`

## 出力先

調査結果は `[配置場所フォルダパス]/ai-prompts/dependabot-review-output/#[PR番号]/` に以下3つのファイルで出力されます：

- `dependabot-review-main-report.md` - 総合レポート（承認判定）
- `dependabot-review-technical-report.md` - 技術詳細分析
- `dependabot-review-[package-name]-proof.md` - 実証テスト記録
