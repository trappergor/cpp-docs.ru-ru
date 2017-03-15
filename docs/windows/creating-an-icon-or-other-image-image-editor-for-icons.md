---
title: "Creating an Icon or Other Image (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.bitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bitmaps [C++]"
  - "images [C++], creating"
  - "resource toolbars"
  - "resources [Visual Studio], creating images"
  - "bitmaps [C++], creating"
  - "graphics [C++], creating"
  - "Image editor [C++], creating images"
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Creating an Icon or Other Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вы можете создать новое изображение \(растровое изображение, значок, курсор или панель инструментов\), а затем в редакторе изображений изменить его вид.  Вы также можете создать новый растровое изображение на основе [шаблона](../Topic/How%20to:%20Use%20Resource%20Templates.md).  
  
### Добавить новый ресурс изображения в неуправляемый проект C\+\+  
  
1.  В [Представлении ресурсов](../windows/resource-view-window.md) щелкните правой кнопкой мыши нужный RC\-файл, а затем выберите в контекстном меню пункт **Вставить ресурс**.  \(Если выбранный RC\-файл уже содержит ресурс изображения, например курсор, можно просто щелкнуть правой кнопкой мыши папку **Курсор** и выбрать в контекстном меню пункт **Вставить курсор**.\)  
  
    > [!NOTE]
    >  **Примечание.** Если в проекте еще нет RC\-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В диалоговом окне [Вставка ресурса](../Topic/Add%20Resource%20Dialog%20Box.md) выберите тип ресурса изображения, который хотите создать \(**растровое изображение**, например\), затем щелкните **Новый**.  
  
     Если значок плюс \(**\+**\) появляется рядом с ресурсом изображения в диалоговом окне **Вставка ресурса**, значит доступны шаблоны для этого ресурса.  Щелкните значок "плюс", чтобы развернуть список шаблонов, выберите шаблон и нажмите кнопку **Создать**.  
  
### Добавить новый ресурс изображения в проект на языке программирования .NET  
  
1.  В окне **Обозреватель решений** щелкните правой кнопкой мыши папку проекта \(например, **WindowsApplication1**\).  
  
2.  В контекстном меню щелкните команду **Добавить**, а затем выберите **Добавить новый элемент**.  
  
3.  В панели **Категории** разверните папку **Элементы локального проекта**, затем выберите **Ресурсы**.  
  
4.  В панели **Шаблоны** выберите тип ресурса, который необходимо добавить в проект.  
  
     Новый ресурс будет добавлен в проект обозревателя решений, после чего будет открыт в [Редакторе изображений](../mfc/image-editor-for-icons.md).  Теперь вы можете использовать все доступные инструменты Редактора изображений, чтобы редактировать изображение.  Дополнительные сведения о добавлении изображений в управляемый проект см. раздел [Загрузка рисунка в режиме разработки](../Topic/How%20to:%20Load%20a%20Picture%20Using%20the%20Designer%20\(Windows%20Forms\).md).  
  
    > [!NOTE]
    >  Все управляемые ресурсы, которые нужно редактировать, должны быть связанными ресурсами.  Редакторы ресурсов Visual Studio не поддерживают редактирование внедренных ресурсов.  Дополнительную информацию см. в разделе [Создание файлов ресурсов](../Topic/Creating%20Resource%20Files%20for%20Desktop%20Apps.md) в *Руководстве разработчика по .NET Framework*.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 None  
  
## См. также  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Converting Bitmaps to Toolbars](../mfc/converting-bitmaps-to-toolbars.md)   
 [Creating New Toolbars](../mfc/creating-new-toolbars.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)