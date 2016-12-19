---
title: "Editing a String in a Version Information Resource | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "version information resources"
  - "resources [Visual Studio], editing version information"
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Editing a String in a Version Information Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Изменение строки в ресурсе сведений о версии  
  
1.  Щелкните элемент один раз, чтобы выбрать его, а затем щелкните его повторно, чтобы приступить к редактированию. Изменения следует вносить непосредственно в таблице сведений о версии или в [окне свойств](../Topic/Properties%20Window.md). Внесенные изменения будут отображаться и там, и там.  
  
     **Примечание.** В процессе редактирования раздела **FILEFLAGS** в редакторе сведений о версии вы можете обратить внимание на то, что для RC\-файлов нельзя задать значения свойств **Debug**, **Private Build** и **Special Build** в окне свойств.  
  
    -   Редактор сведений о версии задает для свойства **Debug** значение \#ifdef в описании ресурса в зависимости от флага сборки **\_DEBUG**.  
  
    -   Если для раздела **Private Build** в таблице сведений о версии задано **Значение**, для соответствующего свойства **Private Build** \(в окне свойств\) раздела **FILEFLAGS** будет задано значение **True**. Если **Значение** пусто, это свойство будет иметь значение **False**. Аналогичным образом раздел **Special Build** \(в таблице сведений о версии\) связан со свойством **Special Build** раздела **FILEFLAGS**.  
  
 Чтобы отсортировать строки в блоке, щелкните заголовок столбца "Раздел" или "Значение". В результате сведения автоматически будут отображаться в порядке, заданном сортировкой.  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [Сведения о версии \(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)