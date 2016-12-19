---
title: "Adding Event Handlers for Dialog Box Controls | Microsoft Docs"
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
  - "Dialog editor, adding event handlers to controls"
  - "controls [C++], event handlers"
  - "dialog box controls, events"
  - "event handlers, for dialog box controls"
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Event Handlers for Dialog Box Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если диалоговое окно проекта уже связано с классом, при создании обработчиков можно воспользоваться сочетаниями клавиш.  Пользователь может оперативно создать обработчик событий для стандартного уведомления элемента управления или для любого соответствующего сообщения операционной системы Windows.  
  
#### Создание обработчика событий для стандартного уведомления элемента управления  
  
1.  Дважды щелкните элемент управления.  Откроется редактор текста.  
  
2.  Добавьте код обработчика уведомления элемента управления в редактор текста.  
  
#### Создание обработчика для любого соответствующего сообщения Windows  
  
1.  Щелкните элемент управления, для которого следует обрабатывать событие уведомления.  
  
2.  В [окне свойств](../Topic/Properties%20Window.md) нажмите кнопку **ControlEvents**, чтобы вывести список стандартных событий Windows, связанных с элементом управления.  Например, для стандартной кнопки **ОК** в диалоговом окне **О программе** перечислены следующие события уведомления:  
  
     **BN\_CLICKED**  
  
     **BN\_DOUBLECLICKED**  
  
     **BN\_KILLFOCUS**  
  
     **BN\_SETFOCUS**  
  
    > [!NOTE]
    >  Или же выберите диалоговое окно и нажмите кнопку **ControlEvents**, чтобы вывести список стандартных событий Windows, связанных со всеми элементами управления в диалоговом окне.  
  
3.  В **окне свойств** щелкните столбец справа от события, которое необходимо обработать, а затем выберите предлагаемое имя для события уведомления \(например, **OnBnClickedOK** обрабатывает событие **BN\_CLICKED**\).  
  
    > [!NOTE]
    >  С другой стороны, пользователь также может придумать имя обработчика событий самостоятельно.  
  
     После того как пользователь выбрал событие, Visual Studio открывает редактор текста, в котором отображается код обработчика событий.  Например, для стандартного обработчика **OnBnClickedOK** будет добавлен следующий код:  
  
    ```  
    void CAboutDlg::OnBnClickedOk(void)  
    {  
       // TODO: Add your control notification handler code here  
    }  
    ```  
  
 Если необходимо добавить обработчик событий в класс, отличный от класса, который реализует диалоговое окно, рекомендуется использовать [мастер обработчиков событий](../ide/event-handler-wizard.md).  Дополнительные сведения см. в разделе [Добавление обработчиков событий](../ide/adding-an-event-handler-visual-cpp.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Требования  
 Win32  
  
## См. также  
 [Default Control Events](../Topic/Default%20Control%20Events.md)   
 [Defining Member Variables for Dialog Controls](../mfc/defining-member-variables-for-dialog-controls.md)   
 [Элементы управления "Диалоговые окна" и типы переменных](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)   
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Добавление функции\-члена](../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной\-члена](../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)