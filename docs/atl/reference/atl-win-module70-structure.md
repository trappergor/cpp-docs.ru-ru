---
title: "Структура _ATL_WIN_MODULE70 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4e393abb2a904a0f5e101efe3d78d0645664397b
ms.openlocfilehash: 383384c8f08b98592f92b5d38850137c1c0c6d54
ms.lasthandoff: 02/24/2017

---
# <a name="atlwinmodule70-structure"></a>Структура _ATL_WIN_MODULE70
Используемый код управления окнами в ATL.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize; 
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```  
  
## <a name="members"></a>Члены  
 `cbSize`  
 Размер структуры, используемые для управления версиями.  
  
 `m_csWindowCreate`  
 Используется для сериализации доступа к коду окно регистрации. Используется внутренними механизмами ATL.  
  
 **m_pCreateWndList**  
 Используется для привязки windows их объекты. Используется внутренними механизмами ATL.  
  
 **m_rgWindowClassAtoms**  
 Используется для отслеживания регистрации класса окна, чтобы их можно было правильно удалена при завершении. Используется внутренними механизмами ATL.  
  
## <a name="remarks"></a>Примечания  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) определяется как typedef для `_ATL_WIN_MODULE70`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Структуры](../../atl/reference/atl-structures.md)






