---
title: "Associating a Menu Command with an Accelerator Key | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "keyboard shortcuts, menu association"
  - "commands, associating menu commands with accelerator keys"
  - "menu commands, associating with keyboard shortcuts"
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Associating a Menu Command with an Accelerator Key
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В некоторых ситуациях может потребоваться, чтобы программную команду можно было вызывать с помощью команды меню и сочетания клавиш. Для этого необходимо с помощью редактора меню назначить один и тот же идентификатор ресурса команде меню и записи в таблице сочетаний клавиш приложения. Затем необходимо изменить [Заголовок](../windows/menu-command-properties.md) команды меню, чтобы в нем отображалось название сочетания клавиш.  
  
### Сопоставление команды меню с сочетанием клавиш  
  
1.  В редакторе **меню** выберите нужную команду меню.  
  
2.  В [окне свойств](../Topic/Properties%20Window.md) добавьте название сочетания клавиш в свойство **Заголовок**.  
  
    -   Сразу после заголовка меню введите escape\-последовательность для табуляции \(\\t\), чтобы все сочетания клавиш в меню были выровнены по левому краю.  
  
    -   Введите имя клавиши\-модификатора \(**CTRL**, **ALT** или **SHIFT**\), а затем знак плюса \(**\+**\) и имя, букву или символ дополнительной клавиши.  
  
         Например, чтобы назначить клавиши **CTRL\+O** команде **Открыть** в меню **Файл**, необходимо изменить **Заголовок** команды меню следующим образом:  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         Команда меню в редакторе меню обновляется по мере ввода нового названия.  
  
3.  [Создайте запись в таблице сочетаний клавиш](../windows/adding-an-entry-to-an-accelerator-table.md) с помощью редактора **сочетаний клавиш** и назначьте ему тот же идентификатор ресурса, что и команде меню. Рекомендуется выбирать сочетания, которые легче запомнить.  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [Adding Commands to a Menu](../Topic/Adding%20Commands%20to%20a%20Menu.md)   
 [Menu Editor](../Topic/Menu%20Editor.md)