---
title: "Создание элемента управления &quot;Вкладка&quot; | Microsoft Docs"
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
  - "TCS_EX_REGISTERDROP"
  - "TCS_EX_FLATSEPARATORS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabCtrl - класс, создание"
  - "элементы управления вкладка, создание"
  - "TCS_EX_FLATSEPARATORS - расширенный стиль"
  - "TCS_EX_REGISTERDROP - расширенный стиль"
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Создание элемента управления &quot;Вкладка&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Когда элемент управления TAB создается зависит от того, используется ли элемент управления в диалоговом окне или создать его в окне nondialog.  
  
### Использовать CTabCtrl непосредственно в диалоговом окне  
  
1.  В редакторе диалоговых окон, добавьте элемент управления TAB в ресурс шаблона диалоговых окон.  Укажите его идентификатор элемента управления.  
  
2.  Используйте [Мастер добавления переменной\-члена](../ide/adding-a-member-variable-visual-cpp.md), чтобы добавить переменную\-член типа [CTabCtrl](../Topic/CTabCtrl%20Class.md) со свойством элемента управления.  Можно использовать этот член вызова функции\-члены `CTabCtrl`.  
  
3.  Функции обработчика сопоставления в классе диалогового окна для всех сообщений уведомлений элемента управления TAB необходимо обработать.  Дополнительные сведения см. в разделе [Сопоставление сообщений с функциями](../Topic/Mapping%20Messages%20to%20Functions.md).  
  
4.  В [OnInitDialog](../Topic/CDialog::OnInitDialog.md), задайте стили для `CTabCtrl`.  
  
### Использовать CTabCtrl в окне nondialog  
  
1.  Указать элемент управления в представлении или класса окна.  
  
2.  Вызовите функцию\-член [Создать](../Topic/CTabCtrl::Create.md) элемента управления, возможно, в [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), возможно начиная с функции обработчика [OnCreate](../Topic/CWnd::OnCreate.md) родительского окна \(если создание подкласса для элемента управления\).  Задайте стили для элемента управления.  
  
 После создания объекта `CTabCtrl` будет создан, можно установить или сбросить следующие расширенные стили:  
  
-   **TCS\_EX\_FLATSEPARATORS** является элементом управления TAB рисуется разделители между элементами вкладки.  Этот расширенный стиль применяется только к элементам управления TAB, имеющие стилей **TCS\_BUTTONS** и **TCS\_FLATBUTTONS**.  По умолчанию при создании элемента управления "вкладка" со стилем **TCS\_FLATBUTTONS** задает этот расширенный стиль.  
  
-   **TCS\_EX\_REGISTERDROP** является элементом управления TAB создает сообщения уведомления **TCN\_GETOBJECT** для запроса объекта целевым объектом перетаскивания при перемещении объекта над элементами вкладки в элементе управления.  
  
    > [!NOTE]
    >  Чтобы получать уведомление **TCN\_GETOBJECT**, необходимо инициализировать OLE библиотеки с вызовом метода [AfxOleInit](../Topic/AfxOleInit.md).  
  
 Эти стили можно получить и установить, выбрав элемент управления был создан, с соответствующим образом вызовами функциям элемента [GetExtendedStyle](../Topic/CTabCtrl::GetExtendedStyle.md) и [SetExtendedStyle](../Topic/CTabCtrl::SetExtendedStyle.md).  
  
 Например, задать стиль **TCS\_EX\_FLATSEPARATORS** со следующими строками кода:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/CPP/creating-the-tab-control_1.cpp)]  
  
 Снимите стиль **TCS\_EX\_FLATSEPARATORS** из объекта `CTabCtrl` со следующими строками кода:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/CPP/creating-the-tab-control_2.cpp)]  
  
 Это удалит разделителей, отображаемые между кнопками объекта класса `CTabCtrl`.  
  
## См. также  
 [Использование CTabCtrl](../mfc/using-ctabctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)