---
title: Класс CContextMenuManager
ms.date: 11/04/2016
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
ms.openlocfilehash: c8a51a33c69b09d0ecd61520b5f1c9ff18c290a0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779798"
---
# <a name="ccontextmenumanager-class"></a>Класс CContextMenuManager

`CContextMenuManager` Управляет контекстные меню, также известный как контекстные меню.

## <a name="syntax"></a>Синтаксис

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Создает объект `CContextMenuManager`.|
|`CContextMenuManager::~CContextMenuManager`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CContextMenuManager::AddMenu](#addmenu)|Добавляет новый контекстное меню.|
|[CContextMenuManager::GetMenuById](#getmenubyid)|Возвращает дескриптор для меню, связанное с идентификатором предоставленного ресурса.|
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Возвращает дескриптор для меню, которое соответствует имени предоставленного меню.|
|[CContextMenuManager::GetMenuNames](#getmenunames)|Возвращает список имен меню.|
|[CContextMenuManager::LoadState](#loadstate)|Загружает контекстных меню, хранящихся в реестре Windows.|
|[CContextMenuManager::ResetState](#resetstate)|Очищает контекстных меню, из меню диспетчера контекста.|
|[CContextMenuManager::SaveState](#savestate)|Сохраняет контекстных меню в реестр Windows.|
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Элементы управления ли `CContextMenuManager` закрывает active контекстное меню, при отображении новой контекстное меню.|
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Отображает указанное контекстное меню.|
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Отображает указанное контекстное меню. Возвращает индекс команды меню.|

## <a name="remarks"></a>Примечания

`CContextMenuManager` Управляет контекстных меню и гарантирует, что они имеют согласованного внешнего вида.

Не следует создавать `CContextMenuManager` объект вручную. Платформа приложения создает `CContextMenuManager` объекта. Тем не менее, следует вызывать [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) при инициализации приложения. После инициализации диспетчера контекста, используйте метод [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) получить указатель на диспетчер контекста для вашего приложения.

Можно создать контекстное меню во время выполнения путем вызова `AddMenu`. Если вы хотите Показать меню без получения первых входных данных пользователя, вызовите `ShowPopupMenu`. `TrackPopupMenu` используется, если вы хотите создать меню и ожидает действий пользователя. `TrackPopupMenu` Возвращает индекс выбранной команды или 0, если пользователь завершил работу без выбора элементов.

`CContextMenuManager` Можно также сохранять и загружать свое состояние в реестр Windows.

## <a name="example"></a>Пример

Следующий пример демонстрирует добавить меню `CContextMenuManager` , а также не удается закрыть активное всплывающее меню при `CContextMenuManager` объекта отобразится новое всплывающее меню. Этот фрагмент кода является частью [пример пользовательские страницы](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxcontextmenumanager.h

##  <a name="addmenu"></a>  CContextMenuManager::AddMenu

Добавляет новый контекстное меню для [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
BOOL AddMenu(
    UINT uiMenuNameResId,
    UINT uiMenuResId);

BOOL AddMenu(
    LPCTSTR lpszName,
    UINT uiMenuResId);
```

### <a name="parameters"></a>Параметры

*uiMenuNameResId*<br/>
[in] Идентификатор ресурса для строка, содержащая имя нового меню.

*uiMenuResId*<br/>
[in] Идентификатор ресурса меню.

*lpszName*<br/>
[in] Строка, содержащая имя нового меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод был выполнен успешно; 0, если происходит сбой метода.

### <a name="remarks"></a>Примечания

Этот метод завершается ошибкой, если *uiMenuResId* недопустим или если другого меню с таким именем уже присутствует в `CContextMenuManager`.

##  <a name="ccontextmenumanager"></a>  CContextMenuManager::CContextMenuManager

Создает [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) объекта.

```
CContextMenuManager();
```

### <a name="remarks"></a>Примечания

В большинстве случаев не следует создавать `CContextMenuManager` вручную. Платформа приложения создает `CContextMenuManager` объекта. Следует вызывать [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) во время инициализации приложения. Чтобы получить указатель на диспетчер контекста, вызовите [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).

##  <a name="getmenubyid"></a>  CContextMenuManager::GetMenuById

Возвращает дескриптор для меню, связанное с идентификатором определенного ресурса.

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>Параметры

*nMenuResId*<br/>
[in] Идентификатор ресурса для меню.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор соответствующие пункты меню или `NULL` Если меню не найден.

##  <a name="getmenubyname"></a>  CContextMenuManager::GetMenuByName

Возвращает дескриптор для конкретного меню.

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
[in] Строка, содержащая имя меню, для извлечения.

*puiOrigResID*<br/>
[out] Указатель на целое число без знака. Этот параметр содержит идентификатор ресурса указанное меню, если найден.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для меню, которое совпадает с именем, указанным *lpszName*. Значение NULL, если меню не вызывается *lpszName*.

### <a name="remarks"></a>Примечания

Если этот метод находит меню, которое соответствует *lpszName*, `GetMenuByName` хранится идентификатор ресурса меню в параметре *puiOrigResID*.

##  <a name="getmenunames"></a>  CContextMenuManager::GetMenuNames

Возвращает список имен меню, добавляемые [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Параметры

*listOfNames*<br/>
[out] Ссылку на [CStringList](../../mfc/reference/cstringlist-class.md) параметра. Этот метод записывает список имен меню к данному параметру.

##  <a name="loadstate"></a>  CContextMenuManager::LoadState

Загружает сведения, связанные с [класс CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) из реестра Windows.

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Строка, содержащая относительный путь раздела реестра.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

*LpszProfileName* параметр не абсолютный путь для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.

Используйте метод [CContextMenuManager::SaveState](#savestate) для сохранения контекстных меню в реестр.

##  <a name="resetstate"></a>  CContextMenuManager::ResetState

Удаляет все элементы из контекстных меню, связанный с [класс CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; Значение FALSE, если происходит сбой.

### <a name="remarks"></a>Примечания

Этот метод очищает всплывающих меню и удаляет их из `CContextMenuManager`.

##  <a name="savestate"></a>  CContextMenuManager::SaveState

Сохраняет сведения, связанные с [класс CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) в реестр Windows.

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Строка, содержащая относительный путь раздела реестра.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

*LpszProfileName* параметр не абсолютный путь для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для вашего приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.

Используйте метод [CContextMenuManager::LoadState](#loadstate) загрузить контекстных меню из реестра.

##  <a name="setdontcloseactivemenu"></a>  CContextMenuManager::SetDontCloseActiveMenu

Элементы управления ли [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) закрывает активное всплывающее меню при его отображении нового всплывающего меню.

```
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

*bSet*<br/>
[in] Логический параметр, указывающее, следует ли закрыть активное всплывающее меню. Значение TRUE указывает, что не закрывается активное всплывающее меню. Значение FALSE указывает, что активное всплывающее меню закрыто.

### <a name="remarks"></a>Примечания

По умолчанию `CContextMenuManager` закрывает активное всплывающее меню.

##  <a name="showpopupmenu"></a>  CContextMenuManager::ShowPopupMenu

Отображает указанное контекстное меню.

```
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bRightAlign = FALSE);

virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bAutoDestroy = TRUE,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>Параметры

*uiMenuResId*<br/>
[in] Идентификатор ресурса меню, которое будет отображаться этот метод.

*x*<br/>
[in] Горизонтальное смещение для контекстного меню в координатах клиентской области окна.

*y*<br/>
[in] Вертикальное смещение для контекстного меню в координатах клиентской области окна

*pWndOwner*<br/>
[in] Указатель на родительское окно в контекстном меню.

*bOwnMessage*<br/>
[in] Логический параметр, который указывает способ маршрутизации сообщений. Если *bOwnMessage* является FALSE "," стандартный MFC используется маршрут. В противном случае *pWndOwner* получает сообщения.

*hmenuPopup*<br/>
[in] Дескриптор меню, которое будет отображаться этот метод.

*bAutoDestroy*<br/>
[in] Логический параметр, который указывает, будет ли автоматически уничтожается меню.

*bRightAlign*<br/>
[in] Логический параметр, который указывает способ выравнивания элементов меню. Если *bRightAlign* имеет значение TRUE, меню по правому краю для порядок чтения справа налево.

### <a name="return-value"></a>Возвращаемое значение

По первой перегрузке метода возвращает ненулевое значение, если метод успешно; показано меню в противном случае 0. Вторая перегрузка метода возвращает указатель на [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) , если в контекстном меню отображаются правильно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Этот метод похож на метод [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) в том, что оба метода отображения контекстного меню. Тем не менее `TrackPopupMenu` возвращает индекс команды меню.

Если параметр *bAutoDestroy* имеет значение FALSE, необходимо вручную вызвать наследуемого `DestroyMenu` метод для освобождения ресурсов памяти. Реализация по умолчанию `ShowPopupMenu` , не используйте параметр *bAutoDestroy*. Он предоставляется для использования в будущем или для пользовательских классов, производных от `CContextMenuManager` класса.

##  <a name="trackpopupmenu"></a>  CContextMenuManager::TrackPopupMenu

Отображает указанное контекстное меню и возвращает индекс команды выбранного контекстного меню.

```
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>Параметры

*hmenuPopup*<br/>
[in] Дескриптор, этот метод отображает контекстное меню.

*x*<br/>
[in] Горизонтальное смещение для контекстного меню в координатах клиентской области окна.

*y*<br/>
[in] Размер смещения по вертикали для контекстного меню в координатах клиентской области окна.

*pWndOwner*<br/>
[in] Указатель на родительское окно в контекстном меню.

*bRightAlign*<br/>
[in] Логический параметр, который указывает способ выравнивания элементов меню. Если *bRightAlign* имеет значение TRUE, меню по правому краю для порядок чтения справа налево. Если *bRightAlign* имеет значение FALSE, меню по левому краю для порядок чтения слева направо.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды меню, команды, когда пользователь нажимает; 0, если пользователь закрывает контекстное меню без выбора команды меню.

### <a name="remarks"></a>Примечания

Этот метод работает как модальное вызов отображения контекстного меню. Приложение не будет продолжать следующую строку в коде, пока пользователь закрывает контекстное меню или выбирает команду. Является альтернативным методом, можно использовать для отображения контекстного меню [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Этот метод не является модальным вызовом и не вернет идентификатор выбранной команды.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
