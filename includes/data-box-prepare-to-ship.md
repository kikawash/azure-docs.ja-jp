---
author: alkohli
ms.service: databox
ms.topic: include
ms.date: 01/07/2019
ms.author: alkohli
ms.openlocfilehash: c7e5231650ec1afb97a72ec0cf26cb8f80088b63
ms.sourcegitcommit: 9999fe6e2400cf734f79e2edd6f96a8adf118d92
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2019
ms.locfileid: "54440423"
---
最後に、発送するデバイスを準備します。 このステップでは、デバイスのすべての共有がオフラインにされます。 いったんこのプロセスを始めると、共有にアクセスできなくなります。

> [!IMPORTANT]
> 発送準備は必須です。Azure の名前付け規則に準拠していないデータにはフラグが設定されます。 この手順をスキップすると、データが規則に準拠していないために、データのアップロードに失敗するおそれがあります。

1. **[発送準備]** に移動し、**[準備の開始]** をクリックします。 既定では、チェックサムは発送準備中にインラインで計算されます。 チェックサムの計算は、データのサイズによっては数時間から数日間かかる場合があります。 
   
    ![発送の準備をする 1](media/data-box-prepare-to-ship/prepare-to-ship1.png)

    なんらかの理由でデバイスの準備を中止したい場合は、**[準備の停止]** をクリックします。 発送準備は後から再開できます。
        
    ![発送の準備をする 2](media/data-box-prepare-to-ship/prepare-to-ship2.png)
    
2. 発送準備が開始され、デバイスの共有がオフラインになります。 デバイスの準備が完了すると、配送先住所ラベルをダウンロードするためのリマインダーが表示されます。

    ![配送先住所ラベルのリマインダーをダウンロードしてください](media/data-box-prepare-to-ship/download-shipping-label-reminder.png)

3. デバイスの準備が完了すると、デバイスの状態が "*発送する準備ができました*" に更新され、デバイスがロックされます。
        
    ![発送の準備をする 3](media/data-box-prepare-to-ship/prepare-to-ship3.png)

    デバイスにコピーしたいデータが他にもある場合は、デバイスのロックを解除して、それらをコピーしてから、もう一度、発送準備を実行します。

    この手順でエラーが発生した場合は、エラー ログをダウンロードしてエラーを解決する必要があります。 エラーが解決されたら、**[発送準備]** を実行します。

4. 発送準備が正常に (エラーが発生することなく) 完了したら、この手順でコピーしたファイルのリスト (マニフェスト) をダウンロードします。 後でこのリストを使用して、Azure にアップロードされたファイルを確認できます。
        
    ![発送の準備をする 1](media/data-box-prepare-to-ship/prepare-to-ship4.png)

5. デバイスをシャットダウンします。 **[シャットダウンまたは再起動]** ページに移動し、**[シャットダウン]** をクリックします。 確認を求められたら、**[OK]** をクリックして続行します。

6. ケーブルを取り外します。 次の手順では、Microsoft にデバイスを発送します。
