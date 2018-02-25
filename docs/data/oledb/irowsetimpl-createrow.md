---
title: "IRowsetImpl::CreateRow | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs:
- C++
helpviewer_keywords:
- CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fd378ed599795911a86fb4bc10625721c76f417b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
Вспомогательный метод, вызываемый [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) выделить новый **HROW**.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT CreateRow(DBROWOFFSET lRowsOffset,  
  DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows);  
```  
  
#### <a name="parameters"></a>Параметры  
 *lRowsOffset*  
 Позиция курсора создаваемой строки.  
  
 *cRowsObtained*  
 Ссылка передается обратно в пользователя, указывая число созданных строк.  
  
 *rgRows*  
 Массив **HROW**s возвращается вызывающему с дескрипторами только что созданной строки.  
  
## <a name="remarks"></a>Примечания  
 Если строка существует, этот метод вызывает метод [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) и возвращает. В противном случае он выделяет новый экземпляр переменной шаблона RowClass и добавляет его в [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)