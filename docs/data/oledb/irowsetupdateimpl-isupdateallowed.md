---
title: "IRowsetUpdateImpl::IsUpdateAllowed | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs:
- C++
helpviewer_keywords:
- IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4744e6f5be9c9b535c7359b615a5195c6da33fd9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
Переопределите этот метод для проверки безопасности, целостность и так далее до обновления.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */);  
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