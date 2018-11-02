---
title: Структура _AtlCreateWndData
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: 860d5772279d0ca0581a8cac1e0ef224f829586d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534190"
---
# <a name="atlcreatewnddata-structure"></a>Структура _AtlCreateWndData

Эта структура содержит данные экземпляра класса в коде управления окнами в ATL

## <a name="syntax"></a>Синтаксис

```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>Участники

`m_pThis`<br/>
**Это** указатель, используемый для получения доступа к экземпляру класса в процедуры окна.

`m_dwThreadID`<br/>
Идентификатор текущего экземпляра класса.

`m_pNext`<br/>
Указатель на следующий `_AtlCreateWndData` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)

