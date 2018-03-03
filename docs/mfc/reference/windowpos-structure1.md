---
title: "WINDOWPOS Structure1 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7db3991a6767e33c73857daf40a977ac5f6f0b85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="windowpos-structure1"></a>WINDOWPOS Structure1
`WINDOWPOS` Структура содержит сведения о размере и положение окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagWINDOWPOS { /* wp */  
    HWND hwnd;  
    HWND hwndInsertAfter;  
    int x;  
    int y;  
    int cx;  
    int cy;  
    UINT flags;  
} WINDOWPOS;  
```  
  
#### <a name="parameters"></a>Параметры  
 *HWND*  
 Идентифицирует окно.  
  
 *hwndInsertAfter*  
 Идентифицирует окно, за которым помещается в этом окне.  
  
 *x*  
 Задает позицию левого края окна.  
  
 *y*  
 Задает положение правого края окна.  
  
 `cx`  
 Ширина окна в пикселях.  
  
 `cy`  
 Высота окна в пикселях.  
  
 `flags`  
 Указывает параметры позиционирования окна. Этот член может принимать одно из следующих значений:  
  
- **SWP_DRAWFRAME** рисует вокруг окна фрейма (определяется в описании класса окна). Получает окно `WM_NCCALCSIZE` сообщения.  
  
- **SWP_FRAMECHANGED** отправляет `WM_NCCALCSIZE` сообщение в окно, даже если не изменяется размер окна. Если этот флаг не указан, `WM_NCCALCSIZE` отправляется только при изменении размера окна.  
  
- **SWP_HIDEWINDOW** скрывает окно.  
  
- `SWP_NOACTIVATE`Не активирует окно.  
  
- **SWP_NOCOPYBITS** удаляет все содержимое клиентской области. Если этот флаг не указан, сохраняются и скопированы обратно в клиентской области после размера или положения окна допустимое содержимое клиентской области.  
  
- `SWP_NOMOVE`Сохраняет текущую позицию (не учитывает **x** и **y** членов).  
  
- **SWP_NOOWNERZORDER** не меняет позицию окна-владельца в Z-порядке.  
  
- `SWP_NOSIZE`Сохраняет текущий размер (не учитывает **cx** и **cy** членов).  
  
- **SWP_NOREDRAW** не перерисовывает изменения.  
  
- **SWP_NOREPOSITION** то же, что **SWP_NOOWNERZORDER**.  
  
- **SWP_NOSENDCHANGING** предотвращает получение окна `WM_WINDOWPOSCHANGING` сообщения.  
  
- `SWP_NOZORDER`Сохраняет текущий порядок (не учитывает **hwndInsertAfter** члена).  
  
- **SWP_SHOWWINDOW** Отображение окна.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

