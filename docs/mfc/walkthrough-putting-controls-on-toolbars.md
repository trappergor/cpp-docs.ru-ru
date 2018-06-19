---
title: 'Пошаговое руководство: Размещение элементов управления на панели инструментов | Документы Microsoft'
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
ms.openlocfilehash: c134431500ed3e7b2b2229ea5b4b3da7cac6fa48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385087"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>Пошаговое руководство. Размещение элементов управления на панели инструментов
В этом разделе описывается добавление кнопки панели инструментов, содержащей элемент управления Windows на панель инструментов. Кнопки панели инструментов MFC, необходимо [класса CMFCToolBarButton](../mfc/reference/cmfctoolbarbutton-class.md)-производного класса, например [класса CMFCToolBarComboBoxButton](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton класса](../mfc/reference/cmfctoolbareditboxbutton-class.md), [Класса CMFCDropDownToolbarButton](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), или [CMFCToolBarMenuButton класса](../mfc/reference/cmfctoolbarmenubutton-class.md).  
  
## <a name="adding-controls-to-toolbars"></a>Добавление элементов управления панели инструментов  
 Чтобы добавить элемент управления панели инструментов, выполните следующие действия.  
  
1.  Зарезервировать идентификатора фиктивный ресурса для кнопки в родительский ресурс панели инструментов. Дополнительные сведения о способах создания кнопки с помощью редактор панелей инструментов в Visual Studio см. в разделе [редактор панелей инструментов](../windows/toolbar-editor.md) раздела.  
  
2.  Зарезервируйте изображение кнопки панели инструментов (значок) для кнопки в все битовые карты на панели инструментов родительской.  
  
