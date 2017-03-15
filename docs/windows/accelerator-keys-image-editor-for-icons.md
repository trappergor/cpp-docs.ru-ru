---
title: "Accelerator Keys (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator keys"
  - "Image editor [C++], accelerator keys"
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Accelerator Keys (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ниже перечислены сочетания клавиш для команд редактора изображений, привязанные к клавишам по умолчанию.  Чтобы изменить сочетания клавиш, в меню **Сервис** щелкните **Параметры**, а затем щелкните **Клавиатура** в папке **Среда**.  Дополнительные сведения см. в разделе [Определение и настройка сочетаний клавиш](../Topic/Identifying%20and%20Customizing%20Keyboard%20Shortcuts%20in%20Visual%20Studio.md).  
  
> [!NOTE]
>  Доступные в диалоговых окнах параметры, а также названия и расположение команд меню могут отличаться от описанных в справке в зависимости от текущих параметров или версии.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
|Command|Разделы|Описание|  
|-------------|-------------|--------------|  
|Image.AirBrushTool|CTRL \+ A|Рисование с помощью воздушной кисти с выбранным размером и цветом.|  
|Image.BrushTool|CTRL \+ B|Рисование с помощью кисти с выбранной формой, размером и цветом.|  
|Image.CopyAndOutlineSelection|CTRL \+ SHIFT \+ U|Копирование текущего выделенного фрагмента и формирование его контура.  Если в выделенной области находится цвет фона, он будет исключен, если выбран [прозрачный фон](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|  
|Image.DrawOpaque|CTRL \+ J|Включение или отключение [прозрачности](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) выделенного фрагмента.|  
|Image.EllipseTool|CTRL \+ P|Рисование эллипса линией выбранной толщины и цвета.|  
|Image.EraserTool|CTRL \+ SHIFT \+ I|Удаление части рисунка \(с текущим цветом фона\).|  
|Image.FilledEllipseTool|CTRL \+ SHIFT \+ ALT \+ P|Рисование эллипса с заливкой.|  
|Image.FilledRectangleTool|CTRL \+ SHIFT \+ ALT \+ R|Рисование прямоугольника с заливкой.|  
|Image.FilledRoundRectangleTool|CTRL \+ SHIFT \+ ALT \+ W|Рисование скругленного прямоугольника с заливкой.|  
|Image.FillTool|CTRL \+ F|Заливка области.|  
|Image.FlipHorizontal|CTRL \+ H|Горизонтальное зеркальное отражение изображения или выбранного фрагмента.|  
|Image.FlipVertical|SHIFT \+ ALT \+ H|Вертикальное зеркальное отражение изображения или выделенного фрагмента.|  
|Image.LargerBrush|CTRL \+ \=|Увеличение размера кисти на один пиксель в каждом направлении.  Чтобы уменьшить размер кисти, см. Image.SmallerBrush в этой таблице.|  
|Image.LineTool|CTRL \+ L|Рисование прямой линии с выбранной формой, размером и цветом.|  
|Image.MagnificationTool|CTRL \+ M|Включение инструмента **Увеличить**, с помощью которого можно увеличивать фрагменты изображения.|  
|Image.Magnify|CTRL \+ SHIFT \+ M|Переключение между текущим масштабом и масштабом 1:1.|  
|Image.NewImageType|INSERT|Открытие диалогового окна [Создание типа изображений \<название\_устройства\>](../mfc/new-device-image-type-dialog-box-image-editor-for-icons.md), с помощью которого можно создать изображение другого типа.|  
|Image.NextColor|CTRL \+ \]<br /><br /> \- или \-<br /><br /> CTRL \+ СТРЕЛКА ВПРАВО|Изменение основного цвета на следующий цвет в палитре.|  
|Image.NextRightColor|CTRL \+ SHIFT \+ \]<br /><br /> \- или \-<br /><br /> SHIFT \+ CTRL \+ СТРЕЛКА ВПРАВО|Изменение цвета фона на следующий цвет в палитре.|  
|Image.OutlinedEllipseTool|SHIFT \+ ALT \+ P|Рисование эллипса с заливкой и с контуром.|  
|Image.OutlinedRectangleTool|SHIFT \+ ATL \+ R|Рисование прямоугольника с заливкой и с контуром.|  
|Image.OutlinedRoundRectangleTool|SHIFT \+ ALT \+ W|Рисование скругленного прямоугольника с заливкой и с контуром.|  
|Image.PencilTool|CTRL \+ I|Рисование при помощи карандаша \(толщина линии — 1 пиксель\).|  
|Image.PreviousColor|CTRL \+ \[<br /><br /> \- или \-<br /><br /> CTRL \+ СТРЕЛКА ВЛЕВО|Изменение основного цвета на предыдущий цвет в палитре.|  
|Image.PreviousRightColor|CTRL \+ SHIFT \+ \[<br /><br /> \- или \-<br /><br /> CTRL \+ SHIFT \+ СТРЕЛКА ВЛЕВО|Изменение цвета фона на предыдущий цвет в палитре.|  
|Image.RectangleSelectionTool|SHIFT \+ ALT \+ S|Выделение прямоугольного фрагмента изображения для перемещения, копирования или изменения.|  
|Image.RectangleTool|ATL \+ R|Рисование прямоугольника линией выбранной толщины и цвета.|  
|Image.Rotate90Degrees|CTRL \+ SHIFT \+ H|Поворот изображения или выделенного фрагмента на 90 градусов.|  
|Image.RoundedRectangleTool|ALT \+ W|Рисование скругленного прямоугольника линией выбранной толщины и цвета.|  
|Image.ShowGrid|CTRL \+ ALT \+ S|Включение или отключение пиксельной сетки \(аналогично включению или отключению параметра **Пиксельная сетка** в диалоговом окне [Настройка сетки](../mfc/grid-settings-dialog-box-image-editor-for-icons.md)\).|  
|Image.ShowTileGrid|CTRL \+ SHIFT \+ ALT \+ S|Включение или отключение мозаичного представления \(аналогично включению или отключению параметра **Мозаичная сетка** в диалоговом окне [Настройка сетки](../mfc/grid-settings-dialog-box-image-editor-for-icons.md)\).|  
|Image.SmallBrush|CTRL \+ .  \(точка\)|Уменьшение размера **кисти** до 1 пиксели.  \(Также см. Image.LargerBrush и Image.SmallerBrush в этой таблице.\)|  
|Image.SmallerBrush|CTRL \+ МИНУС|Уменьшение размера кисти на один пиксель в каждом направлении.  Чтобы увеличить размер кисти, см. Image.LargerBrush в этой таблице.|  
|Image.TextTool|CTRL \+ T|Открытие диалогового окна [Текст](../Topic/Text%20Tool%20Dialog%20Box%20\(Image%20Editor%20for%20Icons\).md).|  
|Image.UseSelectionAsBrush|CTRL \+ U|Рисование с использованием выделенного фрагмента в качестве кисти.|  
|Image.ZoomIn|CTRL \+ SHIFT \+ .  \(точка\)<br /><br /> \- или \-<br /><br /> CTRL \+ СТРЕЛКА ВВЕРХ|Увеличение масштаба текущего представления.|  
|Image.ZoomOut|CTRL \+ , \(запятая\)<br /><br /> \- или \-<br /><br /> CTRL \+ СТРЕЛКА ВНИЗ|Уменьшение масштаба текущего представления.|  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 None  
  
## См. также  
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)