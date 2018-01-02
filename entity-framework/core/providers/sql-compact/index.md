---
title: "Microsoft SQL Server Compact Edition 資料庫提供者 - EF Core"
author: rowanmiller
ms.author: divega
ms.date: 10/27/2016
ms.assetid: 073f0004-3eb5-4618-ab93-0674910e1819
ms.technology: entity-framework-core
uid: core/providers/sql-compact/index
ms.openlocfilehash: d8b73621bdd363efec5bb7728886e0a0f6bdcf76
ms.sourcegitcommit: 5e2d97e731f975cf3405ff3deab2a3c75ad1b969
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2017
---
# <a name="microsoft-sql-server-compact-edition-ef-core-database-provider"></a><span data-ttu-id="92d57-102">Microsoft SQL Server Compact Edition EF Core 資料庫提供者</span><span class="sxs-lookup"><span data-stu-id="92d57-102">Microsoft SQL Server Compact Edition EF Core Database Provider</span></span>

<span data-ttu-id="92d57-103">此資料庫提供者可讓 Entity Framework Core 與 SQL Server Compact Edition 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="92d57-103">This database provider allows Entity Framework Core to be used with SQL Server Compact Edition.</span></span> <span data-ttu-id="92d57-104">此提供者會維護為 [ErikEJ/EntityFramework.SqlServerCompact GitHub 專案](https://github.com/ErikEJ/EntityFramework.SqlServerCompact)的一部分。</span><span class="sxs-lookup"><span data-stu-id="92d57-104">The provider is maintained as part of the [ErikEJ/EntityFramework.SqlServerCompact GitHub Project](https://github.com/ErikEJ/EntityFramework.SqlServerCompact).</span></span>

> [!NOTE]  
> <span data-ttu-id="92d57-105">但此提供者不會維護為 Entity Framework Core 專案的一部分。</span><span class="sxs-lookup"><span data-stu-id="92d57-105">This provider is not maintained as part of the Entity Framework Core project.</span></span> <span data-ttu-id="92d57-106">考慮使用協力廠商提供者時，請務必評估品質、授權、支援等，確保它們符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="92d57-106">When considering a third party provider, be sure to evaluate quality, licensing, support, etc. to ensure they meet your requirements.</span></span>

## <a name="install"></a><span data-ttu-id="92d57-107">Install</span><span class="sxs-lookup"><span data-stu-id="92d57-107">Install</span></span>

<span data-ttu-id="92d57-108">若要使用 SQL Server Compact Edition 4.0，請安裝 [EntityFrameworkCore.SqlServerCompact40 NuGet 套件](https://www.nuget.org/packages/EntityFrameworkCore.SqlServerCompact40)。</span><span class="sxs-lookup"><span data-stu-id="92d57-108">To work with SQL Server Compact Edition 4.0, install the [EntityFrameworkCore.SqlServerCompact40 NuGet package](https://www.nuget.org/packages/EntityFrameworkCore.SqlServerCompact40).</span></span>

``` powershell
Install-Package EntityFrameworkCore.SqlServerCompact40
```

<span data-ttu-id="92d57-109">若要使用 SQL Server Compact Edition 3.5，請安裝 [EntityFrameworkCore.SqlServerCompact35](https://www.nuget.org/packages/EntityFrameworkCore.SqlServerCompact35)。</span><span class="sxs-lookup"><span data-stu-id="92d57-109">To work with SQL Server Compact Edition 3.5, install the [EntityFrameworkCore.SqlServerCompact35](https://www.nuget.org/packages/EntityFrameworkCore.SqlServerCompact35).</span></span>

``` powershell
Install-Package EntityFrameworkCore.SqlServerCompact35
```

## <a name="get-started"></a><span data-ttu-id="92d57-110">開始使用</span><span class="sxs-lookup"><span data-stu-id="92d57-110">Get Started</span></span>

<span data-ttu-id="92d57-111">請參閱[專案網站上的快速入門文件](https://github.com/ErikEJ/EntityFramework.SqlServerCompact/wiki/Using-EF-Core-with-SQL-Server-Compact-in-Traditional-.NET-Applications)</span><span class="sxs-lookup"><span data-stu-id="92d57-111">See the [getting started documentation on the project site](https://github.com/ErikEJ/EntityFramework.SqlServerCompact/wiki/Using-EF-Core-with-SQL-Server-Compact-in-Traditional-.NET-Applications)</span></span>

## <a name="supported-database-engines"></a><span data-ttu-id="92d57-112">支援的資料庫引擎</span><span class="sxs-lookup"><span data-stu-id="92d57-112">Supported Database Engines</span></span>

* <span data-ttu-id="92d57-113">SQL Server Compact Edition 3.5</span><span class="sxs-lookup"><span data-stu-id="92d57-113">SQL Server Compact Edition 3.5</span></span>

* <span data-ttu-id="92d57-114">SQL Server Compact Edition 4.0</span><span class="sxs-lookup"><span data-stu-id="92d57-114">SQL Server Compact Edition 4.0</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="92d57-115">支援的平台</span><span class="sxs-lookup"><span data-stu-id="92d57-115">Supported Platforms</span></span>

* <span data-ttu-id="92d57-116">.NET Framework (4.5.1 和更新版本)</span><span class="sxs-lookup"><span data-stu-id="92d57-116">.NET Framework (4.5.1 onwards)</span></span>