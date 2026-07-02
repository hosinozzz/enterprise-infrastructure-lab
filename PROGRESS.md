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
| Golden Image 用 Full Clone 作成 | Done | VMware Full Clone |
| Oracle Installation Baseline Snapshot 取得 | Done | VMware Snapshot |

### RHEL / 運用環境

| 項目 | Status | Evidence |
| --- | --- | --- |
| RHEL 8.10 Base 構成 | Done | RHEL VM |
| VMware Tools 構成 | Done | VMware guest tools |
| OpenSSH 構成 | Done | SSH service |
| `oracle` ユーザー作成 | Done | OS user |
| `root` パスワード設定 | Done | OS setting |
| Firewall で SSH 許可 | Done | Firewall setting |
| Tera Term 接続確認 | Done | SSH client connection |
| Server with GUI 追加導入 | Done | GUI package group |
| `graphical.target` 設定 | Done | systemd default target |
| GNOME Desktop ログイン確認 | Done | GUI login |

### Red Hat

| 項目 | Status | Evidence |
| --- | --- | --- |
| Developer for Individuals 登録 | Done | Red Hat account |
| `subscription-manager` 登録 | Done | RHEL subscription |
| BaseOS Repository 有効化 | Done | RHEL repository |
| AppStream Repository 有効化 | Done | RHEL repository |
| `dnf update` 実施 | Done | Package update |

### Oracle Database 19c インストール前準備

| 項目 | Status | Evidence |
| --- | --- | --- |
| Oracle Installation Readiness Check | Done | OS requirement check |
| Memory 確認 | Done | Readiness check |
| Swap 確認 | Done | Readiness check |
| Disk 容量確認 | Done | Readiness check |
| Hostname 確認 | Done | Readiness check |
| Oracle User 確認 | Done | Readiness check |
| Kernel Version 確認 | Done | Readiness check |
| SELinux 確認 | Done | Readiness check |
| Firewall 確認 | Done | Readiness check |
| VMware 環境確認 | Done | Readiness check |
| Oracle Prerequisite Package 確認 | Done | RPM package check |
| 不足 Package 追加インストール | Done | RPM package install |
| 必要 Package の `rpm` 確認 | Done | RPM verification |
| Oracle Directory Layout 作成 | Done | `/u01/app` layout |
| `ORACLE_HOME` 配置先作成 | Done | `/u01/app/oracle/product/19.0.0/dbhome_1` |
| Oracle Inventory 用 Directory 管理 | Done | `/u01/app/oraInventory` |

## 2026-07-02

### Completed

- Installed RHEL 8.10
- Configured Oracle 19c preinstallation environment
- Created VMware Golden Image before Oracle software installation

### Oracle Database 19c インストール直前OSチューニング

| 項目 | Status | Evidence |
| --- | --- | --- |
| Oracle Environment Variables 設定 | Done | `oracle` user `.bash_profile` |
| `ORACLE_BASE` 設定 | Done | `.bash_profile` |
| `ORACLE_HOME` 設定 | Done | `.bash_profile` |
| `ORACLE_SID` 設定 | Done | `.bash_profile` |
| `PATH` 設定 | Done | `.bash_profile` |
| Oracle Resource Limits 設定 | Done | `/etc/security/limits.d/oracle.conf` |
| `nofile` 設定 | Done | `oracle.conf` |
| `nproc` 設定 | Done | `oracle.conf` |
| `stack` 設定 | Done | `oracle.conf` |
| Oracle Kernel Parameters 設定 | Done | `/etc/sysctl.d/99-oracle.conf` |
| `fs.aio-max-nr` 設定 | Done | `99-oracle.conf` |
| `kernel.sem` 設定 | Done | `99-oracle.conf` |
| `net.ipv4.ip_local_port_range` 設定 | Done | `99-oracle.conf` |
| `net.core.rmem_default` 設定 | Done | `99-oracle.conf` |
| `net.core.rmem_max` 設定 | Done | `99-oracle.conf` |
| `net.core.wmem_default` 設定 | Done | `99-oracle.conf` |
| `net.core.wmem_max` 設定 | Done | `99-oracle.conf` |
| `sysctl --system` 実行 | Done | Kernel Parameter applied |
| Kernel Parameter 適用確認 | Done | sysctl verification |
| SELinux `Permissive` 変更 | Done | Lab configuration |
| Oracle Installation Baseline Snapshot 取得 | Done | VMware Snapshot |

