---
title: "Drawing Lines or Closed Figures (Image Editor for Icons) | Microsoft Docs"
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
  - "closed figures, drawing"
  - "lines [C++], painting"
  - "lines [C++], drawing"
  - "Image editor [C++], drawing lines"
  - "shapes, drawing"
ms.assetid: 7edd86db-77b1-451f-8001-bbfed9c6304f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Drawing Lines or Closed Figures (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Все инструменты редактора изображений, предназначенные для рисования линий и замкнутых фигур, работают одинаковым образом: точку вставки следует поместить в одну из точек и протащить ее к другой точке.  В случае линий эти точки являются конечными точками.  В случае замкнутых фигур эти точки соответствуют противоположным углам ограничивающего прямоугольника.  
  
 Ширина рисуемых линий определяется текущим выбором кисти, а ширина пустых замкнутых фигур — текущим выбором ширины.  Линии и фигуры \(как пустые, так и закрашенные\) рисуются с использованием основного цвета, если будет нажата левая кнопка мыши, или с использованием цвета фона, если будет нажата правая кнопка мыши.  
  
### Чтобы нарисовать линию  
  
1.  На [панели инструментов редактора изображений](../mfc/toolbar-image-editor-for-icons.md) \(или в меню **Изображение**, команда **Инструменты**\) щелкните инструмент **Линия**.  
  
2.  При необходимости выберите цвета и кисть:  
  
    -   В области [Палитра цветов](../Topic/Colors%20Window%20\(Image%20Editor%20for%20Icons\).md) щелкните левой кнопкой мыши, чтобы выбрать основной цвет, или правой кнопкой мыши, чтобы выбрать цвет фона.  
  
    -   В области [Селектор вариантов](../mfc/toolbar-image-editor-for-icons.md) щелкните форму, представляющую нужную кисть.  
  
3.  Поместите указатель мыши в начальную точку линии.  
  
4.  Перетащите его к конечной точке.  
  
### Чтобы нарисовать замкнутую фигуру  
  
1.  В панели инструментов **Редактор изображений** \(или в меню **Изображение**, команда **Инструменты**\), щелкните какой\-либо инструмент **Рисование замкнутой фигуры**.  
  
     С помощью инструментов **Рисование замкнутой фигуры** создаются те фигуры, которые указаны на соответствующих им кнопках.  
  
2.  При необходимости выберите нужный цвет и ширину линии.  
  
3.  Переместите указатель мыши в один из углов прямоугольной области, в которой требуется нарисовать фигуру.  
  
4.  Перетащите указатель по диагонали к противоположному углу этой области.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 None  
  
## См. также  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)