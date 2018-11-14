---
title: Интерфейсы объекта Rowset
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
ms.openlocfilehash: 3f20550558a4af4b286aa0de170763df979ffc5d
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556586"
---
# <a name="rowset-object-interfaces"></a>Интерфейсы объекта Rowset

Ниже приведены обязательные и необязательные интерфейсы, определенные в OLE DB для объекта набора строк.

|Интерфейс|Обязательный?|Реализовано с помощью шаблонов OLE DB?|
|---------------|---------------|--------------------------------------|
|[IAccessor](https://docs.microsoft.com/previous-versions/windows/desktop/ms719672(v=vs.85))|Обязательный|Да|
|[IColumnsInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms724541(v=vs.85))|Обязательный|Да|
|[Интерфейс IConvertType](https://docs.microsoft.com/previous-versions/windows/desktop/ms715926(v=vs.85))|Обязательный|Да|
|[IRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms720986(v=vs.85))|Обязательный|Да|
|[IRowsetInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms724541(v=vs.85))|Обязательный|Да|
|[IChapteredRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms718180(v=vs.85))|Optional|Нет|
|[IColumnsInfo2](https://docs.microsoft.com/previous-versions/windows/desktop/ms712953(v=vs.85))|Optional|Нет|
|[IColumnsRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms722657(v=vs.85))|Optional|Нет|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|Да (с помощью ATL)|
|[IDBAsynchStatus](https://docs.microsoft.com/previous-versions/windows/desktop/ms709832(v=vs.85))|Optional|Нет|
|[IGetRow](https://docs.microsoft.com/previous-versions/windows/desktop/ms718047(v=vs.85))|Optional|Нет|
|[IRowsetChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms715790(v=vs.85))|Optional|Да|
|[IRowsetChapterMember](https://docs.microsoft.com/previous-versions/windows/desktop/ms725430(v=vs.85))|Optional|Нет|
|[IRowsetCurrentIndex](https://docs.microsoft.com/previous-versions/windows/desktop/ms709700(v=vs.85))|Optional|Нет|
|[IRowsetFind](https://docs.microsoft.com/previous-versions/windows/desktop/ms724221(v=vs.85))|Optional|Нет|
|[IRowsetIdentity](https://docs.microsoft.com/previous-versions/windows/desktop/ms715913(v=vs.85))|Необязательно (но требуемый для поставщиков уровня 0)|Да|
|[IRowsetIndex](https://docs.microsoft.com/previous-versions/windows/desktop/ms719604(v=vs.85))|Optional|Нет|
|[IRowsetLocate](https://docs.microsoft.com/previous-versions/windows/desktop/ms721190(v=vs.85))|Optional|Да|
|[IRowsetRefresh](https://docs.microsoft.com/previous-versions/windows/desktop/ms714892(v=vs.85))|Optional|Нет|
|[IRowsetScroll](https://docs.microsoft.com/previous-versions/windows/desktop/ms712984(v=vs.85))|Optional|Нет|
|[IRowsetUpdate](https://docs.microsoft.com/previous-versions/windows/desktop/ms714401(v=vs.85))|Optional|Да|
|[IRowsetView](https://docs.microsoft.com/previous-versions/windows/desktop/ms709755(v=vs.85))|Optional|Нет|
|[ISupportErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|Да|
|[IRowsetBookmark](https://docs.microsoft.com/previous-versions/windows/desktop/ms714246(v=vs.85))|Optional|Нет|

Реализует объект набора строк, создаваемые мастером `IAccessor`, `IRowset`, и `IRowsetInfo` через наследование. `IAccessorImpl` Привязывает обоих выходных столбцов. `IRowset` Интерфейс обработки выборок строк и данных. `IRowsetInfo` Интерфейс обрабатывает свойства набора строк.

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
