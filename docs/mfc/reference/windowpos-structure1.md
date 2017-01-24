---
title: "Структура WINDOWPOS | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WINDOWPOS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WINDOWPOS - структура"
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура WINDOWPOS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `WINDOWPOS` содержит сведения о размере и положения окна.  
  
## Синтаксис  
  
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
  
#### Параметры  
 *hwnd*  
 Определяет окно.  
  
 *hwndInsertAfter*  
 Определяет окно за которым данное окно помещается.  
  
 *x*  
 Задает положение левого края окна.  
  
 *y*  
 Задает положение правого края окна.  
  
 `cx`  
 Задает ширину окна, в пикселях.  
  
 `cy`  
 Задает высоту окна, в пикселях.  
  
 `flags`  
 Определяет параметры размещения окна.  Этот элемент может быть одним из следующих значений:  
  
-   **SWP\_DRAWFRAME** рисуется кадр \(указанного в описании класса для окна\) вокруг окна.  Окно получает сообщение `WM_NCCALCSIZE`.  
  
-   **SWP\_FRAMECHANGED** отправляет сообщение `WM_NCCALCSIZE` в окно, даже если не изменить размер окна.  Если этот флажок не указан, то `WM_NCCALCSIZE` отправляется только при изменении размера окна.  
  
-   **SWP\_HIDEWINDOW** скрывает окно.  
  
-   `SWP_NOACTIVATE` не активирует окно.  
  
-   **SWP\_NOCOPYBITS** отменяет все содержимое клиентской области.  Если этот флажок не указан, то допустимые содержимое клиентской области сохраняются и копируются назад в клиентскую область после изменения размера или перемещении окно.  
  
-   `SWP_NOMOVE` сохраняет текущее положение \(пропускает элементы **x** и **y** \).  
  
-   Метод **SWP\_NOOWNERZORDER** не меняет положение окна " в соответствии с z\-порядком.  
  
-   `SWP_NOSIZE` сохраняет текущий размер \(пропускает элементы **cx** и **cy** \).  
  
-   **SWP\_NOREDRAW** redraw изменения.  
  
-   **SWP\_NOREPOSITION** так же, как **SWP\_NOOWNERZORDER**.  
  
-   **SWP\_NOSENDCHANGING** предотвращает окно из получении сообщения `WM_WINDOWPOSCHANGING`.  
  
-   `SWP_NOZORDER` сохраняется порядок текущего игнорирует член \( **hwndInsertAfter** \).  
  
-   Отображение окна **SWP\_SHOWWINDOW**.  
  
## Требования  
 **Header:** winuser.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)