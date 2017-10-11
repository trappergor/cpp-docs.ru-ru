---
title: "Структура _ATL_MODULE70 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 104596d55ee2580cbee3cfc916ad9ef7390ce4c1
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
  
## <a name="members"></a>Члены  
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








