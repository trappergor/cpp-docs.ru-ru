---
title: "Структура _AtlCreateWndData | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs: C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a5b0811e88188bb29ef3153f739804cbdac66083
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
  
## <a name="members"></a>Члены  
 **m_pThis**  
 **Это** указатель используется для получения доступа к экземпляру класса в процедуры окна.  
  
 `m_dwThreadID`  
 Идентификатор потока текущего экземпляра класса.  
  
 **m_pNext**  
 Указатель на следующий `_AtlCreateWndData` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Структуры](../../atl/reference/atl-structures.md)





