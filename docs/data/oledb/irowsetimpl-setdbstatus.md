---
title: "IRowsetImpl::SetDBStatus | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
dev_langs: C++
helpviewer_keywords: SetDBStatus method
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 285f9004c9971d18646626b7410dcb52485227c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplsetdbstatus"></a>IRowsetImpl::SetDBStatus
Наборы `DBSTATUS` флаги состояния для указанного поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      virtual HRESULT SetDBStatus(  
   DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo   
);  
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