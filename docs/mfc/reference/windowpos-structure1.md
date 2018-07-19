---
title: WINDOWPOS Structure1 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db51e8f9924d69406989b3a9ac12b45f0e55e870
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885966"
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
 Определяет окно, за которым помещается в этом окне.  
  
 *x*  
 Задает положение левого края окна.  
  
 *y*  
 Задает положение правой границы окна.  
  
 *CX*  
 Ширина окна в пикселях.  
  
 *CY*  
 Высота окна в пикселях.  
  
 *flags*  
 Указывает параметры размещения окна. Этот член может принимать одно из следующих значений:  
  
- SWP_DRAWFRAME рисует кадр (определенной в описании класса окна) вокруг окна. Окно получает сообщение WM_NCCALCSIZE.  
  
- Отправляет SWP_FRAMECHANGED WM_NCCALCSIZE сообщения в окно, даже если размер окна не изменяется. Если этот флаг не задан, WM_NCCALCSIZE отправляется только в том случае, при изменении размера окна.  
  
- SWP_HIDEWINDOW скрывает окно.  
  
- SWP_NOACTIVATE не активирует окно.  
  
- SWP_NOCOPYBITS удаляет все содержимое клиентской области. Если этот флаг не задан, сохраняются и скопировать обратно в клиентской области после размера или положения окна допустимое содержимое клиентской области.  
  
- Сохраняет SWP_NOMOVE текущей позиции (игнорирует `x` и `y` членов).  
  
- SWP_NOOWNERZORDER не меняет позицию для окна-владельца в Z-порядке.  
  
- SWP_NOSIZE сохраняет текущий размер (игнорирует `cx` и `cy` членов).  
  
- SWP_NOREDRAW не будут перерисовываться изменения.  
  
- SWP_NOREPOSITION совпадение с кодом SWP_NOOWNERZORDER.  
  
- SWP_NOSENDCHANGING предотвращает получение WM_WINDOWPOSCHANGING сообщения окна.  
  
- Текущую систему заказа на сохраняет SWP_NOZORDER (игнорирует `hwndInsertAfter` член).  
  
- SWP_SHOWWINDOW Отображение окна.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

