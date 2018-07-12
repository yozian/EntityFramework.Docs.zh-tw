---
title: 建立模型 - EF6
author: divega
ms.date: 2018-07-05
ms.prod: entity-framework
ms.author: divega
ms.manager: avickers
ms.technology: entity-framework-6
ms.topic: article
ms.assetid: 4890228E-CEA1-4595-B8AD-CA81253F8767
caps.latest.revision: 3
ms.openlocfilehash: e1eb4077a1fd77c66bb3e992e1d25a5de4fcc64c
ms.sourcegitcommit: 45494121254ad4fdcec613d1dd22d850068d6f39
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2018
ms.locfileid: "37913508"
---
# <a name="creating-a-model"></a><span data-ttu-id="c2100-102">建立模型</span><span class="sxs-lookup"><span data-stu-id="c2100-102">Creating a Model</span></span>

<span data-ttu-id="c2100-103">EF 模型會儲存有關應用程式類別和屬性如何對應至資料庫資料表和資料行的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c2100-103">An EF model stores the details about how application classes and properties map to database tables and columns.</span></span> <span data-ttu-id="c2100-104">有兩種主要的方式可用來建立 EF 模型：</span><span class="sxs-lookup"><span data-stu-id="c2100-104">There are two main ways to create an EF model:</span></span>

- <span data-ttu-id="c2100-105">**使用 Code First**：開發人員撰寫程式碼以指定模型。</span><span class="sxs-lookup"><span data-stu-id="c2100-105">**Using Code First**: The developer writes code to specify the model.</span></span> <span data-ttu-id="c2100-106">EF 會根據實體類別和開發人員提供的其他模型組態，在執行階段產生模型和對應。</span><span class="sxs-lookup"><span data-stu-id="c2100-106">EF generates the models and mappings at runtime based on entity classes and additional model configuration provided by the developer.</span></span>

- <span data-ttu-id="c2100-107">**使用 EF 設計工具**：開發人員使用 EF 設計工具繪製方塊和線來指定模型。</span><span class="sxs-lookup"><span data-stu-id="c2100-107">**Using the EF Designer**: The developer draws boxes and lines to specify the model using the EF Designer.</span></span> <span data-ttu-id="c2100-108">產生的模型會以 XML 的形式儲存在副檔名為 EDMX 的檔案中。</span><span class="sxs-lookup"><span data-stu-id="c2100-108">The resulting model is stored as XML in a file with the EDMX extension.</span></span> <span data-ttu-id="c2100-109">應用程式的領域物件通常是從概念模型自動產生。</span><span class="sxs-lookup"><span data-stu-id="c2100-109">The application's domain objects are typically generated automatically from the conceptual model.</span></span>

## <a name="ef-workflows"></a><span data-ttu-id="c2100-110">EF 工作流程</span><span class="sxs-lookup"><span data-stu-id="c2100-110">EF workflows</span></span>

<span data-ttu-id="c2100-111">這兩種方法可用來將現有資料庫設為目標，或建立新的資料庫，進而產生 4 個不同的工作流程。</span><span class="sxs-lookup"><span data-stu-id="c2100-111">Both of these approaches can be used to target an existing database or create a new database, resulting in 4 different workflows.</span></span>
<span data-ttu-id="c2100-112">請找出哪一個最適合您：</span><span class="sxs-lookup"><span data-stu-id="c2100-112">Find out about which one is best for you:</span></span>  

