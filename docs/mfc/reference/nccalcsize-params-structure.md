---
title: "Структура NCCALCSIZE_PARAMS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NCCALCSIZE_PARAMS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NCCALCSIZE_PARAMS - структура"
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Структура NCCALCSIZE_PARAMS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

 `NCCALCSIZE_PARAMS` Структура содержит сведения, которые приложение может использовать при обработке `WM_NCCALCSIZE` сообщений для расчета размера, положения и допустимое содержимое клиентской области окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 
    typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>Параметры  
 *rgrc*  
 Указывает массив прямоугольников. Первый содержит новые координаты, перемещении или изменении размера окна. Второй содержит координаты окна, прежде чем он был перемещен или изменении размера. Третий содержит координаты клиентской области окна, прежде чем он был перемещен или изменении размера. Если окно дочернего окна, координаты указываются относительно клиентской области родительского окна. Если окно является окном верхнего уровня, координаты указываются относительно экрана.  
  
 *lppos*  
 Указывает [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) Структура, содержащая значения размеров и положения, указанный в операции, вызвавшей окно закреплены.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../Topic/CWnd%20Class.md#OnNcCalcSize)

