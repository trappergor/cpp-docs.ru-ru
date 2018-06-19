---
title: Структура _ATL_BASE_MODULE70 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 484fc4a68d0421cb12e901b2d56f30e95f6cb79b
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34256422"
---
# <a name="atlbasemodule70-structure"></a>Структура _ATL_BASE_MODULE70
Используются проектом, которое использует ATL.  
  
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
  
## <a name="members"></a>Участники  
 `cbSize`  
 Размер структуры, используемые для управления версиями.  
  
 `m_hInst`  
 **HInstance** для этого модуля (exe или dll).  
  
 `m_hInstResource`  
 Дескриптор ресурса для экземпляра по умолчанию.  
  
 **m_bNT5orWin98**  
 Сведения о версии операционной системы. Используется внутренними механизмами ATL.  
  
 **dwAtlBuildVer**  
 Сохраняет версию библиотеки ATL. В настоящее время 0x0700.  
  
 **pguidVer**  
 ATL внутренний идентификатор GUID.  
  
 **m_csResource**  
 Используется для синхронизации доступа к **m_rgResourceInstance** массива. Используется внутренними механизмами ATL.  
  
 **m_rgResourceInstance**  
 Массив, используемый для поиска ресурсов во всех экземплярах ресурсов, в которых известно ATL. Используется внутренними механизмами ATL.  
  
## <a name="remarks"></a>Примечания  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) определяется как typedef из `_ATL_BASE_MODULE70`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
## <a name="see-also"></a>См. также  
 [Классы и структуры](../../atl/reference/atl-classes.md)





