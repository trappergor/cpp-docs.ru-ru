---
title: "CMyProviderSession (MyProviderSess.H) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmyprovidersession
- myprovidersess.h
dev_langs: C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3cf8a75a416f03fed1ae7e0deb9118b3c40ea5fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmyprovidersession-myprovidersessh"></a>CMyProviderSession (MyProviderSess.H)
MyProviderSess.H содержит объявления и реализации для объекта сеанса OLE DB. Объект источника данных создает объект сеанса и представляет диалоге клиента и поставщика. Несколько параллельных сеансов может быть открыт для одного источника данных. Список наследования для `CMyProviderSession` ниже:  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 Объект сеанса наследуется от **IGetDataSource**, `IOpenRowset`, **ISessionProperties**, и **IDBCreateCommand**. **IGetDataSource** интерфейс позволяет сеансу извлекать создавший его источник данных. Это полезно, если вам нужно получить свойства из источника данных, созданный или другие сведения, которые можно указать источник данных. **ISessionProperties** интерфейс обрабатывает все свойства для данного сеанса. `IOpenRowset` И **IDBCreateCommand** интерфейсы используются для выполнения работы в базе данных. Если поставщик поддерживает команды, он реализует **IDBCreateCommand** интерфейса. Он используется для создания объекта команды, который позволяет выполнять команды. Поставщик всегда реализует `IOpenRowset` объекта. Он используется для создания простого набора строк из поставщика. Это стандартный набор строк (например, `"select * from mytable"`) от поставщика.  
  
 Мастер также создает три класса сеансов: `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema`, и `CMyProviderSessionTRSchema`. Эти сеансы используются для наборов строк схемы. Наборы строк схемы позволяют поставщику возвращать метаданные потребителю без необходимости выполнения запроса или выборки данных потребитель. Выборка метаданных может оказаться гораздо быстрее, чем изучение возможностей поставщика.  
  
 Спецификация OLE DB требует, поставщики, реализующие **IDBSchemaRowset** схемы набора строк интерфейса поддержки трех типов: **DBSCHEMA_COLUMNS**, **DBSCHEMA_PROVIDER_TYPES** , и `DBSCHEMA_TABLES`. Мастер создает реализации для каждого набора строк схемы. Каждый класс, созданные с помощью мастера содержит `Execute` метод. В этом `Execute` метода, могут возвращать данные поставщика о том, какие таблицы, столбцы и типы данных поддерживаются. Эти данные обычно известен во время компиляции.  
  
## <a name="see-also"></a>См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)