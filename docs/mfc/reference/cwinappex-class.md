---
title: "CWinAppEx Class | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinAppEx
- AFXWINAPPEX/CWinAppEx
- AFXWINAPPEX/CWinAppEx::CWinAppEx
- AFXWINAPPEX/CWinAppEx::CleanState
- AFXWINAPPEX/CWinAppEx::EnableLoadWindowPlacement
- AFXWINAPPEX/CWinAppEx::EnableTearOffMenus
- AFXWINAPPEX/CWinAppEx::EnableUserTools
- AFXWINAPPEX/CWinAppEx::ExitInstance
- AFXWINAPPEX/CWinAppEx::GetBinary
- AFXWINAPPEX/CWinAppEx::GetContextMenuManager
- AFXWINAPPEX/CWinAppEx::GetDataVersion
- AFXWINAPPEX/CWinAppEx::GetDataVersionMajor
- AFXWINAPPEX/CWinAppEx::GetDataVersionMinor
- AFXWINAPPEX/CWinAppEx::GetInt
- AFXWINAPPEX/CWinAppEx::GetKeyboardManager
- AFXWINAPPEX/CWinAppEx::GetMouseManager
- AFXWINAPPEX/CWinAppEx::GetObject
- AFXWINAPPEX/CWinAppEx::GetRegSectionPath
- AFXWINAPPEX/CWinAppEx::GetRegistryBase
- AFXWINAPPEX/CWinAppEx::GetSectionBinary
- AFXWINAPPEX/CWinAppEx::GetSectionInt
- AFXWINAPPEX/CWinAppEx::GetSectionObject
- AFXWINAPPEX/CWinAppEx::GetSectionString
- AFXWINAPPEX/CWinAppEx::GetShellManager
- AFXWINAPPEX/CWinAppEx::GetString
- AFXWINAPPEX/CWinAppEx::GetTooltipManager
- AFXWINAPPEX/CWinAppEx::GetUserToolsManager
- AFXWINAPPEX/CWinAppEx::InitContextMenuManager
- AFXWINAPPEX/CWinAppEx::InitKeyboardManager
- AFXWINAPPEX/CWinAppEx::InitMouseManager
- AFXWINAPPEX/CWinAppEx::InitShellManager
- AFXWINAPPEX/CWinAppEx::InitTooltipManager
- AFXWINAPPEX/CWinAppEx::IsResourceSmartUpdate
- AFXWINAPPEX/CWinAppEx::IsStateExists
- AFXWINAPPEX/CWinAppEx::LoadState
- AFXWINAPPEX/CWinAppEx::OnAppContextHelp
- AFXWINAPPEX/CWinAppEx::OnViewDoubleClick
- AFXWINAPPEX/CWinAppEx::OnWorkspaceIdle
- AFXWINAPPEX/CWinAppEx::SaveState
- AFXWINAPPEX/CWinAppEx::SetRegistryBase
- AFXWINAPPEX/CWinAppEx::ShowPopupMenu
- AFXWINAPPEX/CWinAppEx::WriteBinary
- AFXWINAPPEX/CWinAppEx::WriteInt
- AFXWINAPPEX/CWinAppEx::WriteObject
- AFXWINAPPEX/CWinAppEx::WriteSectionBinary
- AFXWINAPPEX/CWinAppEx::WriteSectionInt
- AFXWINAPPEX/CWinAppEx::WriteSectionObject
- AFXWINAPPEX/CWinAppEx::WriteSectionString
- AFXWINAPPEX/CWinAppEx::WriteString
- AFXWINAPPEX/CWinAppEx::LoadCustomState
- AFXWINAPPEX/CWinAppEx::LoadWindowPlacement
- AFXWINAPPEX/CWinAppEx::OnClosingMainFrame
- AFXWINAPPEX/CWinAppEx::PreLoadState
- AFXWINAPPEX/CWinAppEx::PreSaveState
- AFXWINAPPEX/CWinAppEx::ReloadWindowPlacement
- AFXWINAPPEX/CWinAppEx::SaveCustomState
- AFXWINAPPEX/CWinAppEx::StoreWindowPlacement
- AFXWINAPPEX/CWinAppEx::m_bForceImageReset
dev_langs:
- C++
helpviewer_keywords:
- CWinAppEx class
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6931f1e794116882722e402c9cb95acec1ebdfd5
ms.lasthandoff: 02/24/2017