|                                           | <span data-ttu-id="c2100-113">我只想要撰寫程式碼...</span><span class="sxs-lookup"><span data-stu-id="c2100-113">I just want to write code...</span></span>                                                                                                                   | <span data-ttu-id="c2100-114">我想要使用設計工具...</span><span class="sxs-lookup"><span data-stu-id="c2100-114">I want to use a designer...</span></span>                                                                                                                        |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c2100-115">**我要建立新的資料庫**</span><span class="sxs-lookup"><span data-stu-id="c2100-115">**I am creating a new database**</span></span>          | [<span data-ttu-id="c2100-116">使用 **Code First** 在程式碼中定義您的模型，然後產生資料庫。</span><span class="sxs-lookup"><span data-stu-id="c2100-116">Use **Code First** to define your model in code and then generate a database.</span></span>](~/ef6/modeling/code-first/workflows/new-database.md)           | [<span data-ttu-id="c2100-117">使用 **Model First** 利用方塊和線定義您的模型，然後產生資料庫。</span><span class="sxs-lookup"><span data-stu-id="c2100-117">Use **Model First** to define your model using boxes and lines and then generate a database.</span></span>](~/ef6/modeling/designer/workflows/model-first.md)   |
| <span data-ttu-id="c2100-118">**我需要存取現有資料庫**</span><span class="sxs-lookup"><span data-stu-id="c2100-118">**I need to access an existing database**</span></span> | [<span data-ttu-id="c2100-119">使用 **Code First** 建立對應至現有資料庫的程式碼架構模型。</span><span class="sxs-lookup"><span data-stu-id="c2100-119">Use **Code First** to create a code based model that maps to an existing database.</span></span>](~/ef6/modeling/code-first/workflows/existing-database.md) | [<span data-ttu-id="c2100-120">使用 **Database First** 建立對應至現有資料庫的方塊和線條模型。</span><span class="sxs-lookup"><span data-stu-id="c2100-120">Use **Database First** to create a boxes and lines model that maps to an existing database.</span></span>](~/ef6/modeling/designer/workflows/database-first.md) |

### <a name="watch-the-video-what-ef-workflow-should-i-use"></a><span data-ttu-id="c2100-121">觀看影片：應該使用哪個 EF 工作流程？</span><span class="sxs-lookup"><span data-stu-id="c2100-121">Watch the video: What EF workflow should I use?</span></span>

<span data-ttu-id="c2100-122">這個短片說明這些差異，以及如何找出最適合您的工作流程。</span><span class="sxs-lookup"><span data-stu-id="c2100-122">This short video explains the differences, and how to find the one that is right for you.</span></span>

