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
ms.openlocfilehash: 9c784db2e1a482b313147e6837d6bbbd16d0ecb4
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775495"
---
# <a name="toolbar-fundamentals"></a>Основные сведения о панелях инструментов

В этой статье описываются основные реализации MFC, позволяющий добавить панель инструментов по умолчанию для приложения, выбрав параметр в мастере приложений. Рассмотрены следующие темы.

- [Параметр панель инструментов мастера приложений](#_core_the_appwizard_toolbar_option)

- [Панели инструментов в коде](#_core_the_toolbar_in_code)

- [Изменение ресурса панели инструментов](#_core_editing_the_toolbar_resource)

- [Несколько панелей инструментов](#_core_multiple_toolbars)

##  <a name="_core_the_appwizard_toolbar_option"></a> Параметр данных панели инструментов

Чтобы получить одну панель инструментов с кнопками по умолчанию, выберите параметр стандартное Закрепление панели инструментов на страницу с меткой возможностей пользовательского интерфейса. Это добавляет код в приложение:

- Создает объект панели инструментов.

- Управляет панели инструментов, включая его возможность закрепления или число с плавающей запятой.

##  <a name="_core_the_toolbar_in_code"></a> Панели инструментов в коде

Панель инструментов [CToolBar](../mfc/reference/ctoolbar-class.md) объект, объявленный в качестве члена данных вашего приложения `CMainFrame` класса. Другими словами объект панели инструментов внедряется в объект фрейма главного окна. Это означает, что MFC создает панели инструментов, когда он создает фрейм окна и уничтожает панели инструментов, когда она уничтожает окно фрейма. Следующее объявление разделяемого класса, для нескольких приложений интерфейса (MDI) документа отображаются элементы данных для встроенной панели инструментов и встроенная строка состояния. Также показано переопределение метода `OnCreate` функция-член.

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

Создание панели инструментов, происходит в `CMainFrame::OnCreate`. MFC вызывает [OnCreate](../mfc/reference/cwnd-class.md#oncreate) после создания окна фрейма, но прежде чем он станет видимым. Значение по умолчанию `OnCreate` что мастер приложения создает выполняет следующие задачи инструментов:

1. Вызовы `CToolBar` объекта [создать](../mfc/reference/ctoolbar-class.md#create) функция-член для создания базового [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объекта.

1. Вызовы [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) для загрузки сведений ресурса панели инструментов.

1. Вызывает функции для реализации закрепления, с плавающей запятой и всплывающие подсказки. Подробные сведения об этих вызовов, см. в статье [закрепления и плавающие панели инструментов](../mfc/docking-and-floating-toolbars.md).

> [!NOTE]
>  Пример MFC Общие [DOCKTOOL ПОКАЗАНА](../overview/visual-cpp-samples.md) включает иллюстрации новых и старых панелей инструментов MFC. Панели инструментов, использующих `COldToolbar` требуют вызовов на шаге 2, чтобы `LoadBitmap` (а не `LoadToolBar`) и `SetButtons`. Новые панели инструментов требуют вызовов `LoadToolBar`.

Закрепление, с плавающей запятой и средство советы вызовы являются необязательными. Вы можете удалить эти строки из `OnCreate` при желании. Результат — панель инструментов, которая остается предопределенной, float или redock не удалось и не удалось отобразить всплывающие подсказки.

##  <a name="_core_editing_the_toolbar_resource"></a> Изменение ресурса панели инструментов

Панель инструментов по умолчанию, вы получаете с помощью мастера приложений на основе **RT_TOOLBAR** настраиваемого ресурса, представленный в MFC версии 4.0. Можно изменить этот ресурс с [редактор панелей инструментов](../windows/toolbar-editor.md). Редактор позволяет легко добавить, удалить и переупорядочить кнопки. Он содержит графический редактор для кнопок, которая очень похожа на общие графический редактор в Visual C++. Если вы редактировали панелей инструментов в предыдущих версиях Visual C++, вы найдете задачу гораздо проще, теперь.

Соединиться с кнопки панели инструментов команду, можно присвоить кнопке идентификатор команды, такие как `ID_MYCOMMAND`. Укажите идентификатор команды на странице свойств кнопки в панели инструментов редактора. Затем создайте функцию обработчика событий для команды (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md) Дополнительные сведения).

Новый [CToolBar](../mfc/reference/ctoolbar-class.md) функции-члены работают с **RT_TOOLBAR** ресурсов. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) теперь занимает место [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) для загрузки точечного рисунка изображения кнопок панели инструментов, и [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) установить стили кнопок и подключиться кнопок с растровыми изображениями.

Дополнительные сведения об использовании редактор панелей инструментов см. в разделе [редактор панелей инструментов](../windows/toolbar-editor.md).

##  <a name="_core_multiple_toolbars"></a> Несколько панелей инструментов

Мастер приложений предоставляет панель инструментов одно значение по умолчанию. Если вам требуется более чем одной панели инструментов в приложении, вы можете моделировать кода для дополнительных панелей инструментов, на основе кода созданный мастером для панели инструментов по умолчанию.

Если вы хотите отображать панель инструментов в результате выполнения команды, вам потребуется:

- Создание ресурса панели инструментов с помощью панели инструментов редактора и загрузить его в `OnCreate` с [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) функция-член.

- Внедрение нового [CToolBar](../mfc/reference/ctoolbar-class.md) объекта в классе главного фрейма окна.

- Убедитесь, вызывает соответствующую функцию в `OnCreate` закрепление или число с плавающей запятой на панели инструментов, задайте его стили, и так далее.

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Реализация панели инструментов MFC (Общие сведения на панелях инструментов)](../mfc/mfc-toolbar-implementation.md)

- [Закрепленные и плавающие панели инструментов](../mfc/docking-and-floating-toolbars.md)

- [Всплывающие подсказки панели инструментов](../mfc/toolbar-tool-tips.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) и [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) классы

- [Работа с элементом управления панели инструментов](../mfc/working-with-the-toolbar-control.md)

- [Использование старых панелей инструментов](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>См. также

[Реализация панели инструментов MFC](../mfc/mfc-toolbar-implementation.md)
