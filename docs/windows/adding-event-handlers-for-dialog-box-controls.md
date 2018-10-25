---
title: Добавление обработчиков событий для элементов управления диалогового окна (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog Editor [C++], adding event handlers to controls
- controls [C++], event handlers
- dialog box controls [C++], events
- event handlers, for dialog box controls
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebb644c64bbc5eba65860ffb1c1115bfc7662951
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075274"
---
# <a name="adding-event-handlers-for-dialog-box-controls-c"></a>Добавление обработчиков событий для элементов управления диалогового окна (C++)

Для проекта диалоговых окон, которые уже связаны с классом можно воспользоваться преимуществами некоторые сочетания клавиш, при создании обработчиков событий. Можно быстро создать обработчик для события уведомления элемента управления по умолчанию или для любого соответствующего сообщения Windows.

### <a name="to-create-a-handler-for-the-default-control-notification-event"></a>Чтобы создать обработчик для события уведомления элемента управления по умолчанию

1. Дважды щелкните элемент управления. **Текст** Откроется редактор.

2. Добавьте код обработчика уведомлений в **текст** редактора.

### <a name="to-create-a-handler-for-any-applicable-windows-message"></a>Чтобы создать обработчик для любого соответствующего сообщения Windows

1. Щелкните элемент управления, для которого вы хотите обрабатывать событие уведомления.

2. В [окно "Свойства"](/visualstudio/ide/reference/properties-window), нажмите кнопку **события элемента управления** кнопку, чтобы открыть список общих событий Windows, связанные с элементом управления. Например, стандартные **ОК** кнопку **о** диалоговом окне перечислены следующие события уведомления:

   - BN_CLICKED

   - BN_DOUBLECLICKED

   - BN_KILLFOCUS

   - BN_SETFOCUS

   > [!NOTE]
   > Кроме того, диалоговое окно выбора и нажмите кнопку **события элемента управления** кнопку, чтобы открыть список общих событий Windows для всех элементов управления в диалоговом окне.

3. В **свойства** щелкните столбец справа для обработки и затем выберите имя события предлагаемые уведомлений (например, `OnBnClickedOK` обрабатывает BN_CLICKED).

   > [!NOTE]
   > Кроме того можно предоставить имя обработчика события выбор, а не выбрав имя обработчика событий по умолчанию.

   После выбора события, Visual Studio открывает **текстовый редактор** и отображает код обработчика событий. Например, следующий код добавляется по умолчанию `OnBnClickedOK`:

    ```cpp
    void CAboutDlg::OnBnClickedOk(void)
    {
        // TODO: Add your control notification handler code here
    }
    ```

Если вы хотите добавить обработчик событий к классу отличное от того, реализует диалоговое окно, используйте [мастер обработчиков событий](../ide/event-handler-wizard.md). Дополнительные сведения см. в разделе [Добавление обработчика событий](../ide/adding-an-event-handler-visual-cpp.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[События по умолчанию элемента управления](../windows/default-control-events.md)<br/>
[Определение переменных-членов для элементов управления диалоговых окон](../windows/defining-member-variables-for-dialog-controls.md)<br/>
[Элементы управления "Диалоговое окно" и типы переменных](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Добавление класса](../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление функции-члена](../ide/adding-a-member-function-visual-cpp.md)<br/>
[Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Переопределение виртуальной функции](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)