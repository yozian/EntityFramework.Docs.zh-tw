---
title: 新功能 - EF6
author: divega
ms.date: 2016-10-23
ms.prod: entity-framework
ms.author: divega
ms.manager: avickers
ms.technology: entity-framework-6
ms.topic: article
ms.assetid: 41d1f86b-ce66-4bf2-8963-48514406fb4c
caps.latest.revision: 3
ms.openlocfilehash: 0da2ce778a765037ecacd0726cbb7cda08b5683f
ms.sourcegitcommit: f05e7b62584cf228f17390bb086a61d505712e1b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2018
ms.locfileid: "37911702"
---
# <a name="whats-new-in-ef6"></a><span data-ttu-id="03dcb-102">EF6 的新功能</span><span class="sxs-lookup"><span data-stu-id="03dcb-102">What's New in EF6</span></span>

<span data-ttu-id="03dcb-103">強烈建議您使用 Entity Framework 的最新發行版本，以確保您取得最新的功能和最高的穩定性。</span><span class="sxs-lookup"><span data-stu-id="03dcb-103">We highly recommend that you use the latest released version of Entity Framework to ensure you get the latest features and the highest stability.</span></span>
<span data-ttu-id="03dcb-104">不過，我們了解您可能需要使用先前的版本，或者可能想要體驗最新發行前版本中的新改善。</span><span class="sxs-lookup"><span data-stu-id="03dcb-104">However, we realize that you may need to use a previous version, or that you may want to experiment with new improvements in the latest pre-release.</span></span>
<span data-ttu-id="03dcb-105">若要安裝特定版本的 EF，請參閱[取得 Entity Framework](~/ef6/fundamentals/install.md)。</span><span class="sxs-lookup"><span data-stu-id="03dcb-105">To install specific versions of EF, see [Get Entity Framework](~/ef6/fundamentals/install.md).</span></span>

<span data-ttu-id="03dcb-106">此頁面記每個新版本所包含的功能。</span><span class="sxs-lookup"><span data-stu-id="03dcb-106">This page documents the features that are included on each new release.</span></span>

## <a name="recent-releases"></a><span data-ttu-id="03dcb-107">最新發行</span><span class="sxs-lookup"><span data-stu-id="03dcb-107">Recent releases</span></span>

### <a name="ef-tools-update-in-visual-studio-2017-157"></a><span data-ttu-id="03dcb-108">Visual Studio 2017 15.7 中的 EF 工具更新</span><span class="sxs-lookup"><span data-stu-id="03dcb-108">EF Tools Update in Visual Studio 2017 15.7</span></span>

<span data-ttu-id="03dcb-109">在 2018 年 5 月，我們在 Visual Studio 2017 15.7 中發行了 EF6 工具的更新版本。</span><span class="sxs-lookup"><span data-stu-id="03dcb-109">In May 2018, we released an updated version of the EF6 Tools in Visual Studio 2017 15.7.</span></span>
<span data-ttu-id="03dcb-110">它包含一些常見難題方面的改善：</span><span class="sxs-lookup"><span data-stu-id="03dcb-110">It includes improvements in some common pain areas:</span></span>

