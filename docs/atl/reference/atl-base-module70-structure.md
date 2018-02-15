---
title: "Структура _ATL_BASE_MODULE70 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f711621188cffb739fe6895af3b222993c84576c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70 Structure
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
 [Структуры](../../atl/reference/atl-structures.md)





