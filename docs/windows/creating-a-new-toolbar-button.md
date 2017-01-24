---
title: "Creating a New Toolbar Button | Microsoft Docs"
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
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Toolbar editor, creating buttons"
  - "toolbar buttons (in Toolbar editor), button image"
  - "toolbar buttons (in Toolbar editor), creating"
  - "toolbar buttons (in Toolbar editor)"
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a New Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Создание новой кнопки панели инструментов  
  
1.  В [представлении ресурсов](../windows/resource-view-window.md) разверните папку ресурсов \(например Project1.rc\).  
  
    > [!NOTE]
    >  Если в проекте нет RC\-файла, см. раздел [Создание нового файла скрипта ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Разверните папку **Панель инструментов** и выберите редактируемую панель инструментов.  
  
3.  Назначьте идентификатор пустой кнопке в правом конце панели инструментов.  Это можно выполнить, редактируя свойство **Идентификатор** в [окне "Свойства"](../Topic/Properties%20Window.md).  Например, может понадобиться назначить кнопке меню тот же идентификатор, что и пункту меню.  В этом случае используйте раскрывающийся список, чтобы выбрать **Идентификатор** пункта меню.  
  
     —либо—  
  
     Выберите пустую кнопку в правом конце панели инструментов \(в области представления панели инструментов\) и начните рисование.  Назначается идентификатор команды кнопки по умолчанию \(ID\_BUTTON\<n\>\).  
  
 Можно также скопировать и вставить изображение на панель инструментов в качестве новой кнопки.  
  
#### Добавление изображения на панель инструментов в качестве новой кнопки  
  
1.  В [представлении ресурсов](../windows/resource-view-window.md) откройте панель инструментов, дважды щелкнув ее.  
  
2.  Далее, откройте изображение, которое нужно добавить на панель инструментов.  
  
    > [!NOTE]
    >  При открытии изображения в Visual Studio оно откроется в редакторе изображений.  Изображение можно также открыть в других графических программах.  
  
3.  В меню **Правка** выберите пункт **Копировать**.  
  
4.  Переключитесь на панель инструментов, щелкнув ее вкладку в верхней части окна исходного кода.  
  
5.  В меню **Правка** выберите команду **Вставить**.  
  
     Изображение появится в панели инструментов в виде новой кнопки.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Требования  
 MFC или ATL  
  
## См. также  
 [Toolbar Button Properties](../mfc/toolbar-button-properties.md)   
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)