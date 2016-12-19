---
title: "Manifest Resources | Microsoft Docs"
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
  - "manifest resources"
  - "resources [Visual Studio], manifest"
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Manifest Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ресурсы манифеста — это XML\-файлы, описывающие зависимости, которые использует приложение. Например, в Visual Studio файл манифеста, созданный мастером MFC, определяет, какие версии библиотек DLL общих элементов управления Windows \(5.0 или 6.0\), приложение должно использовать:  
  
```  
<description>Your app description here</description> <dependency> <dependentAssembly> <assemblyIdentity type="win32" name="Microsoft.Windows.Common-Controls" version="6.0.0.0" processorArchitecture="X86" publicKeyToken="6595b64144ccf1df" language="*" /> </dependentAssembly> </dependency>   
```  
  
 Для приложений Windows XP и Windows Vista ресурс манифеста не только определяет, что приложение должно использовать последнюю версию общих элементов управления Windows \(версии 6.0, см. выше\), но также поддерживает [элемент управления Syslink](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 Чтобы узнать версию и просмотреть сведения о типах, содержащиеся в ресурсе манифеста, нужно открыть файл в средстве просмотра XML или в [текстовом редакторе](http://msdn.microsoft.com/ru-ru/508e1f18-99d5-48ad-b5ad-d011b21c6ab1) Visual Studio. Дополнительные сведения см. в статье [Открытие ресурса манифеста в текстовом редакторе Visual Studio](../Topic/How%20to:%20Open%20a%20Manifest%20Resource.md).  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Ограничения  
 Допускается иметь только один ресурс манифеста на каждый модуль.  
  
## Требования  
 Win32  
  
## См. также  
 [Элементы управления](../mfc/controls-mfc.md)   
 [Working with Resource Files](../mfc/working-with-resource-files.md)