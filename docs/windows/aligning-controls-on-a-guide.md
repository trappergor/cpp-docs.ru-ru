---
title: Выравнивание элементов управления по направляющей | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLUs (dialog units)
- controls [C++], aligning
- Dialog editor, snap to guides
- guides, tick mark interval
- dialog box controls, placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55cf669d2c84bc0a603354a672706e32656a7c3c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603932"
---
# <a name="aligning-controls-on-a-guide"></a>Выравнивание элементов управления по направляющей

Маркеры изменения размера элементов управления привязка к описаниям, при перемещении элементов управления, а направляющие привязываются к элементам управления (если нет элементов управления, ранее привязываются к структуре). При перемещении по элементам управления, привязанные к нему переместить также. Элементы управления привязаны к нескольких структур изменяется при перемещении одно из руководств.

Деления линейки, которые определяют интервал направляющих и элементов управления определяются единицы диалогового (окна DLU). Единица основан на размер шрифта диалогового, обычно 8 пунктов MS Shell Dlg. Горизонтальная Единица диалогового окна — среднюю ширину деления четыре на шрифт диалогового окна. Вертикальная Единица диалогового окна — это средняя высота шрифта, деленная на восемь.

### <a name="to-size-a-group-of-controls-with-guides"></a>Для изменения размера группы элементов управления с направляющими

1. Привязка одной стороны элемента управления (или элементов управления) к структуре.

2. Перетащите направляющую другой стороне элемента управления (или элементов управления).

   При необходимости с несколькими элементами управления, размер каждого, чтобы привязать к второй направляющей.

3. Переместите направляющую, либо для изменения размера элемента управления (или элементов управления).

### <a name="to-change-the-intervals-of-the-tick-marks"></a>Чтобы изменить интервал меток делений

1. Из **формат** меню, выберите **параметры направляющих**.

2. В [диалоговое окно "Параметры направляющих"](../windows/guide-settings-dialog-box.md)в **шаг сетки** укажите новая ширина и высота в единицах диалогового окна.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Состояния редактора диалоговых окон (направляющие и сетки)](../windows/dialog-editor-states-guides-and-grids.md)  
[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)