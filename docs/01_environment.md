# Environment

## 現在の環境

現在の検証環境は以下です。

| 項目 | 内容 |
| --- | --- |
| 仮想化基盤 | VMware Workstation |
| OS | Oracle Linux |
| Database | Oracle Database 19c |
| 管理 | Git / GitHub |

## 現在までに確認した構成要素

| 項目 | 状態 |
| --- | --- |
| VM 作成 | 確認済み |
| Oracle Linux 構築 | 確認済み |
| Oracle ユーザー作成 | 確認済み |
| Oracle Software 配置 | 確認済み |
| Oracle Home 展開 | 確認済み |
| GUI 環境構築 | 確認済み |
| Oracle Universal Installer 実行準備 | 確認済み |
| Git 管理 | 開始済み |

## 再構築方針

今後は Oracle Linux ではなく、RHEL 8.10 を前提に環境を再構築します。

理由は以下です。

- 本番環境に近い構成で学習するため
- Oracle 構築手順を RHEL 前提で整理するため
- Oracle Silver / Gold DBA 学習内容と実案件の構築観点を対応させるため

## 注意事項

現在の Oracle Linux 環境で得た内容は、構築経験として残します。

ただし、RHEL 8.10 再構築後の正式な構築手順とは分離して管理します。
