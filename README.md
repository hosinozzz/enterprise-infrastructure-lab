# Enterprise Infrastructure Lab

## プロジェクト概要

Enterprise Infrastructure Lab は、実際の Oracle Database Migration 案件を自宅環境で再現しながら、Oracle Database 構築・移行・運用を Hands-on で学習するためのリポジトリです。

このリポジトリは、インターネット上の一般論をまとめた資料置き場ではありません。実際に構築・検証した内容を最優先で記録し、未検証の内容は検証済みの記録と明確に分けて管理します。

## 構築の目的

本プロジェクトの目的は、Oracle Database 19c を中心としたオンプレミス相当のインフラ構築・移行作業を、自宅検証環境で段階的に再現することです。

最終的には、以下の領域を実機ベースで整理します。

- Oracle Database 19c 構築
- Oracle to Oracle Migration
- RMAN
- Data Pump
- Backup & Recovery
- Oracle Silver / Gold 学習
- Oracle DBA Hands-on
- GitHub による構築記録

## ドキュメント作成方針

本リポジトリでは、以下のルールを守ります。

- 実際に構築・検証した内容を優先して記録する
- 未実施・未検証の内容は、検証済みの手順として書かない
- 不足している情報は推測で補完せず、TODO または未検証として扱う
- 「検証済み」と「未検証」を必ず区別する
- 手順、確認結果、作業目的、判断理由を可能な限り残す
- 実際の SI 案件で参照できる構築ドキュメント品質を目指す

## Current Environment

現在の検証環境は以下の通りです。

| 項目 | 内容 |
| --- | --- |
| 仮想化基盤 | VMware Workstation Pro |
| OS | RHEL 9.2 Minimal |
| CPU | 1 Socket / 4 Core |
| Memory | 8GB |
| Disk | 50GB Thin Provision |
| Network | NAT |

## 検証済み作業

以下は、現時点で実施済みとして記録する作業です。

### GitHub / Codex

- GitHub Repository 作成
- Enterprise Infrastructure Lab 作成
- Codex Project 作成

### VMware

- VMware Workstation Pro インストール
- VM 保存先変更
- Snapshot 取得
- Golden Image 用 Full Clone 作成

### RHEL

- RHEL 9.2 Minimal インストール
- `oracle` ユーザー作成
- `root` パスワード設定

### Red Hat

- Developer for Individuals 登録
- `subscription-manager` 登録
- BaseOS / AppStream Repository 有効化
- `dnf update` 実施

### 運用環境

- `open-vm-tools` インストール
- `vmtoolsd` 動作確認
- OpenSSH Server 設定
- Firewall で SSH 許可
- Tera Term 接続確認

### Oracle Database 19c インストール前準備

Oracle Database 19c インストール前の Prerequisite 環境を構築しました。

実際の Oracle 構築案件を想定し、Oracle Database をインストールする前段階として OS 要件の確認、Prerequisite Package の導入、Oracle Software 配置用の Directory Layout 作成を実施しました。

#### Oracle Installation Readiness Check

以下の項目を確認しました。

- Memory
- Swap
- Disk 容量
- Hostname
- Oracle User
- Kernel Version
- SELinux
- Firewall
- VMware 環境

確認結果として、Oracle Database 19c をインストール可能な状態であることを確認しました。

#### Oracle Prerequisite Package

Oracle Database 19c に必要となる RPM Package を確認し、不足していた Package を追加インストールしました。

導入した Package は以下です。

- `gcc`
- `gcc-c++`
- `glibc-devel`
- `ksh`
- `libaio-devel`
- `libstdc++-devel`
- `make`
- `sysstat`
- `unzip`
- `elfutils-libelf-devel`

必要 Package が正常に導入されていることを `rpm` コマンドで確認しました。

#### Oracle Directory Layout

Oracle 公式ベストプラクティスを参考に、以下の Directory Layout を採用しました。

```text
/u01
└── app
    ├── oracle
    │   └── product
    │       └── 19.0.0
    │           └── dbhome_1
    └── oraInventory
```

Oracle Software は `ORACLE_HOME` へ配置し、Inventory は独立した Directory として管理する構成とします。

`oraInventory` は Oracle Installer による自動生成も考慮し、Oracle 標準構成に合わせて管理します。

## Golden Image と Snapshot の位置付け

Oracle Database をインストールする前の RHEL 9 環境を Golden Image として保存しています。

今後は、この Golden Image から Oracle 構築用 VM を複製し、Oracle Database 19c のインストールや移行検証を進めます。

### Golden Image

Golden Image は、再利用可能な基準 VM です。

主な目的は以下です。

- Oracle インストール前のクリーンな RHEL 9 環境を保持する
- 同じ前提条件の VM を繰り返し作成できるようにする
- Oracle 構築、RMAN、Data Pump、移行検証などの開始地点を統一する

### Snapshot

Snapshot は、特定時点へロールバックするための一時的な復旧ポイントです。

主な目的は以下です。

- Oracle 構築作業中の失敗に備える
- 設定変更前の状態へ戻せるようにする
- 検証途中の試行錯誤を安全に行う

### 使い分け

| 項目 | Golden Image | Snapshot |
| --- | --- | --- |
| 用途 | VM 複製の基準 | 作業中のロールバック |
| 利用タイミング | 新しい検証 VM を作る時 | 構築・設定変更の前 |
| 保存期間 | 長期保存 | 一時利用 |
| 対象 | Oracle インストール前の標準環境 | 作業途中の特定時点 |

## Oracle DBA Memo

今回の作業では、Oracle Software のインストールはまだ実施していません。

Oracle Installer 実行前に、以下の作業までを完了しました。

- OS Validation
- Prerequisite Package
- Directory Layout

今後は Oracle Environment Variable 設定を行った後、Oracle Universal Installer (OUI) による Oracle Database 19c Software Installation を実施します。

## Oracle Silver / Gold 学習ポイント

今回の作業は、Oracle Database 構築前の前提条件確認とインストール準備に対応します。

学習した内容は以下です。

- Oracle Prerequisite Package の役割
- Oracle 公式 Directory Layout
- `ORACLE_BASE`
- `ORACLE_HOME`
- Oracle Inventory
- Oracle Installation Readiness Check

Oracle Silver / Gold 学習では、Oracle Database の構成要素や管理対象を理解するだけでなく、実際にインストール可能な OS 状態を整える観点が重要になります。本リポジトリでは、資格学習の知識を Hands-on の構築記録と対応させて整理します。

## 今後のロードマップ

今後は以下の順序で検証を進めます。

1. Oracle Environment Variables
2. Oracle User Profile 設定
3. Oracle Universal Installer (OUI)
4. `root.sh`
5. Oracle Software Installation
6. DBCA
7. Listener Configuration
8. RMAN
9. Data Pump
10. Oracle to Oracle Migration
11. Validation
12. Hyper-V 環境構築
13. Oracle Linux 環境構築

上記は現時点では今後の予定であり、検証済み手順ではありません。実際に Hands-on で確認した後、個別ドキュメントとして追加します。

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

## 関連ドキュメント

- [ROADMAP.md](./ROADMAP.md)
- [PROGRESS.md](./PROGRESS.md)
