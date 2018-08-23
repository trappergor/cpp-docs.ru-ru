---
title: Цвета окна (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.colorswindow
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], Colors Palette
- Colors Palette
- colors [C++], image
- Image editor [C++], Colors window
- Screen-Color Selector
- Colors Palette, Image editor
- Colors window
- colors [C++], inverting
- colors [C++]
- Color Indicator
ms.assetid: 1d9b6c16-bf1d-4488-a19b-5d6fe601846a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6cb463f95bc68d6880fb593ba394ec94d585696
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597340"
---
# <a name="colors-window-image-editor-for-icons"></a>Окно "Цвета" (редактор изображений для значков)

**Цвета** окно состоит из двух частей:

1. **Палитра цветов**, который является массивом образцов цветов, представляющих цвета, можно использовать. Можно щелкать эти образцы для выбора цвета переднего плана и фона при использовании графических средств.

2. **Индикатор цветов**, показывающий цвета переднего плана и фона, селекторы для экрана и инвертированный цвет.

   ![Окно "цвета"](../windows/media/vccolorswindow.gif "vcColorsWindow")  
Окно "Цвета"

> [!NOTE]
> **Экрана цвет** и **Инвертированный цвет** средства доступны только для значков и курсоров.

Можно использовать **цвета** окно с [панель инструментов редактора изображений](../windows/toolbar-image-editor-for-icons.md).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Отображение или скрытие окна выбора цвета](../windows/displaying-or-hiding-the-colors-window-image-editor-for-icons.md)  
[Создание прозрачных областей или областей с обращенными цветами на изображениях устройств](../windows/creating-transparent-or-inverse-regions-in-device-images.md)  
[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)  
["Диалоговое окно" селектор пользовательских цветов "](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)  
[Редактор изображений для значков](../windows/image-editor-for-icons.md)