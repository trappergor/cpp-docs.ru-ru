---
title: ТОЧКА Structure1 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- POINT
- LPPOINT
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure [MFC]
- POINT structure [MFC]
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a31af23b336e5a911b62d23d0cce2795aa66f0f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371909"
---
# <a name="point-structure1"></a>ТОЧКА Structure1
**ТОЧКИ** структура определяет x*-* и координаты y точки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagPOINT {  
    LONG x;  
    LONG y;  
} POINT;  
```  
  
#### <a name="parameters"></a>Параметры  
 *x*  
 Задает координату x точки.  
  
 *y*  
 Задает координату y точки.  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/cpp/point-structure1_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** windef.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CPoint](../../atl-mfc-shared/reference/cpoint-class.md)
