---
title: "CAccessorBase::GetHAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs:
- C++
helpviewer_keywords:
- GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a078ddcbeffc96af35274746de8f052cc6c38810
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
Извлекает дескриптор метода доступа, указанного метода доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      HACCESSOR GetHAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>Параметры  
 `nAccessor`  
 [in] Номер нуля смещение для метода доступа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метода доступа.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CAccessorBase](../../data/oledb/caccessorbase-class.md)