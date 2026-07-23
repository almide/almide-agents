# almide-agents

[English](./README.md)

Claude Code・Codexをはじめ、どんなコーディングAIエージェントにも、[Almide](https://github.com/almide/almide)を一発で正しく書けるようにする、置くだけのリファレンスパッケージです。

Almideは、AIによるコード生成のために設計された静的型付け言語です。コンパイラ自身の診断メッセージも、AIエージェントが読んで自動で直せる形式で書かれています。このパッケージは、その仕組みの最後の1ピースです。AIエージェントに、コードを書かせる前に渡してください。

## 内容

- **`AGENTS.md`** — [AGENTS.md](https://agents.md/)という、ツールをまたいで広まりつつある規約に沿ったリファレンスです（Codexなどのツールが、プロジェクトのルートから自動で読み込みます）。
- **`claude-skill/almide/SKILL.md`** — 同じ内容を、[Claude Codeのスキル](https://docs.claude.com/en/docs/claude-code/skills)として使える形にしたものです。

## 使い方

### Claude Code

スキルのディレクトリを、ユーザー単位のスキルフォルダにコピー（またはシンボリックリンク）してください

```bash
git clone https://github.com/almide/almide-agents.git /tmp/almide-agents
cp -r /tmp/almide-agents/claude-skill/almide ~/.claude/skills/almide
```

Almideに関する作業のときに、Claude Codeが自動で読み込みます。

### Codex（またはAGENTS.mdを読むツール全般）

`AGENTS.md`を、Almideを書きたいプロジェクトのルートにコピーしてください

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/almide/almide-agents/main/AGENTS.md
```

すでに`AGENTS.md`がある場合は、上書きせずにこの内容を追記してください。

### その他

`AGENTS.md`はツール専用の記法を含まない、普通のMarkdownです。システムプロンプトやプロジェクトの指示欄、チャットにそのまま貼り付けても、どのモデルでも使えます。

## 作った理由

Almide自身の[CHEATSHEET.md](https://github.com/almide/almide/blob/develop/docs/CHEATSHEET.md)は、もともとAIによるコード生成のために書かれています。このリポジトリは、それを「毎回手で貼り付けるもの」から「インストールするもの」に変えただけです。

## 更新について

このリファレンスは、本体[almide/almide](https://github.com/almide/almide)の`docs/CHEATSHEET.md`を写したものです。言語側に変更が入ったときは、そちらが正で、このリポジトリを追従させるPull Requestを歓迎します。
