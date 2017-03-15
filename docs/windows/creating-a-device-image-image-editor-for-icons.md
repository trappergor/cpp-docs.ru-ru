---
title: "Creating a Device Image (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], creating"
  - "icons [C++], creating"
  - "display devices"
  - "display devices, creating image"
  - "images [C++], creating for display devices"
  - "icons [C++], inserting"
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Creating a Device Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При создании значка или курсора в редакторе изображений сначала появляется изображение стандартного типа \(32 × 32, 16 цветов для значков и 32 × 32, монохром для курсоров\).  Затем вы можете добавлять изображения различных размеров и типов к первоначальному значку или курсору, а также редактировать каждое дополнительное изображение, как это необходимо, для различных устройств отображения.  Кроме того, можно редактировать изображение, выполнив операции вырезания и вставки из существующего типа изображений или из растрового изображения, созданного в графической программе.  Дополнительные сведения о размерах значков для Windows см. в разделе [Значки](_win32_Icons_cpp) документации по Windows SDK.  
  
 При открытии значка или курсора в [редакторе изображений](../mfc/image-editor-for-icons.md), изображение наиболее точно соответствует текущему устройству отображения, открытому по умолчанию.  
  
### Создать новый значок или курсор  
  
1.  В [Представлении ресурсов](../windows/resource-view-window.md) щелкните правой кнопкой мыши нужный RC\-файл, а затем выберите в контекстном меню пункт **Вставить ресурс**.  \(Если выбранный RC\-файл уже содержит ресурс изображения, например курсор, можно просто щелкнуть правой кнопкой мыши папку **Курсор** и выбрать в контекстном меню пункт **Вставить курсор**.\)  
  
    > [!NOTE]
    >  Если в проекте нет RC\-файла, см. раздел [Создание нового файла скрипта ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В [диалоговом окне "Вставка ресурса"](../Topic/Add%20Resource%20Dialog%20Box.md) выберите **Значок** или **Курсор** и нажмите кнопку **Создать**.  Значки создаются со следующими параметрами: 32 × 32, 16 цветов.  Курсоры создаются со следующими параметрами: 32 × 32, монохромные \(2 цвета\).  
  
     Если значок плюс \(**\+**\) появляется рядом с ресурсом изображения в диалоговом окне **Вставка ресурса**, значит доступны шаблоны для этого ресурса.  Щелкните значок "плюс", чтобы развернуть список шаблонов, выберите шаблон и нажмите кнопку **Создать**.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 None  
  
## См. также  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)