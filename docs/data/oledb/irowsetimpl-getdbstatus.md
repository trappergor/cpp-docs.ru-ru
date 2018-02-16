---
title: "IRowsetImpl::GetDBStatus | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
dev_langs:
- C++
helpviewer_keywords:
- GetDBStatus method
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: be19ac31acd587d2e594a6867c8ea70d742d0810
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimplgetdbstatus"></a>IRowsetImpl::GetDBStatus
Возвращает `DBSTATUS` флаги состояния для указанного поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      virtual DBSTATUS GetDBStatus(RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `currentRow`  
 Текущая строка.  
  
 [in] `columnNames`  
 Столбец, для которого запрашивается состояния.  
  
## <a name="return-value"></a>Возвращаемое значение  
 [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) флаги для столбца.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)