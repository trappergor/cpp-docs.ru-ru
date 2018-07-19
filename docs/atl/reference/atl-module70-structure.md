---
title: Структура _ATL_MODULE70 | Документация Майкрософт
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
ms.openlocfilehash: 9666d73eec770ff8231e5730e01520b0bee68012
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886223"
---
# <a name="atlmodule70-structure"></a>Структура _ATL_MODULE70
Содержит данные, используемые каждого модуля ATL.  
  
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
  
 `m_pTermFuncs`  
 Отслеживает функции, которые были зарегистрированы для вызова при закрытии ATL.  
  
 `m_csStaticDataInitAndTypeInfo`  
 Используется для управления доступом к внутренним данным в многопоточной ситуации.  
  
## <a name="remarks"></a>Примечания  
 [_ATL_MODULE](atl-typedefs.md#_atl_module) определяется как typedef типа `_ATL_MODULE70`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
  [Классы и структуры](../../atl/reference/atl-classes.md)







