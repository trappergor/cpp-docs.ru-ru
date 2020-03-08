---
title: Класс Кконтекстменуманажер
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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78868994"
---
# <a name="ccontextmenumanager-class"></a>Класс Кконтекстменуманажер

Объект `CContextMenuManager` управляет контекстными меню, также известными как контекстные меню.

## <a name="syntax"></a>Синтаксис

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кконтекстменуманажер:: Кконтекстменуманажер](#ccontextmenumanager)|Формирует объект `CContextMenuManager`.|
|`CContextMenuManager::~CContextMenuManager`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кконтекстменуманажер:: ДобавитьМеню](#addmenu)|Добавляет новое контекстное меню.|
|[Кконтекстменуманажер:: Жетменубид](#getmenubyid)|Возвращает маркер меню, связанный с указанным ИДЕНТИФИКАТОРом ресурса.|
|[Кконтекстменуманажер:: Жетменубинаме](#getmenubyname)|Возвращает маркер меню, соответствующее указанному имени меню.|
|[Кконтекстменуманажер:: Жетменунамес](#getmenunames)|Возвращает список имен меню.|
|[Кконтекстменуманажер:: LoadState](#loadstate)|Загружает контекстные меню, хранящиеся в реестре Windows.|
|[Кконтекстменуманажер:: ResetState](#resetstate)|Удаляет контекстные меню из диспетчера контекстного меню.|
|[Кконтекстменуманажер:: SaveState](#savestate)|Сохраняет контекстные меню в реестре Windows.|
|[Кконтекстменуманажер:: Сетдонтклосеактивемену](#setdontcloseactivemenu)|Определяет, закрывает ли `CContextMenuManager` активное контекстное меню при отображении нового контекстного меню.|
|[Кконтекстменуманажер:: Шовпопупмену](#showpopupmenu)|Отображает указанное контекстное меню.|
|[Кконтекстменуманажер:: метод TrackPopupMenu](#trackpopupmenu)|Отображает указанное контекстное меню. Возвращает индекс выбранной команды меню.|

## <a name="remarks"></a>Remarks

`CContextMenuManager` управляет контекстными меню и гарантирует единообразное оформление.

Не следует создавать объект `CContextMenuManager` вручную. Платформа приложения создает объект `CContextMenuManager`. Однако при инициализации приложения необходимо вызвать метод [CWinAppEx:: инитконтекстменуманажер](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) . После инициализации диспетчера контекста используйте метод [CWinAppEx:: жетконтекстменуманажер](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) , чтобы получить указатель на диспетчер контекста для приложения.

Контекстные меню можно создавать во время выполнения путем вызова `AddMenu`. Если вы хотите отобразить меню без предварительного получения вводимых пользователем данных, вызовите `ShowPopupMenu`. `TrackPopupMenu` используется, если требуется создать меню и дождаться ввода данных пользователем. `TrackPopupMenu` возвращает индекс выбранной команды или значение 0, если пользователь завершил работу без выбора каких-либо данных.

`CContextMenuManager` также может сохранять и загружать свое состояние в реестр Windows.

## <a name="example"></a>Пример

В следующем примере показано, как добавить меню в `CContextMenuManager` объект и как не закрывать активное всплывающее меню, когда объект `CContextMenuManager` отображает новое всплывающее меню. Этот фрагмент кода является частью [примера пользовательских страниц](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>Требования

**Заголовок:** афксконтекстменуманажер. h

##  <a name="addmenu"></a>Кконтекстменуманажер:: ДобавитьМеню

Добавляет новое контекстное меню в [кконтекстменуманажер](../../mfc/reference/ccontextmenumanager-class.md).

```
BOOL AddMenu(
    UINT uiMenuNameResId,
    UINT uiMenuResId);

BOOL AddMenu(
    LPCTSTR lpszName,
    UINT uiMenuResId);
```

### <a name="parameters"></a>Параметры

*уименунамересид*<br/>
окне Идентификатор ресурса для строки, содержащей имя нового меню.

*уименуресид*<br/>
окне Идентификатор ресурса меню.

*лпсзнаме*<br/>
окне Строка, содержащая имя нового меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод был успешным; 0, если метод завершается ошибкой.

### <a name="remarks"></a>Remarks

Этот метод завершается ошибкой, если *уименуресид* является недопустимым или если в `CContextMenuManager`уже имеется другое меню с тем же именем.

##  <a name="ccontextmenumanager"></a>Кконтекстменуманажер:: Кконтекстменуманажер

Конструирует объект [кконтекстменуманажер](../../mfc/reference/ccontextmenumanager-class.md) .

```
CContextMenuManager();
```

### <a name="remarks"></a>Remarks

В большинстве случаев `CContextMenuManager` не следует создавать вручную. Платформа приложения создает объект `CContextMenuManager`. Во время инициализации приложения следует вызвать [CWinAppEx:: инитконтекстменуманажер](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) . Чтобы получить указатель на диспетчер контекста, вызовите метод [CWinAppEx:: жетконтекстменуманажер](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).

##  <a name="getmenubyid"></a>Кконтекстменуманажер:: Жетменубид

Возвращает маркер меню, связанный с заданным ИДЕНТИФИКАТОРом ресурса.

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>Параметры

*нменуресид*<br/>
окне Идентификатор ресурса для меню.

### <a name="return-value"></a>Возвращаемое значение

Маркер связанного меню или `NULL`, если меню не найдено.

##  <a name="getmenubyname"></a>Кконтекстменуманажер:: Жетменубинаме

Возвращает маркер в конкретное меню.

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
окне Строка, содержащая имя извлекаемого меню.

*пуиоригресид*<br/>
заполняет Указатель на UINT. Этот параметр содержит идентификатор ресурса указанного меню, если он найден.

### <a name="return-value"></a>Возвращаемое значение

Маркер меню, которое соответствует имени, заданному параметром *лпсзнаме*. Значение NULL, если нет меню с именем *лпсзнаме*.

### <a name="remarks"></a>Remarks

Если этот метод находит меню, соответствующее *лпсзнаме*, `GetMenuByName` сохраняет идентификатор ресурса меню в параметре *пуиоригресид*.

##  <a name="getmenunames"></a>Кконтекстменуманажер:: Жетменунамес

Возвращает список имен меню, добавленных в [кконтекстменуманажер](../../mfc/reference/ccontextmenumanager-class.md).

```
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Параметры

*листофнамес*<br/>
заполняет Ссылка на параметр [кстринглист](../../mfc/reference/cstringlist-class.md) . Этот метод записывает список имен меню в этот параметр.

##  <a name="loadstate"></a>Кконтекстменуманажер:: LoadState

Загружает сведения, связанные с [классом кконтекстменуманажер](../../mfc/reference/ccontextmenumanager-class.md) , из реестра Windows.

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
окне Строка, содержащая относительный путь к разделу реестра.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод успешно выполнен; в противном случае — 0.

### <a name="remarks"></a>Remarks

Параметр *лпсзпрофиленаме* не является абсолютным путем для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx:: жетрегистрибасе](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx:: сетрегистрибасе](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.

Используйте метод [кконтекстменуманажер:: SaveState](#savestate) для сохранения контекстных меню в реестре.

##  <a name="resetstate"></a>Кконтекстменуманажер:: ResetState

Удаляет все элементы из контекстных меню, связанных с [классом кконтекстменуманажер](../../mfc/reference/ccontextmenumanager-class.md).

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод успешно выполнен; Значение FALSE, если происходит сбой.

### <a name="remarks"></a>Remarks

Этот метод очищает всплывающие меню и удаляет их из `CContextMenuManager`.

##  <a name="savestate"></a>Кконтекстменуманажер:: SaveState

Сохраняет сведения, связанные с [классом кконтекстменуманажер](../../mfc/reference/ccontextmenumanager-class.md) , в реестр Windows.

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
окне Строка, содержащая относительный путь к разделу реестра.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод успешно выполнен; в противном случае — 0.

### <a name="remarks"></a>Remarks

Параметр *лпсзпрофиленаме* не является абсолютным путем для записи реестра. Это относительный путь, который добавляется в конец раздела реестра по умолчанию для приложения. Чтобы получить или задать раздел реестра по умолчанию, используйте методы [CWinAppEx:: жетрегистрибасе](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx:: сетрегистрибасе](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.

Используйте метод [кконтекстменуманажер:: LoadState](#loadstate) для загрузки контекстных меню из реестра.

##  <a name="setdontcloseactivemenu"></a>Кконтекстменуманажер:: Сетдонтклосеактивемену

Определяет, закрывает ли [кконтекстменуманажер](../../mfc/reference/ccontextmenumanager-class.md) активное всплывающее меню при отображении нового всплывающего меню.

```
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

*Управляемое bSet*<br/>
окне Логический параметр, определяющий, следует ли закрыть активное всплывающее меню. Значение TRUE указывает, что активное всплывающее меню не закрыто. Значение FALSE указывает, что активное всплывающее меню закрыто.

### <a name="remarks"></a>Remarks

По умолчанию `CContextMenuManager` закрывает активное всплывающее меню.

##  <a name="showpopupmenu"></a>Кконтекстменуманажер:: Шовпопупмену

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

*уименуресид*<br/>
окне Идентификатор ресурса меню, которое будет отображаться этим методом.

*x*<br/>
окне Горизонтальное смещение для контекстного меню в клиентских координатах.

*y*<br/>
окне Вертикальное смещение контекстного меню в клиентских координатах

*пвндовнер*<br/>
окне Указатель на родительское окно контекстного меню.

*бовнмессаже*<br/>
окне Логический параметр, указывающий способ маршрутизации сообщений. Если *бовнмессаже* имеет значение false, используется стандартная маршрутизация MFC. В противном случае *пвндовнер* получает сообщения.

*хменупопуп*<br/>
окне Маркер меню, который будет отображаться этим методом.

*баутодестрой*<br/>
окне Логический параметр, который указывает, будет ли меню автоматически уничтожено.

*бригхталигн*<br/>
окне Логический параметр, который указывает, как выводятся элементы меню. Если *бригхталигн* имеет значение true, меню выровняйтеся по правому краю для порядка чтения справа налево.

### <a name="return-value"></a>Возвращаемое значение

Первая перегрузка метода возвращает ненулевое значение, если метод успешно показывает меню; в противном случае — 0. Вторая перегрузка метода возвращает указатель на [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) , если контекстное меню отображается правильно. в противном случае — NULL.

### <a name="remarks"></a>Remarks

Этот метод напоминает метод [кконтекстменуманажер:: метод TrackPopupMenu](#trackpopupmenu) , в котором оба метода отображают контекстное меню. Однако `TrackPopupMenu` возвращает индекс выбранной команды меню.

Если параметр *баутодестрой* имеет значение false, необходимо вручную вызвать наследуемый метод `DestroyMenu`, чтобы освободить ресурсы памяти. Реализация `ShowPopupMenu` по умолчанию не использует параметр *баутодестрой*. Он предоставляется для будущего использования или для пользовательских классов, производных от класса `CContextMenuManager`.

##  <a name="trackpopupmenu"></a>Кконтекстменуманажер:: метод TrackPopupMenu

Отображает указанное контекстное меню и возвращает индекс выбранной команды контекстного меню.

```
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>Параметры

*хменупопуп*<br/>
окне Маркер контекстного меню, отображаемого этим методом.

*x*<br/>
окне Горизонтальное смещение для контекстного меню в клиентских координатах.

*y*<br/>
окне Вертикальное смещение контекстного меню в клиентских координатах.

*пвндовнер*<br/>
окне Указатель на родительское окно контекстного меню.

*бригхталигн*<br/>
окне Логический параметр, который указывает, как выводятся элементы меню. Если *бригхталигн* имеет значение true, меню выровняйтеся по правому краю для порядка чтения справа налево. Если *бригхталигн* имеет значение false, меню размещается по левому краю для порядка чтения слева направо.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды меню для команды, которую выбрал пользователь. 0, если пользователь закрывает контекстное меню без выбора команды меню.

### <a name="remarks"></a>Remarks

Этот метод выступает в качестве модального вызова для вывода контекстного меню. Приложение не будет продолжать следующую строку в коде, пока пользователь не закроет контекстное меню или не выберет команду. Альтернативным методом, который можно использовать для вывода контекстного меню, является [кконтекстменуманажер:: шовпопупмену](#showpopupmenu). Этот метод не является модальным вызовом и не будет возвращать идентификатор выбранной команды.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
