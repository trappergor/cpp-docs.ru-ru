---
title: Пошаговое руководство. Размещение элементов управления на панели инструментов
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: 2a801e61c49301d9b8780bbf7eb77025990337ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360269"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>Пошаговое руководство. Размещение элементов управления на панели инструментов

В этой статье описывается, как добавить кнопку панели инструментов, содержащую элемент управления Windows, в панель инструментов. В MFC кнопкой панели инструментов должен быть [класс CMFCToolBarButton](../mfc/reference/cmfctoolbarbutton-class.md)класса, например, [CMFCToolBarComboButton класса](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolEditButton класса](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbutton класса](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), или [CMFCToolBarMenuButton класса](../mfc/reference/cmfctoolbarmenubutton-class.md).

## <a name="adding-controls-to-toolbars"></a>Добавление элементов управления в панели инструментов

Чтобы добавить элемент управления в панель инструментов, выполните следующие действия:

1. Зарезервируйте идентификатор ресурсов для кнопки в родительском ресурсе панели инструментов. Для получения дополнительной информации о том, как создавать кнопки с помощью **редактора панели инструментов** в Visual Studio, смотрите статью [редактора панели инструментов.](../windows/toolbar-editor.md)

1. Зарезервируйте изображение панели инструментов (значок кнопки) для кнопки во всех бит-картах родительской панели инструментов.

