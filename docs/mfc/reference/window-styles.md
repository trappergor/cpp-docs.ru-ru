---
title: "Стили окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WS_MINIMIZEBOX
- WS_SIZEBOX
- WS_CLIPCHILDREN
- WS_TILED
- WS_GROUP
- WS_VSCROLL
- WS_CHILD
- WS_TABSTOP
- WS_HSCROLL
- WS_THICKFRAME
- WS_DISABLED
- WS_POPUP
- WS_ICONIC
- WS_MAXIMIZE
- WS_VISIBLE
- WS_POPUPWINDOW
- WS_TILEDWINDOW
- WS_DLGFRAME
- WS_MINIMIZE
- WS_CAPTION
- WS_OVERLAPPED
- WS_BORDER
- WS_MAXIMIZEBOX
- WS_OVERLAPPEDWINDOW
- WS_SYSMENU
- WS_CHILDWINDOW
- WS_CLIPSIBLINGS
dev_langs:
- C++
helpviewer_keywords:
- WS_THICKFRAME constant
- WS_TILEDWINDOW constant
- WS_MAXIMIZEBOX constant
- WS_DLGFRAME constant
- WS_CHILDWINDOW constant
- window styles, in MFC
- WS_CHILD constant
- WS_GROUP constant
- WS_MINIMIZE constant
- WS_CAPTION constant
- WS_MAXIMIZE constant
- WS_POPUP constant
- WS_SYSMENU constant
- WS_TILED constant
- window styles
- WS_POPUPWINDOW constant
- WS_CLIPSIBLINGS constant
- WS_BORDER constant
- WS_DISABLED constant
- WS_VSCROLL constant
- WS_OVERLAPPED constant
- WS_MINIMIZEBOX constant
- WS_VISIBLE constant
- WS_OVERLAPPEDWINDOW constant
- WS_TABSTOP constant
- WS_ICONIC constant
- WS_SIZEBOX constant
- WS_HSCROLL constant
- WS_CLIPCHILDREN constant
- styles, windows
ms.assetid: c85ffbe4-f4ff-4227-917a-48ec4a411842
caps.latest.revision: 12
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
ms.openlocfilehash: d814e3a10132fb3fe88969ce434f8286b02afba5
ms.lasthandoff: 02/24/2017

---
# <a name="window-styles"></a>Стили окна
-   `WS_BORDER`Создает границу окна.  
  
-   **WS_CAPTION** создает окно, которое имеет заголовок (подразумевает `WS_BORDER` стиль). Нельзя использовать с **WS_DLGFRAME** стиль.  
  
-   **WS_CHILD** создает дочернего окна. Нельзя использовать с `WS_POPUP` стиль.  
  
-   **WS_CHILDWINDOW** как **WS_CHILD** стиль.  
  
-   **WS_CLIPCHILDREN** исключает область, занимаемая дочерних окон, при рисовании в родительском окне. Используется при создании родительского окна.  
  
-   **WS_CLIPSIBLINGS** клипов дочерние окна относительно друг друга, то есть когда конкретного дочернего окна получает сообщения рисования, **WS_CLIPSIBLINGS** стиль отсекает всех остальных перекрывающихся дочерних окон за пределы области дочернее окно обновления. (Если **WS_CLIPSIBLINGS** не указан и дочерние окна перекрывают друг друга, при рисовании в клиентской области дочернего окна, можно нарисовать в клиентской области соседних дочернего окна.) Для использования с **WS_CHILD** только стиля.  
  
-   **WS_DISABLED** создает окно, которое первоначально будет отключено.  
  
-   **WS_DLGFRAME** создает окно с двойной границей, но без заголовка.  
  
-   **WS_GROUP** определяет первый элемент группы элементов управления, в которых пользователь может перемещать из одного элемента управления к другому с помощью клавиш со стрелками. Все элементы управления, определенные с помощью **WS_GROUP** стиль **FALSE** после первого элемента управления относятся к той же группе. Следующий элемент управления с **WS_GROUP** стиля начинается следующей группы (то есть одна группа заканчивается начинается следующий).  
  
-   **WS_HSCROLL** создает окно, которое имеет горизонтальную полосу прокрутки.  
  
-   **WS_ICONIC** создает окно, которое изначально свернуто. То же, что **WS_MINIMIZE** стиля.  
  
-   **WS_MAXIMIZE** создает окно максимальный размер.  
  
-   **WS_MAXIMIZEBOX** создает окно, которое есть кнопка развертывания.  
  
-   **WS_MINIMIZE** создает окно, которое изначально свернуто. Для использования с **WS_OVERLAPPED** только стиля.  
  
-   **WS_MINIMIZEBOX** создает окно с кнопкой "Свернуть".  
  
-   **WS_OVERLAPPED** создает перекрывающихся окон. Перекрывающиеся окна обычно имеет заголовок и границы.  
  
-   **WS_OVERLAPPEDWINDOW** создает окно с перекрытием **WS_OVERLAPPED**, **WS_CAPTION**, **WS_SYSMENU**, **WS_THICKFRAME**, **WS_MINIMIZEBOX**, и **WS_MAXIMIZEBOX** стили.  
  
-   `WS_POPUP`Создает всплывающее окно. Нельзя использовать с **WS_CHILD** стиль.  
  
-   **WS_POPUPWINDOW** создает всплывающее окно с `WS_BORDER`, `WS_POPUP`, и **WS_SYSMENU** стили. **WS_CAPTION** стиля должны быть объединены с **WS_POPUPWINDOW** стиль для отображения элемента управления меню.  
  
-   **WS_SIZEBOX** создает окно, которое имеет границы для изменения размера. То же, что **WS_THICKFRAME** стиль.  
  
-   **WS_SYSMENU** создает окно, которое имеется поле элемента управления меню в своем заголовке. Используется только для windows с помощью заголовков.  
  
-   **WS_TABSTOP** указывает один из любого количества элементов, по которым можно перемещаться с помощью клавиши TAB. Пользователь перемещается клавишей TAB к следующему элементу управления, определяемое **WS_TABSTOP** стиль.  
  
-   **WS_THICKFRAME** создает окно с толстой кадра, который может использоваться для изменения размеров окна.  
  
-   **WS_TILED** создает перекрывающихся окон. Перекрывающиеся окна имеет заголовок и границы. То же, что **WS_OVERLAPPED** стиль.  
  
-   **WS_TILEDWINDOW** создает окно с перекрытием **WS_OVERLAPPED**, **WS_CAPTION**, **WS_SYSMENU**, **WS_THICKFRAME**, **WS_MINIMIZEBOX**, и **WS_MAXIMIZEBOX** стили. То же, что **WS_OVERLAPPEDWINDOW** стиль.  
  
-   **WS_VISIBLE** создает окно, которое изначально является видимым.  
  
-   **WS_VSCROLL** создает окно, которое имеет вертикальную полосу прокрутки.  
  
## <a name="see-also"></a>См. также  
 [Стили, используемые MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)   
 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)   
 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)