- <span data-ttu-id="03dcb-111">使用者介面協助工具的大幅更新</span><span class="sxs-lookup"><span data-stu-id="03dcb-111">An overhaul to the accessibility of the user interface</span></span>
- <span data-ttu-id="03dcb-112">適用於反向工程上 SQL Server 效能迴歸的因應措施 [#4](https://github.com/aspnet/entityframework6/issues/4)</span><span class="sxs-lookup"><span data-stu-id="03dcb-112">Workaround for SQL Server performance regression on reverse engineering [#4](https://github.com/aspnet/entityframework6/issues/4)</span></span>
- <span data-ttu-id="03dcb-113">支援 SQL Server 上較大型模型的資料庫模型更新 [#185](https://github.com/aspnet/EntityFramework6/issues/185)</span><span class="sxs-lookup"><span data-stu-id="03dcb-113">Update model from database support for larger models on SQL Server [#185](https://github.com/aspnet/EntityFramework6/issues/185)</span></span>

<span data-ttu-id="03dcb-114">這個新版本的 EF 工具會在新專案中建立模型時，安裝 EF 6.2 執行階段。</span><span class="sxs-lookup"><span data-stu-id="03dcb-114">This new version of EF Tools installs the EF 6.2 runtime when creating a model in a new project.</span></span> <span data-ttu-id="03dcb-115">利用舊版的 Visual Studio，就可以安裝 NuGet 套件的對應版本來使用 EF 6.2 執行階段 (以及 EF 的任何過去版本)。</span><span class="sxs-lookup"><span data-stu-id="03dcb-115">With older versions of Visual Studio, it is possible to use the EF 6.2 runtime (as well as any past version of EF) by installing the corresponding version of the NuGet package.</span></span>

### <a name="ef-62-runtime"></a><span data-ttu-id="03dcb-116">EF 6.2 執行階段</span><span class="sxs-lookup"><span data-stu-id="03dcb-116">EF 6.2 Runtime</span></span>

<span data-ttu-id="03dcb-117">EF 6.2 執行階段已於 2017 年 10 月發行至 NuGet。</span><span class="sxs-lookup"><span data-stu-id="03dcb-117">The EF 6.2 runtime was released to NuGet in October of 2017.</span></span>
<span data-ttu-id="03dcb-118">絕大部分歸功於開放原始碼參與者社群的努力，EF 6.2 包含許多 [Bug 修正](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-bug)和[產品增強功能](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-enhancement%20)。</span><span class="sxs-lookup"><span data-stu-id="03dcb-118">Thanks in great part to the efforts our community of open source contributors, EF 6.2 includes numerous [bugs fixes](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-bug) and [product enhancements](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-enhancement%20).</span></span>

<span data-ttu-id="03dcb-119">以下是影響 EF 6.2 執行階段之最重要變更的簡短清單：</span><span class="sxs-lookup"><span data-stu-id="03dcb-119">Here is a brief list of the most important changes affecting the EF 6.2 runtime:</span></span>

- <span data-ttu-id="03dcb-120">從永續性快取載入完成的 Code First 模型來減少啟動時間 [#275](https://github.com/aspnet/EntityFramework6/issues/275)</span><span class="sxs-lookup"><span data-stu-id="03dcb-120">Reduce start up time by loading finished code first models from a persistent cache [#275](https://github.com/aspnet/EntityFramework6/issues/275)</span></span>
- <span data-ttu-id="03dcb-121">Fluent API 用來定義索引 [#274](https://github.com/aspnet/EntityFramework6/issues/274)</span><span class="sxs-lookup"><span data-stu-id="03dcb-121">Fluent API to define indexes [#274](https://github.com/aspnet/EntityFramework6/issues/274)</span></span>
- <span data-ttu-id="03dcb-122">DbFunctions.Like() 用來讓您撰寫在 SQL 中轉譯為 LIKE 的 LINQ 查詢 [#241](https://github.com/aspnet/EntityFramework6/issues/241)</span><span class="sxs-lookup"><span data-stu-id="03dcb-122">DbFunctions.Like() to enable writing LINQ queries that translate to LIKE in SQL [#241](https://github.com/aspnet/EntityFramework6/issues/241)</span></span>
- <span data-ttu-id="03dcb-123">Migrate.exe 現在支援 -script 選項 [#240](https://github.com/aspnet/EntityFramework6/issues/240)</span><span class="sxs-lookup"><span data-stu-id="03dcb-123">Migrate.exe now supports -script option [#240](https://github.com/aspnet/EntityFramework6/issues/240)</span></span>
- <span data-ttu-id="03dcb-124">EF6 現在可以使用 SQL Server 中的序列所產生的索引鍵值 [#165](https://github.com/aspnet/EntityFramework6/issues/165)</span><span class="sxs-lookup"><span data-stu-id="03dcb-124">EF6 can now work with key values generated by a sequence in SQL Server [#165](https://github.com/aspnet/EntityFramework6/issues/165)</span></span>
- <span data-ttu-id="03dcb-125">SQL Azure 執行策略之暫時性錯誤的更新清單 [#83](https://github.com/aspnet/EntityFramework6/issues/83)</span><span class="sxs-lookup"><span data-stu-id="03dcb-125">Update list of transient errors for SQL Azure Execution Strategy [#83](https://github.com/aspnet/EntityFramework6/issues/83)</span></span>
- <span data-ttu-id="03dcb-126">Bug：重試查詢或 SQL 命令失敗，並顯示「SqlParameter 已由另一個 SqlParameterCollection 所包含」 [#81](https://github.com/aspnet/EntityFramework6/issues/81)</span><span class="sxs-lookup"><span data-stu-id="03dcb-126">Bug: Retrying queries or SQL commands fails with "The SqlParameter is already contained by another SqlParameterCollection" [#81](https://github.com/aspnet/EntityFramework6/issues/81)</span></span>
- <span data-ttu-id="03dcb-127">Bug：DbQuery.ToString() 評估經常在偵錯工具中逾時 [#73](https://github.com/aspnet/EntityFramework6/issues/73)</span><span class="sxs-lookup"><span data-stu-id="03dcb-127">Bug: Evaluation of DbQuery.ToString() frequently times out in the debugger [#73](https://github.com/aspnet/EntityFramework6/issues/73)</span></span>

## <a name="future-releases"></a><span data-ttu-id="03dcb-128">未來版本</span><span class="sxs-lookup"><span data-stu-id="03dcb-128">Future Releases</span></span>

<span data-ttu-id="03dcb-129">如需 EF6 未來版本的資訊，請查看我們的[藍圖](roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="03dcb-129">For information on future version of EF6, please look at our [Roadmap](roadmap.md).</span></span>

## <a name="past-releases"></a><span data-ttu-id="03dcb-130">過去版本</span><span class="sxs-lookup"><span data-stu-id="03dcb-130">Past Releases</span></span>

<span data-ttu-id="03dcb-131">[過去版本](past-releases.md)頁面包含所有舊版 EF 與每一版所引進之主要功能的封存。</span><span class="sxs-lookup"><span data-stu-id="03dcb-131">The [Past Releases](past-releases.md) page contains an archive of all previous versions of EF and the major features that were introduced on each release.</span></span> 