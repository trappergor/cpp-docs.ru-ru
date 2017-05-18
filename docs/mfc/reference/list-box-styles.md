---
title: "Стили списков | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LBS_STANDARD
- LBS_NODATA
- LBS_OWNERDRAWVARIABLE
- LBS_EXTENDEDSEL
- LBS_USETABSTOPS
- LBS_WANTKEYBOARDINPUT
- LBS_NOTIFY
- LBS_DISABLENOSCROLL
- LBS_HASSTRINGS
- LBS_NOREDRAW
- LBS_NOSEL
- LBS_NOINTEGRALHEIGHT
- LBS_MULTICOLUMN
- LBS_SORT
- LBS_MULTIPLESEL
- LBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- LBS_NOSEL constant
- LBS_NOREDRAW constant
- LBS_HASSTRINGS constant
- LBS_OWNERDRAWFIXED constant
- LBS_WANTKEYBOARDINPUT constant
- LBS_STANDARD constant
- LBS_MULTIPLESEL constant
- LBS_OWNERDRAWVARIABLE constant
- LBS_DISABLENOSCROLL constant
- LBS_NODATA constant
- list boxes, styles
- LBS_EXTENDEDSEL constant
- LBS_MULTICOLUMN constant
- LBS_NOTIFY constant
- LBS_USETABSTOPS constant
- LBS_NOINTEGRALHEIGHT constant
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8e038e5cef50bd15df85c9d7f8b213b54ed03825
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="list-box-styles"></a>Стили списков
-   **LBS_DISABLENOSCROLL** в списке существует отключено вертикальную полосу прокрутки, когда поле списка не содержит достаточно элементов для прокрутки. Если этот стиль не задан, полоса прокрутки будет скрыта при недостаточном количестве элементов в списке.  
  
-   **LBS_EXTENDEDSEL** пользователь может выбрать несколько элементов, используя клавишу SHIFT и мышь или специальные сочетания клавиш.  
  
-   **LBS_HASSTRINGS** определяет список рисование владельцем, который содержит элементы, состоящие из строк. Поле списка поддерживает память и указатели для строк, поэтому приложение может использовать `GetText` функции-члена для получения текста для определенного элемента.  
  
-   **LBS_MULTICOLUMN** Указывает список из нескольких столбцов, может прокручиваться по горизонтали. `SetColumnWidth` Функция-член задает ширину столбцов.  
  
-   **LBS_MULTIPLESEL** выбора строки заменяется каждый раз пользователь нажимает или дважды щелкает строку. Можно выбрать любое число строк.  
  
-   **LBS_NODATA** указывает поле со списком без данных. Укажите стиль превышения числа элементов в списке тысяч. Поле со списком данных не должно быть **LBS_OWNERDRAWFIXED** стиля, но не должен иметь **LBS_SORT** или **LBS_HASSTRINGS** стиль.  
  
     Поле со списком без данных напоминает определяемые владельцем списка, за исключением того, что он не содержит строку или точечный рисунок данных для элемента. Команды для добавления, вставки или удаления элемента всегда игнорировать любого конкретного элемента данных. запросы для поиска строки в списке всегда завершаться ошибкой. Система отправляет `WM_DRAWITEM` сообщений для окна-владельца, когда необходимо нарисовать элемент. ItemID членом `DRAWITEMSTRUCT` структура, переданная с `WM_DRAWITEM` сообщении указывается номер строки рисуемого элемента. Поле со списком без данных не отправляет `WM_DELETEITEM` сообщение.  
  
-   **LBS_NOINTEGRALHEIGHT** размер списка — точно размер, указанный для приложения, при создании списка. Обычно размер списка, чтобы поле списка избежать частичного отображения элементов.  
  
-   **LBS_NOREDRAW** списка не обновляется при внесении изменений. Этот стиль можно изменить в любое время путем отправки **WM_SETREDRAW** сообщений.  
  
-   **LBS_NOSEL** указывает, что список содержит элементы, которые можно просматривать, но не выбран.  
  
-   **LBS_NOTIFY** родительское окно получает входящее сообщение каждый раз, когда пользователь нажимает или дважды щелкает строку.  
  
-   **LBS_OWNERDRAWFIXED** владелец списка отвечает за рисование его содержимого; элементы в поле со списком, равной высоты.  
  
-   **LBS_OWNERDRAWVARIABLE** владелец списка отвечает за рисование его содержимого; элементов в списке может меняться в высоту.  
  
-   **LBS_SORT** строки в списке сортируются по алфавиту.  
  
-   **LBS_STANDARD** строки в списке сортируются по алфавиту, и родительское окно получает входящее сообщение каждый раз, когда пользователь нажимает или дважды щелкает строку. Список содержит границы со всех сторон.  
  
-   **LBS_USETABSTOPS** позволяет распознавать и расширять знаки табуляции при рисовании строк списка. Позиций табуляции по умолчанию — 32 единицы диалогового окна. (Единица диалогового окна — горизонтальное или вертикальное расстояние. Четверть текущей единице измерения базового ширину диалогового окна равно единице горизонтального диалоговое окно. Базовые единицы диалогового окна вычисляются на основе высота и ширина текущего системного шрифта. **GetDialogBaseUnits** функции Windows возвращает единицу текущего диалогового окна в пикселях.) Не следует использовать этот стиль с **LBS_OWNERDRAWFIXED**.  
  
-   **LBS_WANTKEYBOARDINPUT** получает владельца списка `WM_VKEYTOITEM` или `WM_CHARTOITEM` сообщений при каждом нажатии клавиши, когда фокус ввода списка. Это позволяет приложению выполнять специальную обработку на клавиатуру.  
  
## <a name="see-also"></a>См. также  
 [Стили, используемые MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [Стили окна списка](http://msdn.microsoft.com/library/windows/desktop/bb775149)


