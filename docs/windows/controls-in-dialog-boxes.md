---
title: Элементы управления в диалоговых окнах | Документы Microsoft
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
ms.openlocfilehash: 6a837766bbbe57186f8355895c98ff04d8048bdc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="controls-in-dialog-boxes"></a>Элементы управления в диалоговых окнах
Можно добавить элементы управления в диалоговое окно с помощью [редактор диалоговых окон](../windows/dialog-editor-tab-toolbox.md) в [окно панели элементов](/visualstudio/ide/reference/toolbox), позволяет выбрать элемент управления должен и перетащите его в диалоговом окне. По умолчанию окно панели элементов имеет значение для автоматического скрытия. Оно появляется в виде вкладки на левом краю решения, если открыт редактор диалоговых окон. Тем не менее, вы можете закрепить окно панели элементов в нужное место, щелкнув **Автоскрытие** кнопку в правом верхнем углу окна. Дополнительные сведения о том, как управлять поведением этого окна см. в разделе [Управление окнами](/visualstudio/ide/customizing-window-layouts-in-visual-studio).  
  
 Самый быстрый способ добавление элементов управления в диалоговое окно, положение существующих элементов управления или переместить элементы управления из одного диалогового в другой — с помощью метода перетаскивания и вставки. Положение элемента управления появлялся пунктирная линия до своего удаления в диалоговом окне. При добавлении элемента управления в диалоговое окно с помощью метода и перетащите элемент управления получает стандартной высоты для данного типа элемента управления.  
  
 При добавлении элемента управления в диалоговое или положение, окончательная позиция может определяться направляющими или полями, или имеется включен сетки макета.  
  
 После добавления элемента управления в диалоговое окно, можно изменить свойства, такие как фактически [окно свойств](/visualstudio/ide/reference/properties-window). Можно выбрать несколько элементов управления и изменение их свойств за один раз.  
  
-   [Добавление, изменение и удаление элементов управления](adding-editing-or-deleting-controls.md)  
  
-   [Выбор элементов управления](../windows/selecting-controls.md)  
  
-   [Изменение размера отдельных элементов управления](../windows/sizing-individual-controls.md)  
  
-   [Выравнивание элементов управления по размеру](../windows/making-controls-the-same-width-height-or-size.md)  
  
-   [Задание размера для поля со списком и соответствующего раскрывающегося списка](setting-the-size-of-the-combo-box-and-its-drop-down-list.md)  
  
-   [Добавление значений в элемент управления "Поле со списком"](../windows/adding-values-to-a-combo-box-control.md)  
  
-   [Задание ширины горизонтальной полосы прокрутки](../windows/setting-the-width-of-a-horizontal-scroll-bar.md)  
  
-   [Размещение элементов управления в диалоговые окна](../windows/arrangement-of-controls-on-dialog-boxes.md)  
  
-   [Пользовательские элементы управления в редакторе диалоговых окон](custom-controls-in-the-dialog-editor.md)  
  
-   [Определение клавиш доступа](../windows/defining-mnemonics-access-keys.md)  
  
-   [Задание местоположения и размера диалогового окна](../windows/specifying-the-location-and-size-of-a-dialog-box.md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Добавление обработчиков событий для элементов управления диалогового окна](../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Элементы управления диалоговых окон и типы переменных](../ide/dialog-box-controls-and-variable-types.md)   
 [Редактор диалоговых окон](../windows/dialog-editor.md)

