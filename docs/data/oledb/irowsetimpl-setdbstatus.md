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
ms.openlocfilehash: dcc6783ce210c434e58814bcee8654ddd9111b52
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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