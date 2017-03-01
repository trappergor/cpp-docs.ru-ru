---
title: "Структура NCCALCSIZE_PARAMS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 88c25fd5e5862d5f0954ae853442c66eaf7320c8
ms.lasthandoff: 02/24/2017

---
# <a name="nccalcsizeparams-structure"></a>Структура NCCALCSIZE_PARAMS
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
 Указывает [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) структура, содержащая значения размеров и положения, указанный в операции, вызвавшей окно закреплены.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)


