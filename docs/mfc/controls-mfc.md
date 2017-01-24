---
title: "Элементы управления (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "общие элементы управления Windows [C++]"
  - "стандартные элементы управления [C++]"
  - "элементы управления [MFC]"
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Элементы управления (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Элементы управления — это объекты, используемые для ввода данных и работы с ними. Как правило, они отображаются в диалоговых окнах и на панелях инструментов. В этом документе рассматриваются три основных типа элементов управления.  
  
-   Стандартные элементы управления Windows, включая создаваемые владельцем элементы управления  
  
-   Элементы управления ActiveX  
  
-   Другие классы элементов управления из библиотеки MFC  
  
## Стандартные элементы управления Windows  
 В ОС Windows всегда существовал ряд стандартных элементов управления Windows. Эти объекты элементов управления являются программируемыми и редактор диалоговых окон Visual C\+\+ поддерживает их добавление в диалоговые окна. Библиотека MFC предоставляет классы, инкапсулирующие все эти элементы управления, как показано в таблице [Стандартные элементы управления Windows и классы MFC](#_core_windows_common_controls_and_mfc_classes). \(Для некоторых элементов в таблице существуют связанные разделы с дальнейшим описанием. Если для элементов управления связанные разделы отсутствуют, см. документацию по классу MFC.\)  
  
 Класс [CWnd](../Topic/CWnd%20Class.md) является базовым для всех классов окон, включая все классы элементов управления. Стандартные элементы управления Windows поддерживаются в следующих средах:  
  
-   Windows 95, Windows 98 и Windows 2000;  
  
-   Windows NT 3.51 и более поздние версии;  
  
-   Win32, версия 1.3 \(Visual C\+\+ версии 4.2 и более поздних версий не поддерживает Win32\).  
  
 Более старые стандартные элементы управления — флажки, поля со списками, поля ввода, списки, переключатели, кнопок, элементов управления полосы прокрутки и статические элементы управления — также были доступны в более ранних версиях Windows.  
  
## Элементы управления ActiveX  
 Элементы управления ActiveX, ранее известные как элементы управления OLE, можно использовать в диалоговых окнах в приложениях для Windows или на HTML\-страницах в Интернете. Более подробную информацию см. в разделе [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md).  
  
## Другие классы элементов управления MFC  
 Наряду с классами, инкапсулирующими все стандартные элементы управления Windows и поддерживающими программирование пользовательских элементов управления ActiveX \(или использование элементов управления ActiveX, предоставляемых другими пользователями\), MFC предоставляет следующие свои классы элементов управления:  
  
-   [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
  
-   [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
  
-   [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
  
##  <a name="_core_finding_information_about_windows_common_controls"></a> Сведения о стандартных элементах управления Windows  
 В следующей таблице содержится краткое описание стандартных элементов управления Windows, включая класс\-оболочку MFC элемента управления.  
  
### Стандартные элементы управления Windows и классы MFC  
  
|Control|Класс MFC|Описание|Новинка в Windows 95?|  
|-------------|---------------|--------------|---------------------------|  
|[анимация](../Topic/Using%20CAnimateCtrl.md)|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|Отображение последовательных кадров видеоролика AVI.|Да|  
|button|[CButton](../mfc/reference/cbutton-class.md)|Кнопки, вызывающие действия; также используется для флажков, переключателей и полей групп.|Нет|  
|поле со списком|[CComboBox](../mfc/reference/ccombobox-class.md)|Комбинация текстового поля и поля со списком.|Нет|  
|[элемент выбора даты и времени](../mfc/using-cdatetimectrl.md)|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|Позволяет выбирать определенное значение даты или времени.|Да|  
|поле ввода|[CEdit](../Topic/CEdit%20Class.md)|Поля для ввода текста.|Нет|  
|[расширенное поле со списком](../mfc/using-ccomboboxex.md)|[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)|Поле со списком с возможностью отображения изображений.|Да|  
|[заголовок](../mfc/using-cheaderctrl.md)|[CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md)|Кнопка, которая появляется над столбцом текста. Определяет ширину отображаемого текста.|Да|  
|[сочетание клавиш](../mfc/using-chotkeyctrl.md)|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|Окно, позволяющее создавать сочетания клавиш для быстрого выполнения действий.|Да|  
|[список изображений](../mfc/using-cimagelist.md)|[CImageList](../Topic/CImageList%20Class.md)|Коллекция изображений, используемых для управления большими наборами значков и точечных рисунков \(на самом деле список изображений не является элементом управления — он поддерживает списки, используемые другими элементами управления\).|Да|  
|[list](../Topic/Using%20CListCtrl.md)|[CListCtrl](../Topic/CListCtrl%20Class.md)|Окно, отображающее список текста со значками.|Да|  
|список|[CListBox](../Topic/CListBox%20Class.md)|Поле, содержащее список строк.|Нет|  
|[календарь месяца](../Topic/Using%20CMonthCalCtrl.md)|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|Элемент управления, отображающий сведения о дате.|Да|  
|[ход выполнения](../mfc/using-cprogressctrl.md)|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Окно, в котором отображается ход выполнения длительной операции.|Да|  
|[главная панель](../Topic/Using%20CReBarCtrl.md)|[CRebarCtrl](../mfc/reference/crebarctrl-class.md)|Панель инструментов, которая может содержать дополнительные дочерние окна в виде элементов управления.|Да|  
|[ввод с форматированием](../mfc/using-cricheditctrl.md)|[CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)|Окно, в котором можно выполнять редактирование с форматированием символов и абзацев \(см. раздел [Классы, связанные с элементами управления Rich Edit](../mfc/classes-related-to-rich-edit-controls.md)\).|Да|  
|полоса прокрутки|[CScrollBar](../mfc/reference/cscrollbar-class.md)|Полоса прокрутки, используемая как элемент управления в диалоговом окне \(не в окне\).|Нет|  
|[ползунок](../mfc/using-csliderctrl.md)|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|Окно, содержащее элемент управления "Ползунок" с необязательными делениями.|Да|  
|[кнопка "Счетчик"](../mfc/using-cspinbuttonctrl.md)|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Пара кнопок со стрелками для увеличения или уменьшения значения.|Да|  
|статический текст|[CStatic](../Topic/CStatic%20Class.md)|Текст для надписей других элементов управления.|Нет|  
|[строка состояния](../mfc/using-cstatusbarctrl.md)|[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)|Окно для отображения сведений о состоянии, аналогичное классу MFC `CStatusBar`.|Да|  
|[вкладка](../mfc/using-ctabctrl.md)|[CTabCtrl](../Topic/CTabCtrl%20Class.md)|Аналог разделителей в записной книжке. Используется в диалоговых окнах с вкладками или таблицах свойств.|Да|  
|[панель инструментов](../mfc/using-ctoolbarctrl.md)|[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)|Окно с генерирующими команды кнопками, аналогичное классу MFC `CToolBar`.|Да|  
|[подсказка](../mfc/using-ctooltipctrl.md)|[CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md)|Небольшое всплывающее окно с описанием назначения кнопки панели инструментов или другого инструмента.|Да|  
|[дерево](../Topic/Using%20CTreeCtrl.md)|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Окно, в котором отображается иерархический список элементов.|Да|  
  
### Дополнительные сведения  
  
-   Отдельный элемент управления: см. таблицу [Стандартные элементы управления Windows и классы MFC](#_core_windows_common_controls_and_mfc_classes) в этом разделе, содержащую ссылки на все элементы управления.  
  
-   [Создание и использование элементов управления](../mfc/making-and-using-controls.md)  
  
-   [Использование редактора диалоговых окон для добавления элементов управления](../mfc/using-the-dialog-editor-to-add-controls.md)  
  
-   [Добавление элементов управления в диалоговое окно вручную](../mfc/adding-controls-by-hand.md)  
  
-   [Наследование классов элементов управления от классов элементов управления MFC](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [Использование стандартных элементов управления в качестве дочерних окон](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [Уведомления из стандартных элементов управления](../Topic/Receiving%20Notification%20from%20Common%20Controls.md)  
  
-   [Добавление стандартных элементов управления в диалоговое окно](../mfc/using-common-controls-in-a-dialog-box.md)  
  
-   [Получение элемента управления из стандартного элемента управления Windows](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [Доступ к элементам управления диалогового окна с безопасностью типа](../Topic/Type-Safe%20Access%20to%20Controls%20in%20a%20Dialog%20Box.md)  
  
-   [Получение уведомлений из стандартных элементов управления](../Topic/Receiving%20Notification%20from%20Common%20Controls.md)  
  
-   [Примеры](../mfc/common-control-sample-list.md)  
  
 Сведения о стандартных элементах управления Windows в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] см. в разделе [Стандартные элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb775493).  
  
## См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)   
 [Dialog Editor](../mfc/dialog-editor.md)