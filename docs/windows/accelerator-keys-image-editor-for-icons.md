---
title: "Сочетания клавиш (редактор изображений для значков) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c992ed83f5c86fdd770bda8f9970ff98a90c2722
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-keys-image-editor-for-icons"></a>Сочетания клавиш (редактор изображений для значков)
Ниже перечислены сочетания клавиш для команд редактора изображений, привязанных к ключи по умолчанию. Чтобы изменить сочетания клавиш, нажмите кнопку **параметры** на **средства** меню и нажмите кнопку **клавиатуры** под **среды** папки. Дополнительные сведения см. в разделе [Определение и настройка сочетаний клавиш в Visual Studio](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).  
  
> [!NOTE]
>  Доступные в диалоговых окнах параметры, а также названия и расположение команд меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
|Команда|Клавиши|Описание:|  
|-------------|----------|-----------------|  
|Image.AirBrushTool|CTRL + A|Рисование распылителем с помощью выбранного размера и цвета.|  
|Image.BrushTool|CTRL + B|Рисование с помощью кисти с выбранной формой, размер и цвет.|  
|Image.CopyAndOutlineSelection|CTRL + SHIFT + U|Копирование текущего выделенного фрагмента и формирование его контура. Если в текущем выделенном фрагменте содержится цвет фона, он будет исключен, если у вас есть [прозрачный](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) выбранных.|  
|Image.DrawOpaque|CTRL + J|Делает текущее выделение либо [прозрачный или непрозрачный](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|  
|Image.EllipseTool|CTRL + P|Рисование эллипса с выбранной толщины и цвета.|  
|Image.EraserTool|CTRL + SHIFT + I|Удаление части изображения (с текущим цветом фона).|  
|Image.FilledEllipseTool|CTRL + SHIFT + ALT + P|Рисование эллипса с заливкой.|  
|Image.FilledRectangleTool|CTRL + SHIFT + ALT + R|Рисование прямоугольника с заливкой.|  
|Image.FilledRoundRectangleTool|CTRL + SHIFT + ALT + W|Рисование скругленного прямоугольника с заливкой.|  
|Image.FillTool|CTRL + F|Заливка области.|  
|Image.FlipHorizontal|CTRL+H|Горизонтальное зеркальное отражение изображения или выбранного фрагмента.|  
|Image.FlipVertical|SHIFT + ALT + H|Вертикальное зеркальное отражение изображения или выделенного фрагмента.|  
|Image.LargerBrush|CTRL + =|Увеличение размера кисти на один пиксель в каждом направлении. Чтобы уменьшить размер кисти, см. Image.SmallerBrush в этой таблице.|  
|Image.LineTool|CTRL+L|Рисование прямой линии с выбранной формой, размером и цветом.|  
|Image.MagnificationTool|CTRL + M|Активирует **Magnify** средства, которое позволяет увеличивать фрагменты изображения.|  
|Image.Magnify|CTRL + SHIFT + M|Переключение между текущим масштабом и масштабом 1:1.|  
|Image.NewImageType|INSERT|Запускает [New \<устройства > тип изображения диалогового](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md) с помощью которого можно создавать изображения для другого типа.|  
|Image.NextColor|CTRL +]<br /><br /> -или-<br /><br /> CTRL + СТРЕЛКА ВПРАВО|Изменение основного цвета на следующий цвет в палитре.|  
|Image.NextRightColor|CTRL + SHIFT +]<br /><br /> -или-<br /><br /> SHIFT + CTRL + СТРЕЛКА ВПРАВО|Изменение цвета фона на следующий цвет в палитре.|  
|Image.OutlinedEllipseTool|SHIFT + ALT + P|Рисование эллипса с заливкой и с контуром.|  
|Image.OutlinedRectangleTool|SHIFT + ATL + R|Рисование прямоугольника с заливкой и с контуром.|  
|Image.OutlinedRoundRectangleTool|SHIFT + ALT + W|Рисование скругленного прямоугольника с заливкой и с контуром.|  
|Image.PencilTool|CTRL + I|Рисование при помощи карандаша (толщина линии — 1 пиксель).|  
|Image.PreviousColor|CTRL + [<br /><br /> -или-<br /><br /> CTRL + СТРЕЛКА ВЛЕВО|Изменение основного цвета на предыдущий цвет в палитре.|  
|Image.PreviousRightColor|CTRL + SHIFT + [<br /><br /> -или-<br /><br /> SHIFT + CTRL + СТРЕЛКА ВЛЕВО|Изменение цвета фона на предыдущий цвет в палитре.|  
|Image.RectangleSelectionTool|SHIFT + ALT + S|Выделение прямоугольного фрагмента изображения для перемещения, копирования или изменения.|  
|Image.RectangleTool|ATL + R|Рисование прямоугольника с выбранной толщины и цвета.|  
|Image.Rotate90Degrees|CTRL + SHIFT + H|Поворот изображения или выделенного фрагмента на 90 градусов.|  
|Image.RoundedRectangleTool|ALT + W|Рисование скругленного прямоугольника с выбранной толщины и цвета.|  
|Image.ShowGrid|CTRL + ALT + S|Переключает пиксельной сетки (Установка или снятие **пиксельной сетке** в диалоговом окне [диалоговое окно «Параметры сетки»](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|  
|Image.ShowTileGrid|CTRL + SHIFT + ALT + S|Переключает плиточной сетки (Установка или снятие **ячеек** в диалоговом окне [диалоговое окно «Параметры сетки»](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|  
|Image.SmallBrush|CTRL +. (точка)|Уменьшает **кисти** размер на один пиксель. (Также см. Image.LargerBrush и Image.SmallerBrush в этой таблице.)|  
|Image.SmallerBrush|CTRL + - (минус)|Уменьшение размера кисти на один пиксель в каждом направлении. Чтобы увеличить размер кисти, см. Image.LargerBrush в этой таблице.|  
|Image.TextTool|CTRL + T|Открывает [диалогового текст](../windows/text-tool-dialog-box-image-editor-for-icons.md).|  
|Image.UseSelectionAsBrush|CTRL + U|Рисование с использованием выделенного фрагмента в качестве кисти.|  
|Image.ZoomIn|CTRL + SHIFT +. (точка)<br /><br /> -или-<br /><br /> CTRL + СТРЕЛКА ВВЕРХ|Увеличение масштаба текущего представления.|  
|Image.ZoomOut|CTRL +, (запятая)<br /><br /> -или-<br /><br /> CTRL + СТРЕЛКА ВНИЗ|Уменьшение масштаба текущего представления.|  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)

