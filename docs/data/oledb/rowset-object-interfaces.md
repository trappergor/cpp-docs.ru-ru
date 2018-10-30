---
title: Интерфейсы объекта Rowset | Документация Майкрософт
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dc9ec134321b2acf9994ad7dfb43c5b14bf0e75f
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216452"
---
# <a name="rowset-object-interfaces"></a>Интерфейсы объекта Rowset

Ниже приведены обязательные и необязательные интерфейсы, определенные в OLE DB для объекта набора строк.

|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|
|---------------|---------------|--------------------------------------|
|[IAccessor](/previous-versions/windows/desktop/ms719672)|Обязательный|Да|
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541)|Обязательный|Да|
|[Интерфейс IConvertType](/previous-versions/windows/desktop/ms715926)|Обязательный|Да|
|[IRowset](/previous-versions/windows/desktop/ms720986)|Обязательный|Да|
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541)|Обязательный|Да|
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180)|Optional|Нет|
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953)|Optional|Нет|
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657)|Optional|Нет|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|Да (с помощью ATL)|
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832)|Optional|Нет|
|[IGetRow](/previous-versions/windows/desktop/ms718047)|Optional|Нет|
|[IRowsetChange](/previous-versions/windows/desktop/ms715790)|Optional|Да|
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430)|Optional|Нет|
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700)|Optional|Нет|
|[IRowsetFind](/previous-versions/windows/desktop/ms724221)|Optional|Нет|
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913)|Необязательно (но требуемый для поставщиков уровня 0)|Да|
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604)|Optional|Нет|
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190)|Optional|Да|
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892)|Optional|Нет|
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984)|Optional|Нет|
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401)|Optional|Да|
|[IRowsetView](/previous-versions/windows/desktop/ms709755)|Optional|Нет|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|Optional|Да|
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246)|Optional|Нет|

Реализует объект набора строк, создаваемые мастером `IAccessor`, `IRowset`, и `IRowsetInfo` через наследование. `IAccessorImpl` Привязывает обоих выходных столбцов. `IRowset` Интерфейс обработки выборок строк и данных. `IRowsetInfo` Интерфейс обрабатывает свойства набора строк.

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