---
# <a name="cwinappex-class"></a>CWinAppEx Class
`CWinAppEx`обрабатывает состояние приложения, сохраняет состояние в реестр, загружает состояние из реестра, инициализирует диспетчеры приложения и ссылки на эти же диспетчеры приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinAppEx::CWinAppEx](#cwinappex)|Создает объект `CWinAppEx`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinAppEx::CleanState](#cleanstate)|Удаляет сведения о приложении из реестра Windows.|  
|[CWinAppEx::EnableLoadWindowPlacement](#enableloadwindowplacement)|Указывает, будет ли приложение загрузить начальный размер и расположение фрейма главного окна из реестра.|  
|[CWinAppEx::EnableTearOffMenus](#enabletearoffmenus)|Включает перемещаемое меню для приложения.|  
|[CWinAppEx::EnableUserTools](#enableusertools)|Позволяет пользователю создавать пользовательское меню команд в приложении.|  
|[CWinAppEx::ExitInstance](#exitinstance)|Вызывается платформой из `Run` функции-члена для выхода из этого экземпляра приложения. (Переопределяет [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).)|  
|[CWinAppEx::GetBinary](#getbinary)|Считывает двоичные данные, связанные с указанного значения реестра.|  
|[CWinAppEx::GetContextMenuManager](#getcontextmenumanager)|Возвращает указатель на глобальную [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) объекта.|  
|[CWinAppEx::GetDataVersion](#getdataversion)||  
|[CWinAppEx::GetDataVersionMajor](#getdataversionmajor)|Возвращает основной номер версии приложения, сохраненные в реестре Windows.|  
|[CWinAppEx::GetDataVersionMinor](#getdataversionminor)|Возвращает дополнительный номер версии приложения, сохраненные в реестре Windows.|  
|[CWinAppEx::GetInt](#getint)|Считывает числовых данных, связанный с указанным значением из реестра.|  
|[CWinAppEx::GetKeyboardManager](#getkeyboardmanager)|Возвращает указатель на глобальную [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) объекта.|  
|[CWinAppEx::GetMouseManager](#getmousemanager)|Возвращает указатель на глобальную [CMouseManager](../../mfc/reference/cmousemanager-class.md) объекта.|  
|[CWinAppEx::GetObject](#getobject)|Считывает `CObject`-производные данные, связанные с указанным значением из реестра.|  
|[CWinAppEx::GetRegSectionPath](#getregsectionpath)|Возвращает строку, путь реестра. Этот путь соединяет предоставленного относительный путь с путем приложения.|  
|[CWinAppEx::GetRegistryBase](#getregistrybase)|Возвращает путь в реестре для приложения.|  
|[CWinAppEx::GetSectionBinary](#getsectionbinary)|Считывает двоичные данные, связанные с указанным ключом и значением из реестра.|  
|[CWinAppEx::GetSectionInt](#getsectionint)|Считывает числовые данные из реестра, связанные с указанным ключом и значением.|  
|[CWinAppEx::GetSectionObject](#getsectionobject)|Считывает `CObject` данные, связанные с указанным ключом и значением из реестра.|  
|[CWinAppEx::GetSectionString](#getsectionstring)|Считывает строки данных, связанный с указанным ключом и значением из реестра.|  
|[CWinAppEx::GetShellManager](#getshellmanager)|Возвращает указатель на глобальную [CShellManager](../../mfc/reference/cshellmanager-class.md) объекта.|  
|[CWinAppEx::GetString](#getstring)|Считывает строки данных, связанный с указанным значением из реестра.|  
|[CWinAppEx::GetTooltipManager](#gettooltipmanager)|Возвращает указатель на глобальную [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) объекта.|  
|[CWinAppEx::GetUserToolsManager](#getusertoolsmanager)|Возвращает указатель на глобальную [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) объекта.|  
|[CWinAppEx::InitContextMenuManager](#initcontextmenumanager)|Инициализирует `CContextMenuManager` объекта.|  
|[CWinAppEx::InitKeyboardManager](#initkeyboardmanager)|Инициализирует `CKeyboardManager` объекта.|  
|[CWinAppEx::InitMouseManager](#initmousemanager)|Инициализирует `CMouseManager` объекта.|  
|[CWinAppEx::InitShellManager](#initshellmanager)|Инициализирует `CShellManager` класса|  
|[CWinAppEx::InitTooltipManager](#inittooltipmanager)|Инициализирует `CTooltipManager` класса.|  
|[CWinAppEx::IsResourceSmartUpdate](#isresourcesmartupdate)||  
|[CWinAppEx::IsStateExists](#isstateexists)|Указывает, является ли указанный ключ в реестре.|  
|[CWinAppEx::LoadState](#loadstate)|Загружает состояние приложения из реестра.|  
|[CWinAppEx::OnAppContextHelp](#onappcontexthelp)|Вызывается платформой, когда пользователь запрашивает контекстная справка для **настройки** диалоговое окно.|  
|[CWinAppEx::OnViewDoubleClick](#onviewdoubleclick)|Вызывает команду определяемых пользователем, при двойном щелчке в любом месте в приложении.|  
|[CWinAppEx::OnWorkspaceIdle](#onworkspaceidle)||  
|[CWinAppEx::SaveState](#savestate)|Записывает состояние платформы приложений в реестре Windows.|  
|[CWinAppEx::SetRegistryBase](#setregistrybase)|Задает путь к разделу реестра по умолчанию. Этот ключ будет использоваться в качестве корневого для всех последующих обращений.|  
|[CWinAppEx::ShowPopupMenu](#showpopupmenu)|Отображает всплывающее меню.|  
|[CWinAppEx::WriteBinary](#writebinary)|Записывает двоичные данные для указанного значения реестра.|  
|[CWinAppEx::WriteInt](#writeint)|Записывает указанное значение реестра числовых данных.|  
|[CWinAppEx::WriteObject](#writeobject)|Записывает данные, полученные из [CObject-класс](../../mfc/reference/cobject-class.md) для указанного значения реестра.|  
|[CWinAppEx::WriteSectionBinary](#writesectionbinary)|Записывает значение заданного ключа реестра двоичные данные.|  
|[CWinAppEx::WriteSectionInt](#writesectionint)|Записывает значение заданного ключа реестра числовых данных.|  
|[CWinAppEx::WriteSectionObject](#writesectionobject)|Записывает данные, получаемые из `CObject` класса значение заданного ключа реестра.|  
|[CWinAppEx::WriteSectionString](#writesectionstring)|Записывает значение заданного ключа реестра строковых данных.|  
|[CWinAppEx::WriteString](#writestring)|Записывает строку данных указанного значения реестра.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinAppEx::LoadCustomState](#loadcustomstate)|Вызывается платформой после загрузки состояния приложения.|  
|[CWinAppEx::LoadWindowPlacement](#loadwindowplacement)|Вызывается инфраструктурой при загрузке размер и расположение приложения из реестра. Загрузить данные включают размер и расположение основного фрейма во время последнего закрытия приложения.|  
|[CWinAppEx::OnClosingMainFrame](#onclosingmainframe)|Вызывается инфраструктурой при обработке фрейма главного окна `WM_CLOSE`.|  
|[CWinAppEx::PreLoadState](#preloadstate)|Вызывается непосредственно перед платформой загружается состояние приложения.|  
|[CWinAppEx::PreSaveState](#presavestate)|Вызывается платформой сразу перед сохранением состояния приложения.|  
|[CWinAppEx::ReloadWindowPlacement](#reloadwindowplacement)|Перезагружает размер и расположение окна, предоставленного из реестра|  
|[CWinAppEx::SaveCustomState](#savecustomstate)|Вызывается платформой после записывает состояние приложения в реестр.|  
|[CWinAppEx::StoreWindowPlacement](#storewindowplacement)|Вызывается платформой для записи в реестре размер и расположение основного фрейма.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinAppEx::m_bForceImageReset](#m_bforceimagereset)|Указывает, будет ли платформа Сброс всех изображений на панели инструментов при загрузке окна фрейма, содержащего панели инструментов.|  
  
## <a name="remarks"></a>Примечания  
 Большая часть функциональных возможностей платформы MFC, зависит от `CWinAppEx` класса. Можно включить `CWinAppEx` класс в приложении одним из двух способов:  
  
-   Создать `CWinAppEx` класс в основном потоке.  
  
-   Производный класс от основного приложения `CWinAppEx`.  
  
 После использования `CWinAppEx` в приложение, можно инициализировать один из диспетчеров приложений. Прежде чем использовать диспетчер приложения, необходимо инициализировать его путем вызова метода initialize соответствующие. Чтобы получить указатель тому или иному менеджеру, вызовите метод get связан. `CWinAppEx` Класс управляет следующие диспетчеры приложения: [CMouseManager класса](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager класса](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager класса](../../mfc/reference/ckeyboardmanager-class.md), [CUserToolsManager класса](../../mfc/reference/cusertoolsmanager-class.md), и [CMenuTearOffManager класса](../../mfc/reference/cmenutearoffmanager-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwinappex.h  
  
##  <a name="cleanstate"></a>CWinAppEx::CleanState  
 Удаляет все сведения о приложении из реестра Windows.  
  
```  
virtual BOOL CleanState(LPCTSTR lpszSectionName=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSectionName`  
 Строка, содержащая путь раздела реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод был выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод очищает данные приложения из указанного раздела реестра. Этот раздел, чтобы очистить с помощью параметра можно указать `lpszSectionName`. Если `lpszSectionName` — `NULL`, этот метод будет использоваться путь реестра по умолчанию хранится в `CWinAppEx` объекта. Чтобы получить путь реестра по умолчанию, используйте [CWinAppEx::GetRegistryBase](#getregistrybase).  
  
##  <a name="cwinappex"></a>CWinAppEx::CWinAppEx  
 Создает объект `CWinAppEx`.  
  
```  
CWinAppEx(BOOL bResourceSmartUpdate = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bResourceSmartUpdate`  
 Логический параметр, который указывает, должен ли объект рабочей области обнаружения и обработки обновления ресурса.  
  
### <a name="remarks"></a>Примечания  
 `CWinAppEx` Класс содержит методы инициализации, предоставляет функциональные возможности для сохранения и загрузки сведений о приложении в реестре и определяет глобальные параметры приложения. Он также позволяет использовать глобальный диспетчеры, такие как [класса CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) и [CUserToolsManager класса](../../mfc/reference/cusertoolsmanager-class.md). Каждое приложение может иметь только один экземпляр `CWinAppEx` класса.  
  
##  <a name="enableloadwindowplacement"></a>CWinAppEx::EnableLoadWindowPlacement  
 Указывает, будет ли приложение загрузить начальный размер и расположение фрейма главного окна из реестра.  
  
```  
void EnableLoadWindowPlacement(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Указывает, является ли приложение загружает исходный размер и расположение фрейма главного окна из реестра.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию размер и расположение основного фрейма загружается из реестра и другие параметры приложения. Это происходит во время [CWinAppEx::LoadState](#loadstate). Если вы не хотите загрузить размещения начального окна из реестра, этот метод вызывается со `bEnable` значение `false`.  
  
##  <a name="enabletearoffmenus"></a>CWinAppEx::EnableTearOffMenus  
 Создает и инициализирует [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) объекта.  
  
```  
BOOL EnableTearOffMenus(
    LPCTSTR lpszRegEntry,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszRegEntry`  
 Строка, содержащая путь к разделу реестра. Приложение использует этот раздел реестра для хранения сведений о перемещаемыми меню.  
  
 [in] `uiCmdFirst`  
 Идентификатор первого разрушение меню.  
  
 [in] `uiCmdLast`  
 Идентификатор последнего разрушение меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `True`Если `CMenuTearOffManager` создан и инициализирован успешно. `false` при возникновении ошибки или если `CMenuTearOffManager` уже существует.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для включения перемещаемое меню в приложении. Вы должны вызвать эту функцию из `InitInstance`.  
  
##  <a name="enableusertools"></a>CWinAppEx::EnableUserTools  
 Позволяет пользователю создавать пользовательское меню команд, уменьшить число нажатий клавиш в приложении. Этот метод создает [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) объекта.  
  
```  
BOOL EnableUserTools(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC = RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID = 0,  
    UINT uInitDirMenuID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdToolsDummy`  
 Целое число без знака, она используется в качестве заполнителя для идентификатор команды меню средства пользователя.  
  
 [in] `uiCmdFirst`  
 Идентификатор команды для команды средства первого пользователя.  
  
 [in] `uiCmdLast`  
 Идентификатор команды для команды средства последнего пользователя.  
  
 [in] `pToolRTC`  
 Класс, `CUserToolsManager` объект использует, чтобы создавать новые пользовательские инструменты.  
  
 [in] `uArgMenuID`  
 Идентификатор аргумента меню.  
  
 [in] `uInitDirMenuID`  
 Идентификатор меню начальной средство каталога.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод создает и инициализирует `CUserToolsManager` объекта; `FALSE` при сбое метода или если `CUserToolsManager` объект уже существует.  
  
### <a name="remarks"></a>Примечания  
 При включении пользовательских средств framework автоматически поддерживает динамическое меню, который может быть расширен во время настройки. Платформа связывает каждый новый элемент с внешней команды. Платформа вызывает эти команды, когда пользователь выбирает соответствующий элемент из **средства** меню.  
  
 Каждый раз, когда пользователь добавляет новый элемент, платформа создает новый объект. Тип класса для нового объекта определяется `pToolRTC`. `pToolRTC` Типа класса должен быть производным от [CUserTool класса](../../mfc/reference/cusertool-class.md).  
  
 Дополнительные сведения о пользовательских средств и внедрить их в приложение см. в разделе [пользовательские средства](../../mfc/user-defined-tools.md).  
  
##  <a name="exitinstance"></a>CWinAppEx::ExitInstance  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getbinary"></a>CWinAppEx::GetBinary  
 Считывает двоичные данные из заданного раздела реестра.  
  
```  
BOOL GetBinary(
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszEntry`  
 Строка, содержащая имя раздела реестра.  
  
 [выходной] `ppData`  
 Указатель на буфер, метод заполняет двоичные данные.  
  
 [выходной] `pBytes`  
 Указатель на целое число без знака, который использует метод для записи число считанных байтов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `True`в случае успешного выполнения; `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод считывает двоичные данные, записанные в реестр. Для записи данных в реестр, используйте методы [CWinAppEx::WriteBinary](#writebinary) и [CWinAppEx::WriteSectionBinary](#writesectionbinary).  
  
 `lpszEntry` Параметром является имя записи реестра, расположенный в разделе реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="getcontextmenumanager"></a>CWinAppEx::GetContextMenuManager  
 Возвращает указатель на глобальную [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) объекта.  
  
```  
CContextMenuManager* GetContextMenuManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на глобальную `CContextMenuManager` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если объект CContextMenuManager не инициализирован, эта функция вызывает функцию [CWinAppEx::InitContextMenuManager](#initcontextmenumanager) перед возвращением указателя.  
  
##  <a name="getdataversion"></a>CWinAppEx::GetDataVersion  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetDataVersion() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdataversionmajor"></a>CWinAppEx::GetDataVersionMajor  
 Возвращает основной номер версии приложения, которое сохраняется в реестре Windows, при вызове [CWinAppEx::SaveState](#savestate).  
  
```  
int GetDataVersionMajor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, содержащее номер основной версии.  
  
##  <a name="getdataversionminor"></a>CWinAppEx::GetDataVersionMinor  
 Возвращает дополнительный номер версии приложения, которое сохраняется в реестре Windows, при вызове [CWinAppEx::SaveState](#savestate).  
  
```  
int GetDataVersionMinor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, содержащее дополнительный номер версии.  
  
##  <a name="getint"></a>CWinAppEx::GetInt  
 Считывает целое число из заданного раздела реестра.  
  
```  
int GetInt(
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszEntry`  
 Строка, содержащая имя записи реестра.  
  
 [in] `nDefault`  
 Значение по умолчанию, методом, если указанный параметр не существует.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Данные реестра, если метод был выполнен успешно; в противном случае `nDefault`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод считывает целочисленные данные из реестра. Если нет не целочисленные данные, связанные с разделом реестра, обозначенными `lpszEntry`, этот метод возвращает `nDefault`. Для записи данных в реестр, используйте методы [CWinAppEx::WriteSectionInt](#writesectionint) и [CWinAppEx::WriteInt](#writeint).  
  
 `lpszEntry` Параметром является имя записи реестра, расположенный в разделе реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="getkeyboardmanager"></a>CWinAppEx::GetKeyboardManager  
 Возвращает указатель на глобальную [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) объекта.  
  
```  
CKeyboardManager* GetKeyboardManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на глобальную `CKeyboardManager` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если диспетчер клавиатуры не инициализирован, эта функция вызывает функцию [CWinAppEx::InitKeyboardManager](#initkeyboardmanager) перед возвращением указателя.  
  
##  <a name="getmousemanager"></a>CWinAppEx::GetMouseManager  
 Возвращает указатель на глобальную [CMouseManager](../../mfc/reference/cmousemanager-class.md) объекта.  
  
```  
CMouseManager* GetMouseManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на глобальную `CMouseManager` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если диспетчер мыши не инициализирован, эта функция вызывает функцию [CWinAppEx::InitMouseManager](#initmousemanager) перед возвращением указателя.  
  
##  <a name="getobject"></a>CWinAppEx::GetObject  
 Считывает [CObject](../../mfc/reference/cobject-class.md)- dervied данные из реестра.  
  
```  
BOOL GetObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszEntry`  
 Строка, содержащая относительный путь записи в реестре.  
  
 [выходной] `obj`  
 Ссылку на `CObject`. Метод использует эту ссылку для хранения данных реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод был выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод считывает данные из реестра, который является производным от `CObject`. Для записи `CObject` использовать данные в реестре, либо [CWinAppEx::WriteObject](#writeobject) или [CWinAppEx::WriteSectionObject](#writesectionobject).  
  
 `lpszEntry` Параметром является имя записи реестра, расположенный в разделе реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="getregistrybase"></a>CWinAppEx::GetRegistryBase  
 Возвращает путь в реестре по умолчанию для приложения.  
  
```  
LPCTSTR GetRegistryBase();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая путь к местоположению реестра по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Все методы [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) , доступ к в начале реестра в расположение по умолчанию. Используйте этот метод для получения пути реестра расположение по умолчанию. Используйте [CWinAppEx::SetRegistryBase](#setregistrybase) для изменения расположения реестра по умолчанию.  
  
##  <a name="getregsectionpath"></a>CWinAppEx::GetRegSectionPath  
 Создает и возвращает абсолютный путь раздела реестра.  
  
```  
CString GetRegSectionPath(LPCTSTR szSectionAdd = _T(""));
```  
  
### <a name="parameters"></a>Параметры  
 [in] `szSectionAdd`  
 Строка, содержащая относительный путь раздела реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий абсолютный путь раздела реестра.  
  
### <a name="remarks"></a>Примечания  
 Этот метод определяет абсолютный путь к разделу реестра путем добавления относительный путь в `szSectionAdd` для раздела реестра по умолчанию для вашего приложения. Чтобы получить ключ реестра по умолчанию, используйте метод [CWinAppEx::GetRegistryBase](#getregistrybase).  
  
##  <a name="getsectionbinary"></a>CWinAppEx::GetSectionBinary  
 Считывает двоичные данные из реестра.  
  
```  
BOOL GetSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSubSection`  
 Строка, содержащая относительный путь раздела реестра.  
  
 [in] `lpszEntry`  
 Строка, содержащая значение для чтения.  
  
 [выходной] `ppData`  
 Указатель на буфер, где метод сохраняет данные.  
  
 [выходной] `pBytes`  
 Указатель на целое число без знака. Метод записывает размер `ppData` для этого параметра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `True` в случае успешного выполнения; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод считывает двоичные данные, которые записываются в реестр с помощью методов [CWinAppEx::WriteBinary](#writebinary) и [CWinAppEx::WriteSectionBinary](#writesectionbinary).  
  
 `lpszSubSection` Параметр не является абсолютным для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="getsectionint"></a>CWinAppEx::GetSectionInt  
 Считывает целое число со знаком данные из реестра.  
  
```  
int GetSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSubSection`  
 Строка, содержащая относительный путь раздела реестра.  
  
 [in] `lpszEntry`  
 Строка, содержащая значение для чтения.  
  
 [in] `nDefault`  
 По умолчанию значение, возвращаемое, если указанное значение не существует.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленные данные, хранящиеся в реестре задано значение; `nDefault` Если данные не существует.  
  
### <a name="remarks"></a>Примечания  
 Используйте методы [CWinAppEx::WriteInt](#writeint) и [CWinAppEx::WriteSectionInt](#writesectionint) для записи в реестр целочисленные данные.  
  
 `lpszSubSection` Параметр не является абсолютным запись реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="getsectionobject"></a>CWinAppEx::GetSectionObject  
 Считывает [CObject](../../mfc/reference/cobject-class.md) данных реестра из реестра.  
  
```  
BOOL GetSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSubSection`  
 Строка, содержащая относительный путь раздела реестра.  
  
 [in] `lpszEntry`  
 Строка, содержащая значение для чтения.  
  
 [выходной] `obj`  
 Ссылку на `CObject`. Этот метод использует это `CObject` для хранения данных реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод считывает данные из реестра. Чтение данных может `CObject` данные, или класс, производный от `CObject`. Для записи `CObject` использовать данные в реестре, либо [CWinAppEx::WriteObject](#writeobject) или [CWinAppEx::WriteSectionObject](#writesectionobject).  
  
 `lpszSubSection` Параметр не является абсолютным для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="getsectionstring"></a>CWinAppEx::GetSectionString  
 Чтение строки данных из реестра.  
  
```  
CString GetSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = _T(""));
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSubSection`  
 Строка, содержащая относительный путь раздела реестра.  
  
 [in] `lpszEntry`  
 Строка, содержащая значение для чтения.  
  
 [in] `lpszDefault`  
 По умолчанию значение, возвращаемое, если указанное значение не существует.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка данных, хранящихся в реестре задано значение, если существует данных; в противном случае `lpszDefault`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод считывает строки данных, записываются в реестр. Используйте [CWinAppEx::WriteString](#writestring) и [CWinAppEx::WriteSectionString](#writesectionstring) для записи строки данных в реестр.  
  
 `lpszSubSection` Параметр не является абсолютным для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="getshellmanager"></a>CWinAppEx::GetShellManager  
 Возвращает указатель на глобальную [CShellManager](../../mfc/reference/cshellmanager-class.md) объекта.  
  
```  
CShellManager* GetShellManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на глобальную `CShellManager` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если `CShellManager` объект не инициализирован, эта функция вызывает функцию [CWinAppEx::InitShellManager](#initshellmanager) перед возвращением указателя.  
  
##  <a name="getstring"></a>CWinAppEx::GetString  
 Чтение строковые данные из заданного раздела реестра.  
  
```  
CString GetString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpzDefault= _T(""));
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszEntry`  
 Строка, содержащая имя раздела реестра  
  
 [in] `lpzDefault`  
 Значение по умолчанию, методом, если указанный параметр не существует.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строковые данные, хранящиеся в реестре, если выполнено успешно; `lpszDefault` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод считывает строки данных, записываются в реестр. Для записи данных в реестр, используйте методы [CWinAppEx::WriteString](#writestring) или [CWinAppEx::WriteSectionString](#writesectionstring).  
  
 `lpszEntry` Параметром является имя записи реестра, расположенный в разделе реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="gettooltipmanager"></a>CWinAppEx::GetTooltipManager  
 Возвращает указатель на глобальную [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) объекта.  
  
```  
CTooltipManager* GetTooltipManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на глобальную `CTooltipManager` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если `CTooltipManager` объект не инициализирован, эта функция вызывает функцию [CWinAppEx::InitTooltipManager](#inittooltipmanager) перед возвращением указателя.  
  
##  <a name="getusertoolsmanager"></a>CWinAppEx::GetUserToolsManager  
 Возвращает указатель на глобальную [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) объекта.  
  
```  
CUserToolsManager* GetUserToolsManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на глобальную `CUserToolsManager` объекта; `NULL` Если средств управления пользователя не включена для приложения.  
  
### <a name="remarks"></a>Примечания  
 Прежде чем получить указатель `CUserToolsManager` объекта, необходимо инициализировать диспетчер путем вызова [CWinAppEx::EnableUserTools](#enableusertools).  
  
##  <a name="initcontextmenumanager"></a>CWinAppEx::InitContextMenuManager  
 Инициализирует [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) объекта.  
  
```  
BOOL InitContextMenuManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод создает объект CContextMenuManager; 0, если `CContextMenuManager` объект уже существует.  
  
### <a name="remarks"></a>Примечания  
 При вызове метода [CWinAppEx::GetContextMenuManager](#getcontextmenumanager), реализация по умолчанию этого метода вызывает `InitContextMenuManager`.  
  
 Если приложение уже имеет руководителем контекстного меню можно вызвать метод `InitContextMenuManager`, приложение будет иметь [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) сбоя. Таким образом, не следует вызывать `InitContextMenuManager` при создании `CContextMenuManager` напрямую. Если вы не используете пользовательского `CContextMenuManager`, следует использовать `GetContextMenuManager` для создания `CContextMenuManager` объекта.  
  
##  <a name="initkeyboardmanager"></a>CWinAppEx::InitKeyboardManager  
 Инициализирует [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) объекта.  
  
```  
BOOL InitKeyboardManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод создает `CKeyboardManager` объекта; 0, если `CKeyboardManager` объект уже существует.  
  
### <a name="remarks"></a>Примечания  
 При вызове метода [CWinAppEx::GetKeyboardManager](#getkeyboardmanager), реализация по умолчанию этого метода вызывает `InitKeyboardManager`.  
  
 Если приложение уже имеет manager клавиатуры и вызывается `InitKeyboardManager`, приложение будет иметь [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) сбоя. Таким образом, не следует вызывать `InitKeyboardManager` при создании `CKeyboardManager` напрямую. Если вы не используете пользовательского `CKeyboardManager`, следует использовать `GetKeyboardManager` для создания `CKeyboardManager` объекта.  
  
##  <a name="initmousemanager"></a>CWinAppEx::InitMouseManager  
 Инициализирует [CMouseManager](../../mfc/reference/cmousemanager-class.md) объекта.  
  
```  
BOOL InitMouseManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод создает `CMouseManager` объекта; 0, если `CMouseManager` объект уже существует.  
  
### <a name="remarks"></a>Примечания  
 При вызове метода [CWinAppEx::GetMouseManager](#getmousemanager), реализация по умолчанию этого метода вызывает `InitMouseManager`.  
  
 Если приложение уже имеет manager мыши, можно вызвать метод `InitMouseManager`, приложение будет иметь [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) сбоя. Поэтому не следует вызывать `InitMouseManager` при создании `CMouseManager` напрямую. Если вы не используете пользовательского `CMouseManager`, следует использовать `GetMouseManager` для создания `CMouseManager` объекта.  
  
##  <a name="initshellmanager"></a>CWinAppEx::InitShellManager  
 Инициализирует [CShellManager](../../mfc/reference/cshellmanager-class.md) объекта.  
  
```  
BOOL InitShellManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод создает `CShellManager` объекта; 0, если `CShellManager` объект уже существует.  
  
### <a name="remarks"></a>Примечания  
 При вызове метода [CWinAppEx::GetShellManager](#getshellmanager), реализация по умолчанию этого метода вызывает `InitShellManager`.  
  
 Если приложение уже имеет manager оболочки можно вызвать метод `InitShellManager`, вызывает вашего приложения [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) сбоя. Таким образом, не следует вызывать `InitShellManager` при создании `CShellManager` напрямую. Если вы не используете пользовательского `CShellManager`, используйте `GetShellManager` для создания `CShellManager` объекта.  
  
##  <a name="inittooltipmanager"></a>CWinAppEx::InitTooltipManager  
 Инициализирует [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) объекта.  
  
```  
BOOL InitTooltipManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод создает `CTooltipManager` объекта; 0, если `CTooltipManager` объект уже существует.  
  
### <a name="remarks"></a>Примечания  
 При вызове метода [CWinAppEx::GetTooltipManager](#gettooltipmanager), реализация по умолчанию этого метода вызывает `InitTooltipManager`.  
  
 Если приложение уже имеет manager подсказки можно вызвать метод `InitTooltipManager`, приложение будет иметь [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) сбоя. Таким образом, не следует вызывать `InitTooltipManager` при создании `CTooltipManager` напрямую. Если вы не используете пользовательского `CTooltipManager`, следует использовать `GetTooltipManager` для создания `CTooltipManager` объекта.  
  
##  <a name="isresourcesmartupdate"></a>CWinAppEx::IsResourceSmartUpdate  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsResourceSmartUpdate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isstateexists"></a>CWinAppEx::IsStateExists  
 Указывает, является ли указанный ключ в реестре.  
  
```  
BOOL IsStateExists(LPCTSTR lpszSectionName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSectionName`  
 Строка, содержащая путь раздела реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если ключ в реестре; в противном случае — 0.  
  
##  <a name="loadcustomstate"></a>CWinAppEx::LoadCustomState  
 Платформа вызывает этот метод после загрузки состояния приложения из реестра.  
  
```  
virtual void LoadCustomState();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если требуется выполнять обработку после приложение загружает состояние из реестра. По умолчанию этот метод не выполняет никаких действий.  
  
 Для загрузки сведений о пользовательском состоянии из реестра, данные необходимо сохранить с помощью [CWinAppEx::SaveCustomState](#savecustomstate).  
  
##  <a name="loadstate"></a>CWinAppEx::LoadState  
 Считывает состояние приложения из реестра Windows.  
  
```  
BOOL LoadState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
virtual BOOL LoadState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pFrame`  
 Указатель на объект окна фрейма. Сведения о состоянии в реестре это окно применяется данный метод.  
  
 [in] `lpszSectionName`  
 Строка, содержащая относительный путь раздела реестра.  
  
 [in] `pFrameImpl`  
 Указатель на объект `CFrameImpl`. Сведения о состоянии в реестре это окно применяется данный метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод загружает состояние приложения и данные о состоянии для фрейма окна. Загрузить сведения для фрейма окна применяется к предоставленным фрейме окна. Если не указать рамка окна, загружается только сведения о состоянии приложения. Состояние включает сведения о приложении [CMouseManager класса](../../mfc/reference/cmousemanager-class.md), [класса CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md), [класса CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)и [CUserToolsManager класса](../../mfc/reference/cusertoolsmanager-class.md).  
  
 Реализация по умолчанию `CFrameImpl::OnLoadFrame` вызовов `LoadState`.  
  
 `lpszSectionName` Параметр не абсолютный путь для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="loadwindowplacement"></a>CWinAppEx::LoadWindowPlacement  
 Вызывается инфраструктурой при загрузке размер и расположение фрейма главного окна из реестра.  
  
```  
virtual BOOL LoadWindowPlacement(
    CRect& rectNormalPosition,  
    int& nFlags,  
    int& nShowCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectNormalPosition`  
 Прямоугольник, содержащий координаты фрейма главного окна, находящегося в восстановленной позиции.  
  
 [выходной] `nFlags`  
 Флаги, определяющие положение свернутого окна и как операционная система переключает между свернутого окна и восстановленного окна.  
  
 [выходной] `nShowCmd`  
 Целое число, указывающее состояние отображения окна. Дополнительные сведения о возможных значениях см. в разделе [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию в MFC автоматически загружает предыдущее положение и состояние фрейма главного окна, при запуске приложения. Дополнительные сведения о том, как эти сведения хранятся в реестре в разделе [CWinAppEx::StoreWindowPlacement](#storewindowplacement).  
  
 Переопределите этот метод, если вы хотите загрузить дополнительные сведения о фрейма главного окна.  
  
##  <a name="m_bforceimagereset"></a>CWinAppEx::m_bForceImageReset  
 Указывает ли платформа сбрасывает все изображения с панели инструментов при загрузке окна фрейма, содержащего панели инструментов.  
  
```  
BOOL m_bForceImageReset;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_bForceImageReset` Член данных является защищенной переменной.  
  
##  <a name="onappcontexthelp"></a>CWinAppEx::OnAppContextHelp  
 Платформа вызывает этот метод, когда пользователь запрашивает контекстная справка для **настройки** диалоговое окно.  
  
```  
virtual void OnAppContextHelp(
    CWnd* pWndControl,  
    const DWORD dwHelpIDArray[]);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndControl`  
 Указатель на объект окна, для которого пользователь вызывает контекстная справка.  
  
 [in] `dwHelpIDArray[]`  
 Зарезервированное значение.  
  
### <a name="remarks"></a>Примечания  
 В настоящее время этот метод зарезервирован для использования в будущем. Реализация по умолчанию не выполняет никаких действий, и он в настоящее время не вызывается платформой.  
  
##  <a name="onclosingmainframe"></a>CWinAppEx::OnClosingMainFrame  
 Платформа вызывает этот метод при обработке фрейма окна `WM_CLOSE`.  
  
```  
virtual void OnClosingMainFrame(CFrameImpl* pFrameImpl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pFrameImpl`  
 Указатель на объект `CFrameImpl`.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этот метод сохраняет состояние `pFrameImpl`.  
  
##  <a name="onviewdoubleclick"></a>CWinAppEx::OnViewDoubleClick  
 Вызывает команду определяемых пользователем, связанный с представлением при двойном щелчке в любом месте в этом представлении.  
  
```  
virtual BOOL OnViewDoubleClick(
    CWnd* pWnd,  
    int iViewId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель на объект производного от [CView-класс](../../mfc/reference/cview-class.md).  
  
 [in] `iViewId`  
 Идентификатор представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `True`Если платформа находит команды; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Для поддержки пользовательских мыши поведение, необходимо вызвать эту функцию при обработке `WM_LBUTTONDBLCLK` сообщение. Этот метод выполнит команду, связанных с Идентификатором представления, предоставляемые `iViewId`. Дополнительные сведения о поведении пользовательского мыши в разделе [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md).  
  
##  <a name="onworkspaceidle"></a>CWinAppEx::OnWorkspaceIdle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnWorkspaceIdle(CWnd*);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CWnd*`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="preloadstate"></a>CWinAppEx::PreLoadState  
 Платформа вызывает этот метод непосредственно перед его загружает состояние приложения из реестра.  
  
```  
virtual void PreLoadState();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если требуется выполнять обработку сразу перед загрузкой платформа состояние приложения.  
  
##  <a name="presavestate"></a>CWinAppEx::PreSaveState  
 Платформа вызывает этот метод непосредственно перед сохранением состояния приложения.  
  
```  
virtual void PreSaveState();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если требуется выполнять обработку непосредственно перед framework сохраняет состояние приложения.  
  
##  <a name="reloadwindowplacement"></a>CWinAppEx::ReloadWindowPlacement  
 Перезагружает размер и расположение окна из реестра.  
  
```  
virtual BOOL ReloadWindowPlacement(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pFrame`  
 Указатель фрейма окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод был выполнен успешно; 0, если загрузка сбойных или нет – нет данных для загрузки.  
  
### <a name="remarks"></a>Примечания  
 Используйте функцию [CWinAppEx::StoreWindowPlacement](#storewindowplacement) для записи в реестре размер и расположение окна.  
  
##  <a name="savecustomstate"></a>CWinAppEx::SaveCustomState  
 Платформа вызывает этот метод после сохраняет состояние приложения в реестре.  
  
```  
virtual void SaveCustomState();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если требуется выполнять обработку после приложение сохраняет состояние в реестр. По умолчанию этот метод не выполняет никаких действий.  
  
##  <a name="savestate"></a>CWinAppEx::SaveState  
 Записывает состояние приложения в реестре Windows.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);

 
BOOL SaveState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSectionName`  
 Строка, содержащая относительный путь раздела реестра.  
  
 [in] `pFrameImpl`  
 Указатель на объект `CFrameImpl`. Данный кадр сохраняется в реестре Windows.  
  
 [in] `pFrame`  
 Указатель на объект окна фрейма. Данный кадр сохраняется в реестре Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `True`в случае успешного выполнения; `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод сохраняет состояние приложения и данные о состоянии для предоставленного фрейме окна. Если окно не указано, метод только сохраняет состояние приложения. Состояние включает сведения о приложении [CMouseManager класса](../../mfc/reference/cmousemanager-class.md), [класса CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md), [класса CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)и [CUserToolsManager класса](../../mfc/reference/cusertoolsmanager-class.md).  
  
 `lpszSectionName` Параметр не абсолютный путь для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
##  <a name="setregistrybase"></a>CWinAppEx::SetRegistryBase  
 Задает путь реестра по умолчанию для приложения.  
  
```  
LPCTSTR SetRegistryBase(LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSectionName`  
 Строка, содержащая путь к разделу реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая путь к местоположению реестра по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Все методы [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) , доступ к в начале реестра в расположение по умолчанию. Этот метод можно используйте для изменения реестра, по умолчанию. Используйте [CWinAppEx::GetRegistryBase](#getregistrybase) для получения расположения реестра по умолчанию.  
  
##  <a name="showpopupmenu"></a>CWinAppEx::ShowPopupMenu  
 Отображает всплывающее меню.  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    const CPoint& point,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiMenuResId`  
 Идентификатор ресурса меню.  
  
 [in] `point`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , указывающее положение элемента меню в экранных координатах.  
  
 [in] `pWnd`  
 Указатель на окно, которому принадлежит всплывающее меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если меню отображается успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отображает меню, связанное с `uiMenuResId`.  
  
 Для поддержки всплывающих меню, необходимо иметь [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) объекта. Если не будет инициализирован `CContextMenuManager` объекта, `ShowPopupMenu` завершится ошибкой.  
  
##  <a name="storewindowplacement"></a>CWinAppEx::StoreWindowPlacement  
 Вызывается платформой для записи в реестре размер и расположение фрейма главного окна.  
  
```  
virtual BOOL StoreWindowPlacement(
    const CRect& rectNormalPosition,  
    int nFlags,  
    int nShowCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nFlags`  
 Флаги, определяющие положение свернутого окна и как операционная система переключает между свернутого окна и восстановленного окна.  
  
 [in] `nShowCmd`  
 Целое число, указывающее состояние отображения окна. Дополнительные сведения о возможных значениях см. в разделе [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow).  
  
 [in] `rectNormalPosition`  
 Прямоугольник, содержащий координаты фрейма главного окна, когда он находится в состоянии восстановленного.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию MFC автоматически сохраняет положение и состояние фрейма главного окна до выхода из приложения. Эти сведения хранятся в реестре в разделе WindowPlacement в раздел реестра по умолчанию для вашего приложения. Дополнительные сведения о расположении реестра по умолчанию приложения в разделе [CWinAppEx::GetRegistryBase](#getregistrybase).  
  
 Переопределите этот метод, если требуется для хранения дополнительных сведений о фрейма главного окна.  
  
##  <a name="writebinary"></a>CWinAppEx::WriteBinary  
 Записывает двоичные данные в реестр.  
  
```  
BOOL WriteBinary(
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszEntry`  
 Строка, содержащая имя раздела реестра.  
  
 [in] `pData`  
 Для хранения данных.  
  
 [in] `nBytes`  
 Размер `pData` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `lpszEntry` Параметром является имя записи реестра, расположенный в разделе реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
 Если ключ, указанный параметром `lpszEntry` не существует, этот метод создаст ее.  
  
##  <a name="writeint"></a>CWinAppEx::WriteInt  
 Записывает в реестр числовых данных.  
  
```  
BOOL WriteInt(
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszEntry`  
 Строка, содержащая имя раздела реестра.  
  
 [in] `nValue`  
 Для хранения данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `lpszEntry` Параметром является имя записи реестра, расположенный в разделе реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
 Если ключ, указанный параметром `lpszEntry` не существует, этот метод создаст ее.  
  
##  <a name="writeobject"></a>CWinAppEx::WriteObject  
 Записывает данные, получаемые из [класс CObject](../../mfc/reference/cobject-class.md) в реестре.  
  
```  
BOOL WriteObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszEntry`  
 Строка, содержащая значение.  
  
 [in] `obj`  
 Ссылку на `CObject` данные, которые будут храниться в метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод записывает `obj` данных с указанным значением раздела реестра по умолчанию. Используйте [CWinAppEx::GetRegistryBase](#getregistrybase) для определения текущего раздела реестра.  
  
##  <a name="writesectionbinary"></a>CWinAppEx::WriteSectionBinary  
 Записывает значение в реестре двоичных данных.  
  
```  
BOOL WriteSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSubSection`  
 Строка, содержащая имя раздела реестра  
  
 [in] `lpszEntry`  
 Строка, содержащая значение.  
  
 [in] `pData`  
 Данные для записи в реестр.  
  
 [in] `nBytes`  
 Размер `pData` в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `lpszSubSection` Параметр не абсолютный путь для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
 Если ключ, указанный параметром `lpszEntry` не существует, этот метод создаст ее.  
  
##  <a name="writesectionint"></a>CWinAppEx::WriteSectionInt  
 Записывает в реестр числовых данных.  
  
```  
BOOL WriteSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSubSection`  
 Строка, содержащая относительный путь раздела реестра.  
  
 [in] `lpszEntry`  
 Строка, содержащая значение.  
  
 [in] `nValue`  
 Данные для записи в реестр.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `lpszSubSection` Параметр не является абсолютным для записи реестра. Это относительный путь, который добавляется в раздел реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
 Если ключ, указанный параметром `lpszEntry` не существует, этот метод создаст ее.  
  
##  <a name="writesectionobject"></a>CWinAppEx::WriteSectionObject  
 Записывает данные, получаемые из [класс CObject](../../mfc/reference/cobject-class.md) значение реестра.  
  
```  
BOOL WriteSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSubSection`  
 Строка, содержащая имя раздела реестра.  
  
 [in] `lpszEntry`  
 Строка, содержащая имя значения, которое требуется задать.  
  
 [in] `obj`  
 Для хранения данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `lpszSubSection` Параметр не является абсолютным для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase)соответственно.  
  
 Если значение, заданное `lpszEntry` не существует в раздел реестра, указанный в `lpszSubSection`, этот метод создает это значение.  
  
##  <a name="writesectionstring"></a>CWinAppEx::WriteSectionString  
 Записывает данные строковое значение в реестре.  
  
```  
BOOL WriteSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszSubSection`  
 Строка, содержащая имя раздела реестра.  
  
 [in] `lpszEntry`  
 Строка, содержащая значение.  
  
 [in] `lpszValue`  
 Строковые данные для записи в реестр.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `lpszSubSection` Параметр не является абсолютным для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase)соответственно.  
  
 Если значение, заданное `lpszEntry` не существует в `lpszSubSection`, этот метод создаст ее.  
  
##  <a name="writestring"></a>CWinAppEx::WriteString  
 Строковые данные записи в реестр.  
  
```  
BOOL WriteString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszEntry`  
 Строка, содержащая имя раздела реестра.  
  
 [in] `lpszValue`  
 Для хранения данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `lpszEntry` Параметром является имя записи реестра, расположенный в разделе реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](#getregistrybase) и [CWinAppEx::SetRegistryBase](#setregistrybase) соответственно.  
  
 Если ключ, указанный параметром `lspzEntry` не существует, этот метод создаст ее.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CWinApp-класс](../../mfc/reference/cwinapp-class.md)   
 [Класс CMouseManager](../../mfc/reference/cmousemanager-class.md)   
 [Класс CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)   
 [Класс CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)   
 [Класс CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)

