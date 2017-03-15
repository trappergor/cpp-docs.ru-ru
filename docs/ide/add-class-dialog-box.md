---
title: "Диалоговое окно &quot;Добавление класса&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.addclass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Диалоговое окно "Добавление класса""
ms.assetid: 916259b8-8e5f-4267-bd10-313483beba67
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Диалоговое окно &quot;Добавление класса&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Диалоговое окно **Добавление класса** содержит шаблоны, которые позволяют выполнить следующие действия.  
  
-   Открыть соответствующий мастер создания кода, если он доступен. Дополнительные сведения см. в разделе [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md).  
  
 \-или\-  
  
-   Автоматически создать новый класс, добавив в проект соответствующие файлы и исходный код.  
  
 Перейти к диалоговому окну **Добавление класса** можно из меню **Проект**, **обозревателя решений** или [представления классов](http://msdn.microsoft.com/ru-ru/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
> [!NOTE]
>  При попытке добавить класс, который не подходит для текущего проекта, вы получите сообщение об ошибке. Нажмите кнопку **ОК**, чтобы вернуться в диалоговое окно **Добавление класса**.  
  
## Добавление шаблонов классов  
 Существует четыре категории шаблонов **добавления классов**: .NET, ATL, MFC и универсальные. При выборе шаблона в области **Шаблоны** текст, описывающий выбранный шаблон, появится в областях **Категории** и **Шаблоны**.  
  
### .NET  
  
|Шаблон|Мастер|  
|------------|------------|  
|Веб\-служба ASP.NET;|Недоступно|  
|Класс компонента \(.NET\)|Недоступно|  
|Класс установщика \(.NET\)|Недоступно|  
|Пользовательский элемент управления \(.NET\)|Недоступно|  
|Форма Windows Forms \(.NET\)|Недоступно|  
  
### ATL  
  
|Шаблон|Мастер|  
|------------|------------|  
|Добавление в MFC поддержки ATL|Недоступно|  
|ASP\-компонент библиотеки ATL|[Мастер ASP\-компонента ATL](../atl/reference/atl-active-server-page-component-wizard.md)|  
|Элемент управления ATL|[Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md)|  
|Диалог ATL|[Мастер диалоговых окон ATL](../atl/reference/atl-dialog-wizard.md)|  
|Компонент COM\+ 1.0 библиотеки ATL|[Мастер компонентов ATL COM\+ 1.0](../atl/reference/atl-com-plus-1-0-component-wizard.md)|  
|Потребитель OLEDB библиотеки ATL|[Мастер потребителя ATL OLE DB](../atl/reference/atl-ole-db-consumer-wizard.md)|  
|Поставщик OLEDB библиотеки ATL|[Мастер поставщика ATL OLE DB](../atl/reference/atl-ole-db-provider-wizard.md)|  
|Свойства ATL|[Мастер страницы свойств ATL](../atl/reference/atl-property-page-wizard.md)|  
|Простой объект ATL|[Мастер простых объектов ATL](../atl/reference/atl-simple-object-wizard.md)|  
|Поставщик событий WMI|Мастер поставщика событий WMI|  
|Поставщик экземпляров WMI|Мастер поставщика экземпляра WMI|  
  
### MFC  
  
|Шаблон|Мастер|  
|------------|------------|  
|Класс MFC|[Мастер добавления классов MFC](../mfc/reference/mfc-add-class-wizard.md)|  
|Класс MFC из элемента управления ActiveX|[Мастер добавления классов MFC из элемента управления ActiveX](../ide/add-class-from-activex-control-wizard.md)|  
|Класс MFC из TypeLib|[Мастер добавления классов из библиотеки типов](../mfc/reference/add-class-from-typelib-wizard.md)|  
|Потребитель ODBC MFC|[мастер потребителей ODBC MFC](../mfc/reference/mfc-odbc-consumer-wizard.md)|  
  
### Универсальные классы  
  
|Шаблон|Мастер|  
|------------|------------|  
|Универсальный класс C\+\+|[Мастер универсальных классов C\+\+](../ide/generic-cpp-class-wizard.md)|  
  
## См. также  
 [Добавление функции\-члена](../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной\-члена](../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../ide/navigating-the-class-structure-visual-cpp.md)