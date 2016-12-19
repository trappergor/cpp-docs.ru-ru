---
title: "Assigning Access Keys to Menu Commands | Microsoft Docs"
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
helpviewer_keywords: 
  - "access keys [C++], checking"
  - "menus, shortcut keys"
  - "keyboard shortcuts [C++], command assignments"
  - "access keys [C++], assigning"
  - "mnemonics, adding to menus"
  - "keyboard shortcuts [C++], uniqueness checking"
  - "mnemonics, uniqueness checking"
  - "Check Mnemonics command"
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assigning Access Keys to Menu Commands
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Командам меню и самим меню можно назначить клавиши доступа, позволяющие выбирать элементы меню с клавиатуры.  
  
### Назначение клавиши доступа \(сочетания клавиш\) команде меню  
  
1.  Перед буквой в имени меню или команды меню введите амперсанд \(**&**\), чтобы обозначить таким образом букву, с которой будет связана клавиша доступа. Например, "&Файл" означает, что сочетание ALT\+Ф будет выполнять роль клавиши доступа к меню "Файл" в приложениях для Microsoft Windows.  
  
     Буква, с которой связана клавиша доступа, обычно наглядно обозначена в элементе меню. Как правило, буква, следующая за символом амперсанда, отображается как подчеркнутая \(везде в рамках одной ОС\).  
  
    > [!NOTE]
    >  Чтобы убедиться в том, что клавиши доступа не повторяются в рамках одного меню, щелкните меню правой кнопкой мыши и выберите в контекстном меню команду **Проверить назначенные клавиши**.  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [Menu Editor](../Topic/Menu%20Editor.md)