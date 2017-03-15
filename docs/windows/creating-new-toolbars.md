---
title: "Creating New Toolbars | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "toolbars [C++], creating"
  - "Toolbar editor, creating new toolbars"
  - "Insert Resource"
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Creating New Toolbars
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Создание новой панели инструментов  
  
1.  В представлении **Ресурс** щелкните правой кнопкой мыши свой RC\-файл, затем выберите в контекстном меню пункт **Добавить ресурс**.  \(Если в RC\-файле уже есть панель инструментов, можно просто щелкнуть правой кнопкой мыши папку **Панель инструментов** и выбрать в контекстном меню пункт **Вставить панель инструментов**.\)  
  
     **Примечание.** Если в проекте еще нет RC\-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В диалоговом окне **Добавление ресурса** выберите **Панель инструментов** в списке **Тип ресурса**, а затем нажмите кнопку **Создать**.  
  
     Если рядом с типом ресурса **Панель инструментов** появляется знак "плюс" \(\+\), то доступны шаблоны панелей инструментов.  Щелкните значок "плюс", чтобы развернуть список шаблонов, выберите шаблон и нажмите кнопку **Создать**.  
  
     \- или \-  
  
3.  [Преобразование существующего растрового изображения в панель инструментов](../mfc/converting-bitmaps-to-toolbars.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 MFC или ATL  
  
## См. также  
 [Toolbar Editor](../mfc/toolbar-editor.md)