<span data-ttu-id="c2100-123">**主講人**[Rowan Miller](http://romiller.com/)</span><span class="sxs-lookup"><span data-stu-id="c2100-123">**Presented By**: [Rowan Miller](http://romiller.com/)</span></span>

<span data-ttu-id="c2100-124">![WhichWorkflow_Thumb](../media/whichworkflow-thumb.png) [WMV](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.wmv) | [MP4](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_mp4video_ChoseYourWorkflow.m4v) | [WMV (ZIP)](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.zip)</span><span class="sxs-lookup"><span data-stu-id="c2100-124">![WhichWorkflow_Thumb](../media/whichworkflow-thumb.png) [WMV](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.wmv) | [MP4](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_mp4video_ChoseYourWorkflow.m4v) | [WMV (ZIP)](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.zip)</span></span>

<span data-ttu-id="c2100-125">如果您在觀看影片之後，仍然無法決定是否要使用 EF 設計工具或 Code First，請了解這兩者！</span><span class="sxs-lookup"><span data-stu-id="c2100-125">If after watching the video you still don't feel comfortable deciding if you want to use the EF Designer or Code First, learn both!</span></span>

## <a name="a-look-under-the-hood"></a><span data-ttu-id="c2100-126">深入探討</span><span class="sxs-lookup"><span data-stu-id="c2100-126">A look under the hood</span></span>

<span data-ttu-id="c2100-127">不論您是使用 Code First 還是 EF 設計工具，EF 模型一定會有數個元件：</span><span class="sxs-lookup"><span data-stu-id="c2100-127">Regardless of whether you use Code First or the EF Designer, an EF model always has several components:</span></span>

- <span data-ttu-id="c2100-128">應用程式的定義域物件或實體類型本身。</span><span class="sxs-lookup"><span data-stu-id="c2100-128">The application's domain objects or entity types themselves.</span></span> <span data-ttu-id="c2100-129">這通常稱為物件層</span><span class="sxs-lookup"><span data-stu-id="c2100-129">This is often referred to as the object layer</span></span>

- <span data-ttu-id="c2100-130">概念模型由定義域特定實體類型和關聯性組成，使用[實體資料模型](~/ef6/resources/glossary.md#entity-data-model)加以描述。</span><span class="sxs-lookup"><span data-stu-id="c2100-130">A conceptual model consisting of domain-specific entity types and relationships, described using the [Entity Data Model](~/ef6/resources/glossary.md#entity-data-model).</span></span> <span data-ttu-id="c2100-131">這一層通常以字母 "C" 來指稱，代表「概念」(_conceptual_)。</span><span class="sxs-lookup"><span data-stu-id="c2100-131">This layer is often referred to with the letter "C", for _conceptual_.</span></span>

- <span data-ttu-id="c2100-132">代表資料庫中定義的資料表、資料行和關聯性的儲存體模型。</span><span class="sxs-lookup"><span data-stu-id="c2100-132">A storage model representing tables, columns and relationships as defined in the database.</span></span> <span data-ttu-id="c2100-133">這一層通常以字母 "S" 來指稱，代表「儲存體」(_storage_)。</span><span class="sxs-lookup"><span data-stu-id="c2100-133">This layer is often referred to with the later "S", for _storage_.</span></span>  

- <span data-ttu-id="c2100-134">概念模型與資料庫結構描述之間的對應。</span><span class="sxs-lookup"><span data-stu-id="c2100-134">A mapping between the conceptual model and the database schema.</span></span> <span data-ttu-id="c2100-135">此對應通常稱為 "C-S" 對應。</span><span class="sxs-lookup"><span data-stu-id="c2100-135">This mapping is often referred to as "C-S" mapping.</span></span>

<span data-ttu-id="c2100-136">EF 的對應引擎會利用 "C-S" 對應，將針對實體的作業 (例如建立、讀取、更新和刪除)　轉換成針對資料庫中資料表的對等作業。</span><span class="sxs-lookup"><span data-stu-id="c2100-136">EF's mapping engine leverages the "C-S" mapping to transform operations against entities - such as create, read, update, and delete - into equivalent operations against tables in the database.</span></span>

<span data-ttu-id="c2100-137">概念模型和應用程式物件之間的對應通常稱為 "O-C" 對應。</span><span class="sxs-lookup"><span data-stu-id="c2100-137">The mapping between the conceptual model and the application's objects is often referred to as "O-C" mapping.</span></span> <span data-ttu-id="c2100-138">相較於 "C-S" 對應，"O-C" 對應為隱含而且是一對一：概念模型中定義的實體、屬性和關聯性需要符合 .NET 物件的圖形與類型。</span><span class="sxs-lookup"><span data-stu-id="c2100-138">Compared to the "C-S" mapping, "O-C" mapping is implicit and one-to-one: entities, properties and relationships defined in the conceptual model are required to match the shapes and types of the .NET objects.</span></span> <span data-ttu-id="c2100-139">從 EF4 和更新版本開始，物件層可以由具有屬性的簡單物件所組成，而不需要對 EF 具有任何相依性。</span><span class="sxs-lookup"><span data-stu-id="c2100-139">From EF4 and beyond, the objects layer can be composed of simple objects with properties without any dependencies on EF.</span></span> <span data-ttu-id="c2100-140">這些通常稱為簡單的 CLR 物件 (POCO)，類型和屬性的對應則會根據名稱比對慣例執行。</span><span class="sxs-lookup"><span data-stu-id="c2100-140">These are usually referred to as Plain-Old CLR Objects (POCO) and mapping of types and properties is performed base on name matching conventions.</span></span> <span data-ttu-id="c2100-141">之前，EF 3.5 的物件層中存在特定限制，例如實體必須衍生自 EntityObject 類別，以及必須包含 EF 屬性來實作 "O-C" 對應。</span><span class="sxs-lookup"><span data-stu-id="c2100-141">Previously, in EF 3.5 there were specific restrictions for the object layer, like entities having to derive from the EntityObject class and having to carry EF attributes to implement the "O-C" mapping.</span></span>