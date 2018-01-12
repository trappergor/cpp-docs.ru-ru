---
title: "Структура _ATL_MODULE70 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs: C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8122f733282fa819c3d789a90e60171ee006e27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="atlmodule70-structure"></a>Структура _ATL_MODULE70
Содержит данные, используемые каждый модуль ATL.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```  
  
## <a name="members"></a>Участники  
 `cbSize`  
 Размер структуры, используемые для управления версиями.  
  
 `m_nLockCnt`  
 Чтобы определить, как долго должны оставаться активным модуль счетчика ссылок.  
  
 **m_pTermFuncs**  
 Отслеживает функции, которые были зарегистрированы для вызова при закрытии ATL.  
  
 **m_csStaticDataInitAndTypeInfo**  
 Используется для управления доступом к внутренним данным в многопоточных ситуациях.  
  
## <a name="remarks"></a>Примечания  
 [_ATL_MODULE](atl-typedefs.md#_atl_module) определяется как typedef из `_ATL_MODULE70`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Структуры](../../atl/reference/atl-structures.md)







