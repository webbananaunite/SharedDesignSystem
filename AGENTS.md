# AGENTS.md

このリポジトリは Swift Package `SharedDesignSystem` の開発・レビュー用です。
このファイルはローカル専用の AI ガードレールとして扱い、GitHub リモートへ push しません。

## Pull Request ブランチ命名ルール

- pull request 用ブランチを作成する場合は、変更内容に応じて次の接頭辞を使う。

| 接頭辞 | 用途 |
| --- | --- |
| `feature/` | 新機能 |
| `fix/` | バグ修正 |
| `ci/` | CI 設定 |
| `docs/` | ドキュメント |
| `refactor/` | リファクタ |
| `test/` | テスト追加 |
| `release/` | リリース準備 |

- 例: `feature/button-style`, `fix/ios-compatibility`, `docs/review-guardrails`

## ビルド出力ディレクトリのルール

- ローカル検証では、スナップショット保存時にプロジェクト容量が増えないよう、可能な限りプロジェクト外の `~/appOutput/SharedDesignSystem` を `--build-path` に指定する。
- CI では個人環境の home directory や絶対パスに依存しない。

## してはならない操作

- secret、token、署名鍵、認証情報を表示、保存、ログ出力しない。
- ユーザーの明示的な許可なしに `git reset --hard`、`git clean -fdx`、`git push --force`、`gh pr merge`、`gh release create` を実行しない。