### Oracle Database 19c Software配置

| 項目 | Status | Evidence |
| --- | --- | --- |
| Oracle Software Download | Done | `LINUX.X64_193000_db_home.zip` |
| Oracle Software Staging Directory 作成 | Done | `/u01/software` |
| Oracle Software Staging | Done | `/u01/software` |
| Oracle Home 展開 | Done | `/u01/app/oracle/product/19.0.0/dbhome_1` |
| `runInstaller` 確認 | Done | Oracle Home component |
| `root.sh` 確認 | Done | Oracle Home component |
| `OPatch` 確認 | Done | Oracle Home component |
| `network` Directory 確認 | Done | Oracle Home component |
| `bin` Directory 確認 | Done | Oracle Home component |
| Oracle Home サイズ確認 | Done | 約 6.5GB |
| Server with GUI 追加導入 | Done | RHEL GUI environment |
| `graphical.target` 設定 | Done | systemd default target |
| GNOME Desktop ログイン確認 | Done | GUI login |
| OUI 実行準備 | Done | GUI environment ready |

## Current Environment

| 項目 | 内容 | Status |
| --- | --- | --- |
| 仮想化基盤 | VMware Workstation Pro | Done |
| OS | RHEL 8.10 Base | Done |
| CPU | 1 Socket / 4 Core | Done |
| Memory | 8GB | Done |
| Disk | 50GB Thin Provision | Done |
| Network | NAT | Done |
| GUI | GNOME Desktop | Done |

## 導入済み Oracle Prerequisite Package

| Package | Status |
| --- | --- |
| `gcc` | Done |
| `gcc-c++` | Done |
| `glibc-devel` | Done |
| `ksh` | Done |
| `libaio-devel` | Done |
| `libstdc++-devel` | Done |
| `make` | Done |
| `sysstat` | Done |
| `unzip` | Done |
| `elfutils-libelf-devel` | Done |

## Oracle Directory Layout

```text
/u01
├── software
└── app
    ├── oracle
    │   └── product
    │       └── 19.0.0
    │           └── dbhome_1
    └── oraInventory
```

| Directory | Status | 用途 |
| --- | --- | --- |
| `/u01` | Done | Oracle 関連ファイル配置領域 |
| `/u01/software` | Done | Oracle Software 保管領域 |
| `/u01/app/oracle` | Done | `ORACLE_BASE` |
| `/u01/app/oracle/product/19.0.0/dbhome_1` | Done | `ORACLE_HOME` |
| `/u01/app/oraInventory` | Done | Oracle Inventory |

## Oracle Software / Oracle Home

| 項目 | 内容 | Status |
| --- | --- | --- |
| Software Archive | `LINUX.X64_193000_db_home.zip` | Done |
| Software Staging | `/u01/software` | Done |
| Oracle Home | `/u01/app/oracle/product/19.0.0/dbhome_1` | Done |
| Oracle Home Size | 約 6.5GB | Done |

| Oracle Home 構成要素 | Status |
| --- | --- |
| `runInstaller` | Done |
| `root.sh` | Done |
| `OPatch` | Done |
| `network` | Done |
| `bin` | Done |

## GUI Environment

| 項目 | Status | 備考 |
| --- | --- | --- |
| Server with GUI 追加導入 | Done | RHEL 8.10 Minimal へ追加 |
| `graphical.target` 設定 | Done | systemd default target |
| GNOME Desktop ログイン | Done | GUI login confirmed |
| OUI 実行準備 | Done | Oracle Universal Installer 実行可能状態 |

## Oracle DBA Memo

| 項目 | Status | 備考 |
| --- | --- | --- |
| OS Validation | Done | Oracle Installer 実行前確認 |
| Prerequisite Package | Done | 不足 Package を追加導入 |
| Directory Layout | Done | Oracle Software 配置先を準備 |
| Oracle Environment Variables | Done | `oracle` user profile |
| Oracle Resource Limits | Done | Oracle 専用 limits 設定 |
| Oracle Kernel Parameters | Done | Oracle 向け sysctl 設定 |
| SELinux Configuration | Done | Lab 用途として `Permissive` |
| Oracle Installation Baseline Snapshot | Done | Software Installation 直前の復旧点 |
| Oracle Software Download | Done | 19c Software 取得 |
| Oracle Software Staging | Done | `/u01/software` |
| Oracle Home 展開 | Done | `ORACLE_HOME` |
| GUI Environment | Done | OUI 実行準備 |
| Oracle Software Installation | Not Started | OUI 実行前 |

