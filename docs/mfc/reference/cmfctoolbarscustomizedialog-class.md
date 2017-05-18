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
- CMFCToolBarsCustomizeDialog class
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 069498d958dd5d9c3befc2a179c67636ce0ac9ae
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarscustomizedialog-class"></a>Класс CMFCToolBarsCustomizeDialog
Диалоговое окно немодальное вкладки ( [CPropertySheet-класс](../../mfc/reference/cpropertysheet-class.md)), которые позволяют пользователю настраивать панели инструментов, меню, сочетания клавиш, определенные пользователем инструменты и визуальный стиль в приложении. Обычно пользователь осуществляет доступ к этому диалоговому окну, выбирая **Настроить** в меню **Сервис** .  
  
 **Настройка** диалоговое окно содержит шесть вкладок: **команды**, **панели инструментов**, **средства**, **клавиатуры**, **меню**, и **параметры**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Создает объект `CMFCToolBarsCustomizeDialog`.|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|Вставляет кнопку панели инструментов в списке команд на **команды** страницы|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) Чтобы добавить список команд, меню на **команды** страницы.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) Чтобы добавить список команд, меню на **команды** страницы.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|Загружает панель инструментов из ресурсов. Затем для каждой команды в меню вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод, чтобы добавить кнопку в списке команд на **команды** страницы в указанной категории.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::Create](#create)|Отображает **настройки** диалоговое окно.|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|Зарезервировано для будущего использования.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Включает или отключает создание новых панелей инструментов с помощью **Настройка** диалоговое окно.|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Заполняет предоставленный `CListBox` объектов с помощью команд в **все команды** категории.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Заполняет предоставленный `CComboBox` объект с именем каждой категории команд в **Настройка** диалоговое окно.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Заполняет предоставленный `CListBox` объект с именем каждой категории команд в **Настройка** диалоговое окно.|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|Получает имя, связанный с данной команды.|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Получает число элементов в указанный список с меткой заданный текст.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|Получает набор флагов, влияющих на поведение диалогового окна.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Запускает редактор изображений, что пользователь может настроить значка элемента кнопки или меню на панели инструментов.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|Переопределения для дополнения инициализации листа свойств. (Переопределяет [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|Вызывается платформой после окно уже уничтожено. (Переопределяет `CPropertySheet::PostNcDestroy`.)|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Удаление кнопки с заданным Идентификатором команды из указанной категории, или из всех категорий.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|Переименовывает категорию в списке категорий на **команды** вкладки.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|Заменяет кнопки в списке команд на **команды** вкладки с новый объект кнопки панели инструментов.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|Добавление категории в список категорий, которые будут отображаться на **команды** вкладки.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|Вызывается платформой для определения допустимости список пользовательских средств.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Вызывается инфраструктурой при изменении свойств инструмент, определенный пользователем.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Определяет ли указанный сочетания клавиш могут быть назначены действия.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Определяет, можно ли изменить определяемый пользователем инструмент.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Вызывается платформой, когда пользователь выбирает **средства** вкладку запрашивается.|  
  
## <a name="remarks"></a>Примечания  
 Для отображения **Настройка** диалоговом окне создайте `CMFCToolBarsCustomizeDialog` и вызовите [CMFCToolBarsCustomizeDialog::Create](#create) метод.  
  
 Хотя **Настройка** диалоговом окне, что приложение работает в специальный режим, который ограничивает пользователя задач настройки.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCToolBarsCustomizeDialog` класса. Примере показано, как заменить кнопку панели инструментов в окне списка команд на **команды** включите создание новых панелей инструментов с помощью **Настройка** диалоговое окно параметров отображения и **настройки** диалоговое окно. Этот фрагмент кода является частью [IE демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo&#4;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 `CMFCToolBarsCustomizeDialog`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxToolBarsCustomizeDialog.h  
  
##  <a name="addbutton"></a>CMFCToolBarsCustomizeDialog::AddButton  
 Вставляет кнопку панели инструментов в списке команд на **команды** страницы.  
  
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
 Задает отсчитываемый от нуля индекс кнопки панели инструментов, после которого вставляется кнопки.  
  
 [in] `lpszCategory`  
 Указывает строку категории для вставки кнопки.  
  
### <a name="remarks"></a>Примечания  
 `AddButton` Метод игнорирует кнопок, которые имеют стандартные идентификаторы команд (например, ID_FILE_MRU_FILE1), команды, не допускаются (см. [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) и фиктивная кнопок.  
  
 Этот метод создает новый объект того же типа, что `button` (обычно [CMFCToolBarButton класса](../../mfc/reference/cmfctoolbarbutton-class.md)) с помощью кнопки класса среды выполнения. Затем он вызывает [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) на копирование членов данных кнопки и вставляет ее в указанной категории.  
  
 При вставке новой кнопки, он получает `OnAddToCustomizePage` уведомления.  
  
 Если `iInsertBefore` равно -1, кнопки добавляется в список категорий; в противном случае он вставляется перед элементом с заданным индексом.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddButton` метод `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [образце Slider](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Slider&#1;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]  
  
##  <a name="addmenu"></a>CMFCToolBarsCustomizeDialog::AddMenu  
 Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) Чтобы добавить список команд, меню на **команды** страницы.  
  
```  
BOOL AddMenu(UINT uiMenuResId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiMenuResId`  
 Указывает идентификатор ресурса меню загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если меню был успешно добавлен; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 При вызове `AddMenuCommands`, `bPopup` — `FALSE`. В результате этот метод не добавляет элементы меню, содержащие подменю список команд. Этот метод добавляет пункты меню в подменю список команд.  
  
##  <a name="addmenucommands"></a>CMFCToolBarsCustomizeDialog::AddMenuCommands  
 Добавляет элементы в список команд в **команды** страницу для представления всех элементов в указанное меню.  
  
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
 Указывает, следует ли вставлять элементы всплывающего меню к списку команд.  
  
 [in] `lpszCategory`  
 Имя категории для вставки в меню.  
  
 [in] `lpszMenuPath`  
 Префикс, который добавляется к имени, когда команда отображается в **все категории** списка.  
  
### <a name="remarks"></a>Примечания  
 `AddMenuCommands` Метод циклов через все элементы меню `pMenu`. Для каждого пункта меню, который не содержит подменю, этот метод создает [класса CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) и вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод для добавления элемента меню кнопки панели инструментов в список команд на **команды** страницы. Разделители учитываются в этом процессе.  
  
 Если `bPopup` — `TRUE`, для каждого пункта меню, который содержит подменю этот метод создает [класса CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) объекта и вставляет его в список команд, вызвав `AddButton`. В противном случае элементы меню, содержащие подменю не отображаются в списке команд. В любом случае при `AddMenuCommands` встречает элемент меню с подменю он вызывает себя рекурсивно, передать указатель на подменю как `pMenu` параметр и добавления метки в подменю для `lpszMenuPath`.  
  
##  <a name="addtoolbar"></a>CMFCToolBarsCustomizeDialog::AddToolBar  
 Загружает панель инструментов из ресурсов. Затем для каждой команды в меню вызывает [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод, чтобы добавить кнопку в списке команд на **команды** страницы в указанной категории.  
  
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
 Указывает идентификатор ресурса категории для добавления панели инструментов.  
  
 [in] `uiToolbarResId`  
 Указывает идентификатор ресурса, команды которого вставляются в список команд панели инструментов.  
  
 [in] `lpszCategory`  
 Задает имя категории, к которому необходимо добавить панель инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddToolBar` метод `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [Word Pad образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&11;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Элемент управления, используемый для представления каждой команды [CMFCToolBarButton класс](../../mfc/reference/cmfctoolbarbutton-class.md) объекта. После добавления панели инструментов, можно заменить кнопки элемента управления, производного типа путем вызова [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton).  
  
##  <a name="checktoolsvalidity"></a>CMFCToolBarsCustomizeDialog::CheckToolsValidity  
 Проверяет правильность списка средств пользователя.  
  
```  
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lstTools`  
 Список пользовательских средств для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если список пользовательских средств является допустимым; в противном случае `FALSE`. Реализация по умолчанию всегда возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для проверки допустимости объектов, представляющих пользовательские инструменты, возвращенный [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity).  
  
 Переопределение `CheckToolsValidity` метод в класс производным от `CMFCToolBarsCustomizeDialog` требуется для проверки пользовательских средств, прежде чем пользователь закрывает диалоговое окно. Если этот метод возвращает `FALSE` при щелчке по любой **закрыть** кнопки в правом верхнем углу диалогового окна или кнопка **закрыть** в нижнем правом углу диалогового окна отображает диалоговое окно **средства** вкладку вместо закрытия. Если этот метод возвращает `FALSE` при щелчке вкладки для перехода с **средства** вкладке навигации не происходит. Следует отобразить окно сообщения для информирования пользователей проблема, которая привела к сбою проверки.  
  
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
 Логическое значение, которое указывает, следует ли добавить команды меню все меню список команд на **команды** страницы. Если этот параметр равен `TRUE`, добавляются команды меню. В противном случае — не добавляются команды меню.  
  
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
 Указатель на список `CRuntimeClass` объекты, которые указывают дополнительные пользовательские страницы.  
  
### <a name="remarks"></a>Примечания  
 `plistCustomPages` Параметр ссылается на список `CRuntimeClass` объекты, которые указывают дополнительные пользовательские страницы. Конструктор добавляет дополнительные страницы в диалоговом окне с помощью [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) метод. См. в образце CustomPages пример добавляет дополнительные страницы для **Настройка** диалоговое окно.  
  
 Дополнительные сведения о значениях, которые можно передать в `uiFlags` параметр в разделе [CMFCToolBarsCustomizeDialog::GetFlags](#getflags).  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [пользовательские страницы образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages&#3;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]  
  
##  <a name="create"></a>CMFCToolBarsCustomizeDialog::Create  
 Отображает **настройки** диалоговое окно.  
  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если окно свойств настройки создано успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Вызов `Create` метод только после полной инициализации класса.  
  
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
  
 По умолчанию или если `bEnable` — `FALSE`, эти кнопки не отображаются, и пользователь не может определить новые панели инструментов.  
  
##  <a name="fillallcommandslist"></a>CMFCToolBarsCustomizeDialog::FillAllCommandsList  
 Заполняет предоставленный `CListBox` объектов с помощью команд в **все команды** категории.  
  
```  
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `wndListOfCommands`  
 Ссылку на `CListBox` объекта для заполнения.  
  
### <a name="remarks"></a>Примечания  
 **Все команды** категории команды всех категорий. [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод добавляет команду, которая связана с кнопкой, предоставленный для **все команды** категория для вас.  
  
 Этот метод очищает содержимое указанных `CListBox` объекта до заполнения его с помощью команд в **все команды** категории.  
  
 `CMFCMousePropertyPage` Класс использует этот метод для заполнения списка дважды щелкните событие.  
  
##  <a name="fillcategoriescombobox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesComboBox  
 Заполняет предоставленный `CComboBox` объект с именем каждой категории команд в **Настройка** диалоговое окно.  
  
```  
void FillCategoriesComboBox(
    CComboBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `wndCategory`  
 Ссылку на `CComboBox` объекта для заполнения.  
  
 [in] `bAddEmpty`  
 Логическое значение, указывающее, следует ли добавить категории в поле со списком, у которых нет команды. Если этот параметр равен `TRUE`, пустой категории добавляются в поле со списком. В противном случае — пустой категории не добавляются.  
  
### <a name="remarks"></a>Примечания  
 Этот метод аналогичен [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) метод за исключением того, что этот метод работает с `CComboBox` объекта.  
  
 Этот метод не очищает содержимое `CComboBox` объекта до его заполнения. Гарантирует, что **все команды** категории — последний элемент в поле со списком.  
  
 Можно добавить новые категории команд с помощью [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод. Можно изменить имя существующей категории с помощью [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) метод.  
  
 `CMFCToolBarsKeyboardPropertyPage` И `CMFCKeyMapDialog` классы используют этот метод для категоризации раскладки клавиатуры.  
  
##  <a name="fillcategorieslistbox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesListBox  
 Заполняет предоставленный `CListBox` объект с именем каждой категории команд в **Настройка** диалоговое окно.  
  
```  
void FillCategoriesListBox(
    CListBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `wndCategory`  
 Ссылку на `CListBox` объекта для заполнения.  
  
 [in] `bAddEmpty`  
 Логическое значение, указывающее, следует ли добавить категории в поле списка, у которых нет команды. Если этот параметр равен `TRUE`, пустой категории добавляются в список. В противном случае — пустой категории не добавляются.  
  
### <a name="remarks"></a>Примечания  
 Этот метод аналогичен [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) метод за исключением того, что этот метод работает с `CListBox` объекта.  
  
 Этот метод не очищает содержимое `CListBox` объекта до его заполнения. Гарантирует, что **все команды** категория — последний элемент в поле со списком.  
  
 Можно добавить новые категории команд с помощью [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) метод. Можно изменить имя существующей категории с помощью [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) метод.  
  
 `CMFCToolBarsCommandsPropertyPage` Класс использует этот метод для отображения списка команд, связанных с каждой категорией команды.  
  
##  <a name="getcommandname"></a>CMFCToolBarsCustomizeDialog::GetCommandName  
 Получает имя, связанный с данной команды.  
  
```  
LPCTSTR GetCommandName(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды для получения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя, связанное с заданным Идентификатором команды, или `NULL` Если команда не существует.  
  
##  <a name="getcountincategory"></a>CMFCToolBarsCustomizeDialog::GetCountInCategory  
 Получает число элементов в указанный список с меткой заданный текст.  
  
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
 Число элементов в предоставленном списке которых равно текст метки `lpszItemName`.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент в списке предоставленный объект должен иметь тип `CMFCToolBarButton`. Этот метод сравнивает `lpszItemName` с [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) данные-член.  
  
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
 Позволяет пользователю указать, отображаются ли метки текст под изображения кнопок панели инструментов.  
  
 `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
 Позволяет пользователю задать стиль анимации меню.  
  
 `AFX_CUSTOMIZE_NOHELP`  
 Удаляет «Справка» из диалогового окна настройки.  
  
 `AFX_CUSTOMIZE_CONTEXT_HELP`  
 Позволяет `WS_EX_CONTEXTHELP` визуального стиля.  
  
 `AFX_CUSTOMIZE_NOTOOLS`  
 Удаляет **средства** страницы из диалогового окна настройки. Этот флаг является допустимым, если приложение использует `CUserToolsManager` класса.  
  
 `AFX_CUSTOMIZE_MENUAMPERS`  
 Позволяет кнопках содержать амперсанд ( ** & **) символов.  
  
 `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
 Удаляет **крупные значки** параметр из диалогового окна настройки.  
  
 Дополнительные сведения о `WS_EX_CONTEXTHELP` визуальный стиль в разделе [расширенные стили окна](../../mfc/reference/extended-window-styles.md).  
  
##  <a name="onafterchangetool"></a>CMFCToolBarsCustomizeDialog::OnAfterChangeTool  
 Реагирует на изменения в пользовательский инструмент сразу же после возникновения.  
  
```  
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pSelTool`  
 Указатель на объект пользователя средства, которое было изменено.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при изменении свойства инструмент, определенный пользователем. Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в классе, производном от `CMFCToolBarsCustomizeDialog` для выполнения обработки после изменении пользовательский инструмент.  
  
##  <a name="onassignkey"></a>CMFCToolBarsCustomizeDialog::OnAssignKey  
 Проверяет сочетания клавиш, как пользователь определяет их.  
  
```  
virtual BOOL OnAssignKey(ACCEL* pAccel);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pAccel`  
 Указатель на назначение предложенный клавиатуры, который выражается в виде [ВЫЗОВ](http://msdn.microsoft.com/library/windows/desktop/ms646340) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если ключ может быть назначена или `FALSE` , если ключ не может быть назначен. Реализация по умолчанию всегда возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе для выполнения дополнительной обработки, когда пользователь назначает новое сочетание клавиш или проверить сочетания клавиш как пользователь определяет их. Чтобы запретить присваивание ярлык, возвращают `FALSE`. Следует также отобразить окно сообщения или в противном случае информирует пользователя о причина, почему был отклонен сочетания клавиш.  
  
##  <a name="onbeforechangetool"></a>CMFCToolBarsCustomizeDialog::OnBeforeChangeTool  
 Выполняет специальной обработки при изменении пользовательский инструмент, когда пользователь собирается применить изменение.  
  
```  
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pSelTool`  
 Указатель на объект средства пользователя, который должен быть заменен.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при свойства инструмент, определенный пользователем. Реализация по умолчанию не выполняет никаких действий. Переопределение `OnBeforeChangeTool` метод в класс производным от `CMFCToolBarsCustomizeDialog` Если вы хотите выполнить обработку, прежде чем произойдет изменение пользовательский инструмент, такие как освобождение ресурсов, `pSelTool` использует.  
  
##  <a name="onedittoolbarmenuimage"></a>CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage  
 Запускает редактор изображений, что пользователь может настроить значка элемента кнопки или меню на панели инструментов.  
  
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
 Ссылка на объект bitmap для редактирования.  
  
 [in] `nBitsPerPixel`  
 Битовая карта, цветовое разрешение в бит на пиксель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если изменение фиксируется; в противном случае `FALSE`. Реализация по умолчанию отображается диалоговое окно и возвращает `TRUE` при нажатии кнопки **ОК**, или `FALSE` при нажатии кнопки **отменить** или **закрыть** кнопки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при запуске редактора изображений. Реализация по умолчанию отображает [CMFCImageEditorDialog класса](../../mfc/reference/cmfcimageeditordialog-class.md) диалоговое окно. Переопределение `OnEditToolbarMenuImage` в производном классе с помощью редактора пользовательского образа.  
  
##  <a name="oninitdialog"></a>CMFCToolBarsCustomizeDialog::OnInitDialog  
 Переопределения для дополнения инициализации листа свойств.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат вызова метода [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog), путем отображения **закрыть** кнопки, убедившись, что диалоговое окно соответствует текущий размер экрана и переместив **помочь** кнопки в нижнем левом углу диалогового окна.  
  
##  <a name="oninittoolspage"></a>CMFCToolBarsCustomizeDialog::OnInitToolsPage  
 Обрабатывает уведомления от платформы, **средства** страницы является инициализироваться.  
  
```  
virtual void OnInitToolsPage();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в производном классе для обработки этого уведомления.  
  
##  <a name="postncdestroy"></a>CMFCToolBarsCustomizeDialog::PostNcDestroy  
 Вызывается платформой после окно уже уничтожено.  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, `CPropertySheet::PostNcDestroy`, восстановив его в предыдущий режим.  
  
 [CMFCToolBarsCustomizeDialog::Create](#create) метод помещает его в специальный режим, который ограничивает пользователя задач настройки.  
  
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
 Отсчитываемый от нуля индекс кнопка удаляется или -1, если заданный идентификатор команды не был найден в указанной категории. Если `uiCategoryId` равно -1, возвращаемое значение равно 0.  
  
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
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
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
 A `const` ссылку на объект кнопки панели инструментов, заменяет старый кнопки.  
  
### <a name="remarks"></a>Примечания  
 При [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), или [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) добавляет команды **команды** страницы, что команда находится в форме [класса CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) объекта (или [класса CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) объекта для пункта меню, содержащему вложенное меню, добавленные `AddMenuCommands`). Платформа также вызывает эти три метода, чтобы автоматически добавить команды. Получить команду, чтобы представить его с помощью производного типа, метод `ReplaceButton` и передать в кнопке производного типа.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `ReplaceButton` метод `CMFCToolBarsCustomizeDialog` класса. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#34;](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]  
  
##  <a name="setusercategory"></a>CMFCToolBarsCustomizeDialog::SetUserCategory  
 Указывает категорию в списке категорий на **команды** страница является категории пользователей. Эту функцию необходимо вызывать перед вызовом метода [CMFCToolBarsCustomizeDialog::Create](#create).  
  
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
 [CPropertySheet-класс](../../mfc/reference/cpropertysheet-class.md)

