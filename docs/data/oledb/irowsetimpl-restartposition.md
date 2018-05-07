---
title: IRowsetImpl::RestartPosition | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
dev_langs:
- C++
helpviewer_keywords:
- RestartPosition method
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c203cc19e31f22df5903f099e953fcf5663718f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplrestartposition"></a>IRowsetImpl::RestartPosition
Перемещает позицию следующей выборки в его начальное положение; то есть создать его положение при первоначальной набора строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Позиции строк не определено до **GetNextRow** вызывается. Можно переместить вперед в rowet путем вызова `RestartPosition` и затем выборку и прокрутку в обратном направлении.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)