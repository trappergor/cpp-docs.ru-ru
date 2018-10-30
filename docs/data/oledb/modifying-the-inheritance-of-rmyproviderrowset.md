---
title: Изменение порядка наследования класса RCustomRowset | Документация Майкрософт
ms.custom: ''
ms.date: 10/26/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 13e15b470be6f6a5af4f8012e3a70896f648e665
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216517"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>Изменение порядка наследования класса RCustomRowset

Чтобы добавить `IRowsetLocate` интерфейс, в примере простого поставщика только для чтения, изменение порядка наследования класса `RCustomRowset`. Изначально `RCustomRowset` наследует от `CRowsetImpl`. Вам нужно изменить так, чтобы наследовать от `CRowsetBaseImpl`.

Чтобы сделать это, создайте новый класс, `CCustomRowsetImpl`, в CustomRS.h:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>
{
...
};
```

Теперь, изменить схему интерфейсов COM в *Custom*RS.h быть следующим:

```cpp
BEGIN_COM_MAP(CMyRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Этот код создает схему интерфейсов COM, сообщающий `CMyRowsetImpl` для вызова `QueryInterface` для обоих `IRowset` и `IRowsetLocate` интерфейсов. Чтобы получить все реализации для других набора строк, классы, карта ссылки `CMyRowsetImpl` класс `CRowsetBaseImpl` класс определен в шаблонах OLE DB; карта использует макрос COM_INTERFACE_ENTRY_CHAIN, предписывающие шаблоны OLE DB для сканирования в сопоставление COM в `CRowsetBaseImpl` в ответ на `QueryInterface` вызова.

Свяжите `RAgentRowset` для `CMyRowsetBaseImpl` , изменив `RAgentRowset` наследование `CMyRowsetImpl`, как показано ниже:

```cpp
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CCustomCommand>
```

`RAgentRowset` Теперь можно использовать `IRowsetLocate` интерфейс, при этом преимуществами оставшаяся часть реализации класса набора строк.

Если это сделано, вы можете [динамически определять столбцы, возвращенные объекту-получателю](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>См. также

[Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
