---
title: Структура MINMAXINFO | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12161938f96e5044ae48f9eb5cf380fbc3840d3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="minmaxinfo-structure"></a>Структура MINMAXINFO
`MINMAXINFO` Структура содержит сведения о окна исходного размера и положения его отслеживания минимальный и максимальный размер.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagMINMAXINFO {  
    POINT ptReserved;  
    POINT ptMaxSize;  
    POINT ptMaxPosition;  
    POINT ptMinTrackSize;  
    POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### <a name="parameters"></a>Параметры  
 *ptReserved*  
 Зарезервировано для внутреннего использования.  
  
 *ptMaxSize*  
 Указывает ширину развернутого (point.x) и максимальная высота окна (point.y).  
  
 `ptMaxPosition`  
 Задает позицию левого края развернутого окна (point.x) и положение верхнего края развернутого окна (point.y).  
  
 *ptMinTrackSize*  
 Указывает минимальную отслеживаемую ширину (point.x) и Минимальная отслеживаемая высота окна (point.y).  
  
 *ptMaxTrackSize*  
 Указывает максимально отслеживаемую ширину (point.x) и максимально отслеживаемую высоту (point.y) окна.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

