---
title: Структура _ATL_MODULE70
ms.date: 11/04/2016
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
ms.openlocfilehash: d05683383fab64f027f198d49bfbf42aa593d582
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263433"
---
# <a name="atlmodule70-structure"></a>Структура _ATL_MODULE70

Содержит данные, используемые каждого модуля ATL.

## <a name="syntax"></a>Синтаксис

```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```

## <a name="members"></a>Члены

`cbSize`<br/>
Размер структуры, используемые для управления версиями.

`m_nLockCnt`<br/>
Чтобы определить, как долго должны оставаться активным модуль счетчика ссылок.

`m_pTermFuncs`<br/>
Отслеживает функции, которые были зарегистрированы для вызова при закрытии ATL.

`m_csStaticDataInitAndTypeInfo`<br/>
Используется для управления доступом к внутренним данным в многопоточной ситуации.

## <a name="remarks"></a>Примечания

[_ATL_MODULE](atl-typedefs.md#_atl_module) определяется как typedef типа `_ATL_MODULE70`.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)
