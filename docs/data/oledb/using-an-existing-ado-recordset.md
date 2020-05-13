---
title: Использование существующего набора записей ADO
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: 48f6eb3bac34b37f495b9492e19b4197ed69cca3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209356"
---
# <a name="using-an-existing-ado-recordset"></a>Использование существующего набора записей ADO

Чтобы смешать OLE DB шаблоны потребителей и активные объекты данных (ADO), используйте ADO для открытия набора записей (соответствующего набору строк в шаблонах потребителя OLE DB). Если у вас есть набор записей, выполните следующие действия, чтобы подключиться к набору строк OLE DB.

1. Вызовите `QueryInterface` для указателей `IRowset` и `IAccessor`.

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *лпунк* указывает на объект `IUnknown` набора записей ADO.

1. Присоедините метод доступа и набор строк к соответствующим OLE DB классам шаблонов потребителей.

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>См. также раздел

[Использование методов доступа](../../data/oledb/using-accessors.md)
