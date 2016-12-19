---
title: "Selecting an Area of an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.image.editing"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Image editor [C++], image selection"
  - "Image editor [C++], selecting images"
  - "images [C++], selecting"
  - "cursors [C++], selecting areas of"
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Selecting an Area of an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инструменты выбора позволяют выделить область изображения, которую необходимо вырезать, скопировать, переместить, очистить, в которой необходимо обратить цвета или размеры которой необходимо изменить.  Инструмент **Прямоугольное выделение** позволяет выделить фрагмент изображения в форме прямоугольника.  Инструмент **Произвольное выделение** позволяет пользователю очертить от руки область, которую необходимо вырезать, скопировать и т. д.  
  
> [!NOTE]
>  Инструменты **Прямоугольное выделение** и **Произвольное выделение** представлены в панели инструментов [редактора изображений](../mfc/toolbar-image-editor-for-icons.md), также советуем ознакомиться с подсказками, которые связаны с каждой кнопкой панели инструментов **редактора изображений**.  
  
 Также можно создать свою собственную настраиваемую кисть из набора.  Дополнительные сведения см. в разделе [Создание настраиваемой кисти](../Topic/Creating%20a%20Custom%20Brush%20\(Image%20Editor%20for%20Icons\).md).  
  
### Выбор области изображения  
  
1.  В панели инструментов **редактора изображений** \(или в меню **Изображение**, команда **Инструменты**\) щелкните нужный инструмент выделения.  
  
2.  Поместите курсор на угол выделяемой области изображения.  Когда указатель мыши наведен на изображение, отображаются обрезные метки.  
  
3.  Перетащите курсор к противоположному углу выделяемой области.  Выделенные пиксели будут очерчены прямоугольником.  Все пиксели внутри прямоугольника и те, что перекрыты границами прямоугольника, относятся к выделенной области.  
  
4.  Отпустите кнопку мыши.  Выделенная область будет очерчена границами.  
  
### Выбор всего изображения полностью  
  
1.  Щелкните область изображения за пределами текущего выделения.  Фокус изображения изменится, в результате снова будет выделено все изображение целиком.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 None  
  
## См. также  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)