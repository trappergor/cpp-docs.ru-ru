---
title: "Класс CUserToolsManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
dev_langs:
- C++
helpviewer_keywords:
- CUserToolsManager class
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
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
ms.openlocfilehash: 0b82adf0f9eba5ee334ada2c169546f27894c1dd
ms.lasthandoff: 02/24/2017

---
# <a name="cusertoolsmanager-class"></a>Класс CUserToolsManager
Поддерживает коллекцию [CUserTool класс](../../mfc/reference/cusertool-class.md) объектов в приложении. Пользовательский инструмент — это пункт меню, который запускает внешнее приложение. Объект `CUserToolsManager` позволяет пользователю или разработчику добавить в приложение новые пользовательские инструменты. Он поддерживает выполнение команд, связанных со средствами пользователя, а также сохраняет сведения о пользовательских средствах в реестре Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CUserToolsManager : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Создает документ `CUserToolsManager`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](#createnewtool)|Создает новый пользовательский инструмент.|  
|[CUserToolsManager::FindTool](#findtool)|Возвращает указатель на `CMFCUserTool` объект, связанный с идентификатором указанную команду.|  
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|Возвращает идентификатор ресурса, с которым связан **аргументы** меню **средства** вкладке **Настройка** диалоговое окно.|  
|[CUserToolsManager::GetDefExt](#getdefext)|Возвращает расширение по умолчанию, **Открытие файла** диалоговое окно ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) используется в **команда** на **средства** вкладке **Настройка** диалоговое окно.|  
|[CUserToolsManager::GetFilter](#getfilter)|Возвращает фильтр файлов, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) использует в **команда** на **средства** вкладке **Настройка** диалоговое окно.|  
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|Возвращает идентификатор ресурса, с которым связан **исходный каталог** меню **средства** вкладке **Настройка** диалоговое окно.|  
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Возвращает максимальное количество средства пользователей, которые могут быть распределены в приложении.|  
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Возвращает идентификатор команды прототипа элемента меню для пользователя средств.|  
|[CUserToolsManager::GetUserTools](#getusertools)|Возвращает ссылку на список средств пользователя.|  
|[CUserToolsManager::InvokeTool](#invoketool)|Выполняет приложения, связанного с пользователем средство, которое имеет идентификатор указанной команды.|  
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Определяет, является ли идентификатор команды сопоставлен пользовательский инструмент.|  
|[CUserToolsManager::LoadState](#loadstate)|Загружает сведения о пользовательских средствах в реестре Windows.|  
|[CUserToolsManager::MoveToolDown](#movetooldown)|Перемещает средство указанного пользователя в списке средства пользователя.|  
|[CUserToolsManager::MoveToolUp](#movetoolup)|Перемещает средство указанного пользователя вверх в списке средства пользователя.|  
|[CUserToolsManager::RemoveTool](#removetool)|Удаляет средство указанного пользователя из приложения.|  
|[CUserToolsManager::SaveState](#savestate)|Сохраняет сведения о пользовательских средствах в реестре Windows.|  
|[CUserToolsManager::SetDefExt](#setdefext)|Указывает расширение по умолчанию, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) использует в **команда** на **средства** вкладке **Настройка** диалоговое окно.|  
|[CUserToolsManager::SetFilter](#setfilter)|Задает файл, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) использует в **команда** на **средства** вкладке **Настройка** диалоговое окно.|  
  
## <a name="remarks"></a>Примечания  
 Для включения пользовательских средств в приложение, необходимо выполнить следующее:  
  
 1. Зарезервируйте пункта меню и идентификатор связанной команды меню средства пользователя в записи.  
  
 2. Зарезервируйте идентификатор последовательные команды, для каждого пользовательского средства, пользователь может определить в приложении.  
  
 3. Вызов [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) метод и укажите следующие параметры: меню идентификатор команды, идентификатор команды инструмента первого пользователя и идентификатор последнего пользователя средство команды.  
  
 Должен существовать только один глобальный `CUserToolsManager` объект каждого приложения.  
  
 Пример средства пользователя разделе VisualStudioDemo образца проекта.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как получить ссылку на `CUserToolsManager` объекта и как создавать новые пользовательские инструменты. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#38;](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUserToolsManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxusertoolsmanager.h  
  
##  <a name="createnewtool"></a>CUserToolsManager::CreateNewTool  
 Создает новый пользовательский инструмент.  
  
```  
CUserTool* CreateNewTool();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданного пользователя средства, или `NULL` Если количество пользовательских средств превысило максимальное. Возвращаемый тип является таким же, как тип, который передается в `CWinAppEx::EnableUserTools` как `pToolRTC` параметр.  
  
### <a name="remarks"></a>Примечания  
 Этот метод находит идентификатор первой команды меню в диапазоне, который передается в вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) и назначает средство пользователя этот код.  
  
 Метод завершается неудачей, если число инструментов, достигло максимального. Это происходит, когда пользовательская назначаются все идентификаторы команд в пределах диапазона. Максимальное число средств можно получить, вызвав [CUserToolsManager::GetMaxTools](#getmaxtools). Вы можете получить доступ к списку средств, вызвав [CUserToolsManager::GetUserTools](#getusertools) метод.  
  
##  <a name="cusertoolsmanager"></a>CUserToolsManager::CUserToolsManager  
 Создает документ `CUserToolsManager`. Каждое приложение должно иметь более одного средства управляющего.  
  
```  
CUserToolsManager();

 
CUserToolsManager(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID=0,  
    UINT uInitDirMenuID=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdToolsDummy`  
 Целое число без знака, она используется в качестве заполнителя для идентификатор команды меню средства пользователя.  
  
 [in] `uiCmdFirst`  
 Идентификатор команды для команды средства первого пользователя.  
  
 [in] `uiCmdLast`  
 Идентификатор команды для команды средства последнего пользователя.  
  
 [in] `pToolRTC`  
 Класс, [CUserToolsManager::CreateNewTool](#createnewtool) создает. С помощью этого класса можно использовать производный тип [CUserTool класса](../../mfc/reference/cusertool-class.md) вместо реализации по умолчанию.  
  
 [in] `uArgMenuID`  
 Идентификатор ресурса меню аргументы всплывающее меню.  
  
 [in] `uInitDirMenuID`  
 Идентификатор ресурса меню всплывающее меню исходный каталог.  
  
### <a name="remarks"></a>Примечания  
 Не следует вызывать этот конструктор. Вместо этого необходимо вызвать [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) для включения пользовательских средств и вызов [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) может получить указатель на `CUserToolsManager`. Дополнительные сведения см. в разделе [пользовательские средства](../../mfc/user-defined-tools.md).  
  
##  <a name="findtool"></a>CUserToolsManager::FindTool  
 Возвращает указатель на [CUserTool класс](../../mfc/reference/cusertool-class.md) объекта, связанного с идентификатором указанную команду.  
  
```  
CUserTool* FindTool(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
 Идентификатор команды меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [класса CUserTool](../../mfc/reference/cusertool-class.md) или `CUserTool`-производного объекта, если успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Когда `FindTool` — успешно, возвращаемый тип является таким же, как тип `pToolRTC` параметр [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getargumentsmenuid"></a>CUserToolsManager::GetArgumentsMenuID  
 Возвращает идентификатор ресурса, с которым связан **аргументы** меню **средства** вкладке **Настройка** диалоговое окно.  
  
```  
UINT GetArgumentsMenuID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса меню.  
  
### <a name="remarks"></a>Примечания  
 `uArgMenuID` Параметр [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) указывает идентификатор ресурса.  
  
##  <a name="getdefext"></a>CUserToolsManager::GetDefExt  
 Возвращает расширение по умолчанию, **Открытие файла** диалоговое окно ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) используется в **команда** на **средства** вкладке **Настройка** диалоговое окно.  
  
```  
const CString& GetDefExt() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `CString` объект, содержащий расширение.  
  
##  <a name="getfilter"></a>CUserToolsManager::GetFilter  
 Возвращает фильтр файлов, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) использует в **команда** на **средства** вкладке **Настройка** диалоговое окно.  
  
```  
const CString& GetFilter() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `CString` объект, содержащий фильтр.  
  
##  <a name="getinitialdirmenuid"></a>CUserToolsManager::GetInitialDirMenuID  
 Возвращает идентификатор ресурса, с которым связан **исходный каталог** меню **средства** вкладке **Настройка** диалоговое окно.  
  
```  
UINT GetInitialDirMenuID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса меню.  
  
### <a name="remarks"></a>Примечания  
 Возвращенный идентификатор указывается в `uInitDirMenuID` параметр [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getmaxtools"></a>CUserToolsManager::GetMaxTools  
 Возвращает максимальное количество средства пользователей, которые могут быть распределены в приложении.  
  
```  
int GetMaxTools() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное число пользователей средства, которые могут быть выделены.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы получить максимальное количество средств, которые могут быть распределены в приложении. Это число представляет количество идентификаторов в диапазоне от `uiCmdFirst` через `uiCmdLast` параметры, передаваемые [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="gettoolsentrycmd"></a>CUserToolsManager::GetToolsEntryCmd  
 Возвращает идентификатор команды прототипа элемента меню для пользователя средств.  
  
```  
UINT GetToolsEntryCmd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды заполнитель.  
  
### <a name="remarks"></a>Примечания  
 Чтобы включить средства пользователя, следует вызвать [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). `uiCmdToolsDummy` Указывает идентификатор команды команды средства записи. Этот метод возвращает идентификатор команды средства записи Везде, где этот идентификатор используется в меню, оно будет заменено список пользовательских средств в появившемся меню.  
  
##  <a name="getusertools"></a>CUserToolsManager::GetUserTools  
 Возвращает ссылку на список средств пользователя.  
  
```  
const CObList& GetUserTools() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константную ссылку [CObList класс](../../mfc/reference/coblist-class.md) , содержащий список пользовательских средств.  
  
### <a name="remarks"></a>Примечания  
 Этот метод, чтобы получить список пользователей средства, вызова [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) поддерживает объект. Каждое средство пользователя, представленного объекта типа [класса CUserTool](../../mfc/reference/cusertool-class.md) или тип, производный от `CUserTool`. Тип определяется `pToolRTC` параметра при вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) для включения пользовательских средств.  
  
##  <a name="invoketool"></a>CUserToolsManager::InvokeTool  
 Выполняет приложения, связанного с пользователем средство, которое имеет идентификатор указанной команды.  
  
```  
BOOL InvokeTool(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
 Идентификатором команды меню, связанные со средством пользователя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если команда, связанная со средством пользователя была выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод, чтобы выполнить приложение, связанное с пользователем средства, вызова имеет идентификатор команды, заданные `uiCmdId`.  
  
##  <a name="isusertoolcmd"></a>CUserToolsManager::IsUserToolCmd  
 Определяет, является ли идентификатор команды сопоставлен пользовательский инструмент.  
  
```  
BOOL IsUserToolCmd(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
 Идентификатор команды элемента меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если идентификатор данной команды связана со средством пользователя; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод проверяет, является ли идентификатор данной команды диапазон Идентификаторов команд. Укажите диапазон, при вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) для включения пользовательских средств.  
  
##  <a name="loadstate"></a>CUserToolsManager::LoadState  
 Загружает сведения о пользовательских средствах в реестре Windows.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь реестра Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если состояние был загружен успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод загружает состояние `CUserToolsManager` объекта из реестра Windows.  
  
 Как правило этот метод не вызывается напрямую. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) вызывает его как часть процесса инициализации рабочей области.  
  
##  <a name="movetooldown"></a>CUserToolsManager::MoveToolDown  
 Перемещает средство указанного пользователя в списке средства пользователя.  
  
```  
BOOL MoveToolDown(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTool`  
 Указывает пользователя средство для перемещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если средство пользователя была перемещена; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Метод завершается неудачей, если средство, `pTool` указывает не во внутреннем списке или если средство является последним в списке.  
  
##  <a name="movetoolup"></a>CUserToolsManager::MoveToolUp  
 Перемещает средство указанного пользователя вверх в списке средства пользователя.  
  
```  
BOOL MoveToolUp(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTool`  
 Указывает пользователя средство для перемещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если средство пользователя была перемещена; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Метод завершается неудачей, если средство, `pTool` указывает не во внутреннем списке или если средство средство первым в списке.  
  
##  <a name="removetool"></a>CUserToolsManager::RemoveTool  
 Удаляет средство указанного пользователя из приложения.  
  
```  
BOOL RemoveTool(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pTool`  
 Указатель на пользовательский инструмент для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если средство успешно удален. В противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если средство успешно удален, этот метод удаляет `pTool`.  
  
##  <a name="savestate"></a>CUserToolsManager::SaveState  
 Сохраняет сведения о пользовательских средствах в реестре Windows.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь к разделу реестра Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если состояние сохранена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Метод сохраняет текущее состояние `CUserToolsManager` объекта в реестре Windows.  
  
 Обычно не требуется вызывать этот метод непосредственно, [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) вызывает его автоматически как часть процесса сериализации рабочей области приложения.  
  
##  <a name="setdefext"></a>CUserToolsManager::SetDefExt  
 Указывает расширение по умолчанию, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) использует в **команда** на **средства** вкладке **Настройка** диалоговое окно.  
  
```  
void SetDefExt(const CString& strDefExt);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strDefExt`  
 Текстовая строка, содержащая расширение имени файла по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода позволяет указать расширение имени файла по умолчанию в **Открытие файла** диалоговое окно отображается, когда пользователь выбирает сопоставить со средствами пользователя приложения. Значение по умолчанию — «exe».  
  
##  <a name="setfilter"></a>CUserToolsManager::SetFilter  
 Задает файл, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) использует в **команда** на **средства** вкладке **Настройка** диалоговое окно.  
  
```  
void SetFilter(const CString& strFilter);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strFilter`  
 Задает фильтр.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [Класс CUserTool](../../mfc/reference/cusertool-class.md)

