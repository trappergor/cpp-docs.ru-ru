---
title: "Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], screen regions"
  - "inverse colors, device images"
  - "transparent regions, device images"
  - "transparency, device images"
  - "Image editor [C++], device images"
  - "inverse regions, device images"
  - "cursors [C++], transparent regions"
  - "screen colors"
  - "regions, transparent"
  - "icons [C++], transparent regions"
  - "display devices, transparent and screen regions"
  - "transparent regions in devices"
  - "regions, inverse"
  - "colors [C++], Image editor"
  - "device projects, transparent images"
  - "icons [C++], screen regions"
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Изначально в [редакторе изображений](../mfc/image-editor-for-icons.md) изображения значков и курсоров имеют атрибут прозрачности.  Такие изображения, как правило, имеют прямоугольную форму, но выглядят иначе, так как некоторые области изображения прозрачны. В результате сквозь эти области значка или курсора просматривается основное изображение на экране.  При перетаскивании значка, некоторые его области могут отображаться с преобразованными цветами.  Чтобы получить такой эффект, необходимо установить в окне [Цвета](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md) свойства "Цвет экрана" и "Инвертированный цвет".  
  
 Свойства "Цвет экрана" и "Инвертированный цвет", которые применяются к значкам и курсорам, позволяют определить форму и цвет производных изображений, либо обозначить области с обращенными цветами.  Для обозначения областей изображения с этими атрибутами используются разные цвета.  В процессе редактирования можно изменить цвета, соответствующие атрибутам "Цвет экрана" и "Инвертированный цвет".  При этом внешний вид значка или курсора в приложении не изменится.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Создание прозрачных областей или областей с обращенными цветами  
  
1.  В окне **Цвета** щелкните селектор **Цвет экрана** или селектор **Инвертированный цвет**.  
  
2.  Примените выбранный цвет экрана или инвертированный цвет с помощью инструмента рисования.  Дополнительные сведения об инструментах рисования см. в разделе [Using a Drawing Tool](../mfc/using-a-drawing-tool-image-editor-for-icons.md).  
  
### Изменение цвета экрана или инвертированного цвета  
  
1.  Выберите селектор **Цвет экрана** или селектор **Инвертированный цвет**.  
  
2.  Выберите цвет в палитре **Цвета** в окне **Цвета**.  
  
     В другом селекторе дополняющий цвет будет выбран автоматически.  
  
    > [!TIP]
    >  Если дважды щелкнуть селектор "Цвет экрана" или селектор "Инвертированный цвет", откроется диалоговое окно [Выбор цвета](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 None  
  
## См. также  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)