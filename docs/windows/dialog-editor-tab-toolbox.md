---
title: Редактор диалоговых окон вкладка, панель элементов | Документация Майкрософт
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
ms.openlocfilehash: 40e0a13f9379200ee01e0279f9d069f1d58f3a60
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649426"
---
# <a name="dialog-editor-tab-toolbox"></a>Панель элементов, вкладка "Редактор диалоговых окон"
**Редактор диалоговых окон** отображается вкладка [окно панели элементов](/visualstudio/ide/reference/toolbox) при работе **диалоговое окно** редактора. Добавление элементов управления в новое диалоговое окно, перетащите элементы управления из **элементов** в диалоговое окно, вы создаете (Дополнительные сведения см. в разделе [Добавление элемента управления в диалоговое окно](adding-a-control-to-a-dialog-box.md)). Затем можно изменить местонахождение элементов управления или их размеры и форму.  
  
 Стандартные элементы управления в **элементов** являются:  
  
-   [Элемент управления Button](../mfc/reference/cbutton-class.md)  
  
-   [Элемент управления "флажок"](../mfc/reference/styles-used-by-mfc.md#button-styles)  
  
-   [Поле со списком](../mfc/reference/ccombobox-class.md)  
  
-   [Изменение элемента управления](../mfc/reference/cedit-class.md)  
  
-   Группа  
  
-   [Окно списка](../mfc/reference/clistbox-class.md)  
  
-   [Управления "переключатель"](../mfc/reference/styles-used-by-mfc.md#button-styles)  
  
-   [Статический элемент управления текст](../mfc/reference/cstatic-class.md)  
  
-   [Управления изображения](../mfc/reference/cpictureholder-class.md)  
  
-   [Элемент управления Rich Edit 2.0](../mfc/using-cricheditctrl.md)  
  
-   [Полосы прокрутки](../mfc/reference/cscrollbar-class.md)  
  
 [Стандартных элементов управления Windows](../mfc/controls-mfc.md) в **элементов** предоставить расширенные функциональные возможности в приложении. В их число входят следующее.  
  
-   [Элемент управления "ползунок"](../mfc/slider-control-styles.md)  
  
-   [Элемент управления "Счетчик"](../mfc/using-cspinbuttonctrl.md)  
  
-   [Элемент управления хода выполнения](../mfc/styles-for-the-progress-control.md)  
  
-   ["Горячий" ключа управления](../mfc/using-a-hot-key-control.md)  
  
-   [Управления "список"](../mfc/list-control-and-list-view.md)  
  
-   [Дерево](../mfc/tree-control-styles.md)  
  
-   [Набор вкладок](../mfc/tab-controls-and-property-sheets.md)  
  
-   [Анимация элемента управления](../mfc/using-an-animation-control.md)  
  
-   [Элемент управления даты средство выбора времени](../mfc/creating-the-date-and-time-picker-control.md)  
  
-   [Элемент управления месячного календаря](../mfc/month-calendar-control-examples.md)  
  
-   [IP-адрес управления](../mfc/reference/cipaddressctrl-class.md)  
  
-   [Расширенного элемента управления списком](../mfc/creating-an-extended-combo-box-control.md)  
  
-   [Пользовательский элемент управления](custom-controls-in-the-dialog-editor.md)  
  
 Можно добавить пользовательские элементы управления в диалоговое окно, выбрав **пользовательский элемент управления** значок в **элементов** и перетащив его в диалоговое окно. Чтобы добавить **Syslink** управления, добавьте пользовательский элемент управления, а затем изменить элемент управления **класс** свойства **Syslink**. Это приведет к свойства для обновления и Показать **Syslink** свойства элемента управления. Сведения об оболочках MFC см. в разделе [CLinkCtrl](../mfc/reference/clinkctrl-class.md).  
  
 Кроме того, вы можете [Добавление элементов управления ActiveX в диалоговое окно](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Вы также можете настроить **элементов** окно, чтобы упростить работу. Дополнительные сведения см. в разделе [Использование панели элементов](/visualstudio/ide/using-the-toolbox).  

 Дополнительные сведения об использовании **RichEdit 1.0** управления с MFC, см. в разделе [использование элемента управления RichEdit 1.0 с MFC](../windows/using-the-richedit-1-0-control-with-mfc.md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
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