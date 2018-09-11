---
title: Размещение элементов управления в диалоговых окнах (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], positioning
- dialog box controls [C++], placement
- Dialog Editor [C++], arranging controls
ms.assetid: 832491cf-98af-42e5-a854-2cb135fd45c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 46bc2d627c9efbb49227e17c809d188aa3a8b5fc
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315240"
---
# <a name="arrangement-of-controls-on-dialog-box-ces"></a>Размещение элементов управления в диалоговом поле es (C++)

**Диалоговое окно** редактор предоставляет средства разметки, выравнивания и размера элементов управления автоматически. Для выполнения большинства задач можно использовать [редактор диалоговых окон инструментов](../windows/showing-or-hiding-the-dialog-editor-toolbar.md). Все **редактор диалоговых окон** команды панели инструментов, также доступны в **формат** меню, а большинство имеют [сочетания клавиш](../windows/accelerator-keys-for-the-dialog-editor.md).

Многие команды макета по диалоговым окнам, доступны только в том случае, если выбрано несколько элементов управления. Можно выбрать один или несколько элементов управления, и при выборе нескольких элементов управления, первый выбранный по умолчанию «главного» элемента управления. Сведения о выборе элементов управления и главного элемента управления, см. в разделе [элементы управления, выбрав](../windows/selecting-controls.md).

Расположение, высоту и ширину текущего элемента управления отображаются в правом нижнем углу строки состояния. При выборе всего диалоговое окно, в строке состояния отображается положение диалогового окна как единое целое и его высоту и ширину.

- [Состояния редактора диалоговых окон (направляющие и сетки)](../windows/dialog-editor-states-guides-and-grids.md)

- [Группирование переключателей в диалоговом окне](../windows/grouping-radio-buttons-on-a-dialog-box.md)

- [Выравнивание группы элементов управления](../windows/aligning-groups-of-controls.md)

- [Выравнивание интервалов между элементами управления](../windows/evening-the-spacing-between-controls.md)

- [Центрирование элементов управления в диалоговом окне](../windows/centering-controls-in-a-dialog-box.md)

- [Упорядочивание кнопок по правому или нижнему краю диалогового окна](../windows/arranging-push-buttons-along-the-right-or-bottom-of-a-dialog-box.md)

- [Изменение последовательности табуляции элементов управления](../windows/changing-the-tab-order-of-controls.md)

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)  
[Элементы управления](../mfc/controls-mfc.md)