# Enterprise Infrastructure Lab

## プロジェクト概要

Enterprise Infrastructure Lab は、Oracle Database 19c の学習および Oracle Database Silver DBA 資格取得を目的としたハンズオン構築プロジェクトです。

Oracle Database のインストール、OS 前提設定、トラブルシューティング、DBCA、Listener、バックアップ・リカバリ、移行検証を段階的に実施し、実際に確認した内容のみを GitHub に記録します。

将来的には、インフラエンジニア / Oracle DBA としての GitHub Portfolio として公開できる品質を目指します。

## ドキュメント方針

本リポジトリでは、以下の方針でドキュメントを管理します。

- 実際に構築・検証した内容を優先して記録する
- 未実施・未検証の内容を、検証済み手順として記載しない
- インターネット上の一般論だけで資料を作成しない
- 不足情報は推測で補完せず、TODO として管理する
- 「検証済み」と「未検証」を明確に区別する
- 日本企業の SI 案件で参照できる構築ドキュメント品質を意識する

## 現在の環境

現在の検証環境は以下です。

| 項目 | 内容 |
| --- | --- |
| 仮想化基盤 | VMware Workstation Pro |
| OS | Red Hat Enterprise Linux 8.10 |
| Database | Oracle Database 19c (構築予定) |
| 管理 | Git / GitHub |

Oracle Linux 環境で得られた検証結果をアーカイブとして保持し、
現在は RHEL 8.10 をベースとした Oracle Database 19c 検証環境を新たに構築しています。

## 現在までに完了した内容

- VMware 仮想マシン作成
- Red Hat Enterprise Linux 8.10 インストール
- root パスワード設定
- oracle ユーザー作成
- sudo 権限確認
- Hostname 設定
- Red Hat Subscription 登録
- dnf update 実施
- Oracle Lab Base Environment 構築

## 判明した課題

Oracle Linux 上で構築を進める中で、今後の学習・案件再現性を考慮し、以下の課題を整理しました。

- Oracle Linux ではなく RHEL 8.10 で環境を統一する
- 現在の環境は検証経験として残し、環境を最初から作り直す
- 再構築後の手順は、RHEL 8.10 を前提とした構築記録として改めて整理する

## 再構築前チェックポイント

今回のコミットは、RHEL 8.10 へ再構築する前のチェックポイントとして位置付けます。

この時点での目的は、Oracle Linux で得た構築経験、確認済み事項、課題、次の作業方針を明確に残すことです。

## 次のステップ

今後は以下の順序で再構築を進めます。

1. OpenSSH 構成
2. open-vm-tools
3. GUI 環境確認
4. Oracle 19c Preinstall
5. Oracle Software Installation
6. DBCA
7. Listener

## Repository Structure

```text
.
├── README.md
├── ROADMAP.md
├── PROGRESS.md
├── docs/
│   ├── 00_project_overview.md
│   ├── 01_environment.md
│   ├── 02_progress.md
│   ├── 03_todo.md
│   ├── aws/
│   ├── hyper-v/
│   ├── linux/
│   ├── migration/
│   ├── middleware/
│   ├── oracle-database/
│   ├── troubleshooting/
│   ├── vmware/
│   └── windows-server/
├── architecture/
├── diagrams/
├── scripts/
└── templates/
```

## 関連ドキュメント

- [Project Overview](./docs/00_project_overview.md)
- [Environment](./docs/01_environment.md)
- [Progress](./docs/02_progress.md)
- [TODO](./docs/03_todo.md)
- [ROADMAP.md](./ROADMAP.md)
- [PROGRESS.md](./PROGRESS.md)
