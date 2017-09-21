---
title: ".NET 用 Azure Event Hubs ライブラリ"
description: ".NET 用 Azure Event Hubs ライブラリのリファレンス"
keywords: Azure, .NET, SDK, API, Event Hubs
author: camsoper
ms.author: casoper
manager: douge
ms.date: 07/19/2017
ms.topic: reference
ms.prod: azure
ms.technology: azure
ms.devlang: dotnet
ms.service: multiple
ms.openlocfilehash: 1dca44ed716e387d531661093d4c7cfc7780964b
ms.sourcegitcommit: d95a6ad3774a49b16f652e40e7860e47636c7ad0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2017
---
# <a name="azure-event-hubs-libraries-for-net"></a>.NET 用 Azure Event Hubs ライブラリ

## <a name="overview"></a>概要

Azure Event Hubs は、拡張性の高いデータ ストリーミング プラットフォームであり、イベント インジェスト サービスでもあります。

Azure Event Hubs の詳細については、「[Event Hubs とは](/azure/event-hubs/event-hubs-what-is-event-hubs)」をご覧ください。  作業を開始するには、「[Event Hubs のプログラミング ガイド](/azure/event-hubs/event-hubs-programming-guide)」をご覧ください。

## <a name="client-library"></a>クライアント ライブラリ

Event Hubs との間でメッセージを送受信するには、Event Hubs クライアントを使用します。

[NuGet パッケージ](https://www.nuget.org/packages/Microsoft.Azure.EventHubs)を Visual Studio [パッケージ マネージャー コンソール][PackageManager]から直接インストールするか、[.NET Core CLI][DotNetCLI] を使用してインストールします。

#### <a name="visual-studio-package-manager"></a>Visual Studio パッケージ マネージャー

```powershell
Install-Package Microsoft.Azure.EventHubs
```

```bash
dotnet add package Microsoft.Azure.EventHubs
```

### <a name="code-example"></a>コード例

次のコードでは、Event Hubs クライアントを作成し、ハブにメッセージを送信します。

```csharp
EventHubsConnectionStringBuilder connectionStringBuilder = new EventHubsConnectionStringBuilder(eventHubConnectionString)
{
    EntityPath = eventHubEntityPath
};

EventHubClient eventHubClient = EventHubClient.CreateFromConnectionString(connectionStringBuilder.ToString());
string message = $"Message {i}";
Console.WriteLine($"Sending message: {message}");
await eventHubClient.SendAsync(new EventData(Encoding.UTF8.GetBytes(message)));
```

> [!div class="nextstepaction"]
> [クライアント API を探す](/dotnet/api/overview/azure/eventhub/client)

## <a name="management-library"></a>管理ライブラリ

ハブとコンシューマー グループを作成、更新、削除するには、Event Hubs 管理ライブラリを使用します。

[NuGet パッケージ](https://www.nuget.org/packages/Microsoft.Azure.Management.EventHub)を Visual Studio [パッケージ マネージャー コンソール][PackageManager]から直接インストールするか、[.NET Core CLI][DotNetCLI] を使用してインストールします。

#### <a name="visual-studio-package-manager"></a>Visual Studio パッケージ マネージャー

```powershell
Install-Package Microsoft.Azure.Management.EventHub
```

```bash
dotnet add package Microsoft.Azure.Management.EventHub
```

### <a name="code-example"></a>コード例

次のコード例では、新しいイベント ハブを作成します。

```csharp
TokenCredentials creds = new TokenCredentials(token);
EventHubManagementClient ehClient = new EventHubManagementClient(creds)
{
    SubscriptionId = subscriptionId
};

EventHubCreateOrUpdateParameters ehParams = new EventHubCreateOrUpdateParameters()
{
    Location = location
};

Console.WriteLine("Creating Event Hub...");
await ehClient.EventHubs.CreateOrUpdateAsync(resourceGroupName, namespaceName, EventHubName, ehParams);
Console.WriteLine("Created Event Hub successfully.");
```

> [!div class="nextstepaction"]
> [Management API を探す](/dotnet/api/overview/azure/eventhub/management)

## <a name="tutorials"></a>Tutorials (チュートリアル)

* [.NET Framework を使用して Azure Event Hubs にイベントを送信する](/azure/event-hubs/event-hubs-dotnet-framework-getstarted-send)

* [.NET Framework を使用して Azure Event Hubs からイベントを受信する](/azure/event-hubs/event-hubs-dotnet-framework-getstarted-receive-eph)

## <a name="samples"></a>サンプル

* [Azure Event Hubs のサンプル](https://github.com/Azure/azure-event-hubs/tree/master/samples)

アプリで使用できるその他の[サンプル .NET コード](https://azure.microsoft.com/resources/samples/?platform=dotnet)を確認してください。

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package