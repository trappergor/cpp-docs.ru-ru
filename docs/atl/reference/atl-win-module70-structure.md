---
title: Структура _ATL_WIN_MODULE70 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4c5d7ad570d9745e10107f0df09faccd9eb42e3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761557"
---
# <a name="atlwinmodule70-structure"></a>Структура _ATL_WIN_MODULE70

Используется кодом Управление окнами в ATL

## <a name="syntax"></a>Синтаксис

```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize; 
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```

## <a name="members"></a>Участники

`cbSize`  
Размер структуры, используемые для управления версиями.

`m_csWindowCreate`  
Используется для сериализации доступа к коду окно регистрации. Используется системой ATL.

`m_pCreateWndList`  
Используется для привязки windows к соответствующим объектам. Используется системой ATL.

`m_rgWindowClassAtoms`  
Используется для отслеживания регистрации класса окна, чтобы можно было правильно отменить регистрацию при завершении. Используется системой ATL.

## <a name="remarks"></a>Примечания

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) определяется как typedef типа `_ATL_WIN_MODULE70`.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)

