---
title: "Defining Mnemonics (Access Keys) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "access keys [C++], adding"
  - "keyboard shortcuts [C++], controls"
  - "dialog box controls, mnemonics"
  - "access keys [C++], checking"
  - "mnemonics, checking for duplicate"
  - "mnemonics"
  - "mnemonics, dialog box controls"
  - "keyboard shortcuts [C++], uniqueness checking"
  - "Check Mnemonics command"
  - "controls [C++], access keys"
  - "access keys [C++]"
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Defining Mnemonics (Access Keys)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Обычно пользователи перемещают фокус ввода при нажатии клавиши TAB от одного элемента управления к другому в рамках диалогового окна.  Тем не менее, вы можете определить клавишу быстрого доступа \(сокращение или легко запоминаемое имя\), которая позволит пользователю выбрать элемент управления, нажав всего одну клавишу.  
  
### Определить клавишу быстрого доступа для элемента управления в видимом заголовке \(кнопки, флажки и переключатели\)  
  
1.  Нажмите кнопку элемента управления в диалоговом окне.  
  
2.  В [окне "Свойства"](../Topic/Properties%20Window.md), в свойстве **заголовка** впечатайте новое название элемента управления, введя амперсанд\(**&**\) перед буквой, которую вы хотите назначить в сочетании клавиш для быстрого доступа к данному элементу управления.  Например, `&Radio1`.  
  
3.  Нажмите клавишу **ВВОД**.  
  
     Подчеркивание появляется в отображаемом заголовке, чтобы указать клавишу доступа, например, **R**adio1.  
  
### Определение сочетания клавиш для элемента управления без видимого заголовка  
  
1.  Создайте заголовок для элемента управления с использованием **статического текста** в [Панели элементов](../Topic/Toolbox.md).  
  
2.  В заголовке статического текста введите амперсанд \(**&**\), чтобы обозначить таким образом букву, с которой будет связана клавиша быстрого доступа.  
  
3.  Убедитесь, что элемент управления, относящийся к элементу статического текста, непосредственно предшествует элементу статического текста в последовательности переходов.  
  
 Все клавиши быстрого доступа в диалоговом окне должны быть уникальны.  
  
#### Выполнить поиск дубликатов клавиш быстрого доступа.  
  
1.  В меню **Формат** выберите команду **Проверить назначенные клавиши**.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Требования  
 Win32  
  
## См. также  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)