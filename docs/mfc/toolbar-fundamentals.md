---
title: Основные сведения о панелях инструментов
ms.date: 11/04/2016
f1_keywords:
- RT_TOOLBAR
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
ms.openlocfilehash: d4e8793337beb2eed533fe04daf549ec21efc61d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373480"
---
# <a name="toolbar-fundamentals"></a>Основные сведения о панелях инструментов

В этой статье описывается фундаментальная реализация MFC, которая позволяет добавлять панель инструментов по умолчанию в приложение, выбрав опцию в «Волшебнике приложения». Здесь рассматриваются такие темы:

- [Опция панели инструментов «Мастер приложений»](#_core_the_appwizard_toolbar_option)

- [Панель инструментов в коде](#_core_the_toolbar_in_code)

- [Редактирование ресурса панели инструментов](#_core_editing_the_toolbar_resource)

- [Несколько батончиков инструментов](#_core_multiple_toolbars)

## <a name="the-application-wizard-toolbar-option"></a><a name="_core_the_appwizard_toolbar_option"></a>Вариант панели инструментов «Мастер приложения»

Чтобы получить единую панель инструментов с кнопками по умолчанию, выберите опцию панели инструментов Standard Docking на странице с пометкой функции пользовательского интерфейса. Это добавляет код к приложению, который:

- Создает объект панели инструментов.

- Управляет панелью инструментов, включая ее способность пристыковаться или плавать.

## <a name="the-toolbar-in-code"></a><a name="_core_the_toolbar_in_code"></a>Панель инструментов в коде

Панель инструментов — это объект [CToolBar,](../mfc/reference/ctoolbar-class.md) объявленный `CMainFrame` членом класса приложений. Другими словами, объект панели инструментов встраивается в объект окна основной рамы. Это означает, что MFC создает панель инструментов, когда она создает окно кадра и разрушает панель инструментов, когда она разрушает окно рамы. Следующее частичное объявление класса для приложения с несколькими интерфейсами документов (MDI) показывает членов данных для встроенной панели инструментов и встроенной панели статуса. Он также показывает переопределение `OnCreate` функции члена.

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

Создание панели инструментов происходит в `CMainFrame::OnCreate`. MFC вызывает [OnCreate](../mfc/reference/cwnd-class.md#oncreate) после создания окна для кадра, но прежде чем он станет видимым. По `OnCreate` умолчанию, который генерирует «Мастер приложения», выполняется следующие задачи панели инструментов:

1. Вызывает `CToolBar` функцию [члена](../mfc/reference/ctoolbar-class.md#create) создания объекта для создания основного объекта [CToolBarCtrl.](../mfc/reference/ctoolbarctrl-class.md)

1. Вызовы [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) для загрузки информации о ресурсе панели инструментов.

1. Вызовы функций для включения стыковки, плавающие, и советы инструмент. Подробнее об этих звонках читайте в статье [Стыковка и плавающих инструментов.](../mfc/docking-and-floating-toolbars.md)

> [!NOTE]
> Общий образец MFC [DOCKTOOL](../overview/visual-cpp-samples.md) включает в себя иллюстрации как старых, так и новых инструментов MFC. Панели инструментов, `COldToolbar` которые используют требуют `LoadBitmap` вызовов `LoadToolBar`в `SetButtons`шаге 2 (а не) и . Новые панели инструментов `LoadToolBar`требуют вызовов.

Стыковка, плавающие и инструмент советы звонки не являются обязательными. Вы можете удалить `OnCreate` эти строки, если вы предпочитаете. Результатом является панель инструментов, которая остается фиксированной, не в состоянии плавать или redock и не в состоянии отображать советы инструмента.

## <a name="editing-the-toolbar-resource"></a><a name="_core_editing_the_toolbar_resource"></a>Редактирование ресурса панели инструментов

Панель инструментов по умолчанию, получаемая с помощью Мастера приложения, основана на **пользовательском** RT_TOOLBAR ресурсе, представленном в версии MFC 4.0. Вы можете отредкируть этот ресурс с [помощью редактора панели инструментов.](../windows/toolbar-editor.md) Редактор позволяет легко добавлять, удалять и переставлять кнопки. Он содержит графический редактор для кнопок, который очень похож на общий графический редактор в Visual C . Если вы отредактируете панели инструментов в предыдущих версиях Visual C, вы найдете задачу намного проще.

Чтобы подключить кнопку панели инструментов к команде, вы даете кнопке идентификатор команды, `ID_MYCOMMAND`например. Укажите идентификатор команды на странице свойства кнопки в редакторе панели инструментов. Затем создайте функцию обработчика для команды (см. [Отображение сообщений к функциям](../mfc/reference/mapping-messages-to-functions.md) для получения дополнительной информации).

Новые функции участника [CToolBar](../mfc/reference/ctoolbar-class.md) работают с **ресурсом RT_TOOLBAR.** [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) теперь занимает место [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) для загрузки бит-карты изображений кнопки панели инструментов, а [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) установить стили кнопок и подключить кнопки с изображениями bitmap.

Для получения подробной информации об использовании редактора панели инструментов, [см.](../windows/toolbar-editor.md)

## <a name="multiple-toolbars"></a><a name="_core_multiple_toolbars"></a>Несколько панели инструментов

Мастер приложения предоставляет вам одну панель инструментов по умолчанию. Если в приложении требуется несколько панель инструментов, можно смоделировать код для дополнительных инструментов на основе генерируемого мастером кода для панели инструментов по умолчанию.

Если в результате команды необходимо отобразить панель инструментов:

- Создайте новый ресурс панели инструментов с `OnCreate` редактором панели инструментов и загрузите его с функцией члена [LoadToolbar.](../mfc/reference/ctoolbar-class.md#loadtoolbar)

- Встраивайте новый объект [CToolBar](../mfc/reference/ctoolbar-class.md) в класс окна основного кадра.

- Сделайте соответствующую `OnCreate` функцию вызова в стыковки или плавать панели инструментов, установить его стили, и так далее.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Внедрение панели инструментов MFC (обзорная информация о панели инструментов)](../mfc/mfc-toolbar-implementation.md)

- [Закрепленные и плавающие панели инструментов](../mfc/docking-and-floating-toolbars.md)

- [Советы инструмент инструментов панели инструментов](../mfc/toolbar-tool-tips.md)

- Классы [CToolBar](../mfc/reference/ctoolbar-class.md) и [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)

- [Использование элемента управления "Панель инструментов"](../mfc/working-with-the-toolbar-control.md)

- [Использование старых панелей инструментов](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>См. также раздел

[Реализация панели инструментов MFC](../mfc/mfc-toolbar-implementation.md)
