---
title: 既知の問題とトラブルシューティング
titleSuffix: Azure Machine Learning service
description: Azure Machine Learning service に関するの既知の問題、回避策、トラブルシューティングの一覧を示します。
services: machine-learning
author: j-martens
ms.author: jmartens
ms.reviewer: mldocs
ms.service: machine-learning
ms.subservice: core
ms.topic: article
ms.date: 12/04/2018
ms.custom: seodec18
ms.openlocfilehash: b10e434aece0ac214a0fd397ea94cbeccca4e44a
ms.sourcegitcommit: 947b331c4d03f79adcb45f74d275ac160c4a2e83
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "55746492"
---
# <a name="known-issues-and-troubleshooting-azure-machine-learning-service"></a>Azure Machine Learning サービスの既知の問題とトラブルシューティング

この記事は、Azure Machine Learning サービスの使用時に発生したエラーや障害を見つけて修正するのに役立ちます。

## <a name="sdk-installation-issues"></a>SDK のインストールに関する問題

**エラー メッセージ:"Cannot uninstall 'PyYAML'" ('PyYAML' をアンインストールできません)**

Azure Machine Learning SDK for Python:PyYAML は distutils によってインストールされるプロジェクトです。 したがって、部分的なアンインストールが行われた場合、それに属しているファイルを正確に判別できません。 このエラーを無視して SDK のインストールを続行するには、次を使用します。

```Python
pip install --upgrade azureml-sdk[notebooks,automl] --ignore-installed PyYAML
```

## <a name="trouble-creating-azure-machine-learning-compute"></a>Azure Machine Learning コンピューティングの作成に関する問題

まれにですが、GA リリースの前に Azure portal から Azure Machine Learning ワークスペースを作成したユーザーが、そのワークスペースに Azure Machine Learning コンピューティングを作成できないことがあります。 サービスにサポート要求を送るか、ポータルまたは SDK を使って新しいワークスペースを作成してすぐにブロックを解除することができます。

## <a name="image-building-failure"></a>イメージ ビルド エラー

Web サービスのデプロイ時のイメージ ビルド エラー。 回避策は、イメージ構成のために pip の依存関係として "pynacl==1.2.1" を Conda ファイルに追加することです。

## <a name="deployment-failure"></a>デプロイの失敗

`['DaskOnBatch:context_managers.DaskOnBatch', 'setup.py']' died with <Signals.SIGKILL: 9>` を監視する場合、デプロイで使用されている VM の SKU を、メモリがより多い SKU に変更してください。

## <a name="fpgas"></a>FPGA
FPGA クォータを要求して承認されるまでは、FPGA にモデルをデプロイできません。 アクセスを要求するには、クォータ要求フォーム https://aka.ms/aml-real-time-ai に入力します。

## <a name="databricks"></a>Databricks

Databricks と Azure Machine Learning の問題。

1. 追加のパッケージがインストールされている場合、Databricks での Azure Machine Learning SDK のインストールは失敗します。

   `psutil` のようなパッケージでは、競合が発生することがあります。 インストール エラーを回避するには、lib バージョンを止めてパッケージをインストールします。 この問題は Databricks に関連しており、Azure Machine Learning service SDK には関係ありません。他のライブラリでも発生する可能性があります。 例:
   ```python
   pstuil cryptography==1.5 pyopenssl==16.0.0 ipython==2.2.0
   ```
   または、Python ライブラリでのインストールの問題が発生し続けている場合は、初期化スクリプトを使用できます。 このアプローチは、公式にサポートされているアプローチではありません。 [こちらのドキュメント](https://docs.azuredatabricks.net/user-guide/clusters/init-scripts.html#cluster-scoped-init-scripts)をご覧ください。

2. Automated Machine Learning を Databricks で使用しているときに、実行をキャンセルして新しい実験の実行を開始する場合は、Azure Databricks クラスターを再起動してください。

3. Automated ML 設定で、繰り返し回数が 10 を超える場合、実行を送信するときに `show_output` を `False` に設定します。


## <a name="azure-portal"></a>Azure ポータル
SDK またはポータルで共有リンクからワークスペースを直接表示した場合、拡張機能のサブスクリプション情報を含む通常の概要ページを表示できません。 また、別のワークスペースに切り替えることもできません。 別のワークスペースを表示する必要がある場合の回避策としては、[Azure portal](https://portal.azure.com) に直接移動し、ワークスペース名を検索してください。

## <a name="diagnostic-logs"></a>診断ログ
サポートを依頼するときに診断情報を提供できると、役に立つ場合があります。
ここにログ ファイルが保存されます。

## <a name="resource-quotas"></a>リソース クォータ

Azure Machine Learning の使用時に扱うことがあるリソース クォータの詳細は[こちら](how-to-manage-quotas.md)にあります。

## <a name="authentication-errors"></a>認証エラー

リモート ジョブからコンピューティング ターゲットで管理操作を実行すると、次のいずれかのエラーが発生します。

```json
{"code":"Unauthorized","statusCode":401,"message":"Unauthorized","details":[{"code":"InvalidOrExpiredToken","message":"The request token was either invalid or expired. Please try again with a valid token."}]}
```

```json
{"error":{"code":"AuthenticationFailed","message":"Authentication failed."}}
```

たとえば、リモート実行のために送信される ML パイプラインからコンピューティング ターゲットを作成またはアタッチしようとすると、エラーが発生します。

## <a name="get-more-support"></a>さらにサポートが必要な場合

サポート要求を送信し、テクニカル サポートやフォーラムなどからサポートを得ることができます。 [詳細情報](support-for-aml-services.md)
