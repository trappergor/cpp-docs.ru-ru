---
title: Структура MINMAXINFO | Документация Майкрософт
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
ms.openlocfilehash: cf9a6e6a1397b9361df5372af09be8e61d997e62
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337818"
---
# <a name="minmaxinfo-structure"></a>Структура MINMAXINFO
`MINMAXINFO` Структура содержит сведения о размер развернутого окна и его отслеживания минимального и максимального размера и положения.  
  
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
 Указывает ширину развернутого (point.x) и высоту развернутого (point.y) окна.  
  
 *ptMaxPosition*  
 Указывает положение левой части развернутого окна (point.x) и положение верхней части развернутого окна (point.y).  
  
 *ptMinTrackSize*  
 Указывает минимальную отслеживаемую ширину (point.x) и Минимальная отслеживаемая высота окна (point.y).  
  
 *ptMaxTrackSize*  
 Указывает максимально отслеживаемая ширина (point.x) и максимально отслеживаемую высоту окна (point.y).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

