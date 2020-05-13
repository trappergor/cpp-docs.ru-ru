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
ms.openlocfilehash: 6453156a59b73bcb06c7c86920e1dc524874cef8
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168544"
---
# <a name="_atlcreatewnddata-structure"></a>Структура _AtlCreateWndData

Эта структура содержит данные экземпляра класса в коде окна в ATL.

## <a name="syntax"></a>Синтаксис

```cpp
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>Участники

`m_pThis`<br/>
**Этот** указатель используется для получения доступа к экземпляру класса в процедурах окна.

`m_dwThreadID`<br/>
Идентификатор потока текущего экземпляра класса.

`m_pNext`<br/>
Указатель на следующий `_AtlCreateWndData` объект.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)
