---
title: Отображение или скрытие панели инструментов редактора диалоговых окон | Документы Microsoft
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
ms.openlocfilehash: ad456d37252b40be72217e6cbc40a2a399bb34ef
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar"></a>Отображение и скрытие панели инструментов в редакторе диалоговых окон
При открытии редактора диалоговых окон, редактор диалоговых окон инструментов автоматически отображается в верхней части решения.  
  
### <a name="dialog-editor-toolbar"></a>Панель инструментов редактора диалоговых окон  
  
|Значок|Значение|Значок|Значение|  
|----------|-------------|----------|-------------|  
|![Кнопка тестирования диалогового окна](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|Диалоговое окно «Тестирование»|![Кнопка интервалы по горизонтали](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|По горизонтали|  
|![Выравнивание левых границ кнопки](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|Выравнивание левых границ|![Кнопки места работы](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|Вниз|  
|![Выравнивание кнопки права](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|Выравнивание правых границ|![Создание одинаковую ширину кнопки](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|Приведение к одной ширине|  
|![Выравнивание верхних границ кнопки](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|Выравнивание верхних границ|![Создание кнопки одинаковую высоту](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|Приведение к одной высоте|  
|![Выравнивание нижних границ кнопки](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|Выравнивание нижних границ|![Создание одного размера кнопки](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|Приведение к одному размеру|  
|![Кнопка "центрировать вертикальной"](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Вертикально|![Сетка выключатель](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|Сетка|  
|![Кнопка "центрировать горизонтальной"](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|Горизонтально|![Кнопка "Показать направляющие"](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|Направляющие|  
  
 Редактор диалоговых окон инструментов содержит кнопки для упорядочения макет элементов управления в диалоговом окне, например размер и выравнивание. Кнопки панели инструментов редактора диалоговых окон соответствуют командам меню Формат. Дополнительные сведения см. в разделе [сочетания клавиш для редактора диалоговых окон](../windows/accelerator-keys-for-the-dialog-editor.md).  
  
 При работе в редакторе диалоговых окон позволяет управлять отображением панели инструментов редактора диалоговых окон, выбрав его из списка доступных панелей и windows.  
  
### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>Отображение или скрытие панели инструментов редактора диалоговых окон  
  
1.  На **представление** меню **панели инструментов** выберите **редактор диалоговых окон** в подменю.  
  
    > [!NOTE]
    >  Панели инструментов редактора диалоговых окон отображается по умолчанию при открытии ресурс диалогового окна в редакторе диалоговых окон; Однако если явно закрыть панель инструментов, необходимо вызвать его при следующем открытии ресурс диалогового окна.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Размещение элементов управления в диалоговые окна](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [Как: Создание ресурса](../windows/how-to-create-a-resource.md)   
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редактор диалоговых окон](../windows/dialog-editor.md)

