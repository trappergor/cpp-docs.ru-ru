---
title: "Creating Pop-up Menus | Microsoft Docs"
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
  - "context menus, Menu Editor"
  - "pop-up menus, creating"
  - "menus, pop-up"
  - "menus, creating"
  - "shortcut menus, creating"
  - "pop-up menus, displaying"
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating Pop-up Menus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Всплывающие меню](../mfc/menus-mfc.md) отображают часто используемые команды. Они могут быть контекстно\-зависимыми, т. е. зависеть от положения указателя. Использование всплывающего меню в приложении требует создания самого меню и привязки его к коду приложения.  
  
 После создания ресурса меню нужно обеспечить, чтобы код приложения загружал этот ресурс, и, используя [метод TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002), открывал меню на экране. Если пользователь откажется от выполнения команд всплывающего меню, щелкнув за его пределами, или щелкнет команду, будет выполнен возврат из этой функции. Если пользователь выберет команду, будет отправлено сообщение этой команды в то окно, дескриптор которого был передан.  
  
### Создание всплывающего меню  
  
1.  [Создайте меню](../windows/creating-a-menu.md) с пустым заголовком \(не вводите **заголовок**\).  
  
2.  [Добавьте команды в новое меню](../Topic/Adding%20Commands%20to%20a%20Menu.md). Переместите первую команду меню под строку пустого заголовка \(появится временный заголовок "Введите здесь"\). Введите **заголовок** и прочие сведения.  
  
     Повторите эту процедуру для остальных команд всплывающего меню.  
  
3.  Сохраните ресурс меню.  
  
    > [!TIP]
    >  Дополнительные сведения о просмотре всплывающих меню см. в статье [Просмотр меню в виде всплывающего меню](../windows/viewing-a-menu-as-a-pop-up-menu.md).  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [Connecting a Pop\-up Menu to Your Application](../Topic/Connecting%20a%20Pop-up%20Menu%20to%20Your%20Application.md)   
 [Menu Editor](../Topic/Menu%20Editor.md)