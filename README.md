# gopher
gopherは運用改善のために最前線で活躍したがっているIRC Botです。
基本的に独自の機能を提供しています。

# Commands
## topic-create
指定されたブランチ名からtopic/test, topic/test-masterdata, topic/test-assetbundleのブランチを作成して、PullRequestを作成します。
```shell
gopher: topic-create <branch_name> <github PR number>
```
github PR numberはconfigにあるpull_request_commentの末尾に付随します。

## topic-deploy
topic-createで作成されたブランチを一つのブランチにまーじしてpushします。
```shell
gopher: topic-deploy <server_name> <github PR number>
```
github PR numberはtestブランチがmasterブランチに対して作成したPullRequestのissue番号を書いてください。
issue番号からtopic-createで作成されたブランチを探し出し、新たしいブランチを作成後一つにマージします。

## topic-launch
topic-createで作成されたブランチを一つにマージし、指定のサブドメイン経由でアクセス出来る環境を構築します。
```shell
gopher: topic-launch <domain_name> <github PR number>
```
github PR numberはtestブランチがmasterブランチに対して作成したPullRequestのissue番号を書いてください。

## launch
指定したブランチが展開された環境に、指定のサブドメイン経由でアクセス出来る環境を構築します。
```shell
gopher: launch <domain_name> <branch_name>
```。

## help
ヘルプです。READMEを投げつけます。
```shell
gopher: help
```
