# Progress Checklist

このドキュメントは、Enterprise Infrastructure Lab の進捗を管理するためのチェックリストです。

検証済みの作業と、今後実施予定の未検証作業を明確に分けて管理します。

## ステータス定義

| Status | 意味 |
| --- | --- |
| Done | 実施済み、または検証済み |
| In Progress | 作業中、または記録整理中 |
| Not Started | 未着手 |
| TODO | 情報不足、または今後追記予定 |
| Blocked | 環境・権限・前提条件不足により停止中 |

## 検証済み作業

### GitHub / Codex

| 項目 | Status | Evidence |
| --- | --- | --- |
| GitHub Repository 作成 | Done | GitHub Repository |
| Enterprise Infrastructure Lab 作成 | Done | Repository name |
| Codex Project 作成 | Done | Codex workspace |

### VMware

| 項目 | Status | Evidence |
| --- | --- | --- |
| VMware Workstation Pro インストール | Done | Local environment |
| VM 保存先変更 | Done | Local environment |
| Snapshot 取得 | Done | VMware Snapshot |
| Golden Image 用 Full Clone 作成 | Done | VMware Full Clone |

### RHEL

| 項目 | Status | Evidence |
| --- | --- | --- |
| RHEL 9.2 Minimal インストール | Done | RHEL VM |
| `oracle` ユーザー作成 | Done | OS user |
| `root` パスワード設定 | Done | OS setting |

### Red Hat

| 項目 | Status | Evidence |
| --- | --- | --- |
| Developer for Individuals 登録 | Done | Red Hat account |
| `subscription-manager` 登録 | Done | RHEL subscription |
| BaseOS Repository 有効化 | Done | RHEL repository |
| AppStream Repository 有効化 | Done | RHEL repository |
| `dnf update` 実施 | Done | Package update |

### 運用環境

| 項目 | Status | Evidence |
| --- | --- | --- |
| `open-vm-tools` インストール | Done | Installed package |
| `vmtoolsd` 動作確認 | Done | Running service/process |
| OpenSSH Server 設定 | Done | SSH service |
| Firewall で SSH 許可 | Done | Firewall setting |
| Tera Term 接続確認 | Done | SSH client connection |

## Current Environment

| 項目 | 内容 | Status |
| --- | --- | --- |
| 仮想化基盤 | VMware Workstation Pro | Done |
| OS | RHEL 9.2 Minimal | Done |
| CPU | 1 Socket / 4 Core | Done |
| Memory | 8GB | Done |
| Disk | 50GB Thin Provision | Done |
| Network | NAT | Done |

## 未検証 / 今後の予定

以下は今後の作業予定であり、現時点では検証済み手順ではありません。

| No. | 項目 | Status | 備考 |
| --- | --- | --- | --- |
| 1 | Oracle Preinstall | Not Started | Golden Image から複製後に実施予定 |
| 2 | Oracle Database 19c Software Install | Not Started | 未検証 |
| 3 | DBCA | Not Started | 未検証 |
| 4 | Listener 構築 | Not Started | 未検証 |
| 5 | Sample Database 作成 | Not Started | 未検証 |
| 6 | RMAN | Not Started | 未検証 |
| 7 | Data Pump | Not Started | 未検証 |
| 8 | Oracle to Oracle Migration | Not Started | 未検証 |
| 9 | Validation | Not Started | 未検証 |
| 10 | Hyper-V 環境構築 | Not Started | 未検証 |
| 11 | Oracle Linux 環境構築 | Not Started | 未検証 |

## Golden Image 管理

| 項目 | Status | 用途 |
| --- | --- | --- |
| Oracle インストール前 RHEL 9 環境の保存 | Done | Oracle 構築用 VM の複製元 |
| Snapshot 取得 | Done | Oracle 構築時のロールバック |
| Full Clone 作成 | Done | Golden Image として長期利用 |

## ドキュメント完了条件

今後、個別の技術ドキュメントを `Done` とする条件は以下です。

- 実施した環境が記載されている
- 実施した日付が記載されている
- 実際に行った操作が記載されている
- 確認結果が記載されている
- 発生した問題があれば記載されている
- 検証済み事項と未検証事項が分離されている
