---
title: "Структура NCCALCSIZE_PARAMS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NCCALCSIZE_PARAMS
dev_langs: C++
helpviewer_keywords: NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76a0a16ff0a2c90c6dd6060badc2c79dde1af231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nccalcsizeparams-structure"></a>Структура NCCALCSIZE_PARAMS
`NCCALCSIZE_PARAMS` Структура содержит сведения, которые приложение может использовать при обработке `WM_NCCALCSIZE` сообщения, чтобы вычислить размер, положение и допустимое содержимое клиентской области окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>Параметры  
 *rgrc*  
 Указывает массив прямоугольников. Первый содержит новые координаты, перемещении или изменении размера окна. Второй содержит координаты окна, прежде чем он был перемещен или изменения размера. Третий содержит координаты клиентской области окна, прежде чем он был перемещен или изменения размера. Если окно дочернего окна, координаты указываются относительно клиентской области родительского окна. Если окно является окном верхнего уровня, координаты указываются относительно экрана.  
  
 *lppos*  
 Указывает на [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) структура, содержащая значения размеров и положения, указанный в операции, вызвавшей можно перемещать и изменять размер окна.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

