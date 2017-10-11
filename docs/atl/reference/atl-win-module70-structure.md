---
title: "Структура _ATL_WIN_MODULE70 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 7f521b418b7d179eb506a5e9df2887addec059ef
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="atlwinmodule70-structure"></a>Структура _ATL_WIN_MODULE70
Использовать в коде над окнами в ATL.  
  
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
 Используется для привязки windows в объекты. Используется внутренними механизмами ATL.  
  
 **m_rgWindowClassAtoms**  
 Используется для отслеживания регистрации класса окна, чтобы их можно было правильно отменена при завершении. Используется внутренними механизмами ATL.  
  
## <a name="remarks"></a>Примечания  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) определяется как typedef из `_ATL_WIN_MODULE70`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Структуры](../../atl/reference/atl-structures.md)






