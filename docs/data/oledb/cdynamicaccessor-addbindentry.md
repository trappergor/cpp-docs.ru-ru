---
title: "CDynamicAccessor::AddBindEntry | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDynamicAccessor::AddBindEntry
- AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
dev_langs:
- C++
helpviewer_keywords:
- AddBindEntry method
ms.assetid: 8f139376-7db3-4193-ba3b-63fe938ffa79
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f2c5a9efdc0ed13fa20b3ee0bd2cad74a8601f25
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessoraddbindentry"></a>CDynamicAccessor::AddBindEntry
Добавляет запись привязки выходных столбцов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `info`  
 [in] Объект **DBCOLUMNINFO** структуру, содержащую сведения о столбце. В разделе «Структуры DBCOLUMNINFO» в [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) в *справочника программиста OLE DB*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
## <a name="remarks"></a>Примечания  
 Используйте этот метод, переопределяя метод доступа по умолчанию, созданных с помощью `CDynamicAccessor` (см. [инструкции по выполнению выборки данных?](../../data/oledb/fetching-data.md)).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)