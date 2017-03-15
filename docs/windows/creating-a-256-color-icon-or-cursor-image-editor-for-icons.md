---
title: "Creating a 256-Color Icon or Cursor (Image Editor for Icons) | Microsoft Docs"
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
  - "256-color palette"
  - "cursors, color"
  - "colors, icons"
  - "colors, cursors"
  - "icons, color"
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Creating a 256-Color Icon or Cursor (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

С помощью редактора изображений можно создавать значки и курсоры большого размера \(64 × 64\), выбирая нужные цвета из 256\-цветной палитры.  После создания ресурса выбирается стиль изображения устройства.  
  
### Создание 256\-цветного значка или курсора  
  
1.  В [Представлении ресурсов](../windows/resource-view-window.md) щелкните правой кнопкой мыши нужный RC\-файл, а затем выберите в контекстном меню пункт **Вставить ресурс**.  \(Если выбранный RC\-файл уже содержит ресурс изображения, например курсор, можно просто щелкнуть правой кнопкой мыши папку **Курсор** и выбрать в контекстном меню пункт **Вставить курсор**.\)  
  
     **Примечание.** Если в проекте еще нет RC\-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В [диалоговом окне "Вставка ресурса"](../Topic/Add%20Resource%20Dialog%20Box.md) выберите **Значок** или **Курсор** и нажмите кнопку **Создать**.  
  
3.  В меню **Изображение** щелкните **Создать изображение устройства**.  
  
4.  Выберите нужный стиль 256\-цветного изображения.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 None  
  
## См. также  
 [Using the 256\-Color Palette](../Topic/Using%20the%20256-Color%20Palette%20\(Image%20Editor%20for%20Icons\).md)   
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)