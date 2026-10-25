---
title: "レッスン 10 - まとめと次のステップ"
description: "Copilot CLI のワークフロー、2 つのプル リクエスト、再利用可能なカスタマイズ、追加リソースを振り返ります。"
authors:
  - geektrainer
lastUpdated: 2026-09-29
---

Tailspin Toys の一連のワークフローで GitHub Copilot CLI を使用しました。このレッスンでは、次の作業を行いました。

- Codespace を準備し、Copilot CLI をインストールしてプロジェクトを調べ、あらかじめ登録されたフィルター機能の Issue を見つけました。
- 星評価を追加し、転送したブラウザーで結果を確認して、最初のプル リクエスト (PR) を手動でマージしました。
- フィルター機能の Issue から始め、Plan モードで方針を決め、Autopilot モードで実装し、Interactive モードでレビューしました。
- カスタム指示でエージェントをガイドし、既存の `quality-checks` スキルをカスタマイズして、ユニット テスト、lint、型チェックを実行しました。
- Playwright Model Context Protocol (MCP) サーバーを追加し、実際のブラウザーでフィルター機能を確認しました。
- 品質保証 (QA) 用のカスタム エージェントを作成して選択し、要件、テスト範囲、スキルの結果、ブラウザーでの確認内容を評価しました。
- フィルター機能の変更全体をレビューし、フィルター機能の PR に対する Agent Merge を承認しました。
- コンテキストやモデルの管理、共有、必要に応じたクラウドへの委任に使うスラッシュ コマンドを確認しました。

## 提出した成果

このワークショップでは、更新済みの `main` から作成した別々のブランチで、2 つの PR の節目を達成します。

1. **星評価:** 既存の `starRating` と、評価がないことを明示する状態をゲーム カードに表示します。
2. **フィルター機能と品質ワークフロー:** フィルター機能を実装し、指示を更新して機能に適用します。`quality-checks` レポートをカスタマイズし、QA プロファイルを作成して、関連するテストを追加します。

フィルター機能の計画から PR の作成まで、同じ会話とブランチを使用しました。ワークショップを簡潔にするため、その作業を 1 つの PR にまとめています。

## さまざまな検証方法

自動テスト、自分で行うブラウザー確認、MCP を使った Copilot のブラウザー操作など、複数の方法でコードを確認しました。`quality-checks` スキルはユニット テスト、lint、型チェックを実行し、新しい形式で結果を報告しました。QA は PR の前に、要件とテスト範囲のレビューをそれらの結果と組み合わせました。

追加するテストは実際の不足を補うものにします。QA を実行しても新しいテストが不要な場合、それが正しいこともあります。マージを承認する前にコードと確認結果をレビューし、変更後は影響を受ける確認結果を更新します。

## ベスト プラクティス

Copilot に提供するコンテキストとツールが、作業の結果を左右します。このワークショップでは、指示を更新し、スキルをカスタマイズし、QA プロファイルを作成して、MCP サーバーを構成しました。これらのカスタマイズを複数の会話で再利用し、チームのニーズに合わせて調整します。指示は標準を定め、スキルは繰り返し行うタスクを記述し、カスタム エージェントは専門的な役割を定義し、MCP サーバーは外部ツールに接続します。エージェントの要約だけでなく、実際の変更とツールの結果を確認してください。

タスクに合わせて **モードとモデル** を選びます。実装前に方針を検討するときは **Plan**、対象を絞った変更で作業中も確認を続けるときは **Interactive**、範囲が明確なタスクには **Autopilot** を使用します。定型的な編集には高速なモデルを、複雑な作業にはより高性能なモデルを選びます。

インフラストラクチャと同じくらい、コンテキストも重要です。*何を*、*なぜ*、*どのように*作成するかを明確に説明すると、出力が大きく変わります。

## さらに試す

基本的なワークフローを一通り学びました。Copilot CLI のほかの機能も確認してみましょう。

- `/review` を使うと、コード レビュー エージェントに変更の分析を依頼できます。
- `/rubber-duck` を使うと、問題について話し合い、別の視点を得られます。
- `/fleet` を使うと、独立したサブタスクを並行して調整できます。
- `/worktree` を使うと、別のタスクを分離できます。
- `/delegate` を使うと、Copilot cloud agent にタスクを送信できます。

## 次のステップ

どのツールも、使い続けることが上達への近道です。本番コード、趣味のコード、あるいは何年も作ろうと思っていた小さなアプリで使ってみてください。学んだことをチームで共有し、チームの経験からも学びましょう。そして、いつものようにドキュメントも確認してください。

ターミナルから Tailspin Toys を拡張する場合は、オプションの [Foundry Backer Concierge シリーズ][foundry]に進みます。ほかの環境と比較するには、[VS Code ワークショップ][vscode]、[GitHub Copilot app ワークショップ][app]、[Copilot cloud agent ワークショップ][cloud]を確認してください。

## リソース

- [GitHub Copilot CLI について][about-cli]
- [Copilot CLI コマンド リファレンス][cli-reference]
- [Copilot CLI のカスタマイズ][customize-cli]
- [Copilot CLI でプル リクエストを管理する][manage-prs]

[previous-lesson]: ../9-cli-power-tools/
[foundry]: ../8-foundry-agent/
[vscode]: ../../vscode/
[app]: ../../app/
[cloud]: ../../cloud/
[about-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
[customize-cli]: https://docs.github.com/copilot/how-tos/copilot-cli/customize-copilot
[manage-prs]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/manage-pull-requests
