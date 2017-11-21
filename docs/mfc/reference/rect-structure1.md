---
title: "RECT Structure1 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPRECT
- RECT
dev_langs: C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d3a33330ace97db19521362384356b58a6c8dca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="rect-structure1"></a>RECT Structure1
`RECT` Структура определяет координаты верхнего левого и правого нижнего углов прямоугольника.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagRECT {  
    LONG left;  
    LONG top;  
    LONG right;  
    LONG bottom;  
} RECT;  
```  
  
## <a name="members"></a>Члены  
 `left`  
 Указывает Координата по оси x верхнего левого угла прямоугольника.  
  
 `top`  
 Задает координату y верхнего левого угла прямоугольника.  
  
 `right`  
 Указывает Координата по оси x нижнего правого угла прямоугольника.  
  
 `bottom`  
 Указывает Координата по оси y нижнего правого угла прямоугольника.  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** windef.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CRect](../../atl-mfc-shared/reference/crect-class.md)
