---
title: RECT Structure1 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b61c794b8fa383eeea62459a5a83948ef2efe10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
  
## <a name="members"></a>Участники  
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
