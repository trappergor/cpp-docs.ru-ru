---
title: CCustomSession (CustomSess.H) | Документация Майкрософт
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyprovidersession
- myprovidersess.h
- ccustomsession
- customsess.h
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
- CCustomSession class in CustomSess.H
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8873247ee54884236ed3472c345fb15b99e97131
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076689"
---
# <a name="ccustomsession-customsessh"></a>CCustomSession (CustomSess.H)

*Custom*Sess.H содержит объявления и реализации для объекта сеанса OLE DB. Объект источника данных создает объект сеанса и представляет диалога между потребителем и поставщиком. Несколько одновременных сеансов, можно открыть для одного источника данных. Список наследования для `CCustomSession` ниже:

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSession
class ATL_NO_VTABLE CCustomSession :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IGetDataSourceImpl<CCustomSession>,
   public IOpenRowsetImpl<CCustomSession>,
   public ISessionPropertiesImpl<CCustomSession>,
   public IObjectWithSiteSessionImpl<CCustomSession>,
   public IDBSchemaRowsetImpl<CCustomSession>,
   public IDBCreateCommandImpl<CCustomSession, CCustomCommand>
```

Объект сеанса наследуется от `IGetDataSource`, `IOpenRowset`, `ISessionProperties`, и `IDBCreateCommand`. `IGetDataSource` Интерфейс позволяет сеансу для извлечения источника данных, который его создал. Это полезно, если вам нужно получить свойства из источника данных, который вы создали, или другие сведения источника данных. `ISessionProperties` Интерфейс обрабатывает все свойства для данного сеанса. `IOpenRowset` И `IDBCreateCommand` интерфейсы используются для работы в базе данных. Если поставщик поддерживает команды, он реализует `IDBCreateCommand` интерфейс. Он используется для создания объекта команды, который позволяет выполнять команды. Поставщик всегда реализует `IOpenRowset` объекта. Он используется для создания простого набора строк из поставщика. Это стандартный набор строк (например, `"select * from mytable"`) от поставщика.

Мастер также формирует три класса сеанса: `CCustomSessionColSchema`, `CCustomSessionPTSchema`, и `CCustomSessionTRSchema`. Эти сеансы используются для наборов строк схемы. Наборы строк схемы позволяют поставщику возвращать метаданные потребителю без необходимости выполнения запроса или выборки данных потребитель. Идет получение метаданных может быть гораздо быстрее, чем изучение возможностей поставщика.

Спецификация OLE DB требует, поставщики, реализующие `IDBSchemaRowset` схемы набора строк интерфейса поддержку трех типов: DBSCHEMA_COLUMNS, DBSCHEMA_PROVIDER_TYPES и DBSCHEMA_TABLES. Мастер создает реализации для каждого набора строк схемы. Каждый класс, созданный с помощью мастера содержит `Execute` метод. В этом `Execute` метода, могут возвращать данные о том, какие таблицы, столбцы и типы данных поддерживают поставщику. Эти данные обычно известен во время компиляции.

## <a name="see-also"></a>См. также

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)