---
title: Работа с цветом (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.color
dev_langs:
- C++
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors [C++], Image editor
- colors [C++]
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 200c71b6d2196251c8db3542b2b1b2ce88fdff85
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315539"
---
# <a name="working-with-color-image-editor-for-icons"></a>Работа с цветом (редактор изображений для значков)

**Редактор изображений** содержит множество функций и управлять ими Настройка цветов. Можно задать цвет переднего плана или фона, заливка ограниченных областей или выберите цвет в изображения для использования в качестве текущего цвета переднего плана или фона. Вы можете использовать средства на [панель инструментов редактора изображений](../windows/toolbar-image-editor-for-icons.md) вместе с палитра цветов в [окно "цвета"](../windows/colors-window-image-editor-for-icons.md) для создания образов.

Все цвета монохромная и 16 цветов изображения отображаются в **цвета** палитру в **цвета** окна. В дополнение к 16 стандартных цветов можно создать свои собственные цвета. Изменение цвета в палитре немедленно изменится на соответствующий цвет в изображения.

При работе с 256-цветного значка и изображения для курсора, **цвета** свойство в [окно "Свойства"](/visualstudio/ide/reference/properties-window) используется. Дополнительные сведения см. в разделе [Создание 256-цветного значка или курсора](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).

> [!NOTE]
> С помощью **редактор изображений**, 32-разрядные образы можно просмотреть, но не позволяет их редактировать.

Можно также создать изображения True color. Тем не менее, примеры true color не отображаются в полную палитру в **цвета** окно; они появляются только в области индикатора цвет переднего плана или фона. Значение true цветами создаются с помощью [диалоговое окно «Выбор цвета»](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Дополнительные сведения см. в разделе [Настройка и изменение цветов](../windows/customizing-or-changing-colors-image-editor-for-icons.md).

Можно сохранить пользовательские палитры на диске и загружать их при необходимости. Цветовой палитре, которую вы недавно использованные сохраняется в реестре и автоматически загружается при следующем запуске Visual Studio.

- [Выбор основного цвета и цвета фона](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)

- [Заливка выделенной области изображения с цветом](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)

- [Выбор изображении образца цвета из образа для использования в другом фрагменте](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)

- [Выбор прозрачного и непрозрачного фона](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)

- [Преобразование цветов в выделенной области](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)

- [Настройка и изменение цветов](../windows/customizing-or-changing-colors-image-editor-for-icons.md)

- [Сохранение и загрузка различных цветовых палитр](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)

- [Окно "цвета"](../windows/colors-window-image-editor-for-icons.md)

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)  