---
title: ".NET 用 Azure Data Lake Analytics ライブラリ"
description: ".NET 用 Azure Data Lake Analytics ライブラリのリファレンス"
keywords: Azure, .NET, SDK, API, Data Lake Analytics
author: camsoper
ms.author: casoper
manager: douge
ms.date: 07/18/2017
ms.topic: reference
ms.prod: azure
ms.technology: azure
ms.devlang: dotnet
ms.service: multiple
ms.openlocfilehash: 935afa104b1a47f537ea3bcc981670abd6c56413
ms.sourcegitcommit: d95a6ad3774a49b16f652e40e7860e47636c7ad0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2017
---
# <a name="azure-data-lake-analytics-libraries-for-net"></a>.NET 用 Azure Data Lake Analytics ライブラリ

## <a name="overview"></a>概要

Azure Data Lake Analytics は、ビッグ データ分析を簡略化するオンデマンド分析ジョブ サービスです。

詳細については、「[Microsoft Azure Data Lake Analytics の概要](/azure/data-lake-analytics/data-lake-analytics-overview)」をご覧ください。

## <a name="management-library"></a>管理ライブラリ

サービスに接続し、分析ジョブを管理するには、管理ライブラリを使用します。

[NuGet パッケージ](https://www.nuget.org/packages/Microsoft.Azure.Management.DataLake.Analytics)を Visual Studio [パッケージ マネージャー コンソール][PackageManager]から直接インストールするか、[.NET Core CLI][DotNetCLI] を使用してインストールします。

#### <a name="visual-studio-package-manager"></a>Visual Studio パッケージ マネージャー

```powershell
Install-Package Microsoft.Azure.Management.DataLake.Analytics
```

```bash
dotnet add package Microsoft.Azure.Management.DataLake.Analytics
```

### <a name="code-example"></a>コード例

この例では、Analytics アカウントに接続し、アカウントを管理するクライアントを作成します。

```csharp
/*
using AdlClient 
*/

// Setup authentication for this demo
Authentication auth = new Authentication("microsoft.onmicrosoft.com"); // change this to YOUR tenant
auth.Authenticate();

// Identify the accounts
AnalyticsAccountRef adla_account = new AnalyticsAccountRef(subscriptionId, resourceGroup, userName);

// Create the clients
AzureClient az = new AzureClient(auth);
AnalyticsClient adla = new AnalyticsClient(auth, adla_account);
```

> [!div class="nextstepaction"]
> [Management API を探す](/dotnet/api/overview/azure/datalakeanalytics/management)

## <a name="samples"></a>サンプル
* [Azure Data Lake .NET クライアントのサンプル](https://azure.microsoft.com/en-us/resources/samples/data-lake-dotnet-client/)

アプリで使用できるその他の[サンプル .NET コード](https://azure.microsoft.com/resources/samples/?platform=dotnet)を確認してください。

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-add-package