---
title: Элементы управления в диалоговых окнах | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], dialog boxes
- dialog box controls, about dialog box controls
- dialog box controls
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: acbbbe0ecf1151f6159799592a8211bcf11fe7a1
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646947"
---
# <a name="controls-in-dialog-boxes"></a>Элементы управления в диалоговых окнах
Можно добавить элементы управления в диалоговое окно с помощью [вкладка диалогового окна редактора](../windows/dialog-editor-tab-toolbox.md) в [окно панели элементов](/visualstudio/ide/reference/toolbox), что позволяет выбрать элемент управления и перетащите его в диалоговом окне. По умолчанию окно панели элементов будет присвоено автоматического скрытия. Он отображается как вкладка в левой области решения, когда открыт редактор диалоговых окон. Тем не менее, вы можете закрепить **элементов** в позиции, щелкнув окно **автоматическое скрытие** кнопки в правом верхнем углу окна. Дополнительные сведения о том, как управлять поведением этого окна см. в разделе [Управление окнами](/visualstudio/ide/customizing-window-layouts-in-visual-studio).  
  
 Самый быстрый способ добавить элементы управления в диалоговое окно, элемент или переместить элементы управления из одного диалогового окна в другое, является использование метода перетаскивания и вставки. Положение элемента управления представлен в пунктирной линией, до своего удаления в диалоговом окне. При добавлении элемента управления в диалоговое окно с помощью метода перетаскивания и вставки, присваивается стандартной высоте, соответствующие типу элемента управления.  
  
 При добавлении элемента управления в диалоговое окно или переместить, окончательная позиция может определяться руководства или поля, или имеется сетка макета, включен.  
  
 После добавления элемента управления в диалоговое окно, можно изменить свойства, такие как фактически [окно "Свойства"](/visualstudio/ide/reference/properties-window). Можно выбрать несколько элементов управления и изменить их свойства одновременно.  
  
-   [Добавление, изменение и удаление элементов управления](adding-editing-or-deleting-controls.md)  
  
-   [Выбор элементов управления](../windows/selecting-controls.md)  
  
-   [Изменение размера отдельных элементов управления](../windows/sizing-individual-controls.md)  
  
-   [Выравнивание элементов управления по размеру](../windows/making-controls-the-same-width-height-or-size.md)  
  
-   [Задание размера для поля со списком и соответствующего раскрывающегося списка](setting-the-size-of-the-combo-box-and-its-drop-down-list.md)  
  
-   [Добавление значений в элемент управления "Поле со списком"](../windows/adding-values-to-a-combo-box-control.md)  
  
-   [Задание ширины горизонтальной полосы прокрутки](../windows/setting-the-width-of-a-horizontal-scroll-bar.md)  
  
-   [Расположение элементов управления в диалоговых окнах](../windows/arrangement-of-controls-on-dialog-boxes.md)  
  
-   [Пользовательские элементы управления в редакторе диалоговых окон](custom-controls-in-the-dialog-editor.md)  
  
-   [Определение клавиш доступа](../windows/defining-mnemonics-access-keys.md)  
  
-   [Задание местоположения и размера диалогового окна](../windows/specifying-the-location-and-size-of-a-dialog-box.md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Добавление обработчиков событий для элементов управления диалогового окна](../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Диалоговое окно элементов управления, а также типы переменных](../ide/dialog-box-controls-and-variable-types.md)   
 [Редактор диалоговых окон](../windows/dialog-editor.md)