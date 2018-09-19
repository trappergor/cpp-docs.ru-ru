---
title: CMyProviderSession (MyProviderSess.H) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyprovidersession
- myprovidersess.h
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2d74c79535a97e8864ad55d3b0cfb35f98bb5ba4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106100"
---
# <a name="cmyprovidersession-myprovidersessh"></a>CMyProviderSession (MyProviderSess.H)

MyProviderSess.H содержит объявления и реализации для объекта сеанса OLE DB. Объект источника данных создает объект сеанса и представляет диалога между потребителем и поставщиком. Несколько одновременных сеансов, можно открыть для одного источника данных. Список наследования для `CMyProviderSession` ниже:  
  
```cpp
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
  
Объект сеанса наследуется от `IGetDataSource`, `IOpenRowset`, `ISessionProperties`, и `IDBCreateCommand`. `IGetDataSource` Интерфейс позволяет сеансу для извлечения источника данных, который его создал. Это полезно, если вам нужно получить свойства из источника данных, который вы создали, или другие сведения источника данных. `ISessionProperties` Интерфейс обрабатывает все свойства для данного сеанса. `IOpenRowset` И `IDBCreateCommand` интерфейсы используются для работы в базе данных. Если поставщик поддерживает команды, он реализует `IDBCreateCommand` интерфейс. Он используется для создания объекта команды, который позволяет выполнять команды. Поставщик всегда реализует `IOpenRowset` объекта. Он используется для создания простого набора строк из поставщика. Это стандартный набор строк (например, `"select * from mytable"`) от поставщика.  
  
Мастер также формирует три класса сеанса: `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema`, и `CMyProviderSessionTRSchema`. Эти сеансы используются для наборов строк схемы. Наборы строк схемы позволяют поставщику возвращать метаданные потребителю без необходимости выполнения запроса или выборки данных потребитель. Идет получение метаданных может быть гораздо быстрее, чем изучение возможностей поставщика.  
  
Спецификация OLE DB требует, поставщики, реализующие `IDBSchemaRowset` схемы набора строк интерфейса поддержку трех типов: DBSCHEMA_COLUMNS, DBSCHEMA_PROVIDER_TYPES и DBSCHEMA_TABLES. Мастер создает реализации для каждого набора строк схемы. Каждый класс, созданный с помощью мастера содержит `Execute` метод. В этом `Execute` метода, могут возвращать данные о том, какие таблицы, столбцы и типы данных поддерживают поставщику. Эти данные обычно известен во время компиляции.  
  
## <a name="see-also"></a>См. также  

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)