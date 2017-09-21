---
title: ".NET 用 Azure 管理ライブラリ サンプル手順"
description: ".NET 用 Azure 管理ライブラリを使ってリソースの作成と更新を行うサンプル コードを入手してください。"
keywords: "Azure, .NET, SDK, API, サンプル, 例"
author: camsoper
ms.author: casoper
manager: douge
ms.date: 06/20/2017
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: dotnet
ms.service: multiple
ms.assetid: 
ms.openlocfilehash: ffda7cca724962e6f953432c5cab04485ddabb03
ms.sourcegitcommit: d95a6ad3774a49b16f652e40e7860e47636c7ad0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2017
---
# <a name="azure-management-libraries-for-net-sample-instructions"></a>.NET 用 Azure 管理ライブラリ サンプル手順

この記事では、.NET 用 Azure 管理ライブラリのサンプルを実行するために必要な前提条件と認証について説明します。

## <a name="prerequisties"></a>前提条件 

* [Visual Studio 2017](https://www.visualstudio.com/vs/) または [.NET Core SDK](https://www.microsoft.com/net/download/core)
* [Microsoft Azure サブスクリプション](https://azure.microsoft.com/free/)
* [Git コマンド ライン クライアント](https://git-scm.com/)
* [Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps)

## <a name="authentication-for-all-samples"></a>すべてのサンプルの認証

[!include[Create service principal](includes/create-sp.md)]

[!include[File-based authentication](includes/file-based-auth.md)]

## <a name="running-the-samples"></a>サンプルの実行

Git を使ってサンプルを複製した後は、Visual Studio でサンプルを開き、IDE を使ってサンプルを実行できます。  または、.NET Core SDK を使って、次のように、コマンド ラインからサンプルをビルドして実行します。

```cmd
git clone https://github.com/Azure-Samples/app-service-dotnet-configure-deployment-sources-for-web-apps.git
cd app-service-dotnet-configure-deployment-sources-for-web-apps
dotnet restore
dotnet run
```