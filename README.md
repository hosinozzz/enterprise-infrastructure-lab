# Enterprise Infrastructure Lab

このリポジトリは、インフラエンジニアとして実際に構築・検証・調査・障害対応した内容を記録するための技術資産です。

AIが自動生成した手順集ではなく、Hands-onで確認した事実のみを残します。

## Purpose

このプロジェクトの目的は、Oracle to Oracle Migration を中心に、オンプレミスおよびAWS上のエンタープライズインフラ技術を継続的に学習・再現・記録することです。

主な対象領域は以下です。

- VMware ESXi から Hyper-V への基盤理解
- Windows Server / RHEL / Oracle Linux の構築・運用
- Oracle Database の移行・バックアップ・リカバリ・調査
- Application Server / Web Server の構成理解
- Oracle Exadata の概念理解
- AWS上でのOracle Linuxおよび関連インフラ検証

## Repository Policy

このリポジトリでは、以下のルールを守ります。

- 実際にHands-onで実施した内容のみ記録する
- 未実施の手順は書かない
- 推測で構成・手順・原因・対策を書かない
- 実施日、環境、確認結果をできる限り明記する
- Markdownで管理する
- GitHub上で継続的にレビュー・改善する
- 企業向けドキュメントとして読める品質を目指す

## Documentation Principles

各ドキュメントは、以下の観点を重視します。

- What: 何を実施したか
- Why: なぜ実施したか
- Environment: どの環境で確認したか
- Procedure: 実際に行った操作
- Result: 確認できた結果
- Issue: 発生した問題
- Lesson Learned: 得られた知見

未確認の内容は `TODO` として残すのではなく、原則として記載しません。将来実施予定の内容は [ROADMAP.md](./ROADMAP.md) に分離します。

## Repository Structure

```text
.
├── README.md
├── ROADMAP.md
├── PROGRESS.md
├── architecture/
├── docs/
│   ├── aws/
│   ├── hyper-v/
│   ├── linux/
│   ├── migration/
│   ├── middleware/
│   ├── oracle-database/
│   ├── troubleshooting/
│   ├── vmware/
│   └── windows-server/
├── diagrams/
│   └── drawio/
├── scripts/
│   ├── linux/
│   ├── powershell/
│   └── sql/
└── templates/
```

## Directory Purpose

| Directory | Purpose |
| --- | --- |
| `architecture/` | 全体構成、移行方式、設計観点の整理 |
| `docs/vmware/` | VMware ESXi に関する実機確認メモ |
| `docs/hyper-v/` | Hyper-V に関する構築・検証記録 |
| `docs/windows-server/` | Windows Server の構築・運用記録 |
| `docs/linux/` | RHEL / Oracle Linux の構築・運用記録 |
| `docs/aws/` | AWS上での検証記録 |
| `docs/oracle-database/` | Oracle Database の操作・調査・検証記録 |
| `docs/middleware/` | Application Server / Web Server の構成記録 |
| `docs/migration/` | Oracle to Oracle Migration の検証記録 |
| `docs/troubleshooting/` | 障害対応、調査、原因分析、再発防止 |
| `diagrams/drawio/` | draw.io 形式の構成図 |
| `scripts/linux/` | Linux向けShell Script |
| `scripts/powershell/` | Windows / Hyper-V 向けPowerShell |
| `scripts/sql/` | Oracle Database 向けSQLサンプル |
| `templates/` | Markdown記録用テンプレート |

## Current Status

このリポジトリは初期構成作成段階です。

技術ドキュメントは、実際のHands-on実施後に追加します。

## Related Files

- [ROADMAP.md](./ROADMAP.md)
- [PROGRESS.md](./PROGRESS.md)
