---
title: Принципы работы инструментов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- RT_TOOLBAR
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5240cf50b35b2e1a300071ccb6cc15a065ac364e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951641"
---
# <a name="toolbar-fundamentals"></a>Основные сведения о панелях инструментов
В этой статье описываются основные реализации MFC, позволяющий добавить панель инструментов по умолчанию для приложения, выбрав параметр в мастере приложений. Рассмотрены следующие темы.  
  
-   [Параметр панель инструментов мастера приложений](#_core_the_appwizard_toolbar_option)  
  
-   [Панели инструментов в коде](#_core_the_toolbar_in_code)  
  
-   [Изменение ресурса панели инструментов](#_core_editing_the_toolbar_resource)  
  
-   [Несколько панелей инструментов](#_core_multiple_toolbars)  
  
##  <a name="_core_the_appwizard_toolbar_option"></a> Параметр инструментов данных  
 Чтобы получить одну панель инструментов с кнопками по умолчанию, выберите параметр стандартное Закрепление панели инструментов на странице с меткой возможности пользовательского интерфейса. Это добавляет код приложения:  
  
-   Создает объект панели инструментов.  
  
-   Управляет панели инструментов, включая возможности, чтобы закрепить или число с плавающей запятой.  
  
##  <a name="_core_the_toolbar_in_code"></a> Панели инструментов в коде  
 Панель инструментов, [CToolBar](../mfc/reference/ctoolbar-class.md) объекта, объявленный в качестве члена данных вашего приложения `CMainFrame` класса. Другими словами объект панели инструментов внедряется в объект фрейма главного окна. Это означает, что MFC создает панели инструментов, если он создает фрейм окна и уничтожает панели инструментов, если она уничтожает окно фрейма. Следующее объявление разделяемого класса для нескольких приложений интерфейса (MDI) документа, показаны элементы данных для встроенной панели инструментов и встроенной строке состояния. Здесь также показано переопределение метода `OnCreate` функции-члена.  
  
 [!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]  
  
 Создание панели инструментов, происходит в `CMainFrame::OnCreate`. MFC вызывает [OnCreate](../mfc/reference/cwnd-class.md#oncreate) после создания окна рамки, но прежде чем он станет видимым. Значение по умолчанию `OnCreate` , мастер приложений создает выполняет следующие задачи инструментов:  
  
1.  Вызовы `CToolBar` объекта [создать](../mfc/reference/ctoolbar-class.md#create) функции-члена для создания базового [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объекта.  
  
2.  Вызовы [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) для загрузки данных ресурса панели инструментов.  
  
3.  Вызов функции, обеспечивающие закрепления, с плавающей запятой и всплывающие подсказки. Дополнительные сведения об этих вызовов см. в статье [стыковка и плавающей панели инструментов](../mfc/docking-and-floating-toolbars.md).  
  
> [!NOTE]
>  Пример MFC Общие [DOCKTOOL ПОКАЗАНА](../visual-cpp-samples.md) включает иллюстрации старой и новой панели инструментов MFC. Панели инструментов, использующих `COldToolbar` требуют вызовов на шаге 2 в `LoadBitmap` (а не `LoadToolBar`) и `SetButtons`. Новые панели инструментов требуют вызовов `LoadToolBar`.  
  
 Закрепление, с плавающей запятой и вызовы средство советы являются необязательными. Вы можете удалить эти строки из `OnCreate` при необходимости. Результат — панель инструментов, которая остается основных, не удается float или redock и не удается отобразить всплывающие подсказки.  
  
##  <a name="_core_editing_the_toolbar_resource"></a> Изменение ресурса панели инструментов  
 Панели инструментов по умолчанию, можно получить с помощью мастера приложений на основе **RT_TOOLBAR** настраиваемого ресурса, появившиеся в версии 4.0 MFC. Можно изменить этот ресурс с [редактор панелей инструментов](../windows/toolbar-editor.md). Редактор позволяет легко добавлять, удалять и переупорядочивать кнопки. Он содержит графического редактора для кнопки, которая очень похожа на общие графический редактор в Visual C++. Изменение панели инструментов в предыдущих версиях Visual C++, можно найти задачу гораздо проще теперь.  
  
 Для подключения команду кнопки панели инструментов, вы предоставляете кнопки идентификатор команды, такие как `ID_MYCOMMAND`. Укажите идентификатор команды на странице свойств кнопки в редакторе панелей инструментов. Создайте функцию обработчика событий для выполнения команды (в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md) для получения дополнительной информации).  
  
 Новый [CToolBar](../mfc/reference/ctoolbar-class.md) функции-члены работают с **RT_TOOLBAR** ресурсов. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) теперь занимает место [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) загрузить рисунок изображения кнопок панели инструментов, и [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) задать стили кнопок и подключения кнопок с растровыми изображениями.  
  
 Дополнительные сведения об использовании редактор панелей инструментов см. в разделе [редактор панелей инструментов](../windows/toolbar-editor.md).  
  
##  <a name="_core_multiple_toolbars"></a> Несколько панелей инструментов  
 Мастер приложений предоставляет панель инструментов одно значение по умолчанию. Если требуется более чем одной панели инструментов в приложении, можно моделировать дополнительные панели инструментов, на основе мастера создания кода для панели инструментов по умолчанию в коде.  
  
 Если вы хотите отображать панель инструментов в результате выполнения команды, необходимо:  
  
-   Создание ресурса панели инструментов с помощью панели инструментов редактора и загрузить его в `OnCreate` с [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) функции-члена.  
  
-   Внедрить новую [CToolBar](../mfc/reference/ctoolbar-class.md) объекта в классе фрейма главного окна.  
  
-   Убедитесь, вызывает соответствующую функцию в `OnCreate` закрепить или число с плавающей запятой на панели инструментов, задайте его стили и так далее.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Реализация панели инструментов MFC (Общие сведения на панели инструментов)](../mfc/mfc-toolbar-implementation.md)  
  
-   [Закрепленные и плавающие панели инструментов](../mfc/docking-and-floating-toolbars.md)  
  
-   [Всплывающие подсказки панели инструментов](../mfc/toolbar-tool-tips.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) и [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) классы  
  
-   [Работа с элементом управления панели инструментов](../mfc/working-with-the-toolbar-control.md)  
  
-   [Использование старых панелей инструментов](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>См. также  
 [Реализация панели инструментов MFC](../mfc/mfc-toolbar-implementation.md)

