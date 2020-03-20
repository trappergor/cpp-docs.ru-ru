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
ms.openlocfilehash: d9c2c61714a98d9de09d8657352a14f296e35a58
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544546"
---
# <a name="rowset-object-interfaces"></a>Интерфейсы объекта Rowset

В следующей таблице показаны обязательные и необязательные интерфейсы, определенные OLE DB для объекта набора строк.

|Интерфейс|Обязательно?|Реализуется с помощью шаблонов OLE DB?|
|---------------|---------------|--------------------------------------|
|[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85))|Обязательный|Да|
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Обязательный|Да|
|[IConvertType](/previous-versions/windows/desktop/ms715926(v=vs.85))|Обязательный|Да|
|[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85))|Обязательный|Да|
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Обязательный|Да|
|[ичаптередровсет](/previous-versions/windows/desktop/ms718180(v=vs.85))|Необязательно|Нет|
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953(v=vs.85))|Необязательно|Нет|
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657(v=vs.85))|Необязательно|Нет|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Необязательно|Да (с помощью ATL)|
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832(v=vs.85))|Необязательно|Нет|
|[ижетров](/previous-versions/windows/desktop/ms718047(v=vs.85))|Необязательно|Нет|
|[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))|Необязательно|Да|
|[ировсетчаптермембер](/previous-versions/windows/desktop/ms725430(v=vs.85))|Необязательно|Нет|
|[ировсеткуррентиндекс](/previous-versions/windows/desktop/ms709700(v=vs.85))|Необязательно|Нет|
|[IRowsetFind](/previous-versions/windows/desktop/ms724221(v=vs.85))|Необязательно|Нет|
|[ировсетидентити](/previous-versions/windows/desktop/ms715913(v=vs.85))|Необязательный (но требуется для поставщиков уровня 0)|Да|
|[ировсетиндекс](/previous-versions/windows/desktop/ms719604(v=vs.85))|Необязательно|Нет|
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))|Необязательно|Да|
|[ировсетрефреш](/previous-versions/windows/desktop/ms714892(v=vs.85))|Необязательно|Нет|
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984(v=vs.85))|Необязательно|Нет|
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85))|Необязательно|Да|
|[ировсетвиев](/previous-versions/windows/desktop/ms709755(v=vs.85))|Необязательно|Нет|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Необязательно|Да|
|[ировсетбукмарк](/previous-versions/windows/desktop/ms714246(v=vs.85))|Необязательно|Нет|

Созданный мастером объект набора строк реализует `IAccessor`, `IRowset`и `IRowsetInfo` через наследование. `IAccessorImpl` привязывает оба выходных столбца. Интерфейс `IRowset` обрабатывает выборку строк и данных. Интерфейс `IRowsetInfo` обрабатывает свойства набора строк.

## <a name="see-also"></a>См. также:

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
