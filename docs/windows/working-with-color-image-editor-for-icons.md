---
title: "Working with Color (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.image.color"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "images [C++], background colors"
  - "Image editor [C++], Colors Palette"
  - "colors [C++], image"
  - "Colors Palette, Image editor"
  - "palettes, Image editor colors"
  - "foreground colors, Image editor"
  - "colors [C++]"
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Working with Color (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В редакторе изображений есть множество функций, позволяющих настраивать оттенки и управлять ими.  Можно задать основной цвет или цвет фона, заполнить цветом выделенную область, выбрать на изображении образец цвета, который затем будет использоваться в качестве основного цвета или цвета фона.  Для создания изображений можно использовать инструмента в [панели инструментов редактора изображений](../mfc/toolbar-image-editor-for-icons.md), а также цветовую палитру в [окне выбора цвета](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md).  
  
 На цветовой палитре и в окне выбора цвета представлены все цвета, которые можно использовать для создания монохромных и 16\-цветных изображений.  В дополнение к 16 стандартным цветам можно создавать пользовательские оттенки.  При изменении цвета в палитре, этот цвет автоматически меняется и на изображении.  
  
 При работе с 256\-цветными изображениями значков и курсоров используется свойство "Цвет" в [окне свойств](../Topic/Properties%20Window.md).  Дополнительные сведения см. в разделе [Создание 256\-цветных изображений значков и курсоров](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).  
  
> [!NOTE]
>  Редактор изображений позволяет просматривать 32\-разрядные изображения, но не позволяет их редактировать.  
  
 Кроме того, можно создавать изображения True color.  Однако, образцы оттенков "true color" не отображаются на полной палитре в окне выбора цвета; они отображаются только в области определения основного цвета и цвета фона.  Оттенки "true color" можно создавать с помощью диалогового окна [Выбор цвета](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md).  Дополнительные сведения см. в разделе [Настройка или изменение цветов](../windows/customizing-or-changing-colors-image-editor-for-icons.md).  
  
 Пользовательские палитры можно сохранить на диске и загружать их при необходимости.  Цветовая палитра, которая использовалась в последнем рабочем сеансе, сохраняется в реестре и автоматически загружается при очередном запуске Visual Studio.  
  
-   [Выбор основного цвета и цвета фона](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [Заливка цветом выделенной области изображения](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [Выбор на изображении образца цвета для использования в другом фрагменте](../Topic/Picking%20up%20a%20Color%20from%20an%20Image%20to%20Use%20Elsewhere%20\(Image%20Editor%20for%20Icons\).md)  
  
-   [Выбор прозрачного и непрозрачного фона](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [Преобразование цветов в выделенной области](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [Настройка и изменение цветов](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [Сохранение и загрузка разных цветовых палитр](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [Окно выбора цвета](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 None  
  
## См. также  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Ресурсы](_win32_Resources)