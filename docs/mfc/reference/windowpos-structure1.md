---
title: "WINDOWPOS Structure1 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 11
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
ms.openlocfilehash: 522b15d630c3a5a3593010250db0491601493c69
ms.lasthandoff: 02/24/2017

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
 Определяет окно.  
  
 *hwndInsertAfter*  
 Определяет окно, за который помещается в этом окне.  
  
 *x*  
 Задает позицию левого края окна.  
  
 *y*  
 Задает положение правого края окна.  
  
 `cx`  
 Ширина окна в пикселях.  
  
 `cy`  
 Высота окна в пикселях.  
  
 `flags`  
 Задает параметры размещения окна. Этот член может принимать одно из следующих значений:  
  
- **SWP_DRAWFRAME** рисует вокруг окна фрейма (определенной в описании класса окна). Получает окно `WM_NCCALCSIZE` сообщение.  
  
- **SWP_FRAMECHANGED** отправляет `WM_NCCALCSIZE` сообщения в окне, даже если не изменяется размер окна. Если этот флаг не задан, `WM_NCCALCSIZE` отправляется только при изменении размера окна.  
  
- **SWP_HIDEWINDOW** скрывает окно.  
  
- `SWP_NOACTIVATE`Не активируйте окно.  
  
- **SWP_NOCOPYBITS** удаляет все содержимое клиентской области. Если этот флаг не указан, сохраняются и копируются обратно в клиентской области окна размера или положения допустимое содержимое клиентской области.  
  
- `SWP_NOMOVE`Сохраняет текущую позицию (игнорирует **x** и **y** членов).  
  
- **SWP_NOOWNERZORDER** не изменяет положение окна-владельца в Z-порядке.  
  
- `SWP_NOSIZE`Сохраняет текущий размер (не учитывает **cx** и **cy** членов).  
  
- **SWP_NOREDRAW** не будут перерисовываться изменения.  
  
- **SWP_NOREPOSITION** как **SWP_NOOWNERZORDER**.  
  
- **SWP_NOSENDCHANGING** предотвращает получение окна `WM_WINDOWPOSCHANGING` сообщение.  
  
- `SWP_NOZORDER`Сохраняет текущий порядок (игнорирует **hwndInsertAfter** члена).  
  
- **SWP_SHOWWINDOW** Отображение окна.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)


