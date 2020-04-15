---
title: CMFCToolBarsИнтоуктияДиолог класс
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
ms.openlocfilehash: d47ecf45a7bbfc563be0c05cd15ee84d430f502f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377366"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsИнтоуктияДиолог класс

Нештатная панельная панель вкладок [(CPropertySheet Class),](../../mfc/reference/cpropertysheet-class.md)которая позволяет пользователю настроить панели инструментов, меню, ярлыки клавиатуры, инструменты, определяемые пользователем, и визуальный стиль в приложении. Обычно пользователь осуществляет доступ к этому диалоговому окну, выбирая **Настроить** в меню **Сервис** .

**Настраиваемый** диалоговые окна имеет шесть вкладок: **команды,** **панели инструментов,** **инструменты,** **клавиатура,** **меню**и **параметры.**

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarsCustomizeDialog : public CPropertySheet
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Формирует объект `CMFCToolBarsCustomizeDialog`.|
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBars ИнутонажДиолог::Добавить кнопку](#addbutton)|Вставляет кнопку панели инструментов в список команд на странице **Команд**|
|[CMFCToolBars ИнутонажДиолог::AddMenu](#addmenu)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands,](#addmenucommands) чтобы добавить это меню в список команд на странице **Команд.**|
|[CMFCToolBarsCustomizeДиалого::AddMenuCommands](#addmenucommands)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands,](#addmenucommands) чтобы добавить это меню в список команд на странице **Команд.**|
|[CMFCToolBars ИнутонажДиолог::AddToolBar](#addtoolbar)|Загружает панель инструментов из ресурсов. Затем для каждой команды в меню требуется [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод вставить кнопку в список команд на странице **команд** в указанной категории.|
|[CMFCToolBars ИнутодионтироватьДиалого::Создание](#create)|Отображает поле **диалогового настройки.**|
|`CMFCToolBarsCustomizeDialog::EnableTools`|Зарезервировано для последующего использования.|
|[CMFCToolBarsИнтодиалДиолог::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Позволяет или отстращает создание новых панелей инструментов с помощью **настраиваемой** диалоговой коробки.|
|[CMFCToolBarsИнтоутеДиолог::FillAllCommandsList](#fillallcommandslist)|Заполняет предоставленный `CListBox` объект командами в категории **Все команды.**|
|[CMFCToolBarsИнтоутеДиолог::FillCategoriesComboBox](#fillcategoriescombobox)|Заполняет предоставленный `CComboBox` объект с именем каждой категории команд в поле **настраиваемых** диалогов.|
|[CMFCToolBarsИнтоутеДиолог::FillCategoriesListBox](#fillcategorieslistbox)|Заполняет предоставленный `CListBox` объект с именем каждой категории команд в поле **настраиваемых** диалогов.|
|[CMFCToolBarsИнтоутеДиолог::GetCommandName](#getcommandname)|Извлекает имя, связанное с данным идентификатором команды.|
|[CMFCToolBarsИнтоутеДиолог::GetCountInCategory](#getcountincategory)|Извлекает количество элементов в предоставленном списке, которые имеют заданную текстовую метку.|
|[CMFCToolBars ИнутонажДиолог::GetFlags](#getflags)|Извлекает набор флагов, влияющих на поведение диалогового окна.|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCToolBarsCustomizeДиалог::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Запускает редактор изображений, чтобы пользователь мог настроить кнопку панели инструментов или значок элемента меню.|
|[CMFCToolBarsИнтодиалДиолог::OnInitДиалог](#oninitdialog)|Переопределения для увеличения инициализации листа свойств. (Переопределяет [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCToolBars CustomizeDialog::PostNcDestroy](#postncdestroy)|Вызывается рамками после того, как окно было уничтожено. (Переопределяет `CPropertySheet::PostNcDestroy`.)|
|[CMFCToolBarsИнтодиалДиолог::Удалить кнопку](#removebutton)|Удаляет кнопку с указанным идентификатором команды из указанной категории или из всех категорий.|
|[CMFCToolBarsИнтоутеДиолог::ПереименованиеКатегория](#renamecategory)|Переименуем категорию в поле списка категорий на вкладке **Команд.**|
|[CMFCToolBars ИнутоньюсДиолог::Заменить кнопку](#replacebutton)|Заменяет кнопку в списке команд на **вкладке Команд** новым объектом кнопки панели инструментов.|
|[CMFCToolBarsИнтодиалДиолог::SetUserКатегория](#setusercategory)|Добавляет категорию в список категорий, которые будут отображаться на вкладке **«Команды».**|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBars ИнутомердиДиалог::CheckToolsValidity](#checktoolsvalidity)|Вызывается в рамках, чтобы определить, является ли список пользовательских инструментов действительным.|
|[CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Вызывается инфраструктурой при изменении свойств пользовательского инструмента.|
|[CMFCToolBars ИнутонеДиалог::OnAssignKey](#onassignkey)|Определяет, может ли указанный ярлык клавиатуры быть назначен действию.|
|[CMFCToolBars CustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Определяет, можно ли изменить инструмент, определяемый пользователем.|
|[CMFCToolBars ИнтинтомДиолог::OnInitToolsPage](#oninittoolspage)|Вызывается по системе, когда пользователь выбирает вкладку **Инструменты** запрашивается.|

## <a name="remarks"></a>Remarks

Чтобы отобразить **настраиваемый** диалоговый `CMFCToolBarsCustomizeDialog` ящик, создайте объект и позвоните в [CMFCToolBarsCustomizeDialog::Create](#create) method.

В то время как **настраиваемый** диалоговый ящик активен, приложение работает в специальном режиме, который ограничивает пользователя задачами настройки.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCToolBarsCustomizeDialog` . На примере показано, как заменить кнопку панели инструментов в поле списка команд на странице **Команд,** включить создание новых панелей инструментов с помощью окна **настраиваемых** диалогов и отобразить диалоговую коробку **настройки.** Этот фрагмент кода является частью [образца IE Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxToolBarsCustomizeDialog.h

## <a name="cmfctoolbarscustomizedialogaddbutton"></a><a name="addbutton"></a>CMFCToolBars ИнутонажДиолог::Добавить кнопку

Вставляет кнопку панели инструментов в список команд на странице **Команд.**

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
(в) Определяет идентификатор категории, в который можно вставить кнопку.

*Кнопку*<br/>
(в) Определяет кнопку для вставки.

*iInsertBefore*<br/>
(в) Определяет нулевой индекс кнопки панели инструментов, перед которой вставляется кнопка.

*lpszКатегория*<br/>
(в) Определяет строку категории для вставки кнопки.

### <a name="remarks"></a>Remarks

Метод `AddButton` игнорирует кнопки, которые имеют стандартные идентифицированные команды (например, ID_FILE_MRU_FILE1), команды, которые не разрешены (см. [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) и манекены.

Этот метод создает новый объект `button` того же типа, что и (обычно [класс CMFCToolBarButton)](../../mfc/reference/cmfctoolbarbutton-class.md)с помощью класса времени выполнения кнопки. Затем он вызывает [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) для копирования данных членов кнопки, и вставляет копию в указанную категорию.

Когда новая кнопка вставляется, она получает `OnAddToCustomizePage` уведомление.

Если `iInsertBefore` -1, кнопка придана к списку категорий; в противном случае он вставляется перед элементом с указанным индексом.

### <a name="example"></a>Пример

В следующем примере показано, `AddButton` как `CMFCToolBarsCustomizeDialog` использовать метод класса. Этот фрагмент кода является частью [образца Slider.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

## <a name="cmfctoolbarscustomizedialogaddmenu"></a><a name="addmenu"></a>CMFCToolBars ИнутонажДиолог::AddMenu

Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands,](#addmenucommands) чтобы добавить это меню в список команд на странице **Команд.**

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>Параметры

*uiMenuResId*<br/>
(в) Упоняет идентификатор ресурсов меню для загрузки.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если меню было добавлено успешно; в противном случае FALSE.

### <a name="remarks"></a>Remarks

В вызове `AddMenuCommands`к, *bPopup* является FALSE. В результате этот метод не добавляет в список команд элементы меню, содержащие подменю. Этот метод добавляет элементы меню в подменю в список команд.

## <a name="cmfctoolbarscustomizedialogaddmenucommands"></a><a name="addmenucommands"></a>CMFCToolBarsCustomizeДиалого::AddMenuCommands

Добавляет элементы в список команд на странице **команд,** чтобы представить все элементы в указанном меню.

```
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>Параметры

*pMenu*<br/>
(в) Указатель на объект CMenu для добавления.

*bPopup*<br/>
(в) Определяется, следует ли вставлять элементы всплывающих меню в список команд.

*lpszКатегория*<br/>
(в) Название категории для вставки меню.

*lpszМенюПат*<br/>
(в) Приставка, добавленная к имени, когда команда отображается в списке **всех категорий.**

### <a name="remarks"></a>Remarks

Метод `AddMenuCommands` циклов над всеми пунктами меню *pMenu*. Для каждого элемента меню, который не содержит submenu, этот метод создает объект [класса CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) и вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод, чтобы добавить элемент меню в качестве кнопки панели инструментов в список команд на странице **команд.** В этом процессе не учитываются сепараторы.

Если *bPopup* является правдой, для каждого элемента меню, который содержит submenu этот метод создает объект [класса CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) и вставляет его в список команд, позвонив `AddButton`. В противном случае элементы меню, содержащие подменю, не отображаются в списке команд. В любом случае, когда `AddMenuCommands` встречает пункт меню с submenu он называет себя рекурсивно, передавая указатель на submenu как параметр *pMenu* и придатке этикетки submenu к *lpszMenuPath*.

## <a name="cmfctoolbarscustomizedialogaddtoolbar"></a><a name="addtoolbar"></a>CMFCToolBars ИнутонажДиолог::AddToolBar

Загружает панель инструментов из ресурсов. Затем для каждой команды в меню требуется [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод вставить кнопку в список команд на странице **команд** в указанной категории.

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
(в) Упоньте идентификатор ресурса категории для добавления панели инструментов.

*uiToolbarResId*<br/>
(в) Определяет идентификатор ресурсов панели инструментов, команды которого вставляются в список команд.

*lpszКатегория*<br/>
(в) Условляется название категории, к которой можно добавить панель инструментов.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод успешен; в противном случае FALSE.

### <a name="example"></a>Пример

В следующем примере показано, `AddToolBar` как `CMFCToolBarsCustomizeDialog` использовать метод в классе. Этот фрагмент кода входит в состав [примера Word Pad](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>Remarks

Элемент управления, используемого для представления каждой команды, является объектом [класса CMFCToolBarButton.](../../mfc/reference/cmfctoolbarbutton-class.md) После добавления панели инструментов можно заменить кнопку элементом управления производным типом, позвонив [по телефону CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton).

## <a name="cmfctoolbarscustomizedialogchecktoolsvalidity"></a><a name="checktoolsvalidity"></a>CMFCToolBars ИнутомердиДиалог::CheckToolsValidity

Проверяет достоверность списка пользовательских инструментов.

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>Параметры

*lstTools*<br/>
(в) Список пользовательских инструментов для проверки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если список инструментов, определяемых пользователем, действителен; в противном случае FALSE. Реализация по умолчанию всегда возвращает TRUE.

### <a name="remarks"></a>Remarks

Платформа вызывает этот метод для проверки достоверности объектов, представляющих пользовательские инструменты, возвращенные [CMFCToolBarsCustomizeDialog::CheckToolsValidity.](#checktoolsvalidity)

Переопределить `CheckToolsValidity` метод в классе, `CMFCToolBarsCustomizeDialog` полученном из, если вы хотите проверить инструменты пользователя, прежде чем пользователь закроет диалоговую будку. Если этот метод возвращает FALSE, когда пользователь нажимает либо кнопку **"Закрыть"** в правом верхнем углу диалогового окна, либо кнопку с пометкой **"Закрыть"** в нижнем правом углу диалогового окна, в диалоговом поле отображается вкладка **"Инструменты"** вместо закрытия. Если этот метод возвращает FALSE, когда пользователь нажимает на вкладку, чтобы перейти от вкладки **Инструменты,** навигация не происходит. Необходимо отобразить соответствующее окно сообщений, чтобы сообщить пользователю о проблеме, которая привела к сбою проверки.

## <a name="cmfctoolbarscustomizedialogcmfctoolbarscustomizedialog"></a><a name="cmfctoolbarscustomizedialog"></a>CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog

Формирует объект `CMFCToolBarsCustomizeDialog`.

```
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bAutoSetFromMenus = FALSE,
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```

### <a name="parameters"></a>Параметры

*pWndParentFrame*<br/>
(в) Указатель на родительский кадр. Этот параметр не должен быть NULL.

*bAutoSetFromMenus*<br/>
(в) Значение Boolean, которое определяет, следует ли добавлять команды меню из всех меню в список команд на странице **Команд.** Если этот параметр соответствует действительности, добавляются команды меню. В противном случае команды меню не добавляются.

*uiFlags*<br/>
(в) Комбинация флагов, влияющих на поведение диалогового окна. Этот параметр может быть одним или более из следующих значений:

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*plistCustomPages*<br/>
(в) Указатель на список `CRuntimeClass` объектов, которые указывают дополнительные пользовательские страницы.

### <a name="remarks"></a>Remarks

Параметр *plistCustomPages* относится `CRuntimeClass` к списку объектов, которые указывают дополнительные пользовательские страницы. Конструктор добавляет больше страниц в диалоговый ящик с помощью метода [CRuntimeClass::CreateObject.](../../mfc/reference/cruntimeclass-structure.md#createobject) Например, пример CustomPages можно найти пример, который добавляет больше страниц в поле **настраиваемых** диалогов.

Для получения дополнительной информации о значениях, которые вы можете пройти в *параметре uiFlags,* см. [CMFCToolBarsCustomizeDialog::GetFlags](#getflags).

### <a name="example"></a>Пример

В следующем примере показано, как `CMFCToolBarsCustomizeDialog` построить объект класса. Этот фрагмент кода является частью [образца пользовательских страниц.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

## <a name="cmfctoolbarscustomizedialogcreate"></a><a name="create"></a>CMFCToolBars ИнутодионтироватьДиалого::Создание

Отображает поле **диалогового настройки.**

```
virtual BOOL Create();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если лист свойств настройки создан успешно; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Вызов `Create` метода только после полной инициализации класса.

## <a name="cmfctoolbarscustomizedialogenableuserdefinedtoolbars"></a><a name="enableuserdefinedtoolbars"></a>CMFCToolBarsИнтодиалДиолог::EnableUserDefinedToolbars

Позволяет или отстращает создание новых панелей инструментов с помощью **настраиваемой** диалоговой коробки.

```
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для включения пользовательских панелей инструментов; FALSE для отключить панели инструментов.

### <a name="remarks"></a>Remarks

Если *bEnable* является правдой, **новые**кнопки **«Переименование** и **удаление»** отображаются на странице **Toolbars.**

По умолчанию, или если *bEnable* false, эти кнопки не отображаются, и пользователь не может определить новые панели инструментов.

## <a name="cmfctoolbarscustomizedialogfillallcommandslist"></a><a name="fillallcommandslist"></a>CMFCToolBarsИнтоутеДиолог::FillAllCommandsList

Заполняет предоставленный `CListBox` объект командами в категории **Все команды.**

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>Параметры

*wndListOfCommands*<br/>
(ваут) Ссылка на `CListBox` объект для заселений.

### <a name="remarks"></a>Remarks

Категория **«Все команды»** содержит команды всех категорий. [Метод CMFCToolBarsCustomizeDialog::AddButton](#addbutton) добавляет команду, связанную с предоставленной **кнопкой,** в категорию All Commands для вас.

Этот метод очищает содержимое `CListBox` предоставленного объекта, прежде чем заселить его командами в категории **Все команды.**

Класс `CMFCMousePropertyPage` использует этот метод для заполнения окна списка событий с двойным щелчком мыши.

## <a name="cmfctoolbarscustomizedialogfillcategoriescombobox"></a><a name="fillcategoriescombobox"></a>CMFCToolBarsИнтоутеДиолог::FillCategoriesComboBox

Заполняет предоставленный `CComboBox` объект с именем каждой категории команд в поле **настраиваемых** диалогов.

```
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Параметры

*wndКатегория*<br/>
(ваут) Ссылка на `CComboBox` объект для заселений.

*bAddEmpty*<br/>
(в) Значение Boolean, которое определяет, следует ли добавлять категории в комбо-поле, в которых нет команд. Если этот параметр является правдой, пустые категории добавляются в комбо-бокс. В противном случае пустые категории не добавляются.

### <a name="remarks"></a>Remarks

Этот метод похож на метод [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) метод, `CComboBox` за исключением того, что этот метод работает с объектом.

Этот метод не очищает содержимое `CComboBox` объекта перед его заселением. Это гарантирует, что категория **All Commands** является окончательным пунктом в комбо-коробке.

Вы можете добавить новые категории команд с помощью метода [CMFCToolBarsCustomizeDialog::AddButton.](#addbutton) Вы можете изменить название существующей категории с помощью метода [CMFCToolBarsCustomizeDialog::RenameCategory.](#renamecategory)

`CMFCToolBarsKeyboardPropertyPage` Классы `CMFCKeyMapDialog` используют этот метод для классификации отображений клавиатуры.

## <a name="cmfctoolbarscustomizedialogfillcategorieslistbox"></a><a name="fillcategorieslistbox"></a>CMFCToolBarsИнтоутеДиолог::FillCategoriesListBox

Заполняет предоставленный `CListBox` объект с именем каждой категории команд в поле **настраиваемых** диалогов.

```
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Параметры

*wndКатегория*<br/>
(ваут) Ссылка на `CListBox` объект для заселений.

*bAddEmpty*<br/>
(в) Значение Boolean, которое определяет, следует ли добавлять категории в поле списка, в которых нет команд. Если этот параметр является правдой, пустые категории добавляются в поле списка. В противном случае пустые категории не добавляются.

### <a name="remarks"></a>Remarks

Этот метод похож на метод [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) метод, `CListBox` за исключением того, что этот метод работает с объектом.

Этот метод не очищает содержимое `CListBox` объекта перед его заселением. Это гарантирует, что категория **«Все команды»** является окончательным пунктом в поле списка.

Вы можете добавить новые категории команд с помощью метода [CMFCToolBarsCustomizeDialog::AddButton.](#addbutton) Вы можете изменить название существующей категории с помощью метода [CMFCToolBarsCustomizeDialog::RenameCategory.](#renamecategory)

Класс `CMFCToolBarsCommandsPropertyPage` использует этот метод для отображания списка команд, связанных с каждой категорией команд.

## <a name="cmfctoolbarscustomizedialoggetcommandname"></a><a name="getcommandname"></a>CMFCToolBarsИнтоутеДиолог::GetCommandName

Извлекает имя, связанное с данным идентификатором команды.

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды для извлечения.

### <a name="return-value"></a>Возвращаемое значение

Имя, связанное с данным идентификатором команды, или NULL, если команда не существует.

## <a name="cmfctoolbarscustomizedialoggetcountincategory"></a><a name="getcountincategory"></a>CMFCToolBarsИнтоутеДиолог::GetCountInCategory

Извлекает количество элементов в предоставленном списке, которые имеют заданную текстовую метку.

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>Параметры

*lpszItemName*<br/>
(в) Текстовая метка, чтобы соответствовать.

*lstCommands*<br/>
(в) Ссылка на список, содержащий `CMFCToolBarButton` объекты.

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в предоставленном списке, текстовая этикетка которых *равна lpszItemName*.

### <a name="remarks"></a>Remarks

Каждый элемент в предоставленном списке объектов должен быть типа. `CMFCToolBarButton` Этот метод сравнивает *lpszItemName* с [членом данных CMFCToolBarButton:::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) данных.

## <a name="cmfctoolbarscustomizedialoggetflags"></a><a name="getflags"></a>CMFCToolBars ИнутонажДиолог::GetFlags

Извлекает набор флагов, влияющих на поведение диалогового окна.

```
UINT GetFlags() const;
```

### <a name="return-value"></a>Возвращаемое значение

Набор флагов, влияющих на поведение диалогового окна.

### <a name="remarks"></a>Remarks

Этот метод получает значение параметра *uiFlags,* который передается конструктору. Значение возврата может быть одним или более из следующих значений:

|||
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|Позволяет пользователю указать внешний вид тени меню.  |
|AFX_CUSTOMIZE_TEXT_LABELS|Позволяет пользователю указать, отображаются ли текстовые метки под изображениями кнопки панели инструментов.  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|Позволяет пользователю указать стиль анимации меню.  |
|AFX_CUSTOMIZE_NOHELP|Удаляет кнопку справки из окна диалога настройки.  |
|AFX_CUSTOMIZE_CONTEXT_HELP|Обеспечивает WS_EX_CONTEXTHELP визуальный стиль.  |
|AFX_CUSTOMIZE_NOTOOLS|Удаляет страницу **«Инструменты»** из окна диалога настройки. Этот флаг действителен, если `CUserToolsManager` приложение использует класс.  |
|AFX_CUSTOMIZE_MENUAMPERS|Позволяет подписи к кнопке содержать **&** амперсанд () характер.  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|Удаляет опцию **«Большие значки»** из окна диалога настройки.  |

Для получения дополнительной информации о WS_EX_CONTEXTHELP визуальном стиле, см [Расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="cmfctoolbarscustomizedialogonafterchangetool"></a><a name="onafterchangetool"></a>CMFCToolBarsCustomizeDialog::OnAfterChangeTool

Реагирует на изменение пользовательского инструмента сразу же после его возникновения.

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Параметры

*pSelTool*<br/>
(в, вне) Указатель на измененный объект пользователя.

### <a name="remarks"></a>Remarks

Этот метод вызывается инфраструктурой, когда пользователь изменяет свойства пользовательского инструмента. Реализация по умолчанию не выполняет никаких действий. Переопределить этот метод в классе, полученном из `CMFCToolBarsCustomizeDialog` выполнения обработки после изменения в пользовательском инструменте.

## <a name="cmfctoolbarscustomizedialogonassignkey"></a><a name="onassignkey"></a>CMFCToolBars ИнутонеДиалог::OnAssignKey

Проверяет ярлыки клавиатуры, как пользователь определяет их.

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>Параметры

*pAccel*<br/>
(в, вне) Указатель на предлагаемую клавиатуру assigment, который выражается как [accEL](/windows/win32/api/winuser/ns-winuser-accel) структурой.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ключ может быть назначен, или FALSE, если ключ не может быть назначен. Реализация по умолчанию всегда возвращает TRUE.

### <a name="remarks"></a>Remarks

Переопределить этот метод в производном классе для выполнения дополнительной обработки, когда пользователь назначает новый ярлык клавиатуры, или для проверки сочетаний клавиш, как пользователь определяет их. Чтобы предотвратить присвоение ярлыка, верните FALSE. Вы также должны отобразить окно сообщений или иным образом сообщить пользователю о причине, почему ярлык клавиатуры был отклонен.

## <a name="cmfctoolbarscustomizedialogonbeforechangetool"></a><a name="onbeforechangetool"></a>CMFCToolBars CustomizeDialog::OnBeforeChangeTool

Выполняет пользовательскую обработку при изменении пользовательского инструмента, когда пользователь собирается применить изменение.

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Параметры

*pSelTool*<br/>
(в, вне) Указатель на объект пользовательского инструмента, который вот-вот будет заменен.

### <a name="remarks"></a>Remarks

Этот метод вызывается инфраструктурой, когда свойства пользовательского инструмента вот-вот изменятся. Реализация по умолчанию не выполняет никаких действий. Переопределить `OnBeforeChangeTool` метод в классе, `CMFCToolBarsCustomizeDialog` полученном из, если вы хотите выполнить обработку до изменения в пользовательском инструменте, например, высвобождение ресурсов, *используемых pSelTool.*

## <a name="cmfctoolbarscustomizedialogonedittoolbarmenuimage"></a><a name="onedittoolbarmenuimage"></a>CMFCToolBarsCustomizeДиалог::OnEditToolbarMenuImage

Запускает редактор изображений, чтобы пользователь мог настроить кнопку панели инструментов или значок элемента меню.

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на родительское окно.

*Растрового изображения*<br/>
(в) Ссылка на объект bitmap, который будет отредактирован.

*nBitsPerPixel*<br/>
(в) Разрешение цвета Bitmap, в битах на пиксель.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если происходит изменение; в противном случае FALSE. Реализация по умолчанию отображает диалоговое окно и возвращает TRUE, если пользователь нажимает **OK,** или FALSE, если пользователь нажимает **Отмена** или **кнопка "Закрыть".**

### <a name="remarks"></a>Remarks

Этот метод вызывается фректовой при запуске редактором изображений. Реализация по умолчанию отображает диалоговый ящик [cmFCImageEditorEditorDialog.](../../mfc/reference/cmfcimageeditordialog-class.md) Переопределение `OnEditToolbarMenuImage` в производном классе для использования пользовательского редактора изображений.

## <a name="cmfctoolbarscustomizedialogoninitdialog"></a><a name="oninitdialog"></a>CMFCToolBarsИнтодиалДиолог::OnInitДиалог

Переопределения для увеличения инициализации листа свойств.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) метод.

### <a name="remarks"></a>Remarks

Этот метод расширяет реализацию базового класса, [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog), отображая кнопку **«Закрыть»,** убедившись, что диалоговый ящик соответствует текущему размеру экрана, и перемещая кнопку **справки** в левый нижний угол диалогового окна.

## <a name="cmfctoolbarscustomizedialogoninittoolspage"></a><a name="oninittoolspage"></a>CMFCToolBars ИнтинтомДиолог::OnInitToolsPage

Обрабатывает уведомление из платформы о том, что страница **«Инструменты»** вот-вот будет инициализирована.

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>Remarks

Реализация по умолчанию не выполняет никаких действий. Переопределить этот метод в производном классе для обработки этого уведомления.

## <a name="cmfctoolbarscustomizedialogpostncdestroy"></a><a name="postncdestroy"></a>CMFCToolBars CustomizeDialog::PostNcDestroy

Вызывается рамками после того, как окно было уничтожено.

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>Remarks

Этот метод расширяет реализацию базового класса, `CPropertySheet::PostNcDestroy`восстанавливая приложение до предыдущего режима.

[CMFCToolBarsCustomizeDialog::Создание](#create) метода помещает приложение в специальный режим, который ограничивает пользователя задач настройки.

## <a name="cmfctoolbarscustomizedialogremovebutton"></a><a name="removebutton"></a>CMFCToolBarsИнтодиалДиолог::Удалить кнопку

Удаляет кнопку с указанным идентификатором команды из указанной категории или из всех категорий.

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
(в) Упогоняет идентификатор категории, из которого можно удалить кнопку.

*uiCmdId*<br/>
(в) Упоняет идентификатор команды кнопки.

*lpszКатегория*<br/>
(в) Упогоняет название категории, из которой можно удалить кнопку.

### <a name="return-value"></a>Возвращаемое значение

Индекс нулевой основе удаленной кнопки или -1, если указанный идентификатор команды не был найден в указанной категории. Если *uiCategoryId* -1, значение возврата 0.

### <a name="remarks"></a>Remarks

Чтобы удалить кнопку из всех категорий, позвоните в первую перегрузку этого метода и *установите uiCategoryId* до -1.

## <a name="cmfctoolbarscustomizedialogrenamecategory"></a><a name="renamecategory"></a>CMFCToolBarsИнтоутеДиолог::ПереименованиеКатегория

Переименуем категорию в поле списка категорий на странице **Команд.**

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>Параметры

*lpszКатегорияСтарый*<br/>
(в) Имя категории для изменения.

*lpszКатегорияНью*<br/>
(в) Новое название категории.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Название категории должно быть уникальным.

## <a name="cmfctoolbarscustomizedialogreplacebutton"></a><a name="replacebutton"></a>CMFCToolBars ИнутоньюсДиолог::Заменить кнопку

Заменяет кнопку панели инструментов в поле списка команд на странице **Команд.**

```
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Определяет команду кнопки, которая будет заменена.

*Кнопку*<br/>
(в) **Ссылка** на объект кнопки панели инструментов, который заменяет старую кнопку.

### <a name="remarks"></a>Remarks

Когда [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), или [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) добавляет команду на страницу **команд,** что команда находится в виде объекта [класса CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) (или [CMFCToolBarMenuButton объект класса](../../mfc/reference/cmfctoolbarmenubutton-class.md) для пункта меню, который содержит пункт submenu, `AddMenuCommands`добавленный). Платформа также вызывает эти три метода для автоматического добавления команд. Если вместо этого требуется, чтобы команда была представлена производным типом, позвоните `ReplaceButton` и передайте кнопку производного типа.

### <a name="example"></a>Пример

В следующем примере показано, `ReplaceButton` как `CMFCToolBarsCustomizeDialog` использовать метод в классе. Этот фрагмент кода является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

## <a name="cmfctoolbarscustomizedialogsetusercategory"></a><a name="setusercategory"></a>CMFCToolBarsИнтодиалДиолог::SetUserКатегория

Определяется, какая категория в списке категорий на странице **Команд** является категорией пользователей. Вы должны позвонить по этой функции, прежде чем позвонить [CMFCToolBarsCustomizeDialog::Создать](#create).

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>Параметры

*lpszКатегория*<br/>
(в) Название категории.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод успешен; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Настройка категории пользователей в настоящее время не используется в фреймворке.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CPropertySheet](../../mfc/reference/cpropertysheet-class.md)
