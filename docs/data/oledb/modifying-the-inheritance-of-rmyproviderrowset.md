---
title: Изменение порядка наследования класса RMyProviderRowset | Документы Microsoft
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
ms.openlocfilehash: 75acbc8370c1ea164c72aa6f0c61a95fe287e3d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106236"
---
# <a name="modifying-the-inheritance-of-rmyproviderrowset"></a>Изменение порядка наследования класса RMyProviderRowset
Чтобы добавить `IRowsetLocate` интерфейсом пример простого поставщика только для чтения, измените порядок наследования класса **RMyProviderRowset**. Изначально **RMyProviderRowset** наследует от `CRowsetImpl`. Необходимо изменить его, чтобы наследовать от **CRowsetBaseImpl**.  
  
 Чтобы сделать это, создайте новый класс, `CMyRowsetImpl`, (MyProviderRS.h):  
  
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
  
 Теперь измените сопоставление интерфейса COM (MyProviderRS.h) можно использовать следующие:  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 При этом создается схема интерфейса COM, который сообщает `CMyRowsetImpl` для вызова **QueryInterface** для обоих `IRowset` и `IRowsetLocate` интерфейсов. Чтобы получить все реализации других строк классы, карта ссылки `CMyRowsetImpl` класс **CRowsetBaseImpl** определен класс с помощью шаблонов OLE DB; карта использует COM_INTERFACE_ENTRY_CHAIN макрос, который сообщает Сопоставление шаблонов OLE DB для сканирования COM в **CRowsetBaseImpl** в ответ на `QueryInterface` вызова.  
  
 Свяжите `RAgentRowset` для `CMyRowsetBaseImpl` , изменив `RAgentRowset` наследование от `CMyRowsetImpl`, как показано ниже:  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 `RAgentRowset` Теперь можно использовать `IRowsetLocate` интерфейс при одновременном использовании преимуществ остальных реализаций класса набора строк.  
  
 Если это сделано, вы можете [динамически определить столбцы, возвращенные объекту-получателю](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>См. также  
 [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)