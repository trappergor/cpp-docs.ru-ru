---
title: Выбор нескольких элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog Editor [C++], selecting controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- controls [C++], removing from groups
ms.assetid: efbdbade-0a3a-4328-b36e-a6376c06e8de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6789a378b163da9e3cefbabb506f84a3cb9a5d7f
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317784"
---
# <a name="selecting-multiple-controls"></a>Выбор нескольких элементов управления

### <a name="to-select-multiple-controls"></a>Выбор нескольких элементов управления

1. В [окно панели элементов](/visualstudio/ide/reference/toolbox)выберите **указатель** средство.

2. Перетащите указатель, чтобы нарисовать рамку выделения вокруг элементов управления, которые вы хотите выбрать в диалоговом окне.

   Если отпустить кнопку мыши, все элементы управления внутри и пересекающиеся выбраны поле выбора.

   \- или -

- Удерживая нажатой **Shift** ключа и щелкните элементы управления, которые вы хотите включить в список.

   \- или -

- Удерживая нажатой **Ctrl** ключа и щелкните элементы управления, которые вы хотите включить в список.

### <a name="to-remove-a-control-from-a-group-of-selected-controls-or-to-add-a-control-to-a-group-of-selected-controls"></a>Чтобы удалить элемент управления из группы выбранные элементы управления или добавление элемента управления для группы выбранных элементов управления

1. С группой выделенных элементов управления, удерживая нажатой **Shift** ключа и щелкните элемент управления, необходимо удалить или добавить в существующее выделение.

   > [!NOTE]
   > Удерживая нажатой **Ctrl** ключ и щелкая элемент управления в составе сделает, которые управляют главного элемента управления в указанной области. Дополнительные сведения см. в разделе [Задание главного элемента управления](../windows/specifying-the-dominant-control.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Выбор элементов управления](../windows/selecting-controls.md)  
[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)