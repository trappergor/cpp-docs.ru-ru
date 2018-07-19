---
title: Структура NCCALCSIZE_PARAMS | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 095b66af9dab08e3d8fad040c43e2eaf8d2beb81
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335647"
---
# <a name="nccalcsizeparams-structure"></a>Структура NCCALCSIZE_PARAMS
`NCCALCSIZE_PARAMS` Структура содержит сведения, что приложение может использовать при обработке сообщения WM_NCCALCSIZE для расчета размера, положения и допустимое содержимое клиентской области окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>Параметры  
 *rgrc*  
 Указывает массив прямоугольников. Первый содержит новые координаты, перемещения или изменения размера окна. Второй содержит координаты окна, прежде чем он был перемещен или изменении размера. Третий содержит координаты клиентской области окна, прежде чем он был перемещен или изменении размера. Если окно дочернего окна, координаты указываются относительно клиентской области родительского окна. Если окно является окном верхнего уровня, координаты указываются относительно экрана.  
  
 *lppos*  
 Указывает на [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) структуру, содержащую размер и положение значения, указанные в операции, которая вызвала окне, чтобы быть перемещения или изменения размера.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

