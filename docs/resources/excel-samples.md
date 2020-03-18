---
title: Excel on the web の Office スクリプトのサンプルスクリプト
description: Web 上の Excel の Office スクリプトで使用するコードサンプルのコレクションです。
ms.date: 02/19/2020
localization_priority: Normal
ms.openlocfilehash: abb4064dfde8b644035e725832e481e6463e979e
ms.sourcegitcommit: b075eed5a6f275274fbbf6d62633219eac416f26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "42700418"
---
# <a name="sample-scripts-for-office-scripts-in-excel-on-the-web-preview"></a>Web 上の Excel での Office スクリプトのサンプルスクリプト (プレビュー)

次のサンプルは、独自のブックで試すことができる簡単なスクリプトです。 Web 上の Excel で使用するには、次のようにします。

1. [**自動化**] タブを開きます。
2. **コードエディター**を押します。
3. コードエディターの作業ウィンドウで、[**新しいスクリプト**] をクリックします。
4. スクリプト全体を、選択したサンプルに置き換えます。
5. コードエディターの作業ウィンドウで、[**実行**] をクリックします。

[!INCLUDE [Preview note](../includes/preview-note.md)]

## <a name="scripting-basics"></a>スクリプトの基礎

これらのサンプルでは、Office スクリプトの基本的な構成要素を示します。 これらをスクリプトに追加して、ソリューションを拡張し、一般的な問題を解決します。

### <a name="read-and-log-one-cell"></a>1つのセルを読み取り、ログに記録する

この例では、 **A1**の値を読み取り、コンソールに出力します。

``` TypeScript
async function main(context: Excel.RequestContext) {
  // Get the current worksheet.
  let selectedSheet = context.workbook.worksheets.getActiveWorksheet();

  // Get the value of cell A1.
  let range = selectedSheet.getRange("A1");
  range.load("values");
  await context.sync();

  // Print the value of A1.
  console.log(range.values);
}
```

### <a name="work-with-dates"></a>日付の操作

この例では、JavaScript の[date](https://developer.mozilla.org/docs/web/javascript/reference/global_objects/date)オブジェクトを使用して、現在の日付と時刻を取得し、その値を作業中のワークシート内の2つのセルに書き込みます。

```TypeScript
async function main(context: Excel.RequestContext) {
  // Get the cells at A1 and B1.
  let dateRange = context.workbook.worksheets.getActiveWorksheet().getRange("A1");
  let timeRange = context.workbook.worksheets.getActiveWorksheet().getRange("B1");

  // Get the current date and time with the JavaScript Date object.
  let date = new Date(Date.now());

  // Add the date string to A1.
  dateRange.values = [[date.toLocaleDateString()]];
  
  // Add the time string to B1.
  timeRange.values = [[date.toLocaleTimeString()]];
}
```

## <a name="display-data"></a>データの表示

これらのサンプルは、ワークシートデータを操作し、ユーザーにより良い表示や組織を提供する方法を示しています。

### <a name="apply-conditional-formatting"></a>条件付き書式の適用

この例では、ワークシートで現在使用されている範囲に条件付き書式を適用します。 条件付き書式は、値の上位10% の緑の塗りつぶしです。

```TypeScript
async function main(context: Excel.RequestContext) {
  // Get the current worksheet.
  let selectedSheet = context.workbook.worksheets.getActiveWorksheet();

  // Get the used range in the worksheet.
  let range = selectedSheet.getUsedRange();

  // Set the fill color to green for the top 10% of values in the range.
  let conditionalFormat = range.conditionalFormats.add(Excel.ConditionalFormatType.topBottom);
  conditionalFormat.topBottom.format.fill.color = "green";
  conditionalFormat.topBottom.rule = {
    rank: 10, // The percentage threshold.
    type: Excel.ConditionalTopBottomCriterionType.topPercent // The type of the top/bottom condition.
  };
}
```

### <a name="create-a-sorted-table"></a>並べ替えられたテーブルを作成する

次の使用例は、現在のワークシートの使用範囲から表を作成し、最初の列に基づいて並べ替えます。

```TypeScript
async function main(context: Excel.RequestContext) {
  // Get the current worksheet.
  let selectedSheet = context.workbook.worksheets.getActiveWorksheet();

  // Create a table with the used cells.
  let usedRange = selectedSheet.getUsedRange();
  let newTable = selectedSheet.tables.add(usedRange, true);

  // Sort the table using the first column.
  newTable.sort.apply([{ key: 0, ascending: true }]);
}
```

## <a name="collaboration"></a>グループ作業

これらのサンプルは、コメントなど、Excel のグループ作業関連機能を操作する方法を示しています。

### <a name="delete-resolved-comments"></a>解決されたコメントの削除

この例では、現在のワークシートから解決されたすべてのコメントを削除します。

```TypeScript
async function main(context: Excel.RequestContext) {
  // Get the current worksheet.
  let selectedSheet = context.workbook.worksheets.getActiveWorksheet();

  // Get the comments on this worksheet.
  let comments = selectedSheet.comments;
  comments.load("items/resolved");
  await context.sync();

  // Delete the resolved comments.
  comments.items.forEach((comment) => {
      if (comment.resolved) {
          comment.delete();
      }
  });
}
```

## <a name="scenario-samples"></a>シナリオサンプル

大規模な現実世界のソリューションを紹介するサンプルについては、「 [Office スクリプトのサンプルシナリオ](scenarios/sample-scenario-overview.md)」を参照してください。

## <a name="suggest-new-samples"></a>新しいサンプルを提案する

新しいサンプルの提案を歓迎します。 他のスクリプト開発者を支援する一般的なシナリオがある場合は、以下のフィードバックセクションでご連絡ください。