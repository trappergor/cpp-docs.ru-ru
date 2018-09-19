---
title: Структура _AtlCreateWndData | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71c0fb14574aedb74d756e72a93cd0dc626ba086
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057383"
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

