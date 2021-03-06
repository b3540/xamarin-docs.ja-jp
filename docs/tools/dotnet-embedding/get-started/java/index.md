---
title: Java の概要
description: このドキュメントでは、Java で .NET の埋め込みを使用して作業を開始する方法について説明します。 これは、システム要件、インストール、およびサポートされているプラットフォームについて説明します。
ms.prod: xamarin
ms.assetid: B9A25E9B-3EC2-489A-8AD3-F78287609747
author: topgenorth
ms.author: toopge
ms.date: 03/28/2018
ms.openlocfilehash: 53871a5311cdba824b0bddca37dd5c416d06e272
ms.sourcegitcommit: 3f2737f8abf9b855edf060474aa222e973abda3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37066810"
---
# <a name="getting-started-with-java"></a>Java の概要

これは、java の場合、サポートされているすべてのプラットフォームの基本についての内容を含む作業の開始ページです。

## <a name="requirements"></a>必要条件

Java で .NET の埋め込みを使用するには、必要があります。

* Java 1.8 以降
* [モノラル 5.0](http://www.mono-project.com/download/)

For Mac:

* Xcode 8.3.2 以降

Windows の場合。

* C++ のサポートと visual Studio 2017
* Windows 10 SDK

Android:

* [Xamarin.Android 7.5](https://visualstudio.microsoft.com/xamarin/)以降
* [Android Studio 3.x](https://developer.android.com/studio/index.html) with Java 1.8

使用することができます[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)を編集し、c# コードをコンパイルします。

> [!NOTE]
> 以前のバージョンの Xcode、Visual Studio、Xamarin.Android、Android Studio、およびモノラル_可能性があります_機能しますが、テスト、サポートされていません。

## <a name="installation"></a>インストール

現時点では、.NET の埋め込み[NuGet](https://www.nuget.org/packages/Embeddinator-4000/):

```shell
nuget install Embeddinator-4000
```

これは、配置は**Embeddinator 4000.exe**に、**パッケージ/Embeddinator-4000/ツール**ディレクトリ。

さらに、.NET のソースから埋め込みを構築を参照してください、 [git リポジトリ](https://github.com/mono/Embeddinator-4000/)と[の原因となった](https://github.com/mono/Embeddinator-4000/blob/master/Contributing.md)手順についてはドキュメントです。

## <a name="platforms"></a>プラットフォーム

Java は現在 macOS、Windows、および Android 用のプレビュー状態です。

渡すことによって、プラットフォームが選択されている、 `--platform=<platform>` .NET 埋め込みツールのコマンドライン引数。 現在`macOS`、 `Windows`、および`Android`はサポートされています。

### <a name="macos-and-windows"></a>macOS および Windows

開発では、Java 1.8 をサポートする任意の Java IDE を使用できる必要があります。 これを Android Studio を使用することもできます。 必要な場合、[ここに表示](https://stackoverflow.com/questions/16626810/can-android-studio-be-used-to-run-standard-java-projects)です。 標準の Java jar ファイルと同様、JAR ファイル出力を行うこともできます。

### <a name="android"></a>Android

既にセットアップして 1 つを作成する前に Android アプリケーションを開発するかどうかを確認してください。 .NET の埋め込みを使用します。 [の指示に従って](~/tools/dotnet-embedding/get-started/java/android.md)既に正常にビルドしているコンピューターからの Android アプリケーションのデプロイを前提としています。

Android Studio が、開発用に推奨されますのサポートがある限り、他の Ide を使用する必要があります、 [AAR ファイル形式](https://developer.android.com/studio/projects/android-library.html)です。

## <a name="further-reading"></a>関連項目

* [Android で作業の開始](~/tools/dotnet-embedding/get-started/java/android.md)
* [Android でのコールバック](~/tools/dotnet-embedding/android/callbacks.md)
* [Android の事前調査](~/tools/dotnet-embedding/android/index.md)
* [.NET の埋め込みの制限事項](~/tools/dotnet-embedding/limitations.md)
* [オープン ソース プロジェクトに貢献しています。](https://github.com/mono/Embeddinator-4000/blob/master/Contributing.md)
* [エラー コードと説明](~/tools/dotnet-embedding/errors.md)
