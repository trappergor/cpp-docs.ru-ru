---
title: Создание элементов управления, ширины, высоты или размер | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Make Same Size command
- controls [C++], sizing
ms.assetid: 94b50613-67e2-497b-a2b6-6d98dccfd345
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5077d2dcd426182495cc7a414aca7ca411d1fa60
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605380"
---
# <a name="making-controls-the-same-width-height-or-size"></a>Выравнивание элементов управления по размеру

Вы можете изменить размер группы элементов управления в зависимости от размера главного элемента управления. Вы также можете [изменение размеров элемента управления на основе аналитик его заголовке](../windows/sizing-individual-controls.md).

### <a name="to-make-controls-the-same-width-height-or-size"></a>Выравнивание элементов управления ширины, высоты или размер

1. [Выберите элементы управления](../windows/selecting-multiple-controls.md) которого требуется изменить.

   Первый выбранный в серии является главным. Окончательный размер элементов управления в группе зависит от размера главного элемента управления. Дополнительные сведения о выборе главного элемента управления, см. в разделе [Задание главного элемента управления](../windows/specifying-the-dominant-control.md).

2. Из **формат** меню, выберите **установить тот же размер**, затем выберите один из следующих команд:

   - **Оба**

   - **Высота**

   - **Ширина**

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)  
[Элементы управления](../mfc/controls-mfc.md)