Oracle Database 19c では、Software を事前に `ORACLE_HOME` へ展開してから `runInstaller` を実行する方式です。

今回の作業では Oracle Home の構成および役割を確認し、Oracle Universal Installer 実行前の状態まで構築を完了しました。

## Oracle Silver / Gold 学習ポイント

| 学習項目 | Status | 対応するHands-on |
| --- | --- | --- |
| Oracle Prerequisite Package の役割 | Done | RPM Package 確認・導入 |
| Oracle 公式 Directory Layout | Done | `/u01/app` 構成作成 |
| `ORACLE_BASE` | Done | `/u01/app/oracle` |
| `ORACLE_HOME` | Done | `/u01/app/oracle/product/19.0.0/dbhome_1` |
| Oracle Inventory | Done | `/u01/app/oraInventory` |
| Oracle Installation Readiness Check | Done | OS 要件確認 |
| Oracle Environment Variables | Done | `.bash_profile` 設定 |
| Oracle Resource Limits | Done | `/etc/security/limits.d/oracle.conf` |
| Oracle Kernel Parameters | Done | `/etc/sysctl.d/99-oracle.conf` |
| SELinux と Lab 構成判断 | Done | `Permissive` 設定 |
| Oracle Installation Baseline | Done | VMware Snapshot 取得 |
| Oracle Software Staging | Done | `/u01/software` |
| Oracle Home 構成確認 | Done | `runInstaller`, `root.sh`, `OPatch`, `network`, `bin` |
| OUI 実行前GUI環境 | Done | Server with GUI / GNOME Desktop |

## 現在の進捗

### 完了

| 項目 | Status |
| --- | --- |
| RHEL 8.10 Base | Done |
| VMware Tools | Done |
| OpenSSH | Done |
| Oracle User | Done |
| Oracle Prerequisite Package | Done |
| Oracle Directory Layout | Done |
| Oracle Environment Variables | Done |
| Oracle Resource Limits | Done |
| Oracle Kernel Parameters | Done |
| SELinux Configuration | Done |
| Oracle Installation Baseline Snapshot | Done |
| Oracle Software Download | Done |
| Oracle Software Staging | Done |
| Oracle Home 展開 | Done |
| GUI Environment 構築 | Done |
| Oracle Universal Installer 実行準備完了 | Done |

### 未検証 / 次回予定

以下は今後の作業予定であり、現時点では検証済み手順ではありません。

| No. | 項目 | Status | 備考 |
| --- | --- | --- | --- |
| 1 | Oracle Universal Installer (OUI) | Not Started | 未検証 |
| 2 | Oracle Software Installation | Not Started | 未検証 |
| 3 | `root.sh` | Not Started | 未検証 |
| 4 | DBCA | Not Started | 未検証 |
| 5 | Listener Configuration | Not Started | 未検証 |
| 6 | RMAN | Not Started | 未検証 |
| 7 | Data Pump | Not Started | 未検証 |
| 8 | Oracle to Oracle Migration | Not Started | 未検証 |
| 9 | Validation | Not Started | 未検証 |
| 10 | Hyper-V 環境構築 | Not Started | 未検証 |
| 11 | Oracle Linux 環境構築 | Not Started | 未検証 |

## Golden Image / Snapshot 管理

| 項目 | Status | 用途 |
| --- | --- | --- |
| Oracle インストール前 RHEL 環境の保存 | Done | Oracle 構築用 VM の複製元 |
| Golden Image 用 Full Clone 作成 | Done | 長期利用する基準 VM |
| Oracle Installation Baseline Snapshot 取得 | Done | Oracle Software Installation 直前のロールバックポイント |

## ドキュメント完了条件

今後、個別の技術ドキュメントを `Done` とする条件は以下です。

- 実施した環境が記載されている
- 実施した日付が記載されている
- 実際に行った操作が記載されている
- 確認結果が記載されている
- 発生した問題があれば記載されている
- 検証済み事項と未検証事項が分離されている
