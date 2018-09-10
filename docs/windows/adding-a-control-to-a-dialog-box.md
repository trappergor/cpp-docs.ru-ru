---
title: Добавление элемента управления в диалоговое окно (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.dialog
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], adding controls to
ms.assetid: b2a26d19-093f-49ca-93da-fef00dfbb381
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e60c64777ea4b5726721a267bcdd700cd71b4214
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317905"
---
# <a name="adding-a-control-to-a-dialog-box-c"></a>Добавление элемента управления в диалоговое окно (C++)

### <a name="to-add-a-control-to-a-dialog-box"></a>Добавление элемента управления в диалоговое окно

1. Убедитесь, что диалоговое окно с вкладками открыто как текущий документ в окне редактора. Если диалоговое окно не является текущим документом, вы не увидите вкладку **Редактор диалоговых окон** в **панели элементов**.

2. На вкладке [Редактор диалоговых окон](../windows/dialog-editor-tab-toolbox.md) [панели элементов](/visualstudio/ide/reference/toolbox)выберите нужный элемент управления, а затем выполните следующие действия.

   - Щелкните диалоговое окно в том месте, где требуется поместить элемент управления. Элемент управления появится на выбранном месте. Дополнительные сведения см. в разделе [Добавление нескольких элементов управления](../windows/adding-multiple-controls.md).

       \- или -

   - Перетаскивание элемента управления с **элементов** окно в расположение в диалоговом окне. Дополнительные сведения см. в разделе [Изменение размера элемента управления при его добавлении](../windows/sizing-a-control-while-you-add-it.md).

       \- или -

   - Дважды щелкните элемент управления **элементов** (отображается в диалоговом окне), а затем изменить положение элемента управления в расположение, вы предпочитаете.

Сведения о типах элементов управления, доступных на **элементов** окно, см. в разделе [вкладка редактора диалоговых окон, окно панели элементов](../windows/dialog-editor-tab-toolbox.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)  
[Добавление обработчиков событий для элементов управления диалоговых окон](../windows/adding-event-handlers-for-dialog-box-controls.md)  
[Элементы управления "Диалоговое окно" и типы переменных](../ide/dialog-box-controls-and-variable-types.md)