---
title: Получение уведомлений | Документация Майкрософт
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 244ebbfdb1ca706550fa26acd29e0af067cb1a7a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079718"
---
# <a name="receiving-notifications"></a>Получение уведомлений

OLE DB предоставляет интерфейсы для получения уведомлений при возникновении событий. Они описаны в [уведомления объект OLE DB](/previous-versions/windows/desktop/ms725406) в **Справочник программиста OLE DB по**. Программа установки этих событий использует стандартный механизм точки подключения COM. Например, объект ATL, который хочет получить события с помощью `IRowsetNotify` реализует `IRowsetNotify` интерфейс, добавив `IRowsetNotify` списке производный класс и предоставлением доступа через COM_INTERFACE_ENTRY макроса.

`IRowsetNotify` имеет три метода, которые могут быть вызваны в разные моменты времени. Если вы хотите отвечать только к одной из этих методов, можно использовать [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) класс, который возвращает E_NOTIMPL для методов, которые вас не интересуют.

При создании набора строк, вы сообщите поставщику возникает необходимость возвращаемый объект набора строк для поддержки `IConnectionPointContainer`, который необходим для настройки уведомлений.

Ниже показано, как открыть набор строк из объекта ATL и использовать `AtlAdvise` функция настройке приемника уведомлений. `AtlAdvise` Возвращает файл cookie, который используется при вызове `AtlUnadvise`.

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_IConnectionPointContainer, true);
```

После этого используется следующий код:

```cpp
product.Open(session, _T("Products"), &propset);

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);
```

## <a name="see-also"></a>См. также

[Использование методов доступа](../../data/oledb/using-accessors.md)