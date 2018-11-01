---
title: Класс CMouseManager
ms.date: 11/04/2016
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
ms.openlocfilehash: b3c5104038e6d715977a211af5a535cc9a5d916f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498154"
---
# <a name="cmousemanager-class"></a>Класс CMouseManager

Позволяет пользователю связать различные команды с указанным [CView](../../mfc/reference/cview-class.md) объекта, когда пользователь дважды щелкает внутри представления.

## <a name="syntax"></a>Синтаксис

```
class CMouseManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMouseManager::AddView](#addview)|Добавляет `CView` объект **настройки** диалоговое окно. **Настройки** диалоговое окно позволяет пользователю связать двойным щелчком с помощью команды для каждого из перечисленных видов.|
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Возвращает команду, которая выполняется, когда пользователь дважды щелкает внутри указанного представления.|
|[CMouseManager::GetViewIconId](#getviewiconid)|Возвращает значок, связанный с идентификатором указанное представление.|
|[CMouseManager::GetViewIdByName](#getviewidbyname)|Возвращает идентификатор представления, связанные с именем указанное представление.|
|[CMouseManager::GetViewNames](#getviewnames)|Извлекает список имен всех добавленных представления.|
|[CMouseManager::LoadState](#loadstate)|Загружает `CMouseManager` состояния из реестра Windows.|
|[CMouseManager::SaveState](#savestate)|Записывает `CMouseManager` состояния в реестр Windows.|
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Связывает предоставленной команды и указанное представление.|

## <a name="remarks"></a>Примечания

`CMouseManager` Класс поддерживает коллекцию `CView` объектов. Каждое представление идентифицируется по имени и идентификатор. Эти представления отображаются в **настройки** диалоговое окно. Пользователь может изменить команду, которая связана с любого представления через **настройки** диалоговое окно. Связанная команда выполняется в том случае, когда пользователь дважды щелкает в этом представлении. Для этого с точки зрения программирования, необходимо обработать WM_LBUTTONDBLCLK message и call [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) функцию в коде для этого `CView` объекта...

Не следует создавать `CMouseManager` объект вручную. Создается платформой приложения. Он будет также будет удален автоматически, когда пользователь выходит из приложения. Чтобы получить указатель на диспетчер мыши для вашего приложения, вызовите [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxmousemanager.h

##  <a name="addview"></a>  CMouseManager::AddView

Регистрирует [CView](../../mfc/reference/cview-class.md) со [класс CMouseManager](../../mfc/reference/cmousemanager-class.md) для поддержки поведения пользовательского мыши.

```
BOOL AddView(
    int iViewId,
    UINT uiViewNameResId,
    UINT uiIconId = 0);

BOOL AddView(
    int iId,
    LPCTSTR lpszViewName,
    UINT uiIconId = 0);
```

### <a name="parameters"></a>Параметры

*iViewId*<br/>
[in] Код представления.

*uiViewNameResId*<br/>
[in] Идентификатор строки ресурса, который ссылается на имя представления.

*uiIconId*<br/>
[in] Значок код представления.

*iId*<br/>
[in] Код представления.

*lpszViewName*<br/>
[in] Имя представления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Чтобы обеспечить поддержку пользовательских мыши поведение, представление должно быть зарегистрировано `CMouseManager` объекта. Любой объект, производный от `CView` класса могут быть зарегистрированы с помощью диспетчера мыши. Строка и значок, связанный с представлением, отображаются в **мыши** вкладке **Настройка** диалоговое окно.

Он отвечает за программиста для создания и поддержки представления идентификаторов, таких как *iViewId* и *iId*.

Дополнительные сведения о том, как указать поведение пользовательских мыши см. в разделе [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md).

### <a name="example"></a>Пример

Следующий пример демонстрирует, как получить указатель на `CMouseManager` объекта с помощью `CWinAppEx::GetMouseManager` метод и `AddView` метод в `CMouseManager` класса. Этот фрагмент кода является частью [пример коллекции состояний](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

##  <a name="getviewdblclickcommand"></a>  CMouseManager::GetViewDblClickCommand

Возвращает команду, которая выполняется, когда пользователь дважды щелкает внутри указанного представления.

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>Параметры

*iId*<br/>
[in] Код представления.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды, если представление связан с помощью команды; в противном случае 0.

##  <a name="getviewiconid"></a>  CMouseManager::GetViewIconId

Получает значок, связанный с идентификатором представления.

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>Параметры

*iViewId*<br/>
[in] Код представления.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса значка в случае успешного выполнения; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод завершится ошибкой, если представление сначала не зарегистрирован с помощью [CMouseManager::AddView](#addview).

##  <a name="getviewidbyname"></a>  CMouseManager::GetViewIdByName

Извлекает идентификатор представления, связанные с именем представления.

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
[in] Имя представления.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор представления, если выполнение прошло успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод осуществляет через представления, зарегистрированные с помощью [CMouseManager::AddView](#addview).

##  <a name="getviewnames"></a>  CMouseManager::GetViewNames

Извлекает список имен всех зарегистрированных представления.

```
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Параметры

*listOfNames*<br/>
[out] Ссылку на `CStringList` объекта.

### <a name="remarks"></a>Примечания

Этот метод заполняет параметр `listOfNames` с именами всех представлений, зарегистрированные с помощью [CMouseManager::AddView](#addview).

##  <a name="loadstate"></a>  CMouseManager::LoadState

Загружает состояние [класс CMouseManager](../../mfc/reference/cmousemanager-class.md) из реестра.

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Путь реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Сведения о состоянии, загруженный из реестра содержит зарегистрированные представления идентификаторов представлений и связанные команды. Если параметр *lpszProfileName* имеет значение NULL, эта функция загружает `CMouseManager` данных из расположения по умолчанию реестра, контролируются [класс CWinAppEx](../../mfc/reference/cwinappex-class.md).

В большинстве случаев не нужно вызывать эту функцию напрямую. Он вызывается как часть процесса инициализации рабочей области. Дополнительные сведения о процессе инициализации рабочей области см. в разделе [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate).

##  <a name="savestate"></a>  CMouseManager::SaveState

Записывает состояние [класс CMouseManager](../../mfc/reference/cmousemanager-class.md) в реестр.

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Путь реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Сведения о состоянии, записанных в реестр, включает в себя все зарегистрированные представления, идентификаторы представление и связанные команды. Если параметр *lpszProfileName* имеет значение NULL, эта функция записывает `CMouseManager` данные в расположение по умолчанию реестра, контролируются [класс CWinAppEx](../../mfc/reference/cwinappex-class.md).

В большинстве случаев не нужно вызывать эту функцию напрямую. Он вызывается как часть процесса сериализации рабочей области. Дополнительные сведения о рабочей области процесса сериализации см. в разделе [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).

##  <a name="setcommandfordblclk"></a>  CMouseManager::SetCommandForDblClk

Связывает пользовательской команды с представлением, первой регистрации с помощью мыши manager.

```
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*iViewId*<br/>
[in] Идентификатор представления.

*uiCmd*<br/>
[in] Идентификатор команды.

### <a name="remarks"></a>Примечания

Чтобы связать пользовательскую команду с помощью представления, необходимо сначала зарегистрировать представление с помощью [CMouseManager::AddView](#addview). `AddView` Метод требует идентификатора представления в качестве входного параметра. После регистрации представления, можно вызвать `CMouseManager::SetCommandForDblClk` с тем же представления идентификатор входным параметром, который введен для `AddView`. После этого при двойном щелчке мыши в представлении зарегистрированных, приложение выполнит команду обозначается *uiCmd.* Для поддержки поведения пользовательского мыши, также необходимо будет настроить представление, зарегистрированных диспетчером мыши. Дополнительные сведения о поведении пользовательских мыши см. в разделе [Настройка мыши и клавиатуры](../keyboard-and-mouse-customization.md).

Если *uiCmd* имеет значение 0, указанное представление больше не будет связан с командой.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)

