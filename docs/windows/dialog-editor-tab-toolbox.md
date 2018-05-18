---
title: Редактор диалоговых окон, элементов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls ino dialog boxes
- custom controls [Visual Studio], dialog boxes
- controls [C++], standard
- Dialog editor, creating controls
- controls [C++], adding to dialog boxes
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb7da9e08d44435570180859c1614f7817595833
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="dialog-editor-tab-toolbox"></a>Панель элементов, вкладка "Редактор диалоговых окон"
Откроется редактор диалоговых окон в [окно панели элементов](/visualstudio/ide/reference/toolbox) при работе в редакторе диалоговых окон. Добавление элементов управления в новое диалоговое перетащите элементы управления из области элементов в диалоговое окно, вы создаете (Дополнительные сведения см. в разделе [Добавление элемента управления в диалоговое окно](adding-a-control-to-a-dialog-box.md)). Затем можно изменить местонахождение элементов управления или их размеры и форму.  
  
 На панели элементов доступны следующие стандартные элементы управления:  
  
-   [Button-элемент управления](../mfc/reference/cbutton-class.md)  
  
-   [Элемент управления "флажок"](../mfc/reference/styles-used-by-mfc.md#button-styles)  
  
-   [Поле со списком](../mfc/reference/ccombobox-class.md)  
  
-   [Элемент управления](../mfc/reference/cedit-class.md)  
  
-   Группа  
  
-   [Окно списка](../mfc/reference/clistbox-class.md)  
  
-   [Управления "переключатель"](../mfc/reference/styles-used-by-mfc.md#button-styles)  
  
-   [Статический текст элемента управления](../mfc/reference/cstatic-class.md)  
  
-   [Изображение элемента управления](../mfc/reference/cpictureholder-class.md)  
  
-   [Элемент управления Rich Edit 2.0](../mfc/using-cricheditctrl.md)  
  
-   [Полосы прокрутки](../mfc/reference/cscrollbar-class.md)  
  
 [Общие элементы управления Windows](../mfc/controls-mfc.md) на панели элементов предоставляют расширенные функциональные возможности приложения. В их число входят следующее.  
  
-   [Элемент управления "ползунок"](../mfc/slider-control-styles.md)  
  
-   [Элемент управления "Счетчик"](../mfc/using-cspinbuttonctrl.md)  
  
-   [Элемент управления хода выполнения](../mfc/styles-for-the-progress-control.md)  
  
-   [Элемент управления горячие клавиши](../mfc/using-a-hot-key-control.md)  
  
-   [Список элементов управления](../mfc/list-control-and-list-view.md)  
  
-   [Управления "дерево"](../mfc/tree-control-styles.md)  
  
-   [Элемент управления вкладки](../mfc/tab-controls-and-property-sheets.md)  
  
-   [Управления "анимация"](../mfc/using-an-animation-control.md)  
  
-   [Элемент времени выбора даты](../mfc/creating-the-date-and-time-picker-control.md)  
  
-   [Элемент управления месячного календаря](../mfc/month-calendar-control-examples.md)  
  
-   [Управление IP-адрес](../mfc/reference/cipaddressctrl-class.md)  
  
-   [Расширенного элемента управления списком](../mfc/creating-an-extended-combo-box-control.md)  
  
-   [Пользовательский элемент управления](custom-controls-in-the-dialog-editor.md)  
  
 Можно добавить пользовательские элементы управления в диалоговое окно, выбрав **пользовательский элемент управления** значок на панели элементов и перетащив его диалогового окна. Чтобы добавить элемент управления Syslink, добавьте пользовательский элемент управления, а затем изменить элемент управления **класса** свойства **Syslink**. Свойства обновятся, и появятся свойства элемента управления Syslink. Сведения о класс-оболочку MFC см. в разделе [CLinkCtrl](../mfc/reference/clinkctrl-class.md).  
  
 Кроме того, вы можете [добавить элементы управления ActiveX в диалоговое](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Кроме того, можно настроить окно "Панель элементов", чтобы упростить работу с ним. Дополнительные сведения см. в разделе [Использование панели элементов](/visualstudio/ide/using-the-toolbox).  

 Дополнительные сведения об использовании элемента управления RichEdit 1.0 с MFC см. в разделе [использование элемента управления RichEdit 1.0 с MFC](../windows/using-the-richedit-1-0-control-with-mfc.md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления](../mfc/controls-mfc.md)   
 [Классы элементов управления](../mfc/control-classes.md)   
 [Классы диалоговых окон](../mfc/dialog-box-classes.md)   
 [Стили полосы прокрутки](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)   
 [Примеры элементов управления "Rich Edit"](../mfc/rich-edit-control-examples.md)   
 [Добавление обработчиков событий для элементов управления диалогового окна](../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Элементы управления "Диалоговое окно" и типы переменных](../ide/dialog-box-controls-and-variable-types.md)

