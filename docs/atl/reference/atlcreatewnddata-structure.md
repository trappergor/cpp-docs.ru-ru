---
title: _AtlCreateWndData Structure
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: d6e3168b5c86de5bce3c3b9d3b0fbdea28ae604f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57286932"
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData Structure

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
