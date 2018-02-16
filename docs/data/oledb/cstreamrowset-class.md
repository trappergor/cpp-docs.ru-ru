---
title: "Класс CStreamRowset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4e499d732beb2d73dbb6ec0bbe0b360eeb394b9d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cstreamrowset-class"></a>Класс CStreamRowset
Используется в `CCommand` или `CTable` объявления.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### <a name="parameters"></a>Параметры  
 `TAccessor`  
 Класса метода доступа.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|Конструктор. Создает и инициализирует `CStreamRowset` объекта.|  
|[Закрыть](../../data/oledb/cstreamrowset-close.md)|Выпуски [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx) указатель интерфейса в классе.|  
  
## <a name="remarks"></a>Примечания  
 Используйте `CStreamRowset` в ваш `CCommand` или `CTable` объявление, например:  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
 или  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` Возвращает `ISequentialStream` указатель, который хранится в `m_spStream`. Затем с помощью **чтения** метод для извлечения данных (строка в Юникоде) в формате XML. Пример:  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 выполняет форматирование XML и возвращает все столбцы и строки набора как одну строку XML.  
  
> [!NOTE]
>  Эта функция работает только с SQL Server 2000.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)