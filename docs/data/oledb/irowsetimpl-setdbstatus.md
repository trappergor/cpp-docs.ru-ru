---
title: IRowsetImpl::SetDBStatus | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
dev_langs:
- C++
helpviewer_keywords:
- SetDBStatus method
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e6e07b6fe1a45a779c5ffe1e1afffaabdcb6d34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplsetdbstatus"></a>IRowsetImpl::SetDBStatus
Наборы `DBSTATUS` флаги состояния для указанного поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo);  
```  
  
#### <a name="parameters"></a>Параметры  
 `statusFlags`  
 [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) флаги должно быть задано для столбца.  
  
 `currentRow`  
 Текущая строка.  
  
 *columnInfo*  
 Столбец, для которой задается состояние.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
## <a name="remarks"></a>Примечания  
 Поставщик переопределяет эту функцию для обеспечения специальной обработки для **DBSTATUS_S_ISNULL** и **DBSTATUS_S_DEFAULT**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)