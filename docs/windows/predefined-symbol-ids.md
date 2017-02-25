---
title: "Predefined Symbol IDs | Microsoft Docs"
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
  - "symbols, predefined IDs"
  - "predefined symbol IDs"
ms.assetid: 91a5d610-1a04-47e8-b8a4-63ad650a90df
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Predefined Symbol IDs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В начале работы над новым проектом в зависимости от типа проекта предоставляется ряд предопределенных идентификаторов символов, которые можно использовать.  Эти идентификаторы символов поддерживают различные библиотеки и типы проектов, например MFC.  Они представляют типичные задачи, которые обычно включаются в любое приложение, или действия таких устройств, как мышь или принтер.  
  
 Эти идентификаторы символов становятся важными при работе с ресурсами.  Они доступны при редактировании таблиц сочетаний клавиш. Некоторые из них уже связаны с виртуальными клавишами.  Доступ к ним можно также получить через [окно свойств](../Topic/Properties%20Window.md).  Предопределенные идентификаторы символов можно назначать новым ресурсам, или можно назначать им сочетания клавиш и функции, связанные с идентификаторами символов, будут автоматически связаны с этими сочетаниями клавиш.  
  
 Эти библиотеки содержат предопределенные символы, которые будут отображаться как составная часть проекта:  
  
-   [Предопределенные символы MFC](../windows/mfc-predefined-symbols.md)  
  
-   [Предопределенные символы ATL](../windows/atl-predefined-symbols.md)  
  
-   [Предопределенные символы Win32](../windows/win32-predefined-symbols.md)  
  
    > [!NOTE]
    >  Предопределенные символы всегда доступны только для чтения.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в статье [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 Win32, MFC или ATL  
  
## См. также  
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)