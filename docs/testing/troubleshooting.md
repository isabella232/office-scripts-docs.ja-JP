---
title: Office スクリプトのトラブルシューティング
description: Office スクリプトのヒントとテクニック、およびヘルプリソースをデバッグします。
ms.date: 10/08/2020
localization_priority: Normal
ms.openlocfilehash: 9b3f4be778f3cdb4711d1e41d4d68f87ebca8152
ms.sourcegitcommit: 42fa3b629c93930b4e73e9c4c01d0c8bdf6d7487
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411548"
---
# <a name="troubleshooting-office-scripts"></a>Office スクリプトのトラブルシューティング

Office スクリプトを開発する際には、誤りが発生することがあります。 大丈夫です。 問題を見つけてスクリプトを完全に動作させるためのツールが用意されています。

## <a name="console-logs"></a>コンソールログ

トラブルシューティング中に、画面にメッセージを出力することもできます。 これにより、変数の現在の値や、どのコードパスがトリガーされているかを確認できます。 これを行うには、テキストをコンソールに記録します。

```TypeScript
console.log("Logging myRange's address.");
console.log(myRange.getAddress());
```

に渡される文字列 `console.log` は、コードエディターのログコンソールに表示されます。 コンソールをオンにするには、**省略記号**ボタンを押して [**ログ...** ] を選択します。

ログがブックに影響を与えることはありません。

## <a name="error-messages"></a>エラー メッセージ

Excel スクリプトで問題が発生すると、エラーが生成されます。 **ログを表示**するかどうかの確認を求めるポップアップが表示されます。 そのボタンを押してコンソールを開き、エラーを表示します。

## <a name="automate-tab-not-appearing-or-office-scripts-unavailable"></a>タブが表示されない、または Office スクリプトが利用できないことを自動化する

次の手順は、web 上の Excel に表示されない [ **自動化** ] タブに関連する問題のトラブルシューティングに役立ちます。

1. [Microsoft 365 ライセンスに Office スクリプトが含まれていることを確認して](../overview/excel.md#requirements)ください。
1. [管理者に機能を有効にしてもらい](/microsoft-365/admin/manage/manage-office-scripts-settings)ます。
1. [ブラウザーがサポートされていることを確認して](platform-limits.md#browser-support)ください。
1. [サードパーティの cookie が有効になっていることを確認](platform-limits.md#third-party-cookies)します。

[!INCLUDE [Teams support note](../includes/teams-support-note.md)]

## <a name="help-resources"></a>ヘルプリソース

[スタックオーバーフロー](https://stackoverflow.com/questions/tagged/office-scripts) は、コーディングに関する問題の解決に役立つ開発者のコミュニティです。 多くの場合、クイックスタックオーバーフロー検索を使用して、問題の解決策を見つけることができます。 そうでない場合は、質問して、「office スクリプト」タグでタグを付けてください。 Office*アドイン*ではなく、office*スクリプト*を作成していることを必ずお伝えください。

Office JavaScript API で問題が発生した場合は、 [Officedev/Office/js](https://github.com/OfficeDev/office-js) GitHub リポジトリに問題を作成します。 製品チームのメンバーは問題に対応し、さらに支援を提供します。 **Officedev/office-js**リポジトリで問題を発生させることは、製品チームが対処する必要のある OFFICE JavaScript API ライブラリに問題が見つかったことを示しています。

操作レコーダーまたは Editor に問題がある場合は、Excel の **ヘルプ > フィードバック** ボタンを使用してフィードバックを送信してください。

## <a name="see-also"></a>関連項目

- [Excel on the web の Office スクリプト](../overview/excel.md)
- [Web 上の Excel での Office スクリプトのスクリプトの基礎](../develop/scripting-fundamentals.md)
- [Office スクリプトでのプラットフォームの制限](platform-limits.md)
- [Office スクリプトのパフォーマンスを向上させる](../develop/web-client-performance.md)
- [Office スクリプトの効果を元に戻す](undo.md)
