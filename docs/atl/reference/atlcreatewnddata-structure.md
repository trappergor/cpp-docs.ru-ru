---
title: Структура _AtlCreateWndData | Документы Microsoft
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
ms.openlocfilehash: 66388c12def72a9da5b5aeb7e4713ca61c23a6e0
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255799"
---
# <a name="atlcreatewnddata-structure"></a>Структура _AtlCreateWndData
Эта структура содержит данные экземпляра класса в коде над окнами в ATL  
  
## <a name="syntax"></a>Синтаксис  
  
```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```  
  
## <a name="members"></a>Участники  
 **m_pThis**  
 **Это** указатель используется для получения доступа к экземпляру класса в процедуры окна.  
  
 `m_dwThreadID`  
 Идентификатор потока текущего экземпляра класса.  
  
 **m_pNext**  
 Указатель на следующий `_AtlCreateWndData` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Классы и структуры](../../atl/reference/atl-classes.md)





