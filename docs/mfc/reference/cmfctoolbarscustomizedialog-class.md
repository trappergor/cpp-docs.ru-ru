---
title: Класс CMFCToolBarsCustomizeDialog
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillAllCommandsList
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesListBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCommandName
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCountInCategory
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetFlags
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::OnInitDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::PostNcDestroy
helpviewer_keywords:
- CMFCToolBarsCustomizeDialog [MFC], CMFCToolBarsCustomizeDialog
- CMFCToolBarsCustomizeDialog [MFC], FillAllCommandsList
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesComboBox
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesListBox
- CMFCToolBarsCustomizeDialog [MFC], GetCommandName
- CMFCToolBarsCustomizeDialog [MFC], GetCountInCategory
- CMFCToolBarsCustomizeDialog [MFC], GetFlags
- CMFCToolBarsCustomizeDialog [MFC], OnInitDialog
- CMFCToolBarsCustomizeDialog [MFC], PostNcDestroy
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
ms.openlocfilehash: e1dd6fff9fa4f03dbf93510da26c78c73e86c6ab
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780968"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>Класс CMFCToolBarsCustomizeDialog

Немодальное диалоговое окно вкладки ( [класс CPropertySheet](../../mfc/reference/cpropertysheet-class.md)), позволяющий пользователям настраивать панели инструментов, меню, сочетания клавиш, определенные пользователем инструменты и визуальный стиль в приложении. Обычно пользователь осуществляет доступ к этому диалоговому окну, выбирая **Настроить** в меню **Сервис** .

**Настройка** диалоговое окно содержит шесть вкладок: **Команды**, **панелей инструментов**, **средства**, **клавиатуры**, **меню**, и **параметры**.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarsCustomizeDialog : public CPropertySheet
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Создает объект `CMFCToolBarsCustomizeDialog`.|
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|Вставляет кнопки панели инструментов в списке команд на **команды** страницы|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) , добавляемый в список команд соответствующее меню на **команды** страницы.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) , добавляемый в список команд соответствующее меню на **команды** страницы.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|Загружает панель инструментов из ресурсов. Затем для каждой команды в меню вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод, чтобы добавить кнопки в список команд на **команды** страницы в указанной категории.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](#create)|Отображает **настройки** диалоговое окно.|
|`CMFCToolBarsCustomizeDialog::EnableTools`|Зарезервировано для будущего использования.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Включает или отключает создание новых панелей инструментов с помощью **Настройка** диалоговое окно.|
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Заполняет предоставленный `CListBox` объекта с помощью команд в **все команды** категории.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Заполняет предоставленный `CComboBox` объект с именем каждой категории команды в **Настройка** диалоговое окно.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Заполняет предоставленный `CListBox` объект с именем каждой категории команды в **Настройка** диалоговое окно.|
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|Получает имя, связанный с данной команды.|
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Возвращает число элементов в предоставленном списке с меткой заданный текст.|
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|Получает набор флагов, влияющих на поведение диалогового окна.|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Запускает редактор изображений, таким образом, пользователь может изменять значка элемента кнопки или меню на панели инструментов.|
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|Переопределяет для дополнения инициализации листа свойств. (Переопределяет [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|Вызвано структурой после уничтожения окна. (Переопределяет `CPropertySheet::PostNcDestroy`.)|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Удаление кнопки с заданным Идентификатором команды, указанной категории, или из всех категорий.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|Переименовывает категорию в списке категорий на **команды** вкладки.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|Заменяет кнопки в список команд на **команды** вкладки, используя новый объект кнопки панели инструментов.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|Добавляет категорию в список категорий, которые будут отображаться на **команды** вкладки.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|Вызывается платформой для определения, является ли допустимым список пользовательских средств.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Вызывается платформой при изменении свойств инструмента, определенного пользователем.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Определяет, ли указанный сочетания клавиш могут быть назначены действия.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Определяет, возможно ли изменение инструмента, определенного пользователем.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Вызывается платформой, когда пользователь выбирает **средства** запрашивается вкладки.|

## <a name="remarks"></a>Примечания

Для отображения **Настройка** диалоговом окне создания `CMFCToolBarsCustomizeDialog` и вызовите [CMFCToolBarsCustomizeDialog::Create](#create) метод.

Хотя **Настройка** диалоговое окно активна, приложение работает в специальный режим, который ограничивает пользователя задач настройки.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCToolBarsCustomizeDialog` . В примере для замены на кнопке панели инструментов в окне списка команд **команды** странице, включите создание новых панелей инструментов с помощью **Настройка** диалоговое окно параметров отображения и  **Настройки** диалоговое окно. Этот фрагмент кода является частью [IE демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxToolBarsCustomizeDialog.h

##  <a name="addbutton"></a>  CMFCToolBarsCustomizeDialog::AddButton

Вставляет кнопки панели инструментов в списке команд на **команды** страницы.

```
void AddButton(
    UINT uiCategoryId,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);

void AddButton(
    LPCTSTR lpszCategory,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);
```

### <a name="parameters"></a>Параметры

*uiCategoryId*<br/>
[in] Указывает идентификатор категории, к которому следует вставить кнопку.

*Кнопка*<br/>
[in] Указывает кнопку для вставки.

*iInsertBefore*<br/>
[in] Указывает отсчитываемый от нуля индекс кнопки на панели инструментов, перед которым кнопка будет вставлена.

*lpszCategory*<br/>
[in] Указывает строку категории для вставки кнопки.

### <a name="remarks"></a>Примечания

`AddButton` Метод игнорирует кнопок, которые имеют стандартные идентификаторы команд (например, ID_FILE_MRU_FILE1), команды, не допускаются (см. в разделе [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) и пустой кнопок.

Этот метод создает новый объект того же типа как `button` (обычно [класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)) с помощью класса среды выполнения кнопки. Затем он вызывает [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) будут копироваться элементы данных кнопки и вставляет ее в указанной категории.

При вставке новой кнопки, он получает `OnAddToCustomizePage` уведомлений.

Если `iInsertBefore` равно -1, кнопки добавлен в список категорий; в противном случае она вставляется перед элементом с заданным индексом.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `AddButton` метод `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [пример ползунок](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

##  <a name="addmenu"></a>  CMFCToolBarsCustomizeDialog::AddMenu

Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) , добавляемый в список команд соответствующее меню на **команды** страницы.

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>Параметры

*uiMenuResId*<br/>
[in] Указывает идентификатор ресурса меню для загрузки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если меню был успешно добавлен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

В вызове `AddMenuCommands`, *bPopup* имеет значение FALSE. Таким образом этот метод не добавляет элементы меню, содержащие подменю в список команд. Этот метод добавляет пункты меню в подменю в список команд.

##  <a name="addmenucommands"></a>  CMFCToolBarsCustomizeDialog::AddMenuCommands

Добавляет элементы в список команд в **команды** страницу, чтобы добавить все элементы в указанное меню.

```
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>Параметры

*pMenu*<br/>
[in] Указатель на объект CMenu для добавления.

*bPopup*<br/>
[in] Указывает, следует ли вставлять элементы всплывающего меню к списку команд.

*lpszCategory*<br/>
[in] Имя категории для вставки в меню.

*lpszMenuPath*<br/>
[in] Префикс, который добавляется к имени, когда команда отображается в **все категории** списка.

### <a name="remarks"></a>Примечания

`AddMenuCommands` Метод циклы по всем элементам меню *pMenu*. Для каждого пункта меню, который не содержит подменю, этот метод создает [класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) и вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод, чтобы добавить элемент меню как панель инструментов кнопки в список команд **команды** страницы. Разделители учитываются в этом процессе.

Если *bPopup* имеет значение TRUE, для каждого пункта меню, который содержит подменю этот метод создает [класс CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) объекта и вставляет его в список команд, вызвав `AddButton`. В противном случае элементы меню, содержащие подменю не отображаются в списке команд. В любом случае при `AddMenuCommands` встречает элемент меню с подменю он вызывает себя рекурсивно, передача указателя в подменю как *pMenu* параметра и при добавлении метки в подменю для *lpszMenuPath*.

##  <a name="addtoolbar"></a>  CMFCToolBarsCustomizeDialog::AddToolBar

Загружает панель инструментов из ресурсов. Затем для каждой команды в меню вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод, чтобы добавить кнопки в список команд на **команды** страницы в указанной категории.

```
BOOL AddToolBar(
    UINT uiCategoryId,
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,
    UINT uiToolbarResId);
```

### <a name="parameters"></a>Параметры

*uiCategoryId*<br/>
[in] Указывает идентификатор ресурса категории для добавления панели инструментов.

*uiToolbarResId*<br/>
[in] Указывает идентификатор ресурса панели инструментов, команды которого вставляются в список команд.

*lpszCategory*<br/>
[in] Задает имя категории, к которому добавляются на панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `AddToolBar` метод в `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода входит в состав [примера Word Pad](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>Примечания

Элемент управления, который используется для представления каждой из них является [класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) объекта. После добавления панели инструментов, можно заменить кнопки элемента управления, производного типа путем вызова [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton).

##  <a name="checktoolsvalidity"></a>  CMFCToolBarsCustomizeDialog::CheckToolsValidity

Проверяет допустимость список средств пользователя.

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>Параметры

*lstTools*<br/>
[in] Список пользовательских средств для проверки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если список пользовательских средств является допустимым; в противном случае — значение FALSE. Реализация по умолчанию всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод для проверки допустимости объектов, представляющих определенные пользователем инструменты, возвращенный [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity).

Переопределить `CheckToolsValidity` метод в класс, производный от `CMFCToolBarsCustomizeDialog` Если вы хотите проверить средства пользователя, прежде чем пользователь закрывает диалоговое окно. Если этот метод возвращает значение FALSE, когда пользователь нажимает какую-либо **закрыть** кнопки в правом верхнем углу диалогового окна, или кнопку с надписью **закрыть** в правом нижнем углу диалоговое окно Отображает **средства** вкладке вместо закрытия. Если этот метод возвращает значение FALSE, когда пользователь щелкает вкладку для перехода с **средства** вкладке навигации не происходит. Отобразится окно сообщения для уведомления пользователя неполадку, вызвавшую неудачную проверку.

##  <a name="cmfctoolbarscustomizedialog"></a>  CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog

Создает объект `CMFCToolBarsCustomizeDialog`.

```
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bAutoSetFromMenus = FALSE,
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```

### <a name="parameters"></a>Параметры

*pWndParentFrame*<br/>
[in] Указатель на родительского фрейма. Этот параметр не должен иметь значение NULL.

*bAutoSetFromMenus*<br/>
[in] Логическое значение, указывающее, следует ли добавить команды меню из всех меню списка команд на **команды** страницы. Если этот параметр имеет значение TRUE, будут добавлены команды меню. В противном случае не добавляются команды меню.

*uiFlags*<br/>
[in] Сочетание флагов, влияющих на поведение диалогового окна. Этот параметр может иметь один или несколько из следующих значений:

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*plistCustomPages*<br/>
[in] Указатель на список `CRuntimeClass` объектов, указывающих дополнительные настраиваемые страницы.

### <a name="remarks"></a>Примечания

*PlistCustomPages* параметр ссылается на список `CRuntimeClass` объектов, указывающих дополнительные настраиваемые страницы. Конструктор добавляет дополнительные страницы в диалоговое окно с помощью [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) метод. См. в образце CustomPages пример, который добавляет большего числа страниц **Настройка** диалоговое окно.

Дополнительные сведения о значениях, которые можно передать в *uiFlags* параметр, см. в разделе [CMFCToolBarsCustomizeDialog::GetFlags](#getflags).

### <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [пример пользовательские страницы](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

##  <a name="create"></a>  CMFCToolBarsCustomizeDialog::Create

Отображает **настройки** диалоговое окно.

```
virtual BOOL Create();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если окно свойств настройки создан успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызовите `Create` метод только после полной инициализации класса.

##  <a name="enableuserdefinedtoolbars"></a>  CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars

Включает или отключает создание новых панелей инструментов с помощью **Настройка** диалоговое окно.

```
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Значение TRUE, чтобы включить пользовательские панели инструментов; Значение FALSE, чтобы отключить панели инструментов.

### <a name="remarks"></a>Примечания

Если *bEnable* имеет значение TRUE, **New**, **Переименовать** и **удалить** кнопок на **панелей инструментов** страница.

По умолчанию или если *bEnable* имеет значение FALSE, эти кнопки не отображаются и пользователь не может определить новые панели инструментов.

##  <a name="fillallcommandslist"></a>  CMFCToolBarsCustomizeDialog::FillAllCommandsList

Заполняет предоставленный `CListBox` объекта с помощью команд в **все команды** категории.

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>Параметры

*wndListOfCommands*<br/>
[out] Ссылку на `CListBox` объекта для заполнения.

### <a name="remarks"></a>Примечания

**Все команды** категории команды из всех категорий. [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) , связанный с предоставленным кнопку, чтобы команда добавляет метод **все команды** категории для вас.

Этот метод очищает содержимое предоставленного `CListBox` объекта перед его заполнением с командами в **все команды** категории.

`CMFCMousePropertyPage` Класс использует этот метод для заполнения поле со списком событий двойного щелчка.

##  <a name="fillcategoriescombobox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesComboBox

Заполняет предоставленный `CComboBox` объект с именем каждой категории команды в **Настройка** диалоговое окно.

```
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Параметры

*wndCategory*<br/>
[out] Ссылку на `CComboBox` объекта для заполнения.

*bAddEmpty*<br/>
[in] Логическое значение, указывающее, следует ли добавить категории в поле со списком, у которых нет команды. Если этот параметр имеет значение TRUE, пустые категории добавляются в поле со списком. В противном случае — пустой категории не добавляются.

### <a name="remarks"></a>Примечания

Этот метод аналогичен [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) метод за исключением того, что этот метод работает с `CComboBox` объекта.

Этот метод не очищает содержимое `CComboBox` объекта перед его заполнением. Он гарантирует, что **все команды** категории — последний элемент в поле со списком.

Можно добавить новые категории команду с помощью [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод. Можно изменить имя существующей категории с помощью [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) метод.

`CMFCToolBarsKeyboardPropertyPage` И `CMFCKeyMapDialog` классы используют этот метод для категоризации назначения клавиш клавиатуры.

##  <a name="fillcategorieslistbox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesListBox

Заполняет предоставленный `CListBox` объект с именем каждой категории команды в **Настройка** диалоговое окно.

```
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Параметры

*wndCategory*<br/>
[out] Ссылку на `CListBox` объекта для заполнения.

*bAddEmpty*<br/>
[in] Логическое значение, указывающее, следует ли добавить категории в поле списка, у которых нет команды. Если этот параметр имеет значение TRUE, пустые категории добавляются в поле со списком. В противном случае — пустой категории не добавляются.

### <a name="remarks"></a>Примечания

Этот метод аналогичен [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) метод за исключением того, что этот метод работает с `CListBox` объекта.

Этот метод не очищает содержимое `CListBox` объекта перед его заполнением. Он гарантирует, что **все команды** категории — последний элемент в поле со списком.

Можно добавить новые категории команду с помощью [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод. Можно изменить имя существующей категории с помощью [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) метод.

`CMFCToolBarsCommandsPropertyPage` Класс использует этот метод для отображения списка команд, связанный с каждой категорией команды.

##  <a name="getcommandname"></a>  CMFCToolBarsCustomizeDialog::GetCommandName

Получает имя, связанный с данной команды.

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
[in] Идентификатор команды для получения.

### <a name="return-value"></a>Возвращаемое значение

Имя, связанное с заданным Идентификатором команды, или значение NULL, если команда не существует.

##  <a name="getcountincategory"></a>  CMFCToolBarsCustomizeDialog::GetCountInCategory

Возвращает число элементов в предоставленном списке с меткой заданный текст.

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>Параметры

*lpszItemName*<br/>
[in] Текстовая подпись для сопоставления.

*lstCommands*<br/>
[in] Ссылку на список, содержащий `CMFCToolBarButton` объектов.

### <a name="return-value"></a>Возвращаемое значение

Число элементов в предоставленном списке которого равно текст метки *lpszItemName*.

### <a name="remarks"></a>Примечания

Каждый элемент в списке предоставленный объект должен иметь тип `CMFCToolBarButton`. Этот метод сравнивает *lpszItemName* с [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) данные-член.

##  <a name="getflags"></a>  CMFCToolBarsCustomizeDialog::GetFlags

Получает набор флагов, влияющих на поведение диалогового окна.

```
UINT GetFlags() const;
```

### <a name="return-value"></a>Возвращаемое значение

Набор флагов, влияющих на поведение диалогового окна.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение *uiFlags* параметр, передаваемый в конструктор. Возвращаемое значение может быть один или несколько из следующих значений:

|||
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|Позволяет пользователю указать тени внешний вид меню.  |
|AFX_CUSTOMIZE_TEXT_LABELS|Позволяет пользователю указать, показываются ли подписи текст под изображениями кнопок панели инструментов.  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|Позволяет пользователю указать стиль анимации меню.  |
|AFX_CUSTOMIZE_NOHELP|Удаляет кнопку "Справка" в диалоговом окне настройки.  |
|AFX_CUSTOMIZE_CONTEXT_HELP|Позволяет WS_EX_CONTEXTHELP визуальный стиль.  |
|AFX_CUSTOMIZE_NOTOOLS|Удаляет **средства** страницы в диалоговом окне настройки. Этот флаг допустим, если приложение использует `CUserToolsManager` класса.  |
|AFX_CUSTOMIZE_MENUAMPERS|Позволяет подписей кнопок должен содержать амперсанда ( **&**) символов.  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|Удаляет **крупные значки** параметр в диалоговом окне настройки.  |

Дополнительные сведения о визуальном стиле WS_EX_CONTEXTHELP см. в разделе [расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

##  <a name="onafterchangetool"></a>  CMFCToolBarsCustomizeDialog::OnAfterChangeTool

Реагирует на изменения в пользовательский инструмент, сразу же после возникновения.

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Параметры

*pSelTool*<br/>
[in, out] Указатель на объект пользователя средства, которое было изменено.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда пользователь изменяет свойства инструмента, определенного пользователем. Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в класс, производный от `CMFCToolBarsCustomizeDialog` для выполнения обработки после изменении пользовательский инструмент.

##  <a name="onassignkey"></a>  CMFCToolBarsCustomizeDialog::OnAssignKey

Проверяет сочетания клавиш, так как пользователь определяет их.

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>Параметры

*pAccel*<br/>
[in, out] Указатель на назначение предложенное клавиатуры, который выражается в виде [УСКОРЕНИЕ](/windows/desktop/api/winuser/ns-winuser-tagaccel) структуры.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ключ может быть назначенных или FALSE, если ключ не может быть назначена. Реализация по умолчанию всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе для выполнения дополнительной обработки, когда пользователь назначает новое сочетание клавиш или проверить сочетания клавиш, как пользователь определяет их. Чтобы запретить присваивание ярлык, возвращает значение FALSE. Следует также отобразить окно сообщения или в противном случае информировать пользователей об причина, почему был отклонен сочетания клавиш.

##  <a name="onbeforechangetool"></a>  CMFCToolBarsCustomizeDialog::OnBeforeChangeTool

Выполняет специальной обработки при изменении пользовательский инструмент, когда пользователь собирается применить изменение.

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Параметры

*pSelTool*<br/>
[in, out] Указатель на объект средства пользователя, который должен быть заменен.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда свойства инструмента, определенного пользователем. Реализация по умолчанию не выполняет никаких действий. Переопределить `OnBeforeChangeTool` метод в класс, производный от `CMFCToolBarsCustomizeDialog` Если вы хотите выполнить обработку, прежде чем произойдет изменение пользовательский инструмент, например для освобождения ресурсов, *pSelTool* использует.

##  <a name="onedittoolbarmenuimage"></a>  CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage

Запускает редактор изображений, таким образом, пользователь может изменять значка элемента кнопки или меню на панели инструментов.

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Указатель на родительское окно.

*Точечный рисунок*<br/>
[in] Ссылка на объект точечного рисунка для редактирования.

*nBitsPerPixel*<br/>
[in] Битовая карта, разрешения в битах на пиксель.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если изменение фиксируется; в противном случае — значение FALSE. Реализация по умолчанию отображается диалоговое окно и возвращает TRUE, если пользователь нажимает кнопку **ОК**, или значение FALSE, если пользователь нажимает кнопку **отменить** или **закрыть** кнопки.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда пользователь запускает редактор изображений. Отображает реализации по умолчанию [класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md) диалоговое окно. Переопределить `OnEditToolbarMenuImage` в производном классе для редактирования в пользовательский образ.

##  <a name="oninitdialog"></a>  CMFCToolBarsCustomizeDialog::OnInitDialog

Переопределяет для дополнения инициализации листа свойств.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова метода [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) метод.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog), отобразив **закрыть** кнопки, убедившись, что в диалоговом окне соответствует текущий размер экрана и путем перемещения **Помочь** кнопку в левом нижнем углу диалоговое окно.

##  <a name="oninittoolspage"></a>  CMFCToolBarsCustomizeDialog::OnInitToolsPage

Обрабатывает уведомления из .NET framework, **средства** страница является должен быть инициализирован.

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в производном классе для обработки этого уведомления.

##  <a name="postncdestroy"></a>  CMFCToolBarsCustomizeDialog::PostNcDestroy

Вызвано структурой после уничтожения окна.

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, `CPropertySheet::PostNcDestroy`, восстановив его в предыдущий режим.

[CMFCToolBarsCustomizeDialog::Create](#create) метод помещает приложение в специальный режим, который ограничивает пользователя задач настройки.

##  <a name="removebutton"></a>  CMFCToolBarsCustomizeDialog::RemoveButton

Удаление кнопки с заданным Идентификатором команды, указанной категории, или из всех категорий.

```
int RemoveButton(
    UINT uiCategoryId,
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,
    UINT uiCmdId);
```

### <a name="parameters"></a>Параметры

*uiCategoryId*<br/>
[in] Указывает идентификатор категории, из которого следует удалить кнопку.

*uiCmdId*<br/>
[in] Указывает идентификатор команды кнопки.

*lpszCategory*<br/>
[in] Задает имя категории, из которого следует удалить кнопку.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс кнопка удаляется или -1, если заданный идентификатор команды не был найден в указанной категории. Если *uiCategoryId* равно -1, возвращаемое значение равно 0.

### <a name="remarks"></a>Примечания

Чтобы удалить кнопку из всех категорий, вызовите первая перегрузка этого метода и набор *uiCategoryId* значение -1.

##  <a name="renamecategory"></a>  CMFCToolBarsCustomizeDialog::RenameCategory

Переименовывает категорию в списке категорий на **команды** страницы.

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>Параметры

*lpszCategoryOld*<br/>
[in] Чтобы изменить имя категории.

*lpszCategoryNew*<br/>
[in] Имя новой категории.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Имя категории должно быть уникальным.

##  <a name="replacebutton"></a>  CMFCToolBarsCustomizeDialog::ReplaceButton

Заменяет кнопки панели инструментов в окне списка команд на **команды** страницы.

```
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
[in] Указывает команду кнопки, чтобы заменить.

*Кнопка*<br/>
[in] Объект **const** ссылку на объект кнопки панели инструментов, который заменяет старый кнопки.

### <a name="remarks"></a>Примечания

Когда [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), или [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) добавляет команды **команды** странице, что команда находится в форме [класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) объекта (или [класс CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) объекта для меню элемент, который содержит добавленные подменю `AddMenuCommands`). Платформа также вызывает эти три метода, чтобы автоматически добавить команды. Команды должны быть представлены с производным типом, вместо этого следует вызвать `ReplaceButton` и передайте в кнопке производного типа.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `ReplaceButton` метод в `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

##  <a name="setusercategory"></a>  CMFCToolBarsCustomizeDialog::SetUserCategory

Указывает, какая категория в списке категорий на **команды** страница является категорию пользовательских параметров. Эту функцию необходимо вызывать перед вызовом метода [CMFCToolBarsCustomizeDialog::Create](#create).

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>Параметры

*lpszCategory*<br/>
[in] Имя категории.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Параметр категории пользователя в настоящее время не используется платформой.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CPropertySheet](../../mfc/reference/cpropertysheet-class.md)
