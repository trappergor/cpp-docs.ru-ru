---
title: "Defining Member Variables for Dialog Controls | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "member variables, defining for controls"
  - "variables, dialog box control member variables"
  - "controls [C++], member variables"
  - "Dialog editor, defining member variables for controls"
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Defining Member Variables for Dialog Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для определения переменных\-членов для всех элементов управления диалогового окна кроме кнопок можно использовать следующий метод.  
  
> [!NOTE]
>  Метод, описанный в этой статье, применим только к элементам управления диалогового окна в составе проекта MFC.  Проекты ATL должны использовать диалоговое окно **Новые сообщения Windows и обработчики событий**.  
  
### Определение переменной\-члена для элемента управления диалогового окна \(кроме кнопки\)  
  
1.  В [редакторе диалоговых окон](../mfc/dialog-editor.md) выберите нужный элемент управления.  
  
2.  Удерживая нажатой клавишу **CTRL**, дважды щелкните элемент управления диалогового окна.  
  
     Откроется [мастер "Добавление переменной\-члена"](../ide/add-member-variable-wizard.md).  
  
3.  Введите соответствующие сведения в мастере **Добавление переменной\-члена**.  Дополнительные сведения см. в статье [Обмен данными диалогового окна](../mfc/dialog-data-exchange.md).  
  
4.  Нажмите кнопку **ОК** для возврата в редактор диалоговых окон.  
  
    > [!TIP]
    >  Чтобы перейти из любого элемента управления диалогового окна к его обработчику, дважды щелкните элемент управления.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в статье [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Вы можете также использовать вкладку **Переменные\-члены** в **мастере классов MFC**, чтобы добавить новые переменные\-члены для заданного класса и просмотреть те, которые уже были определены.  
  
 Требования  
  
 MFC  
  
## См. также  
 [Сопоставление сообщений с функциями](../Topic/Mapping%20Messages%20to%20Functions.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Мастер классов MFC](../mfc/reference/mfc-class-wizard.md)   
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Добавление функции\-члена](../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной\-члена](../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)