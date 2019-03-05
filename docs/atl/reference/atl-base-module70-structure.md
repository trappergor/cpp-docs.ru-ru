---
title: Структура _ATL_BASE_MODULE70
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
ms.openlocfilehash: 4fddd4b3af6155d0663b9c01edfab4fcf4a60426
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261466"
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

`cbSize`<br/>
Размер структуры, используемые для управления версиями.

`m_hInst`<br/>
`hInstance` Для этого модуля (exe или dll).

`m_hInstResource`<br/>
Дескриптор ресурса для экземпляра по умолчанию.

`m_bNT5orWin98`<br/>
Сведения о версии операционной системы. Используется системой ATL.

`dwAtlBuildVer`<br/>
Хранит версию библиотеки ATL. В настоящее время 0x0700.

`pguidVer`<br/>
Внутренний идентификатор GUID библиотеки ATL.

`m_csResource`<br/>
Используется для синхронизации доступа к `m_rgResourceInstance` массива. Используется системой ATL.

`m_rgResourceInstance`<br/>
Массив, используемый для поиска ресурсов во всех экземплярах ресурсов, из которых известно ATL. Используется системой ATL.

## <a name="remarks"></a>Примечания

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) определяется как typedef типа _ATL_BASE_MODULE70.

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)
