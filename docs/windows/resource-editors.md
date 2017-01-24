---
title: "Resource Editors | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.editors.resource"
  - "vc.resvw.resource.editors"
  - "vs.resvw.resource.editors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors [C++], resource"
  - "editors [C++]"
  - "resource editors"
  - "Windows [C++], application resource editing"
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
caps.latest.revision: 16
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Resource Editors
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Редактор ресурсов представляет собой специализированную среду для создания и изменения ресурсов, включенных в проект Visual Studio. Редакторы ресурсов Visual Studio используют общий набор способов и интерфейсов, упрощая и ускоряя создание и изменение ресурсов приложения. Редакторы ресурсов позволяют [просматривать и изменять ресурсы в соответствующем редакторе](../mfc/viewing-and-editing-resources-in-a-resource-editor.md), а также [предварительно просматривать ресурсы](../mfc/previewing-resources.md).  
  
 Соответствующий редактор открывается автоматически при создании или открытии ресурса.  
  
 **Примечание**.   Поскольку в проектах управляемого кода не используются файлы описания ресурсов, ресурсы необходимо открывать из **обозревателя решений**. Для работы с файлами ресурсов в управляемых проектах можно использовать [редактор изображений](../mfc/image-editor-for-icons.md) и [двоичный редактор](../mfc/binary-editor.md). Все управляемые ресурсы, которые нужно редактировать, должны быть связанными ресурсами. Редакторы ресурсов Visual Studio не поддерживают редактирование внедренных ресурсов.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
|Редактор|Редактируемый элемент|  
|--------------|---------------------------|  
|[Редактор сочетаний клавиш](../Topic/Accelerator%20Editor.md)|Таблицы сочетаний клавиш в проектах Visual C\+\+|  
|[Двоичный редактор](../mfc/binary-editor.md)|Двоичные данные и настраиваемые ресурсы в проектах Visual C\+\+, Visual Basic или Visual C\#|  
|[Редактор диалоговых окон](../mfc/dialog-editor.md)|Диалоговые окна в проектах Visual C\+\+|  
|[Конструктор HTML](../Topic/HTML%20Designer.md)|HTML\-страницы в режиме конструктора и в представлении HTML Предупреждение. Нельзя вносить изменения в HTML\-страницы, которые находятся в файлах EXE или DLL, так как изменения не импортируются обратно в EXE\- или DLL\-файл.|  
|[Редактор изображений](../mfc/image-editor-for-icons.md)|Точечные рисунки, значки, курсоры и другие файлы изображений в проектах Visual C\+\+, Visual Basic или Visual C\#|  
|[Редактор меню](../Topic/Menu%20Editor.md)|Ресурсы меню в проектах Visual C\+\+|  
|[Редактор ленты \(Ribbon\)](../mfc/ribbon-designer-mfc.md)|Ресурсы ленты в проектах MFC|  
|[Редактор строк](../mfc/string-editor.md)|Таблицы строк в проектах Visual C\+\+|  
|[Редактор панелей инструментов](../mfc/toolbar-editor.md)|Ресурсы панелей инструментов в проектах Visual C\+\+ Редактор панелей инструментов входит в состав редактора изображений.|  
|[Редактор сведений о версии](../mfc/version-information-editor.md)|Сведения о версиях в проектах Visual C\+\+|  
  
## Требования  
 Нет  
  
## См. также  
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Меню и другие ресурсы](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)