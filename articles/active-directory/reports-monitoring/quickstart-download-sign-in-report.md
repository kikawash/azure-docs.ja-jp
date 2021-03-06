---
title: 'クイック スタート: Azure portal を使用してサインイン レポートをダウンロードする | Microsoft Docs'
description: Azure portal を使用してサインイン レポートをダウンロードする方法について説明します
services: active-directory
documentationcenter: ''
author: priyamohanram
manager: daveba
editor: ''
ms.assetid: 9131f208-1f90-4cc1-9c29-085cacd69317
ms.service: active-directory
ms.devlang: na
ms.topic: quickstart
ms.tgt_pltfrm: na
ms.workload: identity
ms.subservice: report-monitor
ms.date: 11/13/2018
ms.author: priyamo
ms.reviewer: dhanyahk
ms.collection: M365-identity-device-management
ms.openlocfilehash: eeb5a06aa4eb21ba374344623f9f96ce92a59ff5
ms.sourcegitcommit: 301128ea7d883d432720c64238b0d28ebe9aed59
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56168819"
---
# <a name="quickstart-download-a-sign-in-report-using-the-azure-portal"></a>クイック スタート:Azure portal を使用してサインイン レポートをダウンロードする

このクイック スタートでは、過去 24 時間のテナントに関するサインイン データをダウンロードする方法について説明します。 レコードは Azure portal から 5000 個までダウンロードできます。 レコードは最新の順に並べ替えられており、既定では最新の 5,000 個のレコードが取得されます。 

## <a name="prerequisites"></a>前提条件

必要なもの:

* Premium ライセンスを使用してサインイン アクティビティ レポートを表示する Azure Active Directory テナント。 Azure Active Directory エディションにアップグレードするには、「[Azure Active Directory Premium の概要](../fundamentals/active-directory-get-started-premium.md)」を参照してください。 アップグレード前の時点でアクティビティ データがまったく存在しなかった場合、Premium ライセンスへのアップグレード後、データがレポートに表示されるまでに数日かかります。
* テナントの**セキュリティ管理者**、**セキュリティ閲覧者**、**レポート閲覧者**、**グローバル管理者**のいずれかのロールであるユーザー。 さらに、テナントのすべてのユーザーは自分のサインインにアクセスできます。

## <a name="quickstart-download-a-sign-in-report"></a>クイック スタート:サインイン レポートのダウンロード

1. [Azure Portal](https://portal.azure.com) に移動します。
2. 左側のナビゲーション ウィンドウで **[Azure Active Directory]** を選択し、**[ディレクトリの切り替え]** ボタンを使用して目的の Active Directory を選択します。
3. ダッシュボードから **[Azure Active Directory]** を選択し、**[サインイン]** を選択します。 
4. **[日付]** フィルター ドロップダウンで **[過去 24 時間]** を選択し、**[適用]** を選択して過去 24 時間のサインインを表示します。 
5. **[ダウンロード]** ボタンを選択して、フィルター処理したレコードを含む CSV ファイルをダウンロードします。 

![レポート](./media/quickstart-download-sign-in-report/download-sign-ins.png)

## <a name="next-steps"></a>次の手順

* [Azure Active Directory ポータルのサインイン アクティビティ レポート](concept-sign-ins.md)
* [Azure Active Directory レポートの保持期間](reference-reports-data-retention.md)
* [Azure Active Directory レポートの待機時間](reference-reports-latencies.md)
