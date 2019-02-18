---
title: Сочетания клавиш (редактор C++ изображений для значков)
ms.date: 02/15/2019
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
ms.openlocfilehash: 604f97edc8e4e49bad477d76e0e46334b8cf726b
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336543"
---
# <a name="accelerator-keys-c-image-editor-for-icons"></a>Сочетания клавиш (редактор C++ изображений для значков)

Ниже приведены сочетания клавиш для команд редактора изображений, привязанных к ключи по умолчанию. Чтобы изменить сочетания клавиш, нажмите кнопку **параметры** на **средства** меню и выберите **клавиатуры** под **среды** папки. Дополнительные сведения см. в разделе [Определение и настройка сочетаний клавиш в Visual Studio](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

> [!NOTE]
> Доступные в диалоговых окнах параметры, а также названия и расположение команд меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

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
|Image.FilledRoundRectangleTool|**Ctrl** + **Shift** + **Alt** + **W**|Рисование скругленного прямоугольника с заливкой.|
|Image.FillTool|**CTRL** + **F**|Заливка области.|
|Image.FlipHorizontal|**CTRL** + **H**|Горизонтальное зеркальное отражение изображения или выбранного фрагмента.|
|Image.FlipVertical|**SHIFT**+ **Alt** + **H**|Вертикальное зеркальное отражение изображения или выделенного фрагмента.|
|Image.LargerBrush|**CTRL** + **=**|Увеличение размера кисти на один пиксель в каждом направлении. Чтобы уменьшить размер кисти, см. Image.SmallerBrush в этой таблице.|
|Image.LineTool|**CTRL** + **L**|Рисование прямой линии с выбранной формой, размером и цветом.|
|Image.MagnificationTool|**Ctrl** + **M**|Активирует **увеличить** средство, которое позволяет увеличивать фрагменты рисунка.|
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
|Image.RoundedRectangleTool|**Alt** + **W**|Рисование скругленного прямоугольника линией выбранной толщины и цвета.|
|Image.ShowGrid|**Ctrl** + **Alt** + **S**|Переключает пиксельной сетки (установить или снять флажок **пиксельную сетку** в диалоговом окне [диалоговое окно параметров сетки](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|
|Image.ShowTileGrid|**CTRL** + **Shift** + **Alt** + **S**|Переключает мозаичной сетки (установить или снять флажок **параметры сетки** в диалоговом окне [диалоговое окно параметров сетки](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|
|Image.SmallBrush|**CTRL** + **.** (период)|Уменьшает **кисть** размером до 1 пикселя. (Также см. Image.LargerBrush и Image.SmallerBrush в этой таблице.)|
|Image.SmallerBrush|**CTRL**  +  **-** (минус)|Уменьшение размера кисти на один пиксель в каждом направлении. Чтобы увеличить размер кисти, см. Image.LargerBrush в этой таблице.|
|Image.TextTool|**CTRL** + **T**|Открывает [диалогового текст](../windows/text-tool-dialog-box-image-editor-for-icons.md).|
|Image.UseSelectionAsBrush|**Ctrl** + **U**|Рисование с использованием выделенного фрагмента в качестве кисти.|
|Image.ZoomIn|**CTRL** + **Shift** + **.** (период)<br /><br /> -или-<br /><br /> **CTRL** + **стрелка вверх**|Увеличение масштаба текущего представления.|
|Image.ZoomOut|**CTRL** + **,** (запятая)<br /><br /> -или-<br /><br /> **CTRL** + **стрелка вниз**|Уменьшение масштаба текущего представления.|

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Редактор изображений для значков](../windows/image-editor-for-icons.md)