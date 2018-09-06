---
title: Структура _ATL_BASE_MODULE70 | Документация Майкрософт
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
ms.openlocfilehash: fb7218d7fc8886cffdcce13f09a682fdc635f84f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759932"
---
# <a name="atlbasemodule70-structure"></a>Структура _ATL_BASE_MODULE70

Используемые любого проекта, которое использует ATL.

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
`hInstance` Для этого модуля (exe или dll).

`m_hInstResource`  
Дескриптор ресурса для экземпляра по умолчанию.

`m_bNT5orWin98`  
Сведения о версии операционной системы. Используется системой ATL.

`dwAtlBuildVer`  
Хранит версию библиотеки ATL. В настоящее время 0x0700.

`pguidVer`  
Внутренний идентификатор GUID библиотеки ATL.

`m_csResource`  
Используется для синхронизации доступа к `m_rgResourceInstance` массива. Используется системой ATL.

`m_rgResourceInstance`  
Массив, используемый для поиска ресурсов во всех экземплярах ресурсов, из которых известно ATL. Используется системой ATL.

## <a name="remarks"></a>Примечания

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) определяется как typedef типа _ATL_BASE_MODULE70.

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)

