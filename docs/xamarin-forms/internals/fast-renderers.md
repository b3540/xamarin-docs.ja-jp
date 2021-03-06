---
title: Xamarin.Forms の高速レンダラー
description: この記事では、高速レンダラーは、結果として得られるネイティブ コントロール階層をフラット化して、増加し、android、Xamarin.Forms コントロールのレンダリング コストを削減について説明します。
ms.prod: xamarin
ms.assetid: 097f87f2-d891-4f3c-be02-fb7d195a481a
ms.technology: xamarin-forms
author: davidbritch
ms.author: dabritch
ms.date: 10/24/2017
ms.openlocfilehash: e4b060c703077e140e0f0d2f8c4c2b824c890e8d
ms.sourcegitcommit: 6e955f6851794d58334d41f7a550d93a47e834d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2018
ms.locfileid: "38997121"
---
# <a name="xamarinforms-fast-renderers"></a>Xamarin.Forms の高速レンダラー

_この記事では、高速レンダラーは、結果として得られるネイティブ コントロール階層をフラット化して、増加し、android、Xamarin.Forms コントロールのレンダリング コストを削減について説明します。_

これまでは、Android で元のコントロールのレンダラーのほとんどは、2 つのビューから構成されます。

- ネイティブ コントロールなど、`Button`または`TextView`します。
- コンテナー`ViewGroup`レイアウト作業、ジェスチャの処理、およびその他のタスクの一部を処理します。

ただし、この方法には大容量メモリ、および詳細画面にレンダリングするために処理を必要とするより複雑なビジュアル ツリー内の結果、論理各コントロールの 2 つのビューを作成することで、パフォーマンスに影響します。

高速レンダラーは、1 つのビューに増加を抑制し、Xamarin.Forms コントロールのレンダリング コストを削減します。 そのため、2 つのビューを作成し、ビュー、ツリーに追加するではなく 1 つだけが作成されます。 これにより、あまり複雑なツリーの表示をさらには、少数のオブジェクトを作成し、メモリ使用量 (その結果が少ないガベージ コレクションの一時停止、また) 以下のパフォーマンスが向上します。

高速レンダラーは、利用できる Android で Xamarin.Forms 2.4 で次のコントロールです。

- [`Button`](xref:Xamarin.Forms.Button)
- [`Image`](xref:Xamarin.Forms.Image)
- [`Label`](xref:Xamarin.Forms.Label)

機能的には、これらの高速レンダラーは、元のレンダラーと変わりません。 ただしが現在実験段階し、次のコードの行を追加することでのみ使用できます、`MainActivity`クラスを呼び出す前に`Forms.Init`:

```csharp
Forms.SetFlags("FastRenderers_Experimental");
```

> [!NOTE]
> 高速レンダラーにのみ適用されますアプリ互換性 Android バックエンドように以前アプリ互換性アクティビティでこの設定は無視されます。

パフォーマンスの向上は、レイアウトの複雑さに応じて、アプリケーションごとに異なります。 たとえば、x2 のパフォーマンスの向上する場合は、スクロール、 [ `ListView` ](xref:Xamarin.Forms.ListView)何千もの行の行ごとのセルが高速レンダラーを使用するコントロールの行われる場所、データを格納しているその結果は非表示スムーズにスクロールします。


## <a name="related-links"></a>関連リンク

- [カスタム レンダラー](~/xamarin-forms/app-fundamentals/custom-renderer/index.md)
