---
title: 'Пошаговое руководство: Размещение элементов управления на панели инструментов | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c50be81cbddb30752f401ca7a1784cfe428c379b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384564"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>Пошаговое руководство. Размещение элементов управления на панели инструментов

В этом разделе описывается добавление кнопки панели инструментов, содержащий элемент управления Windows на панель инструментов. Кнопки панели инструментов MFC, необходимо [класс CMFCToolBarButton](../mfc/reference/cmfctoolbarbutton-class.md)-производного класса, например [класс CMFCToolBarComboBoxButton](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [класс CMFCToolBarEditBoxButton](../mfc/reference/cmfctoolbareditboxbutton-class.md), [Класс CMFCDropDownToolbarButton](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), или [класс CMFCToolBarMenuButton](../mfc/reference/cmfctoolbarmenubutton-class.md).

## <a name="adding-controls-to-toolbars"></a>Добавление элементов управления панели инструментов

Чтобы добавить элемент управления панели инструментов, выполните следующие действия.

1. Зарезервируйте идентификатор фиктивный ресурс для кнопки в панели инструментов к родительскому ресурсу. Дополнительные сведения о том, как создавать кнопки, используя редактор панелей инструментов в Visual Studio см. в разделе [редактор панелей инструментов](../windows/toolbar-editor.md) раздела.

1. Резервирование для кнопки в все битовые карты родительской панели инструментов значок панели инструментов (значок кнопки).

1. В обработчике сообщений, который обрабатывает сообщение AFX_WM_RESETTOOLBAR сделайте следующее:

   1. Создать элемент управления button с помощью `CMFCToolbarButton`-производного класса.

   1. Заменить фиктивные кнопку Новый элемент управления с помощью [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Можно создать объект кнопки в стеке, потому что `ReplaceButton` копирует объект кнопки и сохраняет копию.

> [!NOTE]
>  Если вы включили настройки в приложении, возможно потребуется выполнить сброс панели инструментов с помощью **Сброс** , нажмите кнопку **панелей инструментов** вкладке **Настройка** диалоговое окно, чтобы см. в разделе обновленный элемент управления в приложение после перекомпиляции. Состояние панели инструментов сохраняется в реестре Windows, и данные реестра загружается и применяется после `ReplaceButton` метод выполняется во время запуска приложения.

## <a name="toolbar-controls-and-customization"></a>Элементы управления панели инструментов и их настройка

**Команды** вкладке **Настройка** диалоговое окно со списком всех команд, доступных в приложении. По умолчанию **Настройка** диалоговое окно обрабатывает меню приложения и строит список стандартных кнопок панели инструментов в каждой категории меню. Чтобы сохранить расширенные функции, которые предоставляют элементы управления панели инструментов, необходимо заменить стандартных кнопок панели инструментов с пользовательским элементом управления в **Настройка** диалоговое окно.

При включении настройки, вы создаете **Настройка** диалоговое окно, в обработчике настройки `OnViewCustomize` с помощью [класс CMFCToolBarsCustomizeDialog](../mfc/reference/cmfctoolbarscustomizedialog-class.md) класса. Прежде чем использовать **Настройка** диалоговое окно, вызвав [CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), вызовите [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) для замены стандартной кнопки с помощью нового элемента управления.

## <a name="example-creating-a-find-combo-box"></a>Пример: Создание поле со списком поиска

В этом разделе описывается создание **найти** поле со списком, содержащие строки поиска в недавно использованные отображается на панели инструментов. Пользователь может введите строку в элементе управления и затем нажмите клавишу ВВОД для поиска документа или нажмите клавишу ESC для возвращения фокуса в главном фрейме. В этом примере предполагается, что документ отображается в [класс CEditView](../mfc/reference/ceditview-class.md)-производным представления.

### <a name="creating-the-find-control"></a>Создание элемента управления Find

Во-первых, создайте `Find` поле со списком:

1. Добавьте кнопку и соответствующие команды к ресурсам приложения:

   1. В ресурсы приложения, добавьте новую кнопку с `ID_EDIT_FIND` ИД команды в панели инструментов приложения и любые точечные рисунки, связанные с панелью инструментов.

   1. Создать новый элемент меню с ID_EDIT_FIND идентификатор команды.

   1. Добавить новую строку «Найти text\nFind» в таблице строк и назначьте его `ID_EDIT_FIND_COMBO` команды идентификатор. Этот идентификатор будет использоваться как идентификатор команды `Find` кнопку в окне со списком.

        > [!NOTE]
        >  Так как `ID_EDIT_FIND` — это стандартная команда, которая обрабатывается `CEditView`, не требуются для реализации специальный обработчик для этой команды.  Тем не менее, необходимо реализовать обработчик для новой команды `ID_EDIT_FIND_COMBO`.

1. Создайте новый класс, `CFindComboBox`, который является производным от [класс CComboBox](../mfc/reference/ccombobox-class.md).

1. В `CFindComboBox` класса, переопределить `PreTranslateMessage` виртуального метода. Этот метод позволит поле со списком для обработки [WM_KEYDOWN](/windows/desktop/inputdev/wm-keydown) сообщения. Если пользователь нажимает клавишу escape (`VK_ESCAPE`), Возврат фокуса к фрейма главного окна. Если пользователь нажимает клавишу ВВОД (`VK_ENTER`), публикация для фрейма главного окна сообщения WM_COMMAND, содержащий `ID_EDIT_FIND_COMBO` команды идентификатор.

1. Создание класса для **найти** кнопку в окне со списком, производный от [класс CMFCToolBarComboBoxButton](../mfc/reference/cmfctoolbarcomboboxbutton-class.md). В этом примере именем является `CFindComboButton`.

1. Конструктор `CMFCToolbarComboBoxButton` принимает три параметра: идентификатор команды кнопки, кнопки индекс изображения и стиль поля со списком. Установите эти параметры следующим образом:

   1. Передайте `ID_EDIT_FIND_COMBO` как идентификатор команды.

   1. Используйте [CCommandManager::GetCmdImage](reference/internal-classes.md) с `ID_EDIT_FIND` получить индекс изображения.

   1. Список стили поля со списком доступных, см. в разделе [поле со списком стилей](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

1. В классе `CFindComboButton` переопределите метод`CMFCToolbarComboBoxButton::CreateCombo`. Здесь необходимо создать `CFindComboButton` объекта и возвращает указатель на него.

1. Используйте [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) макрос для постоянных кнопки поля со списком. Администратор рабочей области автоматически загружает и сохраняет состояние кнопки в реестре Windows.

1. Реализуйте `ID_EDIT_FIND_COMBO` обработчика в представлении документа. Используйте [CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) с `ID_EDIT_FIND_COMBO` для извлечения всех **найти** кнопки поля со списком. Из-за настроек может существовать несколько копий кнопки с тем же Идентификатором команды.

9. В обработчике сообщений ID_EDIT_FIND `OnFind`, использовать [CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) для определения ли команда find был отправлен **найти** кнопку в окне со списком. Если Да, поиска текста и добавить строку поиска в поле со списком.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>Добавление элемента управления Find на главную панель инструментов

Чтобы добавить кнопку поле со списком на панели инструментов, выполните следующие действия:

1. Реализуйте `AFX_WM_RESETTOOLBAR` обработчик сообщений `OnToolbarReset` в фрейма главного окна.

    > [!NOTE]
    >  Платформы отправляет это сообщение фрейма главного окна в том случае, когда панель инструментов инициализируется во время запуска приложения или при сбросе во время настройки панели инструментов. В любом случае необходимо заменить стандартных кнопок панели инструментов пользовательского **найти** кнопку в окне со списком.

1. В `AFX_WM_RESETTOOLBAR` обработчика, то есть проверить идентификатор панели инструментов, *WPARAM* AFX_WM_RESETTOOLBAR сообщения. Если идентификатор панели инструментов на панели инструментов, содержащий равно **найти** кнопку в окне со списком, вызов [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) для замены **найти** кнопки (т. е Кнопка с Идентификатором команды `ID_EDIT_FIND)` с `CFindComboButton` объекта.

    > [!NOTE]
    >  Вы можете создать `CFindComboBox` объект в стеке, поскольку `ReplaceButton` копирует объект кнопки и сохраняет копию.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Добавление поиска элемента управления в диалоговом окне настройки

В обработчике настройки `OnViewCustomize`, вызовите [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) для замены **найти** кнопки (то есть кнопка с Идентификатором команды `ID_EDIT_FIND)` с `CFindComboButton` объекта.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../mfc/hierarchy-chart.md)<br/>
[Классы](../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarButton](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Класс CMFCToolBarComboBoxButton](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[Класс CMFCToolBarsCustomizeDialog](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
