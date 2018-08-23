---
title: Сочетания клавиш (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 09597e0aff65e8bc2e8f9c92452c80ea4b7618fa
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602110"
---
# <a name="accelerator-keys-image-editor-for-icons"></a>Сочетания клавиш (редактор изображений для значков)

Ниже приведены сочетания клавиш для команд редактора изображений, привязанных к ключи по умолчанию. Чтобы изменить сочетания клавиш, нажмите кнопку **параметры** на **средства** меню и выберите **клавиатуры** под **среды** папки. Дополнительные сведения см. в разделе [Определение и настройка сочетаний клавиш в Visual Studio](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

> [!NOTE]
> Доступные в диалоговых окнах параметры, а также названия и расположение команд меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).

|Команда|Клавиши|Описание:|
|-------------|----------|-----------------|
|Image.AirBrushTool|**CTRL** + **A**|Рисование с помощью воздушной кисти с выбранным размером и цветом.|
|Image.BrushTool|**CTRL** + **B**|Рисование с помощью кисти с выбранной формой, размер и цвет.|
|Image.CopyAndOutlineSelection|**CTRL** + **Shift** + **U**|Копирование текущего выделенного фрагмента и формирование его контура. Если в текущее выделение находится цвет фона, он будет исключен, если у вас есть [прозрачного](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) выбранного.|
|Image.DrawOpaque|**CTRL** + **J**|Делает текущее выделение либо [прозрачный или непрозрачный](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|
|Image.EllipseTool|**CTRL** + **P**|Рисование эллипса линией выбранной толщины и цвета.|
|Image.EraserTool|**CTRL** + **SHIFT** + **I**|Удаление части изображения (с текущим цветом фона).|
|Image.FilledEllipseTool|**CTRL** + **Shift** + **Alt** + **P**|Рисование эллипса с заливкой.|
|Image.FilledRectangleTool|**CTRL** + **Shift** + **Alt** + **R**|Рисование прямоугольника с заливкой.|
|Image.FilledRoundRectangleTool|**CTRL** + **Shift** + **Alt** + **W**|Рисование скругленного прямоугольника с заливкой.|
|Image.FillTool|**CTRL** + **F**|Заливка области.|
|Image.FlipHorizontal|**CTRL** + **H**|Горизонтальное зеркальное отражение изображения или выбранного фрагмента.|
|Image.FlipVertical|**SHIFT**+ **Alt** + **H**|Вертикальное зеркальное отражение изображения или выделенного фрагмента.|
|Image.LargerBrush|**CTRL** + **=**|Увеличение размера кисти на один пиксель в каждом направлении. Чтобы уменьшить размер кисти, см. Image.SmallerBrush в этой таблице.|
|Image.LineTool|**CTRL** + **L**|Рисование прямой линии с выбранной формой, размером и цветом.|
|Image.MagnificationTool|**CTRL** + **M**|Активирует **увеличить** средство, которое позволяет увеличивать фрагменты рисунка.|
|Image.Magnify|**CTRL** + **SHIFT** + **M**|Переключение между текущим масштабом и масштабом 1:1.|
|Image.NewImageType|**Вставить**|Запускает [New \<устройства > тип изображения диалоговое окно](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md) с помощью которого можно создать изображение другого типа.|
|Image.NextColor|**Ctrl** + **]**<br /><br /> -или-<br /><br /> **CTRL** + **Стрелка вправо**|Изменение основного цвета на следующий цвет в палитре.|
|Image.NextRightColor|**Ctrl** + **Shift** + **]**<br /><br /> -или-<br /><br /> **SHIFT** + **Ctrl** + **Стрелка вправо**|Изменение цвета фона на следующий цвет в палитре.|
|Image.OutlinedEllipseTool|**SHIFT** + **Alt** + **P**|Рисование эллипса с заливкой и с контуром.|
|Image.OutlinedRectangleTool|**SHIFT** + **Alt** + **R**|Рисование прямоугольника с заливкой и с контуром.|
|Image.OutlinedRoundRectangleTool|**SHIFT** + **Alt** + **W**|Рисование скругленного прямоугольника с заливкой и с контуром.|
|Image.PencilTool|**CTRL** + **I**|Рисование при помощи карандаша (толщина линии — 1 пиксель).|
|Image.PreviousColor|**Ctrl** + **[**<br /><br /> -или-<br /><br /> **CTRL** + **стрелка влево**|Изменение основного цвета на предыдущий цвет в палитре.|
|Image.PreviousRightColor|**Ctrl** + **Shift** + **[**<br /><br /> -или-<br /><br /> **SHIFT** + **Ctrl** + **стрелка влево**|Изменение цвета фона на предыдущий цвет в палитре.|
|Image.RectangleSelectionTool|**SHIFT** + **Alt** + **S**|Выделение прямоугольного фрагмента изображения для перемещения, копирования или изменения.|
|Image.RectangleTool|ATL + R|Рисование прямоугольника линией выбранной толщины и цвета.|
|Image.Rotate90Degrees|**CTRL** + **SHIFT** + **H**|Поворот изображения или выделенного фрагмента на 90 градусов.|
|Image.RoundedRectangleTool|**ALT** + **W**|Рисование скругленного прямоугольника линией выбранной толщины и цвета.|
|Image.ShowGrid|**CTRL** + **Alt** + **S**|Переключает пиксельной сетки (установить или снять флажок **пиксельную сетку** в диалоговом окне [диалоговое окно параметров сетки](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|
|Image.ShowTileGrid|**CTRL** + **Shift** + **Alt** + **S**|Переключает мозаичной сетки (установить или снять флажок **параметры сетки** в диалоговом окне [диалоговое окно параметров сетки](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|
|Image.SmallBrush|**CTRL** + **.** (период)|Уменьшает **кисть** размером до 1 пикселя. (Также см. Image.LargerBrush и Image.SmallerBrush в этой таблице.)|
|Image.SmallerBrush|**CTRL**  +  **-** (минус)|Уменьшение размера кисти на один пиксель в каждом направлении. Чтобы увеличить размер кисти, см. Image.LargerBrush в этой таблице.|
|Image.TextTool|**CTRL** + **T**|Открывает [диалогового текст](../windows/text-tool-dialog-box-image-editor-for-icons.md).|
|Image.UseSelectionAsBrush|**CTRL** + **U**|Рисование с использованием выделенного фрагмента в качестве кисти.|
|Image.ZoomIn|**CTRL** + **Shift** + **.** (период)<br /><br /> -или-<br /><br /> **CTRL** + **стрелка вверх**|Увеличение масштаба текущего представления.|
|Image.ZoomOut|**CTRL** + **,** (запятая)<br /><br /> -или-<br /><br /> **CTRL** + **стрелка вниз**|Уменьшение масштаба текущего представления.|

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Редактор изображений для значков](../windows/image-editor-for-icons.md)