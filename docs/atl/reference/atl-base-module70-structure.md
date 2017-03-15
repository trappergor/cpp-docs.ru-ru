---
title: "Структура _ATL_BASE_MODULE70 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
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
ms.sourcegitcommit: 347e7bf7cd9173fb2815f44fc052ec23ab4055a6
ms.openlocfilehash: 7456d441d7b3fb74f404f29c893c492feab10ed9
ms.lasthandoff: 02/24/2017

---
# <a name="atlbasemodule70-structure"></a>Структура _ATL_BASE_MODULE70
Используемые любого проекта, использующего библиотеки ATL.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```  
  
## <a name="members"></a>Члены  
 `cbSize`  
 Размер структуры, используемые для управления версиями.  
  
 `m_hInst`  
 **HInstance** для этого модуля (exe или dll).  
  
 `m_hInstResource`  
 По умолчанию экземпляр обработчика ресурсов.  
  
 **m_bNT5orWin98**  
 Сведения о версии операционной системы. Используется внутренними механизмами ATL.  
  
 **dwAtlBuildVer**  
 Сохраняет версию библиотеки ATL. В настоящее время 0x0700.  
  
 **pguidVer**  
 ATL внутренний идентификатор GUID.  
  
 **m_csResource**  
 Используется для синхронизации доступа к **m_rgResourceInstance** массива. Используется внутренними механизмами ATL.  
  
 **m_rgResourceInstance**  
 Массив, используемый для поиска ресурсов в экземпляры ресурсов, которых известно ATL. Используется внутренними механизмами ATL.  
  
## <a name="remarks"></a>Примечания  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) определяется как typedef для `_ATL_BASE_MODULE70`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
## <a name="see-also"></a>См. также  
 [Структуры](../../atl/reference/atl-structures.md)






