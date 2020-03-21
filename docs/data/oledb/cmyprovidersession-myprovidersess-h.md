---
title: CCustomSession (CustomSess.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidersession
- myprovidersess.h
- ccustomsession
- customsess.h
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
- CCustomSession class in CustomSess.H
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
ms.openlocfilehash: 4775f21c1e0fa7666d24b4d6a55e099bc6ae55a2
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079762"
---
# <a name="ccustomsession-customsessh"></a>CCustomSession (CustomSess.H)

*Пользовательский элемент* Подряд. H содержит объявление и реализацию для объекта сеанса OLE DB. Объект источника данных создает объект сеанса и представляет диалог между потребителем и поставщиком. Для одного источника данных можно открыть несколько одновременных сеансов. Список наследования для `CCustomSession` приведен ниже.

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

Объект сеанса наследует от `IGetDataSource`, `IOpenRowset`, `ISessionProperties`и `IDBCreateCommand`. Интерфейс `IGetDataSource` позволяет сеансу получить источник данных, создавший его. Это полезно, если необходимо получить свойства из созданного источника данных или другие сведения, которые может предоставить источник данных. Интерфейс `ISessionProperties` обрабатывает все свойства сеанса. Для работы с базой данных используются интерфейсы `IOpenRowset` и `IDBCreateCommand`. Если поставщик поддерживает команды, он реализует интерфейс `IDBCreateCommand`. Он используется для создания объекта Command, который может выполнять команды. Поставщик всегда реализует объект `IOpenRowset`. Он используется для создания набора строк от поставщика. Это набор строк по умолчанию (например, `"select * from mytable"`) от поставщика.

Мастер также создает три класса сеанса: `CCustomSessionColSchema`, `CCustomSessionPTSchema`и `CCustomSessionTRSchema`. Эти сеансы используются для наборов строк схемы. Наборы строк схемы позволяют поставщику возвращать метаданные потребителю, не требуя от потребителя необходимости выполнять запрос или получать данные. Получение метаданных может быть гораздо быстрее, чем поиск возможностей поставщика.

Спецификация OLE DB требует, чтобы поставщики, реализующие интерфейс `IDBSchemaRowset`, поддерживали три типа наборов строк схемы: DBSCHEMA_COLUMNS, DBSCHEMA_PROVIDER_TYPES и DBSCHEMA_TABLES. Мастер создает реализации для каждого набора строк схемы. Каждый класс, созданный мастером, содержит метод `Execute`. В этом `Execute`ном методе можно вернуть данные поставщику о том, какие таблицы, столбцы и типы данных поддерживаются. Эти данные известны во время компиляции.

## <a name="see-also"></a>См. также:

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)<br/>
