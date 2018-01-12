---
title: "IRowsetUpdateImpl::IsUpdateAllowed | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs: C++
helpviewer_keywords: IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 312d0488afc73d38ebd1ceb8a3f4334468607ed9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
Переопределите этот метод для проверки безопасности, целостность и так далее до обновления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT IsUpdateAllowed(  
   DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *status*  
 [in] Состояние отложенных операций в строках.  
  
 *hRowUpdate*  
 [in] Дескриптор строки, которые пользователю требуется обновить.  
  
 *pRowStatus*  
 [out] Состояние возврата пользователю.  
  
## <a name="remarks"></a>Примечания  
 Если выяснилось, что следует разрешить обновления, возвращает `S_OK`; в противном случае возвращает **E_FAIL**. Если разрешить обновления, необходимо также задать **DBROWSTATUS** в [IRowsetUpdateImpl::Update](../../data/oledb/irowsetupdateimpl-update.md) — соответствующую [состоянием строк](https://msdn.microsoft.com/en-us/library/ms722752.aspx).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)