---
title: Устранение неполадок редактора диалоговых окон (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], troubleshooting
- Dialog Editor [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 21882868-5ac4-4a41-a4a6-eaaa059402ea
ms.openlocfilehash: fe0fe704b5c17d0db4e3419f29d21f0e60bc4211
ms.sourcegitcommit: 5270117dbecc4c49bca0cf10b927bae3c9930038
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/31/2019
ms.locfileid: "55484959"
---
# <a name="troubleshooting-the-dialog-editor-c"></a>Устранение неполадок редактора диалоговых окон (C++)

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

Ниже приведены некоторые проблемы, которые следует иметь в виду при работе в C++ **диалоговое окно** редактора:

## <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function"></a>Добавление элементов управления в диалоговое окно приводит к прекращению работы диалогового окна

После добавления общего элемента управления или элемента управления форматированным редактированием в диалоговое окно, он не будет отображаться при тестировании диалоговое окно или диалоговое окно, сам не будет отображаться.

### <a name="example-of-the-problem"></a>Пример проблемы

1. Создайте проект Win32, измените параметры приложения, поэтому создается приложение Windows (не консольное приложение).

1. В [представление ресурсов](../windows/resource-view-window.md), дважды щелкните RC-файл.

1. В разделе диалоговое окно, дважды щелкните **о** поле.

1. Добавить **контроль IP-адресов** в диалоговое окно.

1. Сохранить и **перестроить все**.

1. Запустите программу.

1. В диалоговом окне **помочь** меню, щелкните **о** командной; диалоговое окно не появляется.

### <a name="the-cause"></a>Причины

В настоящее время **диалоговое окно** редактор не добавляет автоматически код в проект при перетаскивании следующие общие элементы управления или элементов управления в диалоговое окно "rich edit". И не Visual Studio обеспечивает ошибку или предупреждение при возникновении этой проблемы. Чтобы устранить проблему, вручную добавьте код для элемента управления.

||||
|-|-|-|
|Элемент управления «Ползунок»|Дерево|Элемент управления "Выбор даты и времени"|
|Элемент управления "Счетчик"|Набор вкладок|Календарь месяца|
|Элемент управления хода выполнения|Анимация элемента управления|Контроль IP-адресов|
|Сочетания клавиш|Элемент управления "Rich Edit"|Расширенное поле со списком поле|
|Управления "список"|Элемент управления Rich Edit 2.0|Пользовательский элемент управления|

### <a name="fix-for-common-controls"></a>Исправление для общих элементов управления

Чтобы использовать стандартные элементы управления в диалоговом окне, необходимо вызвать [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) или `AFXInitCommonControls` перед созданием диалоговое окно.

### <a name="fix-for-richedit-controls"></a>Исправление для элементов управления RichEdit

Необходимо вызвать метод `LoadLibrary` для элементов управления "rich edit". Дополнительные сведения см. в разделе [о элементами управления Rich Edit](/windows/desktop/Controls/about-rich-edit-controls) в пакете SDK для Windows и [Обзор элемента управления Rich Edit](../mfc/overview-of-the-rich-edit-control.md).

### <a name="requirements"></a>Требования

Win32

## <a name="using-the-richedit-10-control-with-mfc"></a>Использование элемента управления RichEdit 1.0 с MFC

Чтобы использовать элемент управления RichEdit, необходимо сначала вызвать [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) загрузить элемент управления RichEdit 2.0 (библиотеки RICHED20. Библиотека DLL), или вызвать [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) для загрузки более старых элемента управления RichEdit 1.0 (RICHED32. БИБЛИОТЕКА DLL).

Вы можете использовать текущий [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) класса с помощью более старых элемента управления RichEdit 1.0, но `CRichEditCtrl` предназначена только для поддержки управления RichEdit 2.0. Поскольку RichEdit 1.0 и RichEdit 2.0 похожи, большинство методов будет работать. Тем не менее Обратите внимание, что существуют некоторые различия между 1.0 и 2.0 элементы управления, поэтому некоторые методы могут работать неправильно или вообще не работать.

### <a name="requirements"></a>Требования

MFC

## <a name="see-also"></a>См. также

[Редактор диалоговых окон](../windows/dialog-editor.md)