3.  В обработчике сообщений, который обрабатывает `AFX_WM_RESETTOOLBAR` сообщение, выполните следующие действия:  
  
    1.  Создание кнопки с помощью `CMFCToolbarButton`-производного класса.  
  
    2.  Заменить фиктивный кнопки нового элемента управления с помощью [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Можно создать объект "Кнопка" в стеке, поскольку `ReplaceButton` копирует объект "Кнопка" и сохраняет копию.  
  
> [!NOTE]
>  Настройки включен в приложении, может потребоваться выполнить сброс панели инструментов с помощью **Сброс** кнопку на **панели инструментов** вкладке **Настройка** диалогового окна для просмотра обновление для элемента управления в приложении после перекомпиляции. Состояние панели инструментов сохраняется в реестре Windows, и данные реестра загружена и применена после `ReplaceButton` метод выполняется во время запуска приложения.  
  
## <a name="toolbar-controls-and-customization"></a>Элементы управления панели инструментов и настройки  
 **Команды** вкладке **Настройка** диалоговое окно содержит список команд, доступных в приложении. По умолчанию **Настройка** диалоговое окно обрабатывает меню приложения и строит список стандартных кнопок панели инструментов в каждой категории меню. Чтобы сохранить расширенных функциональных возможностей, которые предоставляют элементы управления панели инструментов, необходимо заменить кнопки панели инструментов Стандартная пользовательского элемента управления в **Настройка** диалоговое окно.  
  
 При включении настройки, вы создаете **Настройка** диалоговое окно в обработчике настройки `OnViewCustomize` с помощью [CMFCToolBarsCustomizeDialog класса](../mfc/reference/cmfctoolbarscustomizedialog-class.md) класса. Прежде чем использовать **Настройка** диалоговое окно, вызвав [CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), вызовите [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) для замены стандартной кнопки с помощью нового элемента управления.  
  
## <a name="example-creating-a-find-combo-box"></a>Пример: Создание найти поле со списком  
 В этом разделе описывается создание `Find` поле со списком, содержащие строки поиска недавно использовавшихся появляется на панели инструментов. Пользователь может введите строку в элементе управления и затем нажмите клавишу ВВОД для поиска документа или нажмите клавишу ESC для возвращения фокуса в главного фрейма. В этом примере предполагается, что документ отображается в [класс CEditView](../mfc/reference/ceditview-class.md)-производный представления.  
  
### <a name="creating-the-find-control"></a>Создание элемента управления поиска  
 Сначала создайте `Find` поле со списком:  
  
1.  Добавление ресурсов приложения и кнопки команд:  
  
    1.  В ресурсы приложения, добавьте новую кнопку с `ID_EDIT_FIND` ИД команды на панель инструментов приложения и любые точечные рисунки, связанные с панели инструментов.  
  
    2.  Создание нового пункта меню с ID_EDIT_FIND идентификатор команды.  
  
    3.  Добавьте новую строку «Найти text\nFind» в таблице строк и назначьте его `ID_EDIT_FIND_COMBO` команды идентификатор. Этот идентификатор будет использоваться как идентификатор команды `Find` кнопки поля со списком.  
  
        > [!NOTE]
        >  Поскольку `ID_EDIT_FIND` — это стандартная команда, которая обрабатывается `CEditView`, необходимые для реализации специальных обработчика для этой команды.  Тем не менее, необходимо реализовать обработчик для новой команды `ID_EDIT_FIND_COMBO`.  
  
2.  Создайте новый класс `CFindComboBox`, который является производным от [CComboBox-класс](../mfc/reference/ccombobox-class.md).  
  
3.  В `CFindComboBox` класса и переопределить методы `PreTranslateMessage` виртуального метода. Этот метод позволит обрабатывать поле со списком [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) сообщения. Если пользователь нажимает клавишу escape (`VK_ESCAPE`), Возврат фокуса фрейма главного окна. Если пользователь нажимает клавишу ВВОД (`VK_ENTER`), учет для фрейма главного окна `WM_COMMAND` сообщение, содержащее `ID_EDIT_FIND_COMBO` команды идентификатор.  
  
4.  Создание класса для `Find` кнопки поля со списком, производным от [CMFCToolBarComboBoxButton класса](../mfc/reference/cmfctoolbarcomboboxbutton-class.md). В этом примере именем является `CFindComboButton`.  
  
5.  Конструктор `CMFCToolbarComboBoxButton` принимает три параметра: идентификатор команды кнопки, кнопки индекс изображения и стиль поле со списком. Задайте эти параметры следующим образом.  
  
    1.  Передайте `ID_EDIT_FIND_COMBO` как идентификатор команды.  
  
    2.  Используйте [CCommandManager::GetCmdImage](http://msdn.microsoft.com/en-us/4094d08e-de74-4398-a483-76d27a742dca) с `ID_EDIT_FIND` получить индекс изображения.  
  
    3.  Список стили полей со списком доступных см. в разделе [стили полей со списками](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).  
  
6.  В классе `CFindComboButton` переопределите метод`CMFCToolbarComboBoxButton::CreateCombo`. Следует создать `CFindComboButton` объекта и возвращает указатель на него.  
  
7.  Используйте [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) макрос, чтобы постоянно кнопки поля со списком. Диспетчер рабочих областей автоматически загружает и сохраняет состояние кнопки в реестре Windows.  
  
8.  Реализуйте `ID_EDIT_FIND_COMBO` обработчика в представления документа. Используйте [CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) с `ID_EDIT_FIND_COMBO` для извлечения всех `Find` кнопки, кнопки поля со списком. Из-за настройки может быть несколько копий кнопки с одним и тем же Идентификатором команды.  
  
9. В обработчике сообщений ID_EDIT_FIND `OnFind`, используйте [CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) чтобы определить, является ли команды поиска было отправлено из `Find` кнопки поля со списком. В этом случае найдите текст и добавьте строку поиска в поле со списком.  
  
### <a name="adding-the-find-control-to-the-main-toolbar"></a>Добавление поиска элемента управления главной панели инструментов  
 Чтобы добавить кнопку поле со списком на панели инструментов, выполните следующие действия:  
  
1.  Реализуйте `AFX_WM_RESETTOOLBAR` обработчик сообщений `OnToolbarReset` в окне главного фрейма.  
  
    > [!NOTE]
    >  Платформа отправляет сообщение в основную область окна при инициализации панели инструментов во время запуска приложения или при сбросе во время настройки панели инструментов. В любом случае необходимо заменить кнопки панели инструментов Стандартная пользовательский `Find` кнопки поля со списком.  
  
2.  В `AFX_WM_RESETTOOLBAR` обработчик, проверьте идентификатор панели инструментов, то есть, `WPARAM` из `AFX_WM_RESETTOOLBAR` сообщения. Если равно панели инструментов, которая содержит идентификатор инструментов `Find` кнопки поля со списком, вызовите [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) заменить `Find` кнопки (то есть кнопка с Идентификатором команды `ID_EDIT_FIND)` с `CFindComboButton` объекта.  
  
    > [!NOTE]
    >  Можно создать `CFindComboBox` объекта в стеке, поскольку `ReplaceButton` копирует объект "Кнопка" и сохраняет копию.  
  
### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Добавление элемента управления для поиска в диалоговом окне настройки  
 В обработчике настройки `OnViewCustomize`, вызовите [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) заменить `Find` кнопки (то есть кнопка с Идентификатором команды `ID_EDIT_FIND)` с `CFindComboButton` объекта.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../mfc/hierarchy-chart.md)   
 [Классы](../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCToolBarButton](../mfc/reference/cmfctoolbarbutton-class.md)   
 [Класс CMFCToolBarComboBoxButton](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [Класс CMFCToolBarsCustomizeDialog](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
