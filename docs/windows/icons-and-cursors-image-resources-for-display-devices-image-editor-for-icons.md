---
title: "Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons) | Microsoft Docs"
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
  - "image resources, display devices"
  - "icons [C++], creating"
  - "cursors [C++], types"
  - "icons [C++]"
  - "Image editor [C++], icons and cursors"
  - "cursors [C++]"
  - "display devices, creating icons for"
  - "cursors [C++], hot spots"
  - "icons [C++], types"
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Значки и курсоры представляют собой графические ресурсы, которые могут состоять из нескольких изображений разных размеров, использующих разные цветовые схемы, в зависимости от типа устройства отображения. Кроме того, у курсоров есть "активная точка" — точка, которая используется системой Windows для отслеживания позиции курсора. Как и в случае с растровыми и другими изображениями, для создания и редактирования значков и курсоров используется редактор изображений.  
  
 При создании значка или курсора в редакторе изображений сначала появляется изображение стандартного типа. Это изображение сначала заполняется цветом экрана \(прозрачным\). Если изображение является курсором, его активная точка изначально находится в левом верхнем углу \(и имеет координаты 0,0\).  
  
 По умолчанию в редакторе изображений можно создавать дополнительные изображения для устройств, представленных в таблице ниже. Чтобы создать изображения для других устройств, необходимо задать ширину, высоту и количество цветов в [диалоговом окне "Настраиваемое изображение"](../mfc/custom-image-dialog-box-image-editor-for-icons.md).  
  
> [!NOTE]
>  Редактор изображений позволяет просматривать 32\-разрядные изображения, но не позволяет их редактировать.  
  
|Цвет|Ширина \(в пикселях\)|Высота \(в пикселях\)|  
|----------|---------------------------|---------------------------|  
|Монохромный|16|16|  
|Монохромный|32|32|  
|Монохромный|48|48|  
|Монохромный|64|64|  
|Монохромный|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [Создание изображения \(значка или курсора\) для устройства](../mfc/creating-a-device-image-image-editor-for-icons.md)  
  
-   [Добавление изображения для другого устройства отображения](../mfc/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [Копирование изображения устройства](../mfc/copying-a-device-image-image-editor-for-icons.md)  
  
-   [Удаление изображения устройства](../Topic/Deleting%20a%20Device%20Image%20\(Image%20Editor%20for%20Icons\).md)  
  
-   [Создание прозрачных областей или областей с обращенными цветами на изображениях устройств](../mfc/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [Создание 256\-цветного значка или курсора](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [Настройка активной точки курсора](../Topic/Setting%20a%20Cursor's%20Hot%20Spot%20\(Image%20Editor%20for%20Icons\).md)  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 Нет  
  
## См. также  
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [Значки](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [Курсоры](http://msdn.microsoft.com/library/windows/desktop/ms646970)