---
title: "Класс CMFCToolBarsCustomizeDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 978303c9edaec2d9776d6e1c81b530df791ca5ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctoolbarscustomizedialog-class"></a>Класс CMFCToolBarsCustomizeDialog
Диалоговое окно без режима вкладки ( [CPropertySheet-класс](../../mfc/reference/cpropertysheet-class.md)), позволяющий пользователю настраивать панели инструментов, меню, сочетания клавиш, определенные пользователем инструменты и визуальный стиль в приложении. Обычно пользователь осуществляет доступ к этому диалоговому окну, выбирая **Настроить** в меню **Сервис** .  
  
 **Настройка** диалоговое окно содержит шесть вкладок: **команды**, **панели инструментов**, **средства**, **клавиатуры**,  **Меню**, и **параметры**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Создает объект `CMFCToolBarsCustomizeDialog`.|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|Вставляет кнопку панели инструментов в список команд на **команды** страницы|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) Чтобы добавить соответствующее меню списка команд на **команды** страницы.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) Чтобы добавить соответствующее меню списка команд на **команды** страницы.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|Загружает панель инструментов из ресурсов. Затем для каждой команды в меню не вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) для вставки кнопки в список команд на **команды** страницы в указанной категории.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::Create](#create)|Отображает **настройки** диалоговое окно.|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|Зарезервировано для будущего использования.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Включает или отключает создание новых панелей инструментов с помощью **Настройка** диалоговое окно.|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Заполняет предоставленный `CListBox` объектов с командами в **все команды** категории.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Заполняет предоставленный `CComboBox` объект с именем каждой категории команды в **Настройка** диалоговое окно.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Заполняет предоставленный `CListBox` объект с именем каждой категории команды в **Настройка** диалоговое окно.|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|Получает имя, связанный с данной команды.|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Возвращает число элементов в указанный список с меткой заданный текст.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|Получает набор флагов, влияющих на поведение диалогового окна.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Запускает редактор изображений, чтобы пользователь может изменять значка элемента кнопки или меню на панели инструментов.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|Переопределяет для ускорения инициализации листа свойств. (Переопределяет [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|Вызывается структурой после уничтожения окна. (Переопределяет `CPropertySheet::PostNcDestroy`.)|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Удаление кнопки с заданным Идентификатором команды из указанной категории, или из всех категорий.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|Переименовывает категорию в списке категорий на **команды** вкладки.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|Заменяет кнопки в список команд на **команды** вкладку новым объектом кнопки панели инструментов.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|Добавление категории в список категорий, которые будут отображаться на **команды** вкладки.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|Вызывается платформой для определения, является ли допустимым список пользовательских средств.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Вызывается платформой при изменении свойств определяемый пользователем инструмент.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Определяет, является ли указанный сочетания клавиш можно назначить действие.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Определяет, можно ли изменить определяемый пользователем инструмент.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Вызывается платформой, когда пользователь выбирает **средства** запрашивается вкладки.|  
  
## <a name="remarks"></a>Примечания  
 Для отображения **Настройка** диалоговом окне создайте `CMFCToolBarsCustomizeDialog` и вызовите [CMFCToolBarsCustomizeDialog::Create](#create) метод.  
  
 Хотя **Настройка** диалоговом окне, что приложение работает в специальный режим, который ограничивает пользователю задачи по настройке.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCToolBarsCustomizeDialog` класса. В примере показано замену кнопки панели инструментов в окне списка команд на **команды** включите создание новых панелей инструментов с помощью **Настройка** диалоговое окно параметров отображения и  **Настройка** диалоговое окно. Этот фрагмент кода является частью [IE демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 `CMFCToolBarsCustomizeDialog`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxToolBarsCustomizeDialog.h  
  
##  <a name="addbutton"></a>CMFCToolBarsCustomizeDialog::AddButton  
 Вставляет кнопку панели инструментов в список команд на **команды** страницы.  
  
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
 [in] `uiCategoryId`  
 Указывает идентификатор категории, в который необходимо вставить кнопку.  
  
 [in] `button`  
 Задает кнопки для вставки.  
  
 [in] `iInsertBefore`  
 Задает отсчитываемый от нуля индекс кнопки панели инструментов, прежде чем кнопка будет вставлена.  
  
 [in] `lpszCategory`  
 Указывает строку категории для вставки кнопки.  
  
### <a name="remarks"></a>Примечания  
 `AddButton` Метод игнорирует кнопок, которые имеют стандартные идентификаторы команд (например, ID_FILE_MRU_FILE1), команды, не допускаются (см. [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) и пустой кнопок.  
  
 Этот метод создает новый объект того же типа, что `button` (обычно [CMFCToolBarButton класса](../../mfc/reference/cmfctoolbarbutton-class.md)) с помощью кнопки класса среды выполнения. Затем он вызывает [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) для копирования кнопки, элементы данных и вставляет копии в указанной категории.  
  
 При вставке новой кнопки, он получает `OnAddToCustomizePage` уведомления.  
  
 Если `iInsertBefore` равно -1, кнопки добавляется в список категорий; в противном случае он автоматически вставляется перед элементом с заданным индексом.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddButton` метод `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [ползунок образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]  
  
##  <a name="addmenu"></a>CMFCToolBarsCustomizeDialog::AddMenu  
 Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) Чтобы добавить соответствующее меню списка команд на **команды** страницы.  
  
```  
BOOL AddMenu(UINT uiMenuResId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiMenuResId`  
 Указывает идентификатор ресурса меню загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если меню был успешно добавлен; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В вызове `AddMenuCommands`, `bPopup` — `FALSE`. В результате этот метод не добавляет пункты меню, которые содержат подменю список команд. Этот метод добавляет пункты меню в подменю список команд.  
  
##  <a name="addmenucommands"></a>CMFCToolBarsCustomizeDialog::AddMenuCommands  
 Добавляет элементы в список команд в **команды** страницу, чтобы добавить все элементы в указанное меню.  
  
```  
void AddMenuCommands(
    const CMenu* pMenu,  
    BOOL bPopup,  
    LPCTSTR lpszCategory=NULL,  
    LPCTSTR lpszMenuPath=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenu`  
 Указатель на объект CMenu для добавления.  
  
 [in] `bPopup`  
 Указывает, следует ли вставлять элементы всплывающего меню в список команд.  
  
 [in] `lpszCategory`  
 Имя категории для вставки в меню.  
  
 [in] `lpszMenuPath`  
 Префикс, который добавляется к имени, когда команда отображается в **все категории** списка.  
  
### <a name="remarks"></a>Примечания  
 `AddMenuCommands` Метод циклы по всем элементам меню `pMenu`. Для каждого пункта меню, который не содержит подменю, этот метод создает [класса CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) и вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод, чтобы добавить элемент меню, как панель инструментов кнопки в список команд на **команды** страницы. Разделители учитываются в этом процессе.  
  
 Если `bPopup` — `TRUE`, для каждого пункта меню, который содержит подменю этот метод создает [класса CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) объекта и вставляет его в список команд, вызвав `AddButton`. В противном случае пункты меню, которые содержат подменю не отображаются в списке команд. В любом случае при `AddMenuCommands` обнаруживает пункта меню с подменю вызывает сам себя рекурсивно, передача указателя в подменю как `pMenu` параметр и добавления метки меню, чтобы `lpszMenuPath`.  
  
##  <a name="addtoolbar"></a>CMFCToolBarsCustomizeDialog::AddToolBar  
 Загружает панель инструментов из ресурсов. Затем для каждой команды в меню не вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) для вставки кнопки в список команд на **команды** страницы в указанной категории.  
  
```  
BOOL AddToolBar(
    UINT uiCategoryId,  
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,  
    UINT uiToolbarResId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCategoryId`  
 Указывает идентификатор ресурса категории, чтобы добавить панель инструментов для.  
  
 [in] `uiToolbarResId`  
 Указывает идентификатор ресурса, команды которого вставляются в список команд панели инструментов.  
  
 [in] `lpszCategory`  
 Задает имя категории, к которому необходимо добавить панель инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddToolBar` метод `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода входит в состав [примера Word Pad](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Элемент управления, используемый для представления каждой команды [CMFCToolBarButton класс](../../mfc/reference/cmfctoolbarbutton-class.md) объекта. После добавления панели инструментов, можно заменить кнопки управления производного типа путем вызова [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton).  
  
##  <a name="checktoolsvalidity"></a>CMFCToolBarsCustomizeDialog::CheckToolsValidity  
 Проверяет правильность списка пользовательских средств.  
  
```  
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lstTools`  
 Список пользовательских средств для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если список пользовательских средств является допустимым; в противном случае `FALSE`. Реализация по умолчанию всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для проверки допустимости объектов, представляющих определенные пользователем инструменты, возвращенных [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity).  
  
 Переопределить `CheckToolsValidity` метод в классе, производным от `CMFCToolBarsCustomizeDialog` требуется для проверки пользовательских средств, прежде чем пользователь закрывает диалоговое окно. Если этот метод возвращает `FALSE` при щелчке по любой **закрыть** кнопки в правом верхнем углу диалогового окна, или кнопку с многоточием **закрыть** в правом нижнем углу диалогового окна Отображает диалоговое окно **средства** вкладку вместо закрытия. Если этот метод возвращает `FALSE` при нажатии tab для перехода от **средства** вкладки навигации не возникает. Отображать окно сообщения для уведомления пользователя неполадку, вызвавшую неудачную проверку.  
  
##  <a name="cmfctoolbarscustomizedialog"></a>CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog  
 Создает объект `CMFCToolBarsCustomizeDialog`.  
  
```  
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bAutoSetFromMenus = FALSE,  
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),  
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParentFrame`  
 Указатель родительского фрейма. Этот параметр не должен иметь значение `NULL`.  
  
 [in] `bAutoSetFromMenus`  
 Логическое значение, указывающее, следует ли добавить команды меню из всех меню списка команд на **команды** страницы. Если этот параметр равен `TRUE`, добавлены команды меню. В противном случае команды меню не добавляются.  
  
 [in] `uiFlags`  
 Сочетание флагов, влияющих на поведение диалогового окна. Этот параметр может иметь одно или несколько из следующих значений:  
  
- `AFX_CUSTOMIZE_MENU_SHADOWS`  
  
- `AFX_CUSTOMIZE_TEXT_LABELS`  
  
- `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
  
- `AFX_CUSTOMIZE_NOHELP`  
  
- `AFX_CUSTOMIZE_CONTEXT_HELP`  
  
- `AFX_CUSTOMIZE_NOTOOLS`  
  
- `AFX_CUSTOMIZE_MENUAMPERS`  
  
- `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
  
 [in] `plistCustomPages`  
 Указатель на список `CRuntimeClass` объекты, которые указывают дополнительные настраиваемые страницы.  
  
### <a name="remarks"></a>Примечания  
 `plistCustomPages` Параметр ссылается на список `CRuntimeClass` объекты, которые указывают дополнительные настраиваемые страницы. Конструктор добавляет дополнительные страницы в диалоговое окно с помощью [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) метод. См. в образце CustomPages пример добавляет дополнительные страницы для **Настройка** диалоговое окно.  
  
 Дополнительные сведения о значениях, которые можно передать в `uiFlags` параметр, в разделе [CMFCToolBarsCustomizeDialog::GetFlags](#getflags).  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [образец пользовательские страницы](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]  
  
##  <a name="create"></a>CMFCToolBarsCustomizeDialog::Create  
 Отображает **настройки** диалоговое окно.  
  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если окно свойств настройки создан успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Вызовите `Create` метод только после полной инициализации класса.  
  
##  <a name="enableuserdefinedtoolbars"></a>CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars  
 Включает или отключает создание новых панелей инструментов с помощью **Настройка** диалоговое окно.  
  
```  
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить пользовательские панели инструментов; `FALSE` отключение панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Если `bEnable` — `TRUE`, **New**, **переименование** и **удаление** кнопок на **панели инструментов** страницы.  
  
 По умолчанию или если `bEnable` — `FALSE`, эти кнопки не отображаются, и пользователь не может определять новые панели инструментов.  
  
##  <a name="fillallcommandslist"></a>CMFCToolBarsCustomizeDialog::FillAllCommandsList  
 Заполняет предоставленный `CListBox` объектов с командами в **все команды** категории.  
  
```  
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `wndListOfCommands`  
 Ссылку на `CListBox` объекта для заполнения.  
  
### <a name="remarks"></a>Примечания  
 **Все команды** категории команды из всех категорий. [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод добавляет команду, которая связана с кнопкой, предоставленный для **все команды** категории для вас.  
  
 Этот метод очищает содержимое предоставленного `CListBox` объекта перед его заполнением с командами в **все команды** категории.  
  
 `CMFCMousePropertyPage` Класс использует этот метод для заполнения списка дважды щелкните событие.  
  
##  <a name="fillcategoriescombobox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesComboBox  
 Заполняет предоставленный `CComboBox` объект с именем каждой категории команды в **Настройка** диалоговое окно.  
  
```  
void FillCategoriesComboBox(
    CComboBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `wndCategory`  
 Ссылку на `CComboBox` объекта для заполнения.  
  
 [in] `bAddEmpty`  
 Логическое значение, указывающее, следует ли добавить категории в поле со списком, у которых нет команды. Если этот параметр равен `TRUE`, пустые категории добавляются в поле со списком. В противном случае — пустой категории не добавляются.  
  
### <a name="remarks"></a>Примечания  
 Этот метод аналогичен [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) метод за исключением того, что этот метод работает с `CComboBox` объекта.  
  
 Этот метод не очищает содержимое `CComboBox` объекта перед его заполнением. Гарантирует, что **все команды** категории — последний элемент в поле со списком.  
  
 Можно добавить новые категории команды с помощью [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод. Можно изменить имя существующей категории с помощью [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) метод.  
  
 `CMFCToolBarsKeyboardPropertyPage` И `CMFCKeyMapDialog` классы используют этот метод для категоризации клавиш клавиатуры.  
  
##  <a name="fillcategorieslistbox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesListBox  
 Заполняет предоставленный `CListBox` объект с именем каждой категории команды в **Настройка** диалоговое окно.  
  
```  
void FillCategoriesListBox(
    CListBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `wndCategory`  
 Ссылку на `CListBox` объекта для заполнения.  
  
 [in] `bAddEmpty`  
 Логическое значение, указывающее, следует ли добавить категории в списке, у которых нет команды. Если этот параметр равен `TRUE`, пустые категории добавляются в список. В противном случае — пустой категории не добавляются.  
  
### <a name="remarks"></a>Примечания  
 Этот метод аналогичен [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) метод за исключением того, что этот метод работает с `CListBox` объекта.  
  
 Этот метод не очищает содержимое `CListBox` объекта перед его заполнением. Гарантирует, что **все команды** категория — последний элемент в поле со списком.  
  
 Можно добавить новые категории команды с помощью [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод. Можно изменить имя существующей категории с помощью [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) метод.  
  
 `CMFCToolBarsCommandsPropertyPage` Класс использует этот метод для отображения списка команд, связанный с каждой категорией команды.  
  
##  <a name="getcommandname"></a>CMFCToolBarsCustomizeDialog::GetCommandName  
 Получает имя, связанный с данной команды.  
  
```  
LPCTSTR GetCommandName(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды для получения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя, связанный с заданным Идентификатором команды, или `NULL` Если команда не существует.  
  
##  <a name="getcountincategory"></a>CMFCToolBarsCustomizeDialog::GetCountInCategory  
 Возвращает число элементов в указанный список с меткой заданный текст.  
  
```  
int GetCountInCategory(
    LPCTSTR lpszItemName,  
    const CObList& lstCommands) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszItemName`  
 Текстовая метка для сопоставления.  
  
 [in] `lstCommands`  
 Ссылку на список, содержащий `CMFCToolBarButton` объектов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов в предоставленном списке которого равно текст метки `lpszItemName`.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент в списке предоставленный объект должен иметь тип `CMFCToolBarButton`. Этот метод сравнивает `lpszItemName` с [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) члена данных.  
  
##  <a name="getflags"></a>CMFCToolBarsCustomizeDialog::GetFlags  
 Получает набор флагов, влияющих на поведение диалогового окна.  
  
```  
UINT GetFlags() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Набор флагов, влияющих на поведение диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает значение `uiFlags` параметр, передаваемый в конструктор. Возвращаемое значение может быть один или несколько из следующих значений:  
  
 `AFX_CUSTOMIZE_MENU_SHADOWS`  
 Позволяет пользователю задавать тени внешний вид меню.  
  
 `AFX_CUSTOMIZE_TEXT_LABELS`  
 Позволяет пользователю указать, отображаются ли метки текст под изображениями кнопок панели инструментов.  
  
 `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
 Позволяет пользователю задать стиль анимации меню.  
  
 `AFX_CUSTOMIZE_NOHELP`  
 Удаляет кнопку "Справка" в диалоговом окне настройки.  
  
 `AFX_CUSTOMIZE_CONTEXT_HELP`  
 Позволяет `WS_EX_CONTEXTHELP` визуального стиля.  
  
 `AFX_CUSTOMIZE_NOTOOLS`  
 Удаляет **средства** страницы из диалогового окна настройки. Этот флаг является допустимым, если приложение использует `CUserToolsManager` класса.  
  
 `AFX_CUSTOMIZE_MENUAMPERS`  
 Позволяет подписи кнопки содержит символ амперсанда (  **&** ) символов.  
  
 `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
 Удаляет **крупные значки** параметр из диалогового окна настройки.  
  
 Дополнительные сведения о `WS_EX_CONTEXTHELP` визуального стиля. в разделе [расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).  
  
##  <a name="onafterchangetool"></a>CMFCToolBarsCustomizeDialog::OnAfterChangeTool  
 Реагирует на изменения в пользовательский инструмент сразу же после возникновения.  
  
```  
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pSelTool`  
 Указатель на объект средства пользователя, который был изменен.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда пользователь изменяет свойства определяемый пользователем инструмент. Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в класс, производный от `CMFCToolBarsCustomizeDialog` для выполнения обработки после изменения в пользовательский инструмент.  
  
##  <a name="onassignkey"></a>CMFCToolBarsCustomizeDialog::OnAssignKey  
 Пользователь определяет их проверяется сочетания клавиш.  
  
```  
virtual BOOL OnAssignKey(ACCEL* pAccel);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pAccel`  
 Указатель на назначение предложенных сочетания, которое выражается как [УСКОРЕНИЕ](http://msdn.microsoft.com/library/windows/desktop/ms646340) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если ключ может быть назначена или `FALSE` Если ключ не может быть назначен. Реализация по умолчанию всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе для выполнения дополнительной обработки при назначении новое сочетание клавиш или для проверки имени пользователя, сочетания клавиш они определены. Чтобы предотвратить назначение ярлык, нужно вернуть `FALSE`. Следует также окно сообщения, или в противном случае информировать пользователей причины, почему был отклонен сочетания клавиш.  
  
##  <a name="onbeforechangetool"></a>CMFCToolBarsCustomizeDialog::OnBeforeChangeTool  
 Выполняет специальной обработки при изменении пользовательский инструмент, когда пользователь собирается применить изменение.  
  
```  
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pSelTool`  
 Указатель на объект средства пользователя, который должен быть заменен.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда свойства определяемый пользователем инструмент. Реализация по умолчанию не выполняет никаких действий. Переопределить `OnBeforeChangeTool` метод в классе, производным от `CMFCToolBarsCustomizeDialog` Если требуется выполнять обработку, прежде чем произойдет изменение пользовательский инструмент, такие как освобождение ресурсов, `pSelTool` использует.  
  
##  <a name="onedittoolbarmenuimage"></a>CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage  
 Запускает редактор изображений, чтобы пользователь может изменять значка элемента кнопки или меню на панели инструментов.  
  
```  
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,  
    CBitmap& bitmap,  
    int nBitsPerPixel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на родительское окно.  
  
 [in] `bitmap`  
 Ссылка на растровый объект, который нужно изменить.  
  
 [in] `nBitsPerPixel`  
 Битовая карта, разрешения в битах на пиксель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`При фиксации изменений; в противном случае `FALSE`. Реализация по умолчанию отображает диалоговое окно и возвращает `TRUE` при нажатии кнопки **ОК**, или `FALSE` при нажатии кнопки **отменить** или **закрыть** кнопка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда пользователь запускает редактор изображений. Реализация по умолчанию отображает [CMFCImageEditorDialog класса](../../mfc/reference/cmfcimageeditordialog-class.md) диалоговое окно. Переопределить `OnEditToolbarMenuImage` в производном классе с помощью редактора пользовательского образа.  
  
##  <a name="oninitdialog"></a>CMFCToolBarsCustomizeDialog::OnInitDialog  
 Переопределяет для ускорения инициализации листа свойств.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат вызова [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog), отображая **закрыть** кнопки, убедившись, что диалоговое окно соответствует текущий размер экрана, а также путем перемещения **Справки** кнопки в левом нижнем углу диалоговым окном.  
  
##  <a name="oninittoolspage"></a>CMFCToolBarsCustomizeDialog::OnInitToolsPage  
 Обрабатывает уведомление от платформы, **средства** страницы является инициализироваться.  
  
```  
virtual void OnInitToolsPage();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в производном классе для обработки этого уведомления.  
  
##  <a name="postncdestroy"></a>CMFCToolBarsCustomizeDialog::PostNcDestroy  
 Вызывается структурой после уничтожения окна.  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, `CPropertySheet::PostNcDestroy`, восстановив его в прежнем режиме.  
  
 [CMFCToolBarsCustomizeDialog::Create](#create) метод переводит приложение в специальный режим, который ограничивает пользователю задачи по настройке.  
  
##  <a name="removebutton"></a>CMFCToolBarsCustomizeDialog::RemoveButton  
 Удаление кнопки с заданным Идентификатором команды из указанной категории, или из всех категорий.  
  
```  
int RemoveButton(
    UINT uiCategoryId,  
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,  
    UINT uiCmdId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCategoryId`  
 Указывает идентификатор категории, из которого нужно удалить кнопку.  
  
 [in] `uiCmdId`  
 Указывает идентификатор команды кнопки.  
  
 [in] `lpszCategory`  
 Задает имя категории, из которого нужно удалить кнопку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс кнопки удален или -1, если указанный идентификатор команды не был найден в указанной категории. Если `uiCategoryId` равно -1, возвращаемое значение равно 0.  
  
### <a name="remarks"></a>Примечания  
 Чтобы удалить кнопку из всех категорий, вызовите первая перегрузка этого метода и набор `uiCategoryId` значение -1.  
  
##  <a name="renamecategory"></a>CMFCToolBarsCustomizeDialog::RenameCategory  
 Переименовывает категорию в списке категорий на **команды** страницы.  
  
```  
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,  
    LPCTSTR lpszCategoryNew);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszCategoryOld`  
 Чтобы изменить имя категории.  
  
 [in] `lpszCategoryNew`  
 Имя новой категории.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Имя категории должно быть уникальным.  
  
##  <a name="replacebutton"></a>CMFCToolBarsCustomizeDialog::ReplaceButton  
 Заменяет кнопки панели инструментов в окне списка команд на **команды** страницы.  
  
```  
void ReplaceButton(
    UINT uiCmd,  
    const CMFCToolBarButton& button);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Команда кнопку для замены.  
  
 [in] `button`  
 Объект `const` ссылку на объект кнопки панели инструментов, который заменяет старый кнопки.  
  
### <a name="remarks"></a>Примечания  
 Когда [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), или [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) добавляет команды **команды** страницы, что команда находится в форме [класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) объекта (или [CMFCToolBarMenuButton класс](../../mfc/reference/cmfctoolbarmenubutton-class.md) объекта для меню элемент, который содержит добавленные подменю `AddMenuCommands`). Эти три метода, чтобы автоматически добавить команды также вызывается платформой. Команда представляются с помощью производного типа, вместо этого следует вызвать `ReplaceButton` и передайте в кнопке производного типа.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `ReplaceButton` метод `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]  
  
##  <a name="setusercategory"></a>CMFCToolBarsCustomizeDialog::SetUserCategory  
 Указывает категорию в списке категорий на **команды** страница является категорию пользователей. Эту функцию необходимо вызывать перед вызовом метода [CMFCToolBarsCustomizeDialog::Create](#create).  
  
```  
BOOL SetUserCategory(LPCTSTR lpszCategory);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszCategory`  
 Имя категории.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Параметр категории пользователь в настоящее время не используется платформой.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CPropertySheet](../../mfc/reference/cpropertysheet-class.md)
