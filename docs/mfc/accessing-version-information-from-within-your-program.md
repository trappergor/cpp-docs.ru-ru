---
title: "Accessing Version Information from Within Your Program | Microsoft Docs"
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
  - "VerQueryValue"
  - "version information, accessing from within programs"
  - "GetFileVersionInfo"
  - "version information"
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Accessing Version Information from Within Your Program
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Доступ к сведениям о версии из создаваемой программы  
  
1.  Если нужно получить доступ к сведениям о версии из создаваемой программы, используйте функции [GetFileVersionInfo](http://msdn.microsoft.com/library/windows/desktop/ms647003.aspx) и [VerQueryValue](http://msdn.microsoft.com/library/windows/desktop/ms647464.aspx).  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [Сведения о версии \(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)