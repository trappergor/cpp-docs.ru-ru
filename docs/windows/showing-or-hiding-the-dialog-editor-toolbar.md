---
title: Отображение или скрытие панели инструментов редактора диалоговых окон | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog editor, showing or hiding toolbar
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f1aa9e84e1f03f0299d25ec43b91c93531179ab6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599416"
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar"></a>Отображение и скрытие панели инструментов в редакторе диалоговых окон

При открытии **диалоговое окно** редакторе **редактор диалоговых окон** панель инструментов автоматически отображается в верхней части решения.

### <a name="dialog-editor-toolbar"></a>Панель инструментов редактора диалоговых окон

|Значок|Значение|Значок|Значение|
|----------|-------------|----------|-------------|
|![Кнопка "Проверить диалоговое окно"](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|Диалоговое окно «Тестирование»|![Кнопка задавать интервалы по горизонтали](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|По горизонтали|
|![Выровнять левые границы кнопки](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|Выравнивание левых границ|![Задать интервалы по вертикали кнопку](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|Вниз|
|![Кнопка выровнена относительно кнопки права](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|Выравнивание правых границ|![Создание ту же ширину кнопки](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|Приведение к одной ширине|
|![Выравнивание верхних границ кнопки](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|Выравнивание верхних границ|![Создание ту же высоту кнопки](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|Приведение к одной высоте|
|![Выравнивание нижних границ кнопки](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|Выравнивание нижних границ|![Сделать одного размера кнопки](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|Приведение к одному размеру|
|![Кнопка "Центрировать по вертикали"](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Вертикально|![Сетка выключатель](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|Сетка|
|![Кнопка "Центрировать по горизонтали"](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|Горизонтально|![Руководства по выключатель](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|Направляющие|

**Редактор диалоговых окон** панель инструментов содержит кнопки для упорядочения макет элементов управления в диалоговом окне, например размер и выравнивание. **Редактор диалоговых окон** соответствующие команды на **формат** меню. Дополнительные сведения см. в разделе [сочетания клавиш для редактора диалоговых окон](../windows/accelerator-keys-for-the-dialog-editor.md).

Когда вы будете в **диалоговое окно** редактора, можно включить отображение **редактор диалоговых окон** панели инструментов, выбрав его из списка доступных панелей и windows.

### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>Чтобы отобразить или скрыть панель инструментов редактора диалогового окна

1. На **представление** меню **панелей инструментов** выберите **редактор диалоговых окон** в подменю.

   > [!NOTE]
   > **Редактор диалоговых окон** панели инструментов отображается по умолчанию при открытии ресурс в редакторе диалоговых окон; тем не менее, если вы явно закрыть панель инструментов, необходимо будет вызывать его при следующем открытии ресурс.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Размещение элементов управления в диалоговых окнах](../windows/arrangement-of-controls-on-dialog-boxes.md)  
[Практическое руководство. Создание ресурса](../windows/how-to-create-a-resource.md)  
[Файлы ресурсов](../windows/resource-files-visual-studio.md)  
[Редактор диалоговых окон](../windows/dialog-editor.md)