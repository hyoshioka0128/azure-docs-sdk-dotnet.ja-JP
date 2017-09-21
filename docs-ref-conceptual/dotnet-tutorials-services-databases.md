---
title: "Azure データベースの使用に関する .NET チュートリアル"
description: ".NET アプリケーションで Azure データベースに接続して使う方法に関するチュートリアルです。"
author: camsoper
manager: douge
ms.devlang: dotnet
ms.topic: article
ms.service: Azure
ms.technology: Azure
ms.date: 06/09/2017
ms.author: casoper
ms.openlocfilehash: 0a6d84efab9789090e6780504a39cb83893035d8
ms.sourcegitcommit: d95a6ad3774a49b16f652e40e7860e47636c7ad0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2017
---
# <a name="tutorials-for-using-net-with-azure-databases"></a>Azure データベースでの .NET の使用に関するチュートリアル

次の表では、.NET アプリケーションで Azure データベースのデータに接続して操作する方法についての詳細なチュートリアルへのリンクを示します。

サンプルのソース コードについては、「[Azure のコード サンプル](https://azure.microsoft.com/resources/samples/?platform=dotnet)」の一覧をご覧ください。

| | |
|---|---|
| **SQL Database** ||
| [.NET を使ってデータに接続し、クエリを行う][1] | ADO.NET を使って Azure SQL データベースに接続し Transact-SQL ステートメントを使ってデータベース内のデータを照会、挿入、更新、削除します。 | 
| **Azure Database for PostgreSQL** ||
| [.NET を使ってデータに接続し、クエリを行う][2] | SQL ステートメントを使ってデータベース内のデータを照会、挿入、更新、削除します。 | 
| **Cosmos DB** ||
| [DocumentDB API の概要][4] | DocumentDB API で簡単なコンソール アプリケーションを作成します。 | 
| [CosmosDB を使用して ASP.NET Web アプリを作成する][3] | CosmosDB の DocumentDB NoSQL データベースを使って Web アプリケーションを作成します。 | 
| **Redis Cache** | |
| [Azure Redis Cache の使用方法][6] | Azure Redis Cache を使い始めます。 |
| [Redis Cache で Web アプリを作成する][5] | Visual Studio 2017 を使って ASP.NET Web アプリケーションを作成し、Azure App Service の Web アプリにデプロイします。  | 
| [ASP.NET セッション状態プロバイダー][7] | Azure Redis Cache を使って、ASP.NET のセッション状態を保持します。  | 
| [ASP.NET 出力キャッシュ プロバイダー][8] | ASP.NET 出力キャッシュに Azure Redis Cache を使います。  | 
 

[1]: /azure/sql-database/sql-database-connect-query-dotnet
[2]: /azure/postgresql/connect-csharp
[3]: /azure/cosmos-db/documentdb-dotnet-application
[4]: /azure/cosmos-db/documentdb-dotnetcore-get-started
[5]: /azure/redis-cache/cache-web-app-howto
[6]: /azure/redis-cache/cache-dotnet-how-to-use-azure-redis-cache
[7]: /azure/redis-cache/cache-aspnet-session-state-provider
[8]: /azure/redis-cache/cache-aspnet-output-cache-provider