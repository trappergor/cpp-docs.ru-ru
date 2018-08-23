---
title: Настройка и изменение цветов (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dithered color, Image editor
- Custom Color Selector dialog box
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- luminosity
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command
- Image editor [C++], dithered color
ms.assetid: e58f6b32-f435-4d9a-a570-7569433661ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5eb9b7da8b09fbac1e462394c6ae087b61814ede
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598779"
---
# <a name="customizing-or-changing-colors-image-editor-for-icons"></a>Настройка и изменение цветов (редактор изображений для значков)

**Изображение** редактора [палитра цветов](../windows/colors-window-image-editor-for-icons.md) изначально отображает 16 стандартных цветов. В дополнение к отображаемым цветам вы можете создавать свои собственные цвета. После этого можно [сохранить и загрузить пользовательскую цветовую палитру](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md).

### <a name="to-change-colors-on-the-colors-palette"></a>Изменение цветов в палитре цветов

1. Из **изображение** меню, выберите **Настройка цветов**.

2. В [диалоговое окно «Выбор цвета»](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md), определите цвет путем ввода значения RGB или HSL в соответствующие текстовые поля, или выберите цвет в **Отображение цветового градиента** поле.

3. Отрегулируйте яркость, перемещая ползунок на **яркость** строке.

4. Многие пользовательские цвета сглажены. Если вам нужен сплошной цвет ближайший к сглаженному, дважды щелкните **цвет** поле.

   Если позднее потребуется сглаженный цвет, переместите ползунок на **яркость** гистограммы или передвиньте перекрестие **Отображение цветового градиента** окно повторно, чтобы получить желаемый результат.

5. Нажмите кнопку **ОК** для добавления нового цвета.

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)  
[Работа с цветом](../windows/working-with-color-image-editor-for-icons.md)