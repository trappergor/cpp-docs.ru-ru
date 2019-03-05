---
title: Класс CUserToolsManager
ms.date: 11/04/2016
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
ms.openlocfilehash: 7fa2f0bc5717c7481b4ed415e89fbb0cc8df0ffc
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289368"
---
# <a name="cusertoolsmanager-class"></a>Класс CUserToolsManager

Поддерживает коллекцию объектов [класс CUserTool](../../mfc/reference/cusertool-class.md) объектов в приложении. Пользовательский инструмент — это пункт меню, который запускает внешнее приложение. Объект `CUserToolsManager` позволяет пользователю или разработчику добавить в приложение новые пользовательские инструменты. Он поддерживает выполнение команд, связанных со средствами пользователя, а также сохраняет сведения о пользовательских средствах в реестре Windows.

## <a name="syntax"></a>Синтаксис

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Создает документ `CUserToolsManager`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CUserToolsManager::CreateNewTool](#createnewtool)|Создает новый пользовательский инструмент.|
|[CUserToolsManager::FindTool](#findtool)|Возвращает указатель на `CMFCUserTool` объект, связанный с указанным идентификатором команды.|
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|Возвращает идентификатор ресурса, с которым связан **аргументы** меню **средства** вкладке **Настройка** диалоговое окно.|
|[CUserToolsManager::GetDefExt](#getdefext)|Возвращает расширение по умолчанию, который **Открытие файла** диалоговое окно ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) используется в **команда** на **средства** вкладке **Настройка** диалоговое окно.|
|[CUserToolsManager::GetFilter](#getfilter)|Возвращает фильтр файлов, который **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладке **Настройка** диалоговое окно.|
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|Возвращает идентификатор ресурса, с которым связан **исходный каталог** меню **средства** вкладке **Настройка** диалоговое окно.|
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Возвращает максимальное число средства пользователя, которое может быть выделено в приложении.|
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Возвращает идентификатор команды для средства пользователя местозаполнителя элемента меню.|
|[CUserToolsManager::GetUserTools](#getusertools)|Возвращает ссылку на список средств пользователя.|
|[CUserToolsManager::InvokeTool](#invoketool)|Выполняет приложение, связанное с помощью средства пользователя с указанным идентификатором команды.|
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Определяет, связан ли идентификатор команды с пользовательский инструмент.|
|[CUserToolsManager::LoadState](#loadstate)|Загружает сведения о пользовательских средствах в реестре Windows.|
|[CUserToolsManager::MoveToolDown](#movetooldown)|Перемещает средство указанного пользователя в списке средства пользователя.|
|[CUserToolsManager::MoveToolUp](#movetoolup)|Перемещает средство указанного пользователя вверх в списке средства пользователя.|
|[CUserToolsManager::RemoveTool](#removetool)|Удаляет инструмент указанного пользователя из приложения.|
|[CUserToolsManager::SaveState](#savestate)|Хранит сведения о пользовательских средствах в реестре Windows.|
|[CUserToolsManager::SetDefExt](#setdefext)|Указывает расширение, по умолчанию, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладку из **Настройка** диалоговое окно.|
|[CUserToolsManager::SetFilter](#setfilter)|Задает файл, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладке **Настройка** диалоговое окно.|

## <a name="remarks"></a>Примечания

Чтобы включить средства пользователя в приложение, необходимо следующее:

1. Зарезервируйте пункта меню и идентификатор пользователя в записи меню средства связанная команда.

2. Зарезервируйте идентификатор последовательные команды для каждого пользовательского средства, которое пользователь может определить в приложении.

3. Вызовите [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) метод и указать следующие параметры: меню идентификатор команды, идентификатор команды инструмента первого пользователя и идентификатор последнего пользователя средство команды.

Должен быть только один глобальный `CUserToolsManager` объект каждого приложения.

Пример средства пользователя см. в разделе VisualStudioDemo примера проекта.

## <a name="example"></a>Пример

Следующий пример демонстрирует, как получить ссылку на `CUserToolsManager` объекта и как создавать новые пользовательские инструменты. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxusertoolsmanager.h

##  <a name="createnewtool"></a>  CUserToolsManager::CreateNewTool

Создает новый пользовательский инструмент.

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданного пользователя средства, или значение NULL, если число средства пользователя превышает максимальное. Возвращаемый тип совпадает со значением типа, который передается `CWinAppEx::EnableUserTools` как *pToolRTC* параметра.

### <a name="remarks"></a>Примечания

Этот метод находит идентификатор первой команды меню в диапазоне, который передается в вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) и назначает средства пользовательской этот код.

Метод завершается неудачей, если число инструментов достигло максимума. Это происходит, когда все идентификаторы команд в пределах диапазона назначенных средства пользователя. Максимальное число средств можно получить, вызвав [CUserToolsManager::GetMaxTools](#getmaxtools). Вы можете получить доступ к списку средств, вызвав [CUserToolsManager::GetUserTools](#getusertools) метод.

##  <a name="cusertoolsmanager"></a>  CUserToolsManager::CUserToolsManager

Создает документ `CUserToolsManager`. Каждое приложение должно иметь не больше одного руководителя средства пользователя.

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

*uiCmdToolsDummy*<br/>
[in] Целое число без знака, она используется в качестве заполнителя для идентификатор команды меню "Сервис" пользователя.

*uiCmdFirst*<br/>
[in] Идентификатор команды для команды средство первого пользователя.

*uiCmdLast*<br/>
[in] Идентификатор команды для команды средство последнего пользователя.

*pToolRTC*<br/>
[in] Класс, [CUserToolsManager::CreateNewTool](#createnewtool) создает. С помощью этого класса, можно использовать производным типом класса [класс CUserTool](../../mfc/reference/cusertool-class.md) вместо реализации по умолчанию.

*uArgMenuID*<br/>
[in] Идентификатор ресурса меню аргументы во всплывающем меню.

*uInitDirMenuID*<br/>
[in] Идентификатор ресурса меню во всплывающем меню исходный каталог.

### <a name="remarks"></a>Примечания

Не следует вызывать этот конструктор. Вместо этого необходимо вызвать [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) включить инструменты пользователя и вызовите [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) получить указатель на `CUserToolsManager`. Дополнительные сведения см. в разделе [определенные пользователем инструменты](../../mfc/user-defined-tools.md).

##  <a name="findtool"></a>  CUserToolsManager::FindTool

Возвращает указатель на [класс CUserTool](../../mfc/reference/cusertool-class.md) объект, связанный с указанным идентификатором команды.

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>Параметры

*uiCmdId*<br/>
[in] Идентификатор команды меню.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [класс CUserTool](../../mfc/reference/cusertool-class.md) или `CUserTool`-производного объекта, если успешно; в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Когда `FindTool` — успешно, то возвращаемый тип совпадает со значением типа *pToolRTC* параметр [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

##  <a name="getargumentsmenuid"></a>  CUserToolsManager::GetArgumentsMenuID

Возвращает идентификатор ресурса, с которым связан **аргументы** меню **средства** вкладке **Настройка** диалоговое окно.

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса меню.

### <a name="remarks"></a>Примечания

*UArgMenuID* параметр [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) указывает идентификатор ресурса.

##  <a name="getdefext"></a>  CUserToolsManager::GetDefExt

Возвращает расширение по умолчанию, который **Открытие файла** диалоговое окно ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) используется в **команда** на **средства** вкладке **Настройка** диалоговое окно.

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылку на `CString` объект, содержащий его модуль.

##  <a name="getfilter"></a>  CUserToolsManager::GetFilter

Возвращает фильтр файлов, который **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладке **Настройка** диалоговое окно.

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылку на `CString` , содержащий фильтр.

##  <a name="getinitialdirmenuid"></a>  CUserToolsManager::GetInitialDirMenuID

Возвращает идентификатор ресурса, с которым связан **исходный каталог** меню **средства** вкладке **Настройка** диалоговое окно.

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса меню.

### <a name="remarks"></a>Примечания

Возвращенный идентификатор указывается в *uInitDirMenuID* параметр [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

##  <a name="getmaxtools"></a>  CUserToolsManager::GetMaxTools

Возвращает максимальное число средства пользователя, которое может быть выделено в приложении.

```
int GetMaxTools() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число пользователей средств, которые могут быть выделены.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить максимальное количество средств, которые могут быть распределены в приложении. Это число является количество идентификаторов в диапазоне от *uiCmdFirst* через *uiCmdLast* параметров, которые можно передать [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

##  <a name="gettoolsentrycmd"></a>  CUserToolsManager::GetToolsEntryCmd

Возвращает идентификатор команды для средства пользователя местозаполнителя элемента меню.

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды заполнитель.

### <a name="remarks"></a>Примечания

Чтобы включить средства пользователя, вызовите [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). *UiCmdToolsDummy* параметр указывает идентификатор команды команды средства записи. Этот метод возвращает идентификатор средства записи команды. Везде, где этот идентификатор используется в меню, он заменяется средства пользователя из списка, когда меню отображается.

##  <a name="getusertools"></a>  CUserToolsManager::GetUserTools

Возвращает ссылку на список средств пользователя.

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константную ссылку на [класс CObList](../../mfc/reference/coblist-class.md) , содержащий список пользовательских средств.

### <a name="remarks"></a>Примечания

Этот метод, чтобы получить список пользователей средств, предоставляемых вызов [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) объект удерживает. Объект типа представленного каждого пользовательского средства [класс CUserTool](../../mfc/reference/cusertool-class.md) или тип, производный от `CUserTool`. Тип задается *pToolRTC* параметра при вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) для включения средства пользователя.

##  <a name="invoketool"></a>  CUserToolsManager::InvokeTool

Выполняет приложение, связанное с помощью средства пользователя с указанным идентификатором команды.

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>Параметры

*uiCmdId*<br/>
[in] Идентификатор команды меню, связанный со средством пользователя.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если команда, связанная со средством пользователя была выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов, этот метод для выполнения приложения, связанного с пользователем инструмент, который имеет идентификатор команды, заданные *uiCmdId*.

##  <a name="isusertoolcmd"></a>  CUserToolsManager::IsUserToolCmd

Определяет, связан ли идентификатор команды с пользовательский инструмент.

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>Параметры

*uiCmdId*<br/>
[in] Идентификатор команды для пункта меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если для определенной команды идентификатор связан со средством пользователя; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод проверяет, является ли заданным Идентификатором команды в диапазоне идентификатор команды. Необходимо указать диапазон, при вызове [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) для включения средства пользователя.

##  <a name="loadstate"></a>  CUserToolsManager::LoadState

Загружает сведения о пользовательских средствах в реестре Windows.

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Путь к разделу реестра Windows.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если состояние загружен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод загружает состояние `CUserToolsManager` объекта из реестра Windows.

Как правило этот метод не вызывается напрямую. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) вызывает ее в ходе процесса инициализации рабочей области.

##  <a name="movetooldown"></a>  CUserToolsManager::MoveToolDown

Перемещает средство указанного пользователя в списке средства пользователя.

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>Параметры

*pTool*<br/>
[in] Указывает пользователя средство для перемещения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если средство пользователя был перемещен вниз успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Метод завершается неудачей, если средство, *pTool* указывает не во внутреннем списке или если инструмент был последним в списке.

##  <a name="movetoolup"></a>  CUserToolsManager::MoveToolUp

Перемещает средство указанного пользователя вверх в списке средства пользователя.

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>Параметры

*pTool*<br/>
[in] Указывает пользователя средство для перемещения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если средство пользователя была перемещена; в противном случае 0.

### <a name="remarks"></a>Примечания

Метод завершается неудачей, если средство, *pTool* параметр указывает, не во внутреннем списке или если инструмент был первый элемент в списке средства.

##  <a name="removetool"></a>  CUserToolsManager::RemoveTool

Удаляет инструмент указанного пользователя из приложения.

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>Параметры

*pTool*<br/>
[in, out] Указатель на пользовательский инструмент для удаления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если инструмент успешно удален. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если инструмент успешно удален, этот метод удаляет *pTool*.

##  <a name="savestate"></a>  CUserToolsManager::SaveState

Хранит сведения о пользовательских средствах в реестре Windows.

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Путь к разделу реестра Windows.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если состояние было сохранено успешно. в противном случае 0.

### <a name="remarks"></a>Примечания

Метод сохраняет текущее состояние `CUserToolsManager` объекта в реестре Windows.

Как правило, не нужно вызывать этот метод напрямую, [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) вызывает его автоматически как часть процесса сериализации рабочей области приложения.

##  <a name="setdefext"></a>  CUserToolsManager::SetDefExt

Указывает расширение, по умолчанию, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладку из **Настройка** диалоговое окно.

```
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>Параметры

*strDefExt*<br/>
[in] Текстовая строка, содержащая расширение имени файла по умолчанию.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы указать расширение имени файла по умолчанию в **Открытие файла** диалоговое окно, которое отображается при выборе пользователем приложения должен быть сопоставлен средства пользовательской. Значение по умолчанию — «exe».

##  <a name="setfilter"></a>  CUserToolsManager::SetFilter

Задает файл, **Открытие файла** диалоговое окно ( [класса CFileDialog](../../mfc/reference/cfiledialog-class.md)) используется в **команда** на **средства** вкладке **Настройка** диалоговое окно.

```
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>Параметры

*strFilter*<br/>
[in] Задает фильтр.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[Класс CUserTool](../../mfc/reference/cusertool-class.md)
