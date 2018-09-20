---
title: Выбор элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog Editor [C++], selecting controls
- dominant controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
ms.assetid: 27f05450-4550-4229-9f4c-2c9e06365596
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d6b322559777d10f3a53f7ed8adbc5d6a05a342
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379707"
---
# <a name="selecting-controls"></a>Выбор элементов управления

Выберите элементы управления до размера, выравнивать, переместить, скопировать, или удалить их и выполните операцию, которую вы хотите. В большинстве случаев необходимо выбрать более одного элемента управления, чтобы использовать средства изменения размера и выравнивания на [редактор диалоговых окон инструментов](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

При выборе элемента управления, он имеет затененную рамку вокруг нее с использованием (активный) или пустыми (неактивными) «маркерами» небольшими квадратиками, отображаются в рамки выделенной области. Если выбрано несколько элементов управления, главного элемента управления имеет сплошной маркеров; все другие выбранные элементы управления имеют без заливки маркеров.

При изменения размера или выравнивание нескольких элементов управления, **диалоговое окно** редактор использует «главного элемента управления» для определения, как размер или выровнены других элементов управления. По умолчанию главного элемента управления является первого выбранного элемента управления.

- [Выбор нескольких элементов управления](../windows/selecting-multiple-controls.md)

- [Задание главного элемента управления](../windows/specifying-the-dominant-control.md)

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)