---
title: "Стили списков | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- LBS_NOSEL constant [MFC]
- LBS_NOREDRAW constant [MFC]
- LBS_HASSTRINGS constant [MFC]
- LBS_OWNERDRAWFIXED constant [MFC]
- LBS_WANTKEYBOARDINPUT constant [MFC]
- LBS_STANDARD constant [MFC]
- LBS_MULTIPLESEL constant [MFC]
- LBS_OWNERDRAWVARIABLE constant [MFC]
- LBS_DISABLENOSCROLL constant [MFC]
- LBS_NODATA constant [MFC]
- list boxes [MFC], styles
- LBS_EXTENDEDSEL constant [MFC]
- LBS_MULTICOLUMN constant [MFC]
- LBS_NOTIFY constant [MFC]
- LBS_USETABSTOPS constant [MFC]
- LBS_NOINTEGRALHEIGHT constant [MFC]
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2c1ac3ca255818bab745b7aa320ee69922359c14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="list-box-styles"></a>Стили списков
-   **LBS_DISABLENOSCROLL** отображается отключенная вертикальная полоса прокрутки при списке содержится недостаточно элементов для прокрутки. Если этот стиль не задан, полоса прокрутки будет скрыта при недостаточном количестве элементов в списке.  
  
-   **LBS_EXTENDEDSEL** пользователь может выбрать несколько элементов, с помощью клавиши SHIFT и мышь или специальные сочетания клавиш.  
  
-   **LBS_HASSTRINGS** Указывает список рисуемый владельцем, который содержит элементы, которые являются строками. Поле списка поддерживает память и указатели для строк, поэтому приложение может использовать `GetText` функция-член для извлечения текста для конкретного элемента.  
  
-   **LBS_MULTICOLUMN** Указывает список из нескольких столбцов, может прокручиваться по горизонтали. `SetColumnWidth` Функция-член устанавливает ширину столбцов.  
  
-   **LBS_MULTIPLESEL** переключается выделение строки при каждом щелчке мышью или дважды щелкает строку. Можно выбрать любое число строк.  
  
-   **LBS_NODATA** указывает поле со списком без данных. Укажите стиль превышения числа элементов в списке тысяч. Поле со списком без данных также необходим **LBS_OWNERDRAWFIXED** стиля, но не должен иметь **LBS_SORT** или **LBS_HASSTRINGS** стиля.  
  
     Поле со списком без данных напоминает определяемые владельцем списка, за исключением того, что он не содержит строку "или" точечный рисунок данных для элемента. Команды для добавления, вставлять или удалять элемент всегда игнорировать любой заданной элемента данных; запросы для поиска строки в окне списка всегда завершаться ошибкой. Система отправляет `WM_DRAWITEM` сообщение для окна-владельца, когда необходимо нарисовать элемент. ItemID членом `DRAWITEMSTRUCT` структуры передается `WM_DRAWITEM` сообщения указывает номер строки для отображения элемента. Поле со списком без данных не отправляет `WM_DELETEITEM` сообщения.  
  
-   **LBS_NOINTEGRALHEIGHT** размер списка составляет ровно размер, указанный для приложения при его создании списка. Как правило Windows размеров поле со списком, чтобы поле списка избежать частичного отображения элементов.  
  
-   **LBS_NOREDRAW** списков не обновляется при внесении изменений. Этот стиль можно изменить в любое время путем отправки **WM_SETREDRAW** сообщения.  
  
-   **LBS_NOSEL** указывает, что список содержит элементы, которые можно просматривать, но не выбран.  
  
-   **LBS_NOTIFY** родительское окно получает входящее сообщение каждый раз, когда пользователь нажимает кнопку или дважды щелкает строку.  
  
-   **LBS_OWNERDRAWFIXED** владелец списка отвечает за рисование его содержимого; все элементы в списке имеют одинаковую высоту.  
  
-   **LBS_OWNERDRAWVARIABLE** владелец списка отвечает за рисование его содержимого; все элементы в списке имеют разную высоту.  
  
-   **LBS_SORT** строки в списке сортируются в алфавитном порядке.  
  
-   **LBS_STANDARD** строк в списке сортируются по алфавиту, а родительское окно получает входящее сообщение каждый раз, когда пользователь нажимает кнопку или дважды щелкает строку. Список содержит границы со всех сторон.  
  
-   **LBS_USETABSTOPS** позволяет распознавать и расширять знаки табуляции при рисовании строк списка. Позиций табуляции по умолчанию — 32 единицы диалогового окна. (Единицы диалогового окна является горизонтальное или вертикальное расстояние. Единицы диалогового окна горизонтальной равно одной четвертой текущий блок базовый ширины диалогового окна. Базовые единицы диалогового окна вычисляются в зависимости от высоты и ширины текущего системного шрифта. **GetDialogBaseUnits** Windows функция возвращает базовых единиц текущего диалогового окна в пикселях.) Этот стиль не должны использоваться с **LBS_OWNERDRAWFIXED**.  
  
-   **LBS_WANTKEYBOARDINPUT** владелец списка получает `WM_VKEYTOITEM` или `WM_CHARTOITEM` сообщений при каждом нажатии клавиши, когда фокус ввода списка. Это позволяет приложению выполнять специальную обработку для клавиатуры.  
  
## <a name="see-also"></a>См. также  
 [Стили, используемые MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [Стили окна списка](http://msdn.microsoft.com/library/windows/desktop/bb775149)

