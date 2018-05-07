---
title: Класс CAccessorRowset | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
dev_langs:
- C++
helpviewer_keywords:
- CAccessorRowset class
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 27d2153c6f600c3a5c75c1218e8751baaabcf030
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="caccessorrowset-class"></a>Класс CAccessorRowset
Инкапсулирует набор строк и его связанные методы доступа, в один класс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CNoAccessor, 
          template <typename T> class TRowset = CRowset>  
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>Параметры  
 `TAccessor`  
 Класса метода доступа.  
  
 `TRowset`  
 От класса набора строк.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[BIND](../../data/oledb/caccessorrowset-bind.md)|Создает привязок (используется, когда **bBind** указано как false в [CCommand::Open](../../data/oledb/ccommand-open.md)).|  
|[CAccessorRowset](../../data/oledb/caccessorrowset-caccessorrowset.md)|Конструктор.|  
|[Закрыть](../../data/oledb/caccessorrowset-close.md)|Закрывает все методы доступа и набор строк.|  
|[FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md)|Освобождает все столбцы в текущей записи, которые должны быть освобождены.|  
|[GetColumnInfo](../../data/oledb/caccessorrowset-getcolumninfo.md)|Реализует [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx).|  
  
## <a name="remarks"></a>Примечания  
 Класс `TAccessor` управляет метода доступа. Класс *TRowset* управляет набора строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)