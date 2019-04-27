---
title: Структура _ATL_WIN_MODULE70
ms.date: 11/04/2016
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
ms.openlocfilehash: 0b636d328852daf821269230aae443cef084578b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260757"
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

`cbSize`<br/>
Размер структуры, используемые для управления версиями.

`m_csWindowCreate`<br/>
Используется для сериализации доступа к коду окно регистрации. Используется системой ATL.

`m_pCreateWndList`<br/>
Используется для привязки windows к соответствующим объектам. Используется системой ATL.

`m_rgWindowClassAtoms`<br/>
Используется для отслеживания регистрации класса окна, чтобы можно было правильно отменить регистрацию при завершении. Используется системой ATL.

## <a name="remarks"></a>Примечания

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) определяется как typedef типа `_ATL_WIN_MODULE70`.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)
