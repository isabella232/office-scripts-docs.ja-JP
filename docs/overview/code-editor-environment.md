---
title: Office スクリプトのコードエディター環境
description: Web 上の Excel の Office スクリプトの前提条件と環境情報。
ms.date: 01/21/2020
localization_priority: Normal
ms.openlocfilehash: 06318305e4e0091ce4fd8d1cd8130c474e18aed9
ms.sourcegitcommit: b075eed5a6f275274fbbf6d62633219eac416f26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "42700400"
---
# <a name="office-scripts-code-editor-environment"></a>Office スクリプトのコードエディター環境

Office スクリプトは、 [TypeScript または javascript](#scripting-language-typescript-or-javascript)で記述され、 [Office スクリプト javascript api](#office-scripts-javascript-api)を使用して Excel ブックを操作します。

## <a name="scripting-language-typescript-or-javascript"></a>スクリプト言語: TypeScript または JavaScript

Office スクリプトは、 [TypeScript](https://www.typescriptlang.org/docs/home.html)または[JavaScript](https://developer.mozilla.org/docs/Web/JavaScript)で記述されています。 アクションレコーダーは、TypeScript のコード (JavaScript のスーパーセット) を生成します。 Office スクリプトドキュメントでは TypeScript を使用していますが、JavaScript を使用した方が快適な場合は、その代わりに使用できます。

Office スクリプトには、主に自己完結型のコード部分があります。 TypeScript の機能のごく一部のみが使用されます。 そのため、TypeScript の複雑な部分を学ばずにスクリプトを編集できます。 コードエディターでは、コードのインストール、コンパイル、実行も処理されるため、スクリプト自体について心配する必要はありません。 以前のプログラミング知識がなくても、言語を理解し、スクリプトを作成することができます。 ただし、プログラミングに慣れていない場合は、Office スクリプトを続行する前に、いくつかの基本事項を理解することをお勧めします。

- JavaScript の基本事項について説明します。 変数、制御フロー、関数、データ型などの概念に慣れている必要があります。 [Mozilla には、JavaScript に関する優れた総合的なチュートリアルが用意](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Introduction)されています。
- TypeScript の種類について説明します。 TypeScript は、コンパイル時に適切な型をメソッドの呼び出しと割り当てに使用することによって、JavaScript で構築されます。 [インターフェイス](https://www.typescriptlang.org/docs/handbook/interfaces.html)、[クラス](https://www.typescriptlang.org/docs/handbook/classes.html)、[型の推論](https://www.typescriptlang.org/docs/handbook/type-inference.html)、および型の[互換性](https://www.typescriptlang.org/docs/handbook/type-compatibility.html)に関する TypeScript ドキュメントは、最も有用です。

## <a name="office-scripts-javascript-api"></a>Office スクリプト JavaScript API

Office スクリプトは、 [Office アドイン](/office/dev/add-ins/overview/index)で使用される Office JavaScript api である特別なバージョンを使用します。2つのプラットフォーム間の相違点については、「 [Office スクリプトと Office アドインの相違点](../resources/add-ins-differences.md#apis)」を参照してください。 スクリプトで使用可能なすべての Api は、「 [Office スクリプト API リファレンス」ドキュメント](/javascript/api/office-scripts/overview)で確認できます。

## <a name="intellisense"></a>インテリジェンス

IntelliSense は、スクリプトを編集するときの入力ミスや構文エラーを防止するために役立つコードエディターの機能です。 入力したオブジェクトとフィールド名、および各 API のインラインドキュメントが表示されます。

Excel コードエディターは、Visual Studio Code と同じ IntelliSense エンジンを使用します。 この機能の詳細については、 [Visual Studio Code の IntelliSense 機能](https://code.visualstudio.com/docs/editor/intellisense#_intellisense-features)を参照してください。

## <a name="see-also"></a>関連項目

- [Office スクリプト API リファレンス](/javascript/api/office-scripts/overview)
- [Office スクリプトのトラブルシューティング](../testing/troubleshooting.md)
- [Office スクリプトでの組み込みの JavaScript オブジェクトの使用](../develop/javascript-objects.md)