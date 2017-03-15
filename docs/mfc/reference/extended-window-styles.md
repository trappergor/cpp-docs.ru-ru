---
title: "Расширенные стили окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WS_EX_TOOLWINDOW
- WS_EX_LEFTSCROLLBAR
- WS_EX_RTLREADING
- WS_EX_WINDOWEDGE
- WS_EX_CLIENTEDGE
- WS_EX_STATICEDGE
- WS_EX_LTRREADING
- WS_EX_DLGMODALFRAME
- WS_EX_RIGHTSCROLLBAR
- WS_EX_CONTROLPARENT
- WS_EX_ACCEPTFILES
- WS_EX_TRANSPARENT
- WS_EX_RIGHT
- WS_EX_APPWINDOW
- WS_EX_TOPMOST
- WS_EX_CONTEXTHELP
- WS_EX_MDICHILD
- WS_EX_LEFT
- WS_EX_OVERLAPPEDWINDOW
- WS_EX_PALETTEWINDOW
- WS_EX_NOPARENTNOTIFY
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_PALETTEWINDOW constant
- WS_EX_NOPARENTNOTIFY constant
- WS_EX_RIGHT constant
- WS_EX_DLGMODALFRAME constant
- WS_EX_APPWINDOW constant
- WS_EX_STATICEDGE constant
- WS_EX_LTRREADING constant
- WS_EX_RIGHTSCROLLBAR constant
- WS_EX_CONTROLPARENT constant
- WS_EX_MDICHILD constant
- WS_EX_TOPMOST constant
- WS_EX_RTLREADING constant
- WS_EX_LEFT constant
- WS_EX_TOOLWINDOW constant
- WS_EX_ACCEPTFILES constant
- WS_EX_WINDOWEDGE constant
- WS_EX_OVERLAPPEDWINDOW constant
- extended window styles
- WS_EX_LEFTSCROLLBAR constant
- WS_EX_TRANSPARENT constant
- WS_EX_CLIENTEDGE constant
- WS_EX_CONTEXTHELP constant
- styles, windows
ms.assetid: d18e6c69-0a01-49ed-b58a-55b3802b47c1
caps.latest.revision: 14
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
ms.openlocfilehash: e5a735ffcdaa78a4764e57b3c311979f24b7fdda
ms.lasthandoff: 02/24/2017

---
# <a name="extended-window-styles"></a>Расширенные стили окна
-   **WS_EX_ACCEPTFILES** указывает, что с окном, созданным в этом стиле принимает файлы и перетаскивания.  
  
-   **WS_EX_APPWINDOW** принудительно окна верхнего уровня на панели задач, если окно является видимым.  
  
-   **WS_EX_CLIENTEDGE** указывает, что окно трехмерный вид — то есть элемент border с утопленной границы.  
  
-   **WS_EX_CONTEXTHELP** включают вопросительный знак в строке заголовка окна. Когда пользователь щелкает вопросительный знак, курсор изменяется с вопросительным знаком с указателем. Если пользователь щелкает дочернее окно, это окно получает **WM_HELP** сообщение.  
  
-   **WS_EX_CONTROLPARENT** дает пользователю возможность перемещения между окнами дочернего окна с помощью клавиши TAB.  
  
-   **WS_EX_DLGMODALFRAME** определяет окно с двойной границей, который (при необходимости) может быть создан с использованием заголовка при указании **WS_CAPTION** стиля флаг в `dwStyle` параметр.  
  
-   **WS_EX_LAYERED** окно [многоуровневых окон](http://msdn.microsoft.com/library/ms632599.aspx#layered). Этот стиль не может использоваться, если окно имеет [стиль класса](http://msdn.microsoft.com/library/ms633574.aspx#class_styles) либо **CS_OWNDC** или **CS_CLASSDC**. Тем не менее [!INCLUDE[win8_first](../../mfc/reference/includes/win8_first_md.md)] поддерживает **WS_EX_LAYERED** стиля для дочерних окон, где предыдущие версии Windows поддерживают его только для окон верхнего уровня.  
  
-   **WS_EX_LEFT** предоставляет свойства универсального по левому краю окна. Это значение по умолчанию.  
  
-   **WS_EX_LEFTSCROLLBAR** помещает вертикальную полосу прокрутки слева от клиентской области.  
  
-   **WS_EX_LTRREADING** отображает текст окна с помощью слева направо чтение свойства заказа. Это значение по умолчанию.  
  
-   **WS_EX_MDICHILD** создает дочернего окна MDI.  
  
-   **WS_EX_NOPARENTNOTIFY** указывает, что не будет отправлять дочернего окна, созданные с этим стилем `WM_PARENTNOTIFY` сообщение для родительского окна при создании или удалении дочернего окна.  
  
-   **WS_EX_OVERLAPPEDWINDOW** объединяет **WS_EX_CLIENTEDGE** и **WS_EX_WINDOWEDGE** стили  
  
-   **WS_EX_PALETTEWINDOW** объединяет **WS_EX_WINDOWEDGE** и **WS_EX_TOPMOST** стили.  
  
-   **WS_EX_RIGHT** предоставляет универсальные свойства по правому краю окна. Это определяется класс окна.  
  
-   **WS_EX_RIGHTSCROLLBAR** помещает вертикальная полоса прокрутки (при наличии) в правой части клиентской области. Это значение по умолчанию.  
  
-   **WS_EX_RTLREADING** отображается с помощью чтения слева направо текст окна Упорядочить свойства.  
  
-   **WS_EX_STATICEDGE** создает окно с трехмерный стиль предназначен для использования для элементов, которые не принимают входные данные пользователя.  
  
-   **WS_EX_TOOLWINDOW** создает окно инструментов, — это окно, предназначен для использования в качестве плавающей панели инструментов. Окно инструментов имеет заголовок, короче обычного заголовка и выводится более мелким шрифтом. Окно инструментов не отображается на панели задач или в окно, которое появляется, когда пользователь нажимает сочетание клавиш ALT + TAB.  
  
-   **WS_EX_TOPMOST** указывает, что следует поместить над всеми nontopmost windows с окном, созданным с помощью этого стиля и оставаться над ними даже в том случае, если окно деактивируется. Приложение может использовать `SetWindowPos` функции-члена для добавления или удаления этого атрибута.  
  
-   **WS_EX_TRANSPARENT** указывает, что с окном, созданным в этом стиле является прозрачным. То есть все окна, которые находятся ниже окна не скрываются в окне. Получает окно, созданные с этим стилем `WM_PAINT` сообщения только после обновления всех окон того же уровня под ним.  
  
-   **WS_EX_WINDOWEDGE** указывает, что окно вызванного границу.  
  
## <a name="see-also"></a>См. также  
 [Стили, используемые MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)   
 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)


