# Roadmap

このドキュメントは、Enterprise Infrastructure Lab の今後の検証計画を整理するためのロードマップです。

ここに記載している内容は、今後の予定を含みます。検証済みの作業は [PROGRESS.md](./PROGRESS.md) で管理します。

## Phase 0: Repository / Lab Foundation

- [x] GitHub Repository 作成
- [x] Enterprise Infrastructure Lab 作成
- [x] Codex Project 作成
- [x] README 作成
- [x] Progress Checklist 作成
- [x] Roadmap 作成

## Phase 1: RHEL Golden Image

- [x] VMware Workstation Pro インストール
- [x] VM 保存先変更
- [x] RHEL 9.8 Base 構成
- [x] `oracle` ユーザー作成
- [x] `root` パスワード設定
- [x] Developer for Individuals 登録
- [x] `subscription-manager` 登録
- [x] BaseOS / AppStream Repository 有効化
- [x] `dnf update` 実施
- [x] VMware Tools 構成
- [x] OpenSSH 構成
- [x] Firewall で SSH 許可
- [x] Tera Term 接続確認
- [x] Golden Image 用 Full Clone 作成

## Phase 2: Oracle Database 19c Preinstall Readiness

- [x] Oracle Installation Readiness Check
- [x] Memory / Swap / Disk 容量確認
- [x] Hostname / Oracle User / Kernel Version 確認
- [x] SELinux / Firewall / VMware 環境確認
- [x] Oracle Prerequisite Package 確認
- [x] 不足 Package 追加インストール
- [x] `rpm` コマンドによる Package 導入確認
- [x] Oracle Directory Layout 作成
- [x] `ORACLE_BASE` / `ORACLE_HOME` / Oracle Inventory 配置方針整理

## Phase 3: Oracle Database 19c OS Tuning

- [x] Oracle Environment Variables
- [x] Oracle User Profile 設定
- [x] Oracle Resource Limits
- [x] Oracle Kernel Parameters
- [x] `sysctl --system` による Kernel Parameter 反映
- [x] SELinux `Permissive` 設定
- [x] Oracle Installation Baseline Snapshot 取得

## Phase 4: Oracle Database 19c Software Install

- [ ] Oracle Database 19c Software 配置
- [ ] Oracle Universal Installer (OUI)
- [ ] `root.sh`
- [ ] Oracle Software Installation

## Phase 5: Database Creation / Network

- [ ] DBCA
- [ ] Listener Configuration
- [ ] Sample Database 作成

## Phase 6: Backup / Recovery

- [ ] RMAN 基本操作
- [ ] Backup 取得
- [ ] Restore / Recovery 検証
- [ ] 障害発生時の確認観点整理

## Phase 7: Data Movement

- [ ] Data Pump Export
- [ ] Data Pump Import
- [ ] 移行前後の確認項目整理
- [ ] Validation 手順整理

## Phase 8: Oracle to Oracle Migration

- [ ] 移行元 DB 準備
- [ ] 移行先 DB 準備
- [ ] 移行方式検討
- [ ] 移行作業実施
- [ ] 移行後 Validation
- [ ] 切り戻し観点整理

## Phase 9: Platform Expansion

- [ ] Hyper-V 環境構築
- [ ] Oracle Linux 環境構築
- [ ] AWS 上の Oracle Linux 検証

## Phase 10: Certification / DBA Learning

- [ ] Oracle Silver 学習記録
- [ ] Oracle Gold 学習記録
- [ ] Oracle DBA Hands-on 記録
- [ ] 学習内容と実機検証内容の対応整理

## 注意事項

- 未検証の手順は、検証済み手順として記載しない
- インターネット上の一般論だけで資料化しない
- 不足情報は TODO として扱う
- 検証後に README / PROGRESS / 個別ドキュメントへ反映する
