---
title: .NET 用 Azure Recovery Services および Backup ライブラリ
description: .NET 用 Azure Recovery Services および Backup ライブラリのリファレンス
ms.date: 10/19/2017
ms.topic: reference
ms.service: backup
ms.openlocfilehash: c2faef5c83f28cb35158609b92f0334671161d1d
ms.sourcegitcommit: 1cf4550df8ed3236d838f561f6177d14d89b5e44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2018
ms.locfileid: "49348174"
---
# <a name="azure-recovery-services-and-backup-libraries-for-net"></a>.NET 用 Azure Recovery Services および Backup ライブラリ

## <a name="overview"></a>概要

Azure Recovery Services は、[Azure Backup](/azure/backup/) と [Azure Site Recovery](/azure/site-recovery/) を含む、データ回復のための一連のサービスです。

## <a name="management-library"></a>管理ライブラリ

[NuGet パッケージ](https://www.nuget.org/packages/Microsoft.Azure.Management.RecoveryServices)を Visual Studio [パッケージ マネージャー コンソール][PackageManager]から直接インストールするか、[.NET Core CLI][DotNetCLI] を使ってインストールします。

#### <a name="visual-studio-package-manager"></a>Visual Studio パッケージ マネージャー

```powershell
Install-Package Microsoft.Azure.Management.RecoveryServices
Install-Package Microsoft.Azure.Management.RecoveryServices.Backup
```

#### <a name="net-core-cli"></a>.NET Core CLI

```bash
dotnet add package Microsoft.Azure.Management.RecoveryServices
dotnet add package Microsoft.Azure.Management.RecoveryServices.Backup
```

> [!div class="nextstepaction"]
> [Management API を探す](/dotnet/api/overview/azure/recoveryservices/management)


## <a name="code-example"></a>コード例

次のコード例では、管理ライブラリを使用してバックアップをトリガーします。

```csharp
RecoveryServicesBackupManagementClient client = new RecoveryServicesBackupManagementClient(credentials);
TriggerBackupRequest triggerBackupRequest = new TriggerBackupRequest();
BaseRecoveryServicesJobResponse resp =
    await client.Backups.TriggerBackupAsync(resourceGroupName, resourceName, null,
        fabricName, containerName, protectedItemName, triggerBackupRequest);
```

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package
