---
title: 記錄檔的提供者影響的變更-EF Core
author: ajcvickers
ms.author: avickers
ms.date: 08/08/2018
ms.assetid: 7CEF496E-A5B0-4F5F-B68E-529609B23EF9
ms.technology: entity-framework-core
uid: core/providers/provider-log
ms.openlocfilehash: a87eca72aa58487415eea11e4f83de1a19e73506
ms.sourcegitcommit: 5e11125c9b838ce356d673ef5504aec477321724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/25/2018
ms.locfileid: "50022333"
---
# <a name="provider-impacting-changes"></a>提供者影響的變更

此頁面包含提取要求可能需要其他的資料庫提供者，以回應的作者在 EF Core 存放庫上所做的連結。 目的是要讓現有的協力廠商資料庫提供者作者提供一個起始點，其提供者更新為新版本時。

我們會將此記錄檔開頭 2.1 2.2 的變更。 我們用之前 2.1 [ `providers-beware` ](https://github.com/aspnet/EntityFrameworkCore/labels/providers-beware)並[ `providers-fyi` ](https://github.com/aspnet/EntityFrameworkCore/labels/providers-fyi)上我們的問題和提取要求標籤。

## <a name="21-----22"></a>2.1---> 2.2

### <a name="test-only-changes"></a>僅限測試的變更

* https://github.com/aspnet/EntityFrameworkCore/pull/12057 -在測試中允許可自訂的 SQL 分隔符號
  * 測試可讓非嚴格的浮動點比較 BuiltInDataTypesTestBase 中的變更
  * 允許要重複使用不同的 SQL 分隔符號使用的查詢測試的測試變更
* https://github.com/aspnet/EntityFrameworkCore/pull/12072 -將 DbFunction 測試加入至關聯式規格測試
  * 例如，針對所有的資料庫提供者，可以執行這些測試
* https://github.com/aspnet/EntityFrameworkCore/pull/12362 -非同步測試清除
  * 移除`Wait`呼叫，不需要非同步處理，並重新命名某些測試方法
* https://github.com/aspnet/EntityFrameworkCore/pull/12666 -統一記錄測試基礎結構
  * 新增`CreateListLoggerFactory`和移除一些先前記錄基礎結構，而這需要使用這些測試回應的提供者
* https://github.com/aspnet/EntityFrameworkCore/pull/12500 -執行更多的查詢測試，以同步和非同步
  * 測試名稱和分解已經變更，這將需要使用這些測試回應的提供者
* https://github.com/aspnet/EntityFrameworkCore/pull/12766 -重新命名 ComplexNavigations 模型中的巡覽
  * 使用這些測試的提供者可能需要做出回應
* https://github.com/aspnet/EntityFrameworkCore/pull/12141 -傳回集區，而不是功能測試在處置內容
  * 這項變更會包含可能需要提供者，以因應一些測試重構


### <a name="test-and-product-code-changes"></a>測試和產品程式碼變更

* https://github.com/aspnet/EntityFrameworkCore/pull/12109 -彙總 RelationalTypeMapping.Clone 方法
  * 允許在衍生類別中簡化 RelationalTypeMapping 的 2.1 中的變更。 我們不認為這重大提供者，但提供者可以利用這項變更其衍生類型中對應的類別。
* https://github.com/aspnet/EntityFrameworkCore/pull/12069 -已標記或具名查詢
  * 新增用於標記 LINQ 查詢以及做為 SQL 中的註解會顯示這些標記的基礎結構。 這可能需要以回應 SQL 層代中的提供者。
* https://github.com/aspnet/EntityFrameworkCore/pull/13115 -支援透過 NTS 的空間資料
  * 讓型別對應和成員轉譯外部提供者註冊
    * 提供者必須呼叫基底。FindMapping() 在 ITypeMappingSource 實作，才能正常運作中
  * 請遵循此模式，以將空間的支援新增至您的提供者的提供者間也保持一致。
* https://github.com/aspnet/EntityFrameworkCore/pull/13199 新增服務提供者建立的增強型偵錯
  * 可讓實作新的介面，可協助人員了解內部的服務提供者正在重新建置 DbContextOptionsExtensions
* https://github.com/aspnet/EntityFrameworkCore/pull/13289 -新增 CanConnect API 使用的健康狀態檢查
  * 此提取要求將加入的概念`CanConnect`這會由 ASP.NET Core 健全狀況檢查，來判斷資料庫是否可用。 根據預設，關聯式的實作只會呼叫`Exist`，但如有必要，提供者可以實作不同的項目。 非關聯式的提供者必須實作新的 API，讓健康情況檢查，才能使用。
* https://github.com/aspnet/EntityFrameworkCore/pull/13306 -更新基底 RelationalTypeMapping 不設定 DbParameter 大小
  * 停止設定預設的大小，因為它可能會造成截斷。 提供者可能需要新增自己的邏輯，如果需要設定大小。
* https://github.com/aspnet/EntityFrameworkCore/pull/13372 -RevEng： 一定要指定十進位資料行的資料行類型
  * Scaffold 程式碼，而不是設定依照慣例，一律先設定十進位資料行的資料行類型。
  * 提供者應該不需要在其端上的任何變更。
* https://github.com/aspnet/EntityFrameworkCore/pull/13469 -將 CaseExpression 加入產生案例 SQL 運算式
* https://github.com/aspnet/EntityFrameworkCore/pull/13648 -新增能夠在 SqlFunctionExpression 來改善存放區型別推斷結果引數的指定類型對應。
