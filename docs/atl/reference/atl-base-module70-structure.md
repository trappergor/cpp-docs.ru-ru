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
ms.openlocfilehash: a8ee35df4b6ee792cd91f1b294259544e8944509
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089051"
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

