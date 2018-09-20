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
ms.openlocfilehash: fe7831c12a9ea68525334a55aec5a1fa2ecb847d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405116"
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

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)