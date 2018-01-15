---
title: "Класс CUserToolsManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CUserToolsManager [MFC], CUserToolsManager
- CUserToolsManager [MFC], CreateNewTool
- CUserToolsManager [MFC], FindTool
- CUserToolsManager [MFC], GetArgumentsMenuID
- CUserToolsManager [MFC], GetDefExt
- CUserToolsManager [MFC], GetFilter
- CUserToolsManager [MFC], GetInitialDirMenuID
- CUserToolsManager [MFC], GetMaxTools
- CUserToolsManager [MFC], GetToolsEntryCmd
- CUserToolsManager [MFC], GetUserTools
- CUserToolsManager [MFC], InvokeTool
- CUserToolsManager [MFC], IsUserToolCmd
- CUserToolsManager [MFC], LoadState
- CUserToolsManager [MFC], MoveToolDown
- CUserToolsManager [MFC], MoveToolUp
- CUserToolsManager [MFC], RemoveTool
- CUserToolsManager [MFC], SaveState
- CUserToolsManager [MFC], SetDefExt
- CUserToolsManager [MFC], SetFilter
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d92e0ffa11ea07331704bfcd91798c50c48dabac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cusertoolsmanager-class"></a>Класс CUserToolsManager
Поддерживает коллекцию объектов [CUserTool класс](../../mfc/reference/cusertool-class.md) объектов в приложении. Пользовательский инструмент — это пункт меню, который запускает внешнее приложение. Объект `CUserToolsManager` позволяет пользователю или разработчику добавить в приложение новые пользовательские инструменты. Он поддерживает выполнение команд, связанных со средствами пользователя, а также сохраняет сведения о пользовательских средствах в реестре Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CUserToolsManager : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Создает документ `CUserToolsManager`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](#createnewtool)|Создает новый пользовательский инструмент.|  
|[CUserToolsManager::FindTool](#findtool)|Возвращает указатель на `CMFCUserTool` объект, связанный с указанным идентификатором команды.|  
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|Возвращает идентификатор ресурса, который связан с **аргументы** меню **средства** вкладке **Настройка** диалоговое окно.|  
|[CUserToolsManager::GetDefExt](#getdefext)|Возвращает расширение по умолчанию, который **Открытие файла** диалоговое окно ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) используется в **команда** на **средства** вкладка **Настройка** диалоговое окно.|  
|[CUserToolsManager::GetFilter](#getfilter)|Возвращает фильтр файлов, **Открытие файла** диалоговое окно ( [класс CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладка **Настройка** диалоговое окно.|  
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|Возвращает идентификатор ресурса, который связан с **исходный каталог** меню **средства** вкладке **Настройка** диалоговое окно.|  
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Возвращает максимальное число средства пользователей, которые могут быть распределены в приложении.|  
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Возвращает идентификатор команды для средства пользователя местозаполнителя элемента меню.|  
|[CUserToolsManager::GetUserTools](#getusertools)|Возвращает ссылку на список средств пользователя.|  
|[CUserToolsManager::InvokeTool](#invoketool)|Выполняет приложение, связанное с помощью средства пользователь, имеющий указанный идентификатор команды.|  
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Определяет, является ли идентификатор команды связанную со средством пользователя.|  
|[CUserToolsManager::LoadState](#loadstate)|Загружает сведения о пользовательских средствах в реестре Windows.|  
|[CUserToolsManager::MoveToolDown](#movetooldown)|Перемещает средство указанного пользователя в списке средства пользователя.|  
|[CUserToolsManager::MoveToolUp](#movetoolup)|Перемещает средство указанного пользователя вверх в списке средства пользователя.|  
|[CUserToolsManager::RemoveTool](#removetool)|Удаляет указанного пользователя из приложения.|  
|[CUserToolsManager::SaveState](#savestate)|Хранит сведения о пользовательских средствах в реестре Windows.|  
|[CUserToolsManager::SetDefExt](#setdefext)|Указывает расширение по умолчанию, **Открытие файла** диалоговое окно ( [класс CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладка из **Настройка** диалоговое окно.|  
|[CUserToolsManager::SetFilter](#setfilter)|Задает файл, **Открытие файла** диалоговое окно ( [класс CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладка **Настройка** диалоговое окно.|  
  
## <a name="remarks"></a>Примечания  
 Для включения средства пользователя в приложение, необходимо выполнить следующее:  
  
 1. Зарезервировать пункта меню и связанная команда идентификатор пользователя в записи меню средства.  
  
 2. Зарезервировать идентификатор последовательные команды для каждого пользовательского средства, пользователь может определить в приложении.  
  
 3. Вызовите [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) метод и укажите следующие параметры: меню идентификатор команды, идентификатор команды средство первого пользователя и идентификатор последнего пользователя средство команды.  
  
 Должен быть только один глобальный `CUserToolsManager` объекта каждого приложения.  
  
 Пример средства пользователя разделе VisualStudioDemo образца проекта.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить ссылку на `CUserToolsManager` объекта и как создавать новые пользовательские инструменты. Этот фрагмент кода является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]  
  
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
 Указатель на только что созданного пользователя средства, или `NULL` если ряд средств пользователь превысил максимально. Возвращаемый тип совпадает со значением типа, передаваемый `CWinAppEx::EnableUserTools` как `pToolRTC` параметр.  
  
### <a name="remarks"></a>Примечания  
 Этот метод находит идентификатор первой команды меню в диапазон, указанный в вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) и назначает средство пользовательского этот код.  
  
 Метод завершается ошибкой, если число инструментов, достигло максимального. Это происходит, когда пользовательская назначаются все идентификаторы команд в пределах диапазона. Максимальное число средств можно получить, вызвав [CUserToolsManager::GetMaxTools](#getmaxtools). Вы можете получить доступ к списку средств, вызвав [CUserToolsManager::GetUserTools](#getusertools) метод.  
  
##  <a name="cusertoolsmanager"></a>CUserToolsManager::CUserToolsManager  
 Создает документ `CUserToolsManager`. Каждое приложение должно иметь максимум один диспетчер Сервис пользователя.  
  
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
 Целое число без знака, она используется в качестве заполнителя для идентификатор команды меню "Сервис" пользователя.  
  
 [in] `uiCmdFirst`  
 Идентификатор команды для первой команды средства для пользователя.  
  
 [in] `uiCmdLast`  
 Идентификатор команды для команды средство последнего пользователя.  
  
 [in] `pToolRTC`  
 Класс, [CUserToolsManager::CreateNewTool](#createnewtool) создает. С помощью этого класса можно использовать производным типом [CUserTool класса](../../mfc/reference/cusertool-class.md) вместо реализация по умолчанию.  
  
 [in] `uArgMenuID`  
 Идентификатор ресурса меню аргументы всплывающего меню.  
  
 [in] `uInitDirMenuID`  
 Идентификатор ресурса меню всплывающего меню исходный каталог.  
  
### <a name="remarks"></a>Примечания  
 Не вызывайте этот конструктор. Вместо этого необходимо вызвать [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) для включения пользовательских средств и вызова [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) для получения указателя на `CUserToolsManager`. Дополнительные сведения см. в разделе [определенные пользователем инструменты](../../mfc/user-defined-tools.md).  
  
##  <a name="findtool"></a>CUserToolsManager::FindTool  
 Возвращает указатель на [CUserTool класса](../../mfc/reference/cusertool-class.md) объект, связанный с указанным идентификатором команды.  
  
```  
CUserTool* FindTool(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
 Идентификатор команды меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [класса CUserTool](../../mfc/reference/cusertool-class.md) или `CUserTool`-производный объект, если успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Когда `FindTool` — успешно, возвращаемый тип совпадает со значением типа `pToolRTC` параметр [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getargumentsmenuid"></a>CUserToolsManager::GetArgumentsMenuID  
 Возвращает идентификатор ресурса, который связан с **аргументы** меню **средства** вкладке **Настройка** диалоговое окно.  
  
```  
UINT GetArgumentsMenuID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса меню.  
  
### <a name="remarks"></a>Примечания  
 `uArgMenuID` Параметр [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) указывает идентификатор ресурса.  
  
##  <a name="getdefext"></a>CUserToolsManager::GetDefExt  
 Возвращает расширение по умолчанию, который **Открытие файла** диалоговое окно ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) используется в **команда** на **средства** вкладка **Настройка** диалоговое окно.  
  
```  
const CString& GetDefExt() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `CString` объект, содержащий расширение.  
  
##  <a name="getfilter"></a>CUserToolsManager::GetFilter  
 Возвращает фильтр файлов, **Открытие файла** диалоговое окно ( [класс CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладка **Настройка** диалоговое окно.  
  
```  
const CString& GetFilter() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `CString` , содержащий фильтр.  
  
##  <a name="getinitialdirmenuid"></a>CUserToolsManager::GetInitialDirMenuID  
 Возвращает идентификатор ресурса, который связан с **исходный каталог** меню **средства** вкладке **Настройка** диалоговое окно.  
  
```  
UINT GetInitialDirMenuID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса меню.  
  
### <a name="remarks"></a>Примечания  
 Возвращенный идентификатор задан в `uInitDirMenuID` параметр [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="getmaxtools"></a>CUserToolsManager::GetMaxTools  
 Возвращает максимальное число средства пользователей, которые могут быть распределены в приложении.  
  
```  
int GetMaxTools() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное число средства пользователей, которые могут быть выделены.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для извлечения максимальное число средств, которые могут быть распределены в приложении. Этот номер является номером идентификаторы в диапазоне от `uiCmdFirst` через `uiCmdLast` параметры, которые вы передаете в [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="gettoolsentrycmd"></a>CUserToolsManager::GetToolsEntryCmd  
 Возвращает идентификатор команды для средства пользователя местозаполнителя элемента меню.  
  
```  
UINT GetToolsEntryCmd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды заполнитель.  
  
### <a name="remarks"></a>Примечания  
 Чтобы включить средства пользователя, следует вызвать [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). `uiCmdToolsDummy` Указывает идентификатор команды команды средства записи. Этот метод возвращает идентификатор средства записи команды. Везде, где этот идентификатор используется в меню, он не будет заменен список пользовательских средств в появившемся меню.  
  
##  <a name="getusertools"></a>CUserToolsManager::GetUserTools  
 Возвращает ссылку на список средств пользователя.  
  
```  
const CObList& GetUserTools() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константную ссылку [CObList класс](../../mfc/reference/coblist-class.md) , содержащий список средств пользователя.  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода для получения списка пользователей средств, предоставляемых [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) хранит объект. Объект типа представленного каждого пользовательского средства [класса CUserTool](../../mfc/reference/cusertool-class.md) или тип, производный от `CUserTool`. Тип определяется `pToolRTC` параметра при вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) , чтобы позволить средствам пользователя.  
  
##  <a name="invoketool"></a>CUserToolsManager::InvokeTool  
 Выполняет приложение, связанное с помощью средства пользователь, имеющий указанный идентификатор команды.  
  
```  
BOOL InvokeTool(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
 Идентификатором команды меню, связанных со средством пользователя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если команда, связанная со средством пользователя была выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода для выполнения приложения, связанного с пользователем средства, имеет идентификатор команды, заданные `uiCmdId`.  
  
##  <a name="isusertoolcmd"></a>CUserToolsManager::IsUserToolCmd  
 Определяет, является ли идентификатор команды связанную со средством пользователя.  
  
```  
BOOL IsUserToolCmd(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
 Идентификатор команды для элемента меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если идентификатор данной команды связана со средством пользователя; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод проверяет, является ли идентификатор данной команды диапазон Идентификаторов команд. Укажите диапазон, при вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) , чтобы позволить средствам пользователя.  
  
##  <a name="loadstate"></a>CUserToolsManager::LoadState  
 Загружает сведения о пользовательских средствах в реестре Windows.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь к разделу реестра Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если состояние был загружен успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод загружает состояние `CUserToolsManager` объекта из реестра Windows.  
  
 Как правило этот метод не вызывается напрямую. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) вызывает ее в процессе инициализации рабочей области.  
  
##  <a name="movetooldown"></a>CUserToolsManager::MoveToolDown  
 Перемещает средство указанного пользователя в списке средства пользователя.  
  
```  
BOOL MoveToolDown(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTool`  
 Указывает средство пользователя для перемещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если средство пользователя был перемещен вниз успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Метод завершается ошибкой, если средство, `pTool` указывает не во внутреннем списке или если средство является последним в списке.  
  
##  <a name="movetoolup"></a>CUserToolsManager::MoveToolUp  
 Перемещает средство указанного пользователя вверх в списке средства пользователя.  
  
```  
BOOL MoveToolUp(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTool`  
 Указывает средство пользователя для перемещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если средство пользователя была перемещена; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Метод завершается ошибкой, если средство, `pTool` указывает не во внутреннем списке или если средство является первым в списке средства.  
  
##  <a name="removetool"></a>CUserToolsManager::RemoveTool  
 Удаляет указанного пользователя из приложения.  
  
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
 Хранит сведения о пользовательских средствах в реестре Windows.  
  
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
  
 Обычно не требуется вызывать этот метод непосредственно, [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) вызывает ее автоматически в рамках процесса сериализации рабочей области приложения.  
  
##  <a name="setdefext"></a>CUserToolsManager::SetDefExt  
 Указывает расширение по умолчанию, **Открытие файла** диалоговое окно ( [класс CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладка из **Настройка** диалоговое окно.  
  
```  
void SetDefExt(const CString& strDefExt);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strDefExt`  
 Текстовая строка, содержащая расширение имени файла по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы задать расширение имени файла по умолчанию в **Открытие файла** диалоговое окно отображается, когда пользователь выбирает сопоставить со средствами пользователя приложения. Значение по умолчанию — «exe».  
  
##  <a name="setfilter"></a>CUserToolsManager::SetFilter  
 Задает файл, **Открытие файла** диалоговое окно ( [класс CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладка **Настройка** диалоговое окно.  
  
```  
void SetFilter(const CString& strFilter);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strFilter`  
 Задает фильтр.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)   
 [Класс CUserTool](../../mfc/reference/cusertool-class.md)