1. В обработчике `AFX_WM_RESETTOOLBAR` сообщений, который обрабатывает сообщение, сделайте следующие действия:

   1. Постройте управление кнопками с помощью класса -производные. `CMFCToolbarButton`

   1. Замените кнопку манекена новым управлением с помощью [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Вы можете построить объект кнопки `ReplaceButton` на стеке, потому что копирует объект кнопки и поддерживает копию.

> [!NOTE]
> Если вы включили настройку в приложении, возможно, вам придется сбросить панель инструментов с помощью кнопки **сбросить** на вкладке **Toolbars** в поле **настраиваемых** диалогов, чтобы увидеть обновленный элемент управления в приложении после перекомпивания. Состояние панели инструментов сохраняется в реестре Windows, а информация `ReplaceButton` о реестре загружается и применяется после выполнения метода при запуске приложения.

## <a name="toolbar-controls-and-customization"></a>Управление и настройка панели инструментов

Вкладка **команд** box **of the Customize** dialog содержит список команд, доступных в приложении. По умолчанию box **Customize** dialog обрабатывает меню приложений и создает список стандартных кнопок панели инструментов в каждой категории меню. Чтобы сохранить расширенную функциональность, которую обеспечивает панель инструментов, необходимо заменить стандартную кнопку панели инструментов пользовательским управлением в поле **настраиваемых** диалогов.

При вставке создается **настраиваемый** диалоговый ящик `OnViewCustomize` в обработчике настройки с помощью класса [CMFCToolBarsCustomizeDialog.](../mfc/reference/cmfctoolbarscustomizedialog-class.md) Перед отображением **настраиваемый** диалоговые окна, позвонив [cmFCToolBarsCustomizeDialog::Создание](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), вызов [CMFCToolBarsCustomizeDialog::ReplaceButton,](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) чтобы заменить стандартную кнопку с новым управлением.

## <a name="example-creating-a-find-combo-box"></a>Пример: Создание ящика для поиска комбо

В этом разделе описывается, как создать управление комбо-коробкой **Find,** которое отображается на панели инструментов и содержит последние используемые строки поиска. Пользователь может ввести строку в элементе управления, а затем нажать ключ ввода для поиска документа, или нажмите клавишу побега, чтобы вернуть фокус к главному кадру. Этот пример предполагает, что документ отображается в представлении [класса CEditView.](../mfc/reference/ceditview-class.md)

### <a name="creating-the-find-control"></a>Создание управления поиска

Во-первых, создать **Управление** комбо-коробкой:

1. Добавьте кнопку и ее команды в ресурсы приложения:

   1. В ресурсах приложения добавьте новую кнопку с идентификатором `ID_EDIT_FIND` команды в панель инструментов в приложении и к любым бит-картам, связанным с панелью инструментов.

   1. Создайте новый элемент `ID_EDIT_FIND` меню с идентификатором команды.

   1. Добавьте новую строку «Найди текст» в строку `ID_EDIT_FIND_COMBO` и назначите идентификатор команды. Этот идентификатор будет использоваться в качестве идентификатора команды кнопки **«Найти** комбо-бокс».

        > [!NOTE]
        > Поскольку `ID_EDIT_FIND` это стандартная `CEditView`команда, которая обрабатывается, вы не обязаны реализовывать специальный обработчик для этой команды.  Однако необходимо реализовать обработчик `ID_EDIT_FIND_COMBO`для новой команды.

1. Создайте новый `CFindComboBox`класс, полученный из [класса CComboBox](../mfc/reference/ccombobox-class.md).

1. В `CFindComboBox` классе переопределить `PreTranslateMessage` виртуальный метод. Этот метод позволит комбо-коробке обработать [WM_KEYDOWN](/windows/win32/inputdev/wm-keydown) сообщение. Если пользователь попадает в`VK_ESCAPE`ключ побега (), верните фокус в окно основной рамы. Если пользователь попадает в`VK_ENTER`ключ Enter (), разместите в окне основной `WM_COMMAND` кадр апогея сообщение, содержащее идентификатор `ID_EDIT_FIND_COMBO` команды.

1. Создайте класс для кнопки **«Найти** комбо-коробку», полученную из [класса CMFCToolBarComboButtonButton.](../mfc/reference/cmfctoolbarcomboboxbutton-class.md) В этом примере используется имя `CFindComboButton`.

1. Конструктор `CMFCToolbarComboBoxButton` принимает три параметра: идентификатор команды кнопки, индекс изображения кнопки и стиль комбо-бокса. Установите следующие параметры следующим образом:

   1. Передайте `ID_EDIT_FIND_COMBO` идентификатор команды.

   1. Используйте [CCommandManager::GetCmdImage](reference/internal-classes.md) с, `ID_EDIT_FIND` чтобы получить индекс изображения.

   1. Для списка доступных стилей комбо-бокс, см [Combo-Box стили](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

1. В классе `CFindComboButton` переопределите метод`CMFCToolbarComboBoxButton::CreateCombo`. Здесь вы должны `CFindComboButton` создать объект и вернуть указатель к нему.

1. Используйте [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) макрос, чтобы сделать кнопку комбо стойкой. Менеджер рабочего пространства автоматически загружает и сохраняет состояние кнопки в реестре Windows.

1. Реализация `ID_EDIT_FIND_COMBO` обработчика в представлении документа. Используйте [CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) с `ID_EDIT_FIND_COMBO` для получения всех **кнопк Инайти** комбо-бокс. Из-за настройки может быть несколько копий кнопки с одинаковым идентификатором команды.

1. В `ID_EDIT_FIND` `OnFind`обработчике сообщений используйте [CMFCToolBar::IsLastCommandFromButton,](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) чтобы определить, была ли команда поиска отправлена с кнопки **«Найти** комбо-бокс». Если это так, найти текст и добавить строку поиска в комбо-поле.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>Добавление элемента поиска в основную панель инструментов

Чтобы добавить кнопку комбо-коробки в панель инструментов, выполните следующие действия:

1. Реализация `AFX_WM_RESETTOOLBAR` обработчика `OnToolbarReset` сообщений в окне основного кадра.

    > [!NOTE]
    > Платформа отправляет это сообщение в окно основного кадра, когда панель инструментов инициализирована во время запуска приложения, или когда панель инструментов сбросить во время настройки. В любом случае, вы должны заменить стандартную кнопку панели инструментов с пользовательской **Кнопка Найти** комбо окно.

1. В `AFX_WM_RESETTOOLBAR` обработчике изучите идентификатор панели инструментов, то есть *WPARAM* AFX_WM_RESETTOOLBAR сообщения. Если идентификатор панели инструментов равен панели инструментов, содержащей кнопку **«Найти** комбо-коробку», позвоните [по телефону CMFCToolBar::ReplaceButton,](../mfc/reference/cmfctoolbar-class.md#replacebutton) чтобы заменить кнопку **«Найти»** (т.е. кнопку с идентификатором `ID_EDIT_FIND)` команды с объектом. `CFindComboButton`

    > [!NOTE]
    > Вы можете `CFindComboBox` построить объект на `ReplaceButton` стеке, потому что копирует объект кнопки и поддерживает копию.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Добавление элемента управления поиска в настраиваемый диалоговый ящик

В обработчике `OnViewCustomize`настройки звоните [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) для замены кнопки `ID_EDIT_FIND` **«Найти»** (т.е. кнопки с идентификатором команды) с помощью `CFindComboButton` объекта.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../mfc/hierarchy-chart.md)<br/>
[Классы](../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarButton](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton класс](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBarsИнтоуктияДиолог класс](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
