---
title: "Specifying the Location and Size of a Dialog Box | Microsoft Docs"
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
  - "dialog boxes, size"
  - "dialog boxes, positioning"
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Specifying the Location and Size of a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Местоположение и размер диалогового окна, а также местоположение и размер элементов управления в этом окне, измеряются в единицах диалогового окна.  Значения для отдельных элементов управления и диалогового окна появляются в нижней правой части строки состояния Visual Studio, когда разработчик выбирает эти элементы.  
  
 Существует три свойства, которые можно установить в [окне "Свойства"](../Topic/Properties%20Window.md), чтобы определить, в каком месте экрана будет появляться диалоговое окно.  Свойство "Центр" является логическим. Если его значение равно True, диалоговое окно всегда будет появляться в центре экрана.  Если для него задано значение False, можно задать свойства XPos и YPos, чтобы явно определить, в каком месте экрана будет появляться диалоговое окно.  Свойства положения представляют собой значения смещения от левого верхнего угла области просмотра, координаты которого определены как {X\=0, Y\=0}.  Положение также зависит от свойства **Абсолютное выравнивание**: если его значение равно True, координаты отсчитываются относительно экрана; если False — относительно окна владельца диалогового окна.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 Win32  
  
## См. также  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)