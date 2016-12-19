---
title: "How to: Import and Export Resources | Microsoft Docs"
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
  - "vs.resvw.resource.importing"
  - "vc.resvw.resource.importing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], exporting"
  - "graphics [C++], exporting"
  - "graphics [C++], importing"
  - "resources [Visual Studio], importing"
  - "bitmaps [C++], importing and exporting"
  - "toolbars [C++], importing"
  - "images [C++], importing"
  - "toolbars [C++], exporting"
  - "cursors [C++], importing and exporting"
  - "images [C++], exporting"
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Import and Export Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Графические ресурсы \(растровые изображения, значки, курсоры, панели инструментов\), HTML\-файлы и пользовательские ресурсы можно импортировать для использования в Visual C\+\+.  Эти же типы ресурсов можно экспортировать из проекта Visual C\+\+ в виде отдельных файлов, которые можно использовать за пределами среды разработки.  
  
> [!NOTE]
>  Такие типы ресурсов, как сочетания клавиш, диалоговые окна и таблицы строк, нельзя импортировать или экспортировать, поскольку они не являются типами отдельных файлов.  
  
### Импорт отдельного ресурса в текущий файл ресурса  
  
1.  В [представлении ресурсов](../windows/resource-view-window.md) щелкните правой кнопкой мыши узел файла описания ресурсов \(\* .rc\), к которому требуется добавить ресурс.  
  
2.  В контекстном меню выберите команду **Импорт**.  
  
3.  Найдите и выберите файл растрового изображения \(.bmp\), значка \(.ico\), курсора \(.cur\), HTML\-файл \(.htm\) или другой файл, который требуется импортировать.  
  
4.  Нажмите кнопку **ОК** для добавления ресурса в выбранный в представлении **ресурсов** файл.  
  
    > [!NOTE]
    >  Процедура импорта выполняется одинаково независимо от конкретного типа выбранного ресурса.  Импортированный ресурс автоматически добавляется в соответствующий узел для этого типа ресурса.  
  
### Экспорт растрового изображения, значка или курсора в отдельный файл \(для использования за пределами Visual C\+\+\)  
  
1.  В представлении **ресурсов** щелкните правой кнопкой мыши ресурс, который требуется экспортировать.  
  
2.  В контекстном меню выберите команду **Экспорт**.  
  
3.  В диалоговом окне **Экспорт ресурса** оставьте предложенное имя файла или введите новое.  
  
4.  Откройте папку, в которую вы хотите сохранить файл, и нажмите кнопку **Экспорт**.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в статье [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)