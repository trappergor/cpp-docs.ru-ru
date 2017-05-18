---
title: "Структура MINMAXINFO | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 772416bdac3c72f55644fa31aef23ba76a14e606
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="minmaxinfo-structure"></a>Структура MINMAXINFO
`MINMAXINFO` Структура содержит сведения об окне развернутого размеров и положения его отслеживания минимальный и максимальный размер.  
  
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
 Задает ширину развернутого (point.x) и развернутом высоту окна (point.y).  
  
 `ptMaxPosition`  
 Задает позицию левого края развернутого окна (point.x) и положение верхнего края развернутого окна (point.y).  
  
 *ptMinTrackSize*  
 Указывает минимальную отслеживаемую ширину (point.x) и Минимальная отслеживаемая высота окна (point.y).  
  
 *ptMaxTrackSize*  
 Указывает максимально отслеживаемую ширину (point.x) и максимальным отслеживаемую высоту (point.y) окна.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)


