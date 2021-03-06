---
title: .NET 用 Azure コンピューティング ライブラリ
description: .NET 用 Azure コンピューティング ライブラリのリファレンス
ms.date: 10/19/2017
ms.topic: reference
ms.service: virtual-machines
ms.openlocfilehash: ee481e0f2448a874629bec36a719e7682407d320
ms.sourcegitcommit: 5d9b713653b3d03e1d0a67f6e126ee399d1c2a60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "47190695"
---
# <a name="azure-virtual-machine-libraries-for-net"></a>.NET 用 Azure 仮想マシン ライブラリ

## <a name="overview"></a>概要

Linux または Windows を実行するオンデマンドのスケーラブルなコンピューティング リソースです。

Azure 仮想マシンの概要については、「[Azure Portal で Linux 仮想マシンを作成する](https://review.docs.microsoft.com/azure/virtual-machines/linux/quick-create-portal)」を参照してください。

## <a name="management-apis"></a>管理 API

Azure の Windows 仮想マシンと Linux 仮想マシンは、コードから Management API を使って作成、構成、スケールアウトすることができます。

[NuGet パッケージ](https://www.nuget.org/packages/Microsoft.Azure.Management.Compute.Fluent)を Visual Studio [パッケージ マネージャー コンソール][PackageManager]から直接インストールするか、[.NET Core CLI][DotNetCLI] を使ってインストールします。

#### <a name="visual-studio-package-manager"></a>Visual Studio パッケージ マネージャー

```powershell
Install-Package Microsoft.Azure.Management.Compute.Fluent
```

#### <a name="net-core-cli"></a>.NET Core CLI

```bash
dotnet add package Microsoft.Azure.Management.Compute.Fluent
```

### <a name="code-example"></a>コード例

Windows VM を作成します。

```csharp
/* Include these "using" directives...
using Microsoft.Azure.Management.Compute.Fluent;
using Microsoft.Azure.Management.Compute.Fluent.Models;
using Microsoft.Azure.Management.ResourceManager.Fluent.Core;
*/

IVirtualMachine windowsVM = azure.VirtualMachines.Define("MyVirtualMachine")
    .WithRegion(Region.USEast)
    .WithNewResourceGroup("MyResourceGroup")
    .WithNewPrimaryNetwork("10.0.0.0/28")
    .WithPrimaryPrivateIPAddressDynamic()
    .WithNewPrimaryPublicIPAddress("MyIPAddressLabel")
    .WithPopularWindowsImage(KnownWindowsVirtualMachineImage.WindowsServer2012R2Datacenter)
    .WithAdminUsername("UserName")
    .WithAdminPassword("Password")
    .WithSize(VirtualMachineSizeTypes.StandardD3V2)
    .Create();
```

> [!div class="nextstepaction"]
> [Management API を探す](https://docs.microsoft.com/dotnet/api/overview/azure/virtualmachines/management?view=azure-dotnet)

### <a name="samples"></a>サンプル

* [仮想マシンの作成と管理](/dotnet/azure/dotnet-sdk-azure-virtual-machine-samples)
* [.NET からテンプレートを使用して SSH 対応 VM をデプロイする](https://azure.microsoft.com/resources/samples/resource-manager-dotnet-template-deployment/)

仮想マシン サンプルの[完全な一覧](https://azure.microsoft.com/resources/samples/?platform=dotnet&term=VM)をご覧ください。

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package
