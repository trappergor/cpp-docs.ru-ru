---
title: Получение уведомлений
ms.date: 10/24/2018
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
ms.openlocfilehash: 4b630a9728770a5e35e6d6300cf465b90238350c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209807"
---
# <a name="receiving-notifications"></a>Получение уведомлений

OLE DB предоставляет интерфейсы для получения уведомлений при возникновении событий. Они описаны в разделе [уведомления об объектах OLE DB](/previous-versions/windows/desktop/ms725406(v=vs.85)) в **справочнике по программированию OLE DB**. При установке этих событий используется стандартный механизм точки подключения COM. Например, объект ATL, который хочет получить события через `IRowsetNotify`, реализует интерфейс `IRowsetNotify`, добавляя `IRowsetNotify` в список, производный от класса, и предоставляя его через макрос COM_INTERFACE_ENTRY.

`IRowsetNotify` имеет три метода, которые могут вызываться в различные моменты времени. Если вы хотите ответить только на один из этих методов, можно использовать класс [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) , который возвращает E_NOTIMPL для методов, которые вас не интересуют.

При создании набора строк необходимо сообщить поставщику, что возвращаемый объект набора строк должен поддерживать `IConnectionPointContainer`, который необходим для настройки уведомления.

В следующем коде показано, как открыть набор строк из объекта ATL и использовать функцию `AtlAdvise` для настройки приемника уведомлений. `AtlAdvise` возвращает файл cookie, который используется при вызове `AtlUnadvise`.

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_IConnectionPointContainer, true);
```

Затем используется следующий код:

```cpp
product.Open(session, _T("Products"), &propset);

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);
```

## <a name="see-also"></a>См. также раздел

[Использование методов доступа](../../data/oledb/using-accessors.md)
