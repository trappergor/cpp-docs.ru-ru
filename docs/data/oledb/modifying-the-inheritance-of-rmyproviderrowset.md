---
title: Изменение порядка наследования класса RMyProviderRowset | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 77b26d1d0b67726e1ba2cd66d0e181bc04105a6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028172"
---
# <a name="modifying-the-inheritance-of-rmyproviderrowset"></a>Изменение порядка наследования класса RMyProviderRowset

Чтобы добавить `IRowsetLocate` интерфейс, в примере простого поставщика только для чтения, изменение порядка наследования класса `RMyProviderRowset`. Изначально `RMyProviderRowset` наследует от `CRowsetImpl`. Вам нужно изменить так, чтобы наследовать от `CRowsetBaseImpl`.  
  
Чтобы сделать это, создайте новый класс, `CMyRowsetImpl`, в MyProviderRS.h:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>  
{  
...  
};  
```  
  
Теперь измените схему интерфейсов COM в MyProviderRS.h быть следующим:  
  
```cpp  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
Это создает схему интерфейсов COM, сообщающий `CMyRowsetImpl` для вызова `QueryInterface` для обоих `IRowset` и `IRowsetLocate` интерфейсов. Чтобы получить все реализации для других набора строк, классы, карта ссылки `CMyRowsetImpl` класс `CRowsetBaseImpl` класс определен в шаблонах OLE DB; карта использует макрос COM_INTERFACE_ENTRY_CHAIN, предписывающие шаблоны OLE DB для сканирования в сопоставление COM в `CRowsetBaseImpl` в ответ на `QueryInterface` вызова.  
  
Свяжите `RAgentRowset` для `CMyRowsetBaseImpl` , изменив `RAgentRowset` наследование `CMyRowsetImpl`, как показано ниже:  
  
```cpp  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
`RAgentRowset` Теперь можно использовать `IRowsetLocate` интерфейс, при этом преимуществами оставшаяся часть реализации класса набора строк.  
  
Если это сделано, вы можете [динамически определять столбцы, возвращенные объекту-получателю](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>См. также  

[Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)