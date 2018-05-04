---
title: Структура _ATL_MODULE70 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f189ef58ab83a6e77852c109e6da3ae86dc5555d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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







