---
title: Класс от CCmdTarget
ms.date: 11/04/2016
f1_keywords:
- CCmdTarget
- AFXWIN/CCmdTarget
- AFXWIN/CCmdTarget::CCmdTarget
- AFXWIN/CCmdTarget::BeginWaitCursor
- AFXWIN/CCmdTarget::DoOleVerb
- AFXWIN/CCmdTarget::EnableAutomation
- AFXWIN/CCmdTarget::EnableConnections
- AFXWIN/CCmdTarget::EnableTypeLib
- AFXWIN/CCmdTarget::EndWaitCursor
- AFXWIN/CCmdTarget::EnumOleVerbs
- AFXWIN/CCmdTarget::FromIDispatch
- AFXWIN/CCmdTarget::GetDispatchIID
- AFXWIN/CCmdTarget::GetIDispatch
- AFXWIN/CCmdTarget::GetTypeInfoCount
- AFXWIN/CCmdTarget::GetTypeInfoOfGuid
- AFXWIN/CCmdTarget::GetTypeLib
- AFXWIN/CCmdTarget::GetTypeLibCache
- AFXWIN/CCmdTarget::IsInvokeAllowed
- AFXWIN/CCmdTarget::IsResultExpected
- AFXWIN/CCmdTarget::OnCmdMsg
- AFXWIN/CCmdTarget::OnFinalRelease
- AFXWIN/CCmdTarget::RestoreWaitCursor
helpviewer_keywords:
- CCmdTarget [MFC], CCmdTarget
- CCmdTarget [MFC], BeginWaitCursor
- CCmdTarget [MFC], DoOleVerb
- CCmdTarget [MFC], EnableAutomation
- CCmdTarget [MFC], EnableConnections
- CCmdTarget [MFC], EnableTypeLib
- CCmdTarget [MFC], EndWaitCursor
- CCmdTarget [MFC], EnumOleVerbs
- CCmdTarget [MFC], FromIDispatch
- CCmdTarget [MFC], GetDispatchIID
- CCmdTarget [MFC], GetIDispatch
- CCmdTarget [MFC], GetTypeInfoCount
- CCmdTarget [MFC], GetTypeInfoOfGuid
- CCmdTarget [MFC], GetTypeLib
- CCmdTarget [MFC], GetTypeLibCache
- CCmdTarget [MFC], IsInvokeAllowed
- CCmdTarget [MFC], IsResultExpected
- CCmdTarget [MFC], OnCmdMsg
- CCmdTarget [MFC], OnFinalRelease
- CCmdTarget [MFC], RestoreWaitCursor
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
ms.openlocfilehash: 583b685295bf77910ef134776c1c4fa39baf93ad
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426003"
---
# <a name="ccmdtarget-class"></a>Класс от CCmdTarget

Базовый класс для библиотека Microsoft Foundation Class архитектуры схемы сообщения.

## <a name="syntax"></a>Синтаксис

```
class CCmdTarget : public CObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[От CCmdTarget:: от CCmdTarget](#ccmdtarget)|Формирует объект `CCmdTarget`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[От CCmdTarget:: Бегинваиткурсор](#beginwaitcursor)|Отображает курсор в виде указателя песочных часов.|
|[От CCmdTarget::D Улеверб](#dooleverb)|Вызывает выполнение действия, указанного в команде OLE.|
|[От CCmdTarget:: Енаблеаутоматион](#enableautomation)|Разрешает OLE Automation для объекта `CCmdTarget`.|
|[От CCmdTarget:: Енаблеконнектионс](#enableconnections)|Разрешает обработку событий через точки соединения.|
|[От CCmdTarget:: Енаблетипелиб](#enabletypelib)|Включает библиотеку типов объекта.|
|[От CCmdTarget:: Ендваиткурсор](#endwaitcursor)|Возвращает к предыдущему курсору.|
|[От CCmdTarget:: Енумолевербс](#enumoleverbs)|Перечисляет команды OLE объекта.|
|[От CCmdTarget:: Фромидиспатч](#fromidispatch)|Возвращает указатель на объект `CCmdTarget`, связанный с указателем `IDispatch`.|
|[От CCmdTarget:: Жетдиспатчиид](#getdispatchiid)|Возвращает идентификатор основного интерфейса диспетчеризации.|
|[От CCmdTarget:: IDispatch](#getidispatch)|Возвращает указатель на объект `IDispatch`, связанный с объектом `CCmdTarget`.|
|[От CCmdTarget:: Жеттипеинфокаунт](#gettypeinfocount)|Извлекает число интерфейсов сведений о типе, предоставляемых объектом.|
|[От CCmdTarget:: Жеттипеинфуфгуид](#gettypeinfoofguid)|Загружает описание типа, соответствующее заданному идентификатору GUID.|
|[От CCmdTarget:: Жеттипелиб](#gettypelib)|Возвращает указатель на библиотеку типов.|
|[От CCmdTarget:: Жеттипелибкаче](#gettypelibcache)|Возвращает кэш библиотеки типов.|
|[От CCmdTarget:: Исинвокеалловед](#isinvokeallowed)|Включает вызов метода автоматизации.|
|[От CCmdTarget:: Исресултекспектед](#isresultexpected)|Возвращает ненулевое значение, если функция автоматизации должна возвращать значения.|
|[От CCmdTarget:: OnCmdMsg](#oncmdmsg)|Маршрутизирует и отправляет командные сообщения.|
|[От CCmdTarget:: Онфиналрелеасе](#onfinalrelease)|Очищается после выпуска последней ссылки OLE.|
|[От CCmdTarget:: Рестореваиткурсор](#restorewaitcursor)|Восстанавливает курсор песочных часов.|

## <a name="remarks"></a>Remarks

Схема сообщений направляет команды или сообщения в функции-члены, которые вы пишете для обработки. (Команда является сообщением из пункта меню, кнопки или сочетания клавиш.)

Ключевыми классами платформы, производными от `CCmdTarget`, являются [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md)и [CFrameWnd](../../mfc/reference/cframewnd-class.md). Если требуется, чтобы новый класс обрабатывал сообщения, производные от одного из этих классов, производных от `CCmdTarget`, следует унаследовать класс. Вы редко будете наследовать класс от `CCmdTarget` напрямую.

Общие сведения о целевых объектах команд и маршрутизации `OnCmdMsg` см. в разделе [цели команд](../../mfc/command-targets.md), [Маршрутизация команд](../../mfc/command-routing.md)и [сообщения о сопоставлении](../../mfc/mapping-messages.md).

`CCmdTarget` включает функции элементов, которые обрабатывали отображение курсора песочных часов. Отображение курсора песочных часов, если предполагается, что команда займет заметный интервал времени для выполнения.

Карты диспетчеризации, аналогичные картам сообщений, используются для предоставления функциональных возможностей OLE Automation `IDispatch`. Предоставляя этот интерфейс, другие приложения (такие как Visual Basic) могут вызываться в приложении.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="beginwaitcursor"></a>От CCmdTarget:: Бегинваиткурсор

Вызывайте эту функцию для вывода курсора в виде песочных часов, если предполагается, что команда займет заметный интервал времени для выполнения.

```
void BeginWaitCursor();
```

### <a name="remarks"></a>Remarks

Платформа вызывает эту функцию, чтобы продемонстрировать пользователю, что он занят, например, когда объект `CDocument` загружается или сохраняется в файл.

Действия `BeginWaitCursor` не всегда действуют за пределами одного обработчика сообщений, так как другие действия, такие как обработка `OnSetCursor`, могут изменить курсор.

Вызовите `EndWaitCursor`, чтобы восстановить предыдущий курсор.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="ccmdtarget"></a>От CCmdTarget:: от CCmdTarget

Формирует объект `CCmdTarget`.

```
CCmdTarget();
```

##  <a name="dooleverb"></a>От CCmdTarget::D Улеверб

Вызывает выполнение действия, указанного в команде OLE.

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*иверб*<br/>
Числовой идентификатор команды.

*лпмсг*<br/>
Указатель на структуру [сообщения](/windows/win32/api/winuser/ns-winuser-msg) , описывающую событие (например, двойной щелчок), вызвавшее команду.

*хвндпарент*<br/>
Дескриптор окна документа, содержащего объект.

*лпрект*<br/>
Указатель на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , содержащую координаты (в пикселях), определяющие ограничивающий прямоугольник объекта в *хвндпарент*.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если выполнено успешно; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

Эта функция-член по сути является реализацией [иолеобжект::D оверб](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb). Возможные действия перечисляются с помощью [от CCmdTarget:: енумолевербс](#enumoleverbs).

##  <a name="enableautomation"></a>От CCmdTarget:: Енаблеаутоматион

Вызовите эту функцию, чтобы включить OLE Automation для объекта.

```
void EnableAutomation();
```

### <a name="remarks"></a>Remarks

Эта функция обычно вызывается из конструктора объекта и должна вызываться только в том случае, если для класса была объявлена схема диспетчеризации. Дополнительные сведения об автоматизации см. в статье [Клиенты автоматизации](../../mfc/automation-clients.md) и [серверы автоматизации](../../mfc/automation-servers.md).

##  <a name="enableconnections"></a>От CCmdTarget:: Енаблеконнектионс

Разрешает обработку событий через точки соединения.

```
void EnableConnections();
```

### <a name="remarks"></a>Remarks

Чтобы включить точки подключения, вызовите эту функцию члена в конструкторе производного класса.

##  <a name="enabletypelib"></a>От CCmdTarget:: Енаблетипелиб

Включает библиотеку типов объекта.

```
void EnableTypeLib();
```

### <a name="remarks"></a>Remarks

Вызовите эту функцию-член в конструкторе объекта, производного от `CCmdTarget`, если он предоставляет сведения о типе.

##  <a name="endwaitcursor"></a>От CCmdTarget:: Ендваиткурсор

Вызовите эту функцию после вызова функции члена `BeginWaitCursor`, чтобы вернуться от курсора песочных часов к предыдущему курсору.

```
void EndWaitCursor();
```

### <a name="remarks"></a>Remarks

Платформа также вызывает эту функцию члена после того, как она называлась курсором песочных часов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="enumoleverbs"></a>От CCmdTarget:: Енумолевербс

Перечисляет команды OLE объекта.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>Параметры

*ппенумолеверб*<br/>
Указатель на указатель на интерфейс [иенумолеверб](/windows/win32/api/oleidl/nn-oleidl-ienumoleverb) .

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект поддерживает по крайней мере одну команду OLE (в этом случае \* *ппенумолеверб* указывает на интерфейс перечислителя `IEnumOLEVERB`); в противном случае — значение false.

### <a name="remarks"></a>Remarks

Эта функция-член по сути является реализацией [иолеобжект:: енумвербс](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs).

##  <a name="fromidispatch"></a>От CCmdTarget:: Фромидиспатч

Вызывайте эту функцию для отображения `IDispatch` указателя, полученного от функций-членов автоматизации класса, в объект `CCmdTarget`, реализующий интерфейсы объекта `IDispatch`.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>Параметры

*лпдиспатч*<br/>
Указатель на объект `IDispatch`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CCmdTarget`, связанный с *лпдиспатч*. Эта функция возвращает значение NULL, если `IDispatch` объект не распознан как класс Microsoft Foundation `IDispatch` объект.

### <a name="remarks"></a>Remarks

Результат этой функции является обратным вызовом функции-члена `GetIDispatch`.

##  <a name="getdispatchiid"></a>От CCmdTarget:: Жетдиспатчиид

Возвращает идентификатор основного интерфейса диспетчеризации.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>Параметры

*пиид*<br/>
Указатель на идентификатор интерфейса ( [GUID](/previous-versions/cc317743(v%3dmsdn.10)).

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если выполнено успешно; в противном случае — FALSE. В случае успеха \* *пиид* задается идентификатор основного интерфейса диспетчеризации.

### <a name="remarks"></a>Remarks

Производные классы должны переопределять эту функцию-член (если она не была переопределена, `GetDispatchIID` возвращает значение FALSE). См. [COleControl](../../mfc/reference/colecontrol-class.md).

##  <a name="getidispatch"></a>От CCmdTarget:: IDispatch

Вызовите эту функцию члена, чтобы получить указатель `IDispatch` из метода автоматизации, который возвращает указатель `IDispatch` или принимает указатель `IDispatch` по ссылке.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>Параметры

*баддреф*<br/>
Указывает, следует ли увеличивать значение счетчика ссылок для объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель `IDispatch`, связанный с объектом.

### <a name="remarks"></a>Remarks

Для объектов, которые вызывают `EnableAutomation` в своих конструкторах, делая их включенной, эта функция возвращает указатель на реализацию класса базовых классов `IDispatch`, который используется клиентами, взаимодействующими через интерфейс `IDispatch`. При вызове этой функции автоматически добавляется ссылка на указатель, поэтому нет необходимости выполнять вызов [IUnknown:: AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref).

##  <a name="gettypeinfocount"></a>От CCmdTarget:: Жеттипеинфокаунт

Извлекает число интерфейсов сведений о типе, предоставляемых объектом.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число интерфейсов сведений о типе.

### <a name="remarks"></a>Remarks

Эта функция члена по сути реализует [IDispatch:: жеттипеинфокаунт](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount).

Производные классы должны переопределять эту функцию для возврата числа предоставленных интерфейсов сведений о типе (0 или 1). Если не переопределен, `GetTypeInfoCount` возвращает 0. Для переопределения используйте макрос [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) , который также реализует `GetTypeLib` и `GetTypeLibCache`.

##  <a name="gettypeinfoofguid"></a>От CCmdTarget:: Жеттипеинфуфгуид

Загружает описание типа, соответствующее заданному идентификатору GUID.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>Параметры

*lcid*<br/>
Идентификатор локали (`LCID`).

*guid*<br/>
[Идентификатор GUID](/previous-versions/cc317743(v%3dmsdn.10)) описания типа.

*пптипеинфо*<br/>
Указатель на указатель на интерфейс `ITypeInfo`.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, указывающее на успешное или неудачное завершение вызова. В случае успеха \* *пптипеинфо* указывает на информационный интерфейс типа.

##  <a name="gettypelib"></a>От CCmdTarget:: Жеттипелиб

Возвращает указатель на библиотеку типов.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>Параметры

*lcid*<br/>
Идентификатор языка (LCID).

*пптипелиб*<br/>
Указатель на указатель на интерфейс `ITypeLib`.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, указывающее на успешное или неудачное завершение вызова. В случае успеха \* *пптипелиб* указывает на интерфейс библиотеки типов.

### <a name="remarks"></a>Remarks

Производные классы должны переопределять эту функцию-член (если она не была переопределена, `GetTypeLib` возвращает TYPE_E_CANTLOADLIBRARY). Используйте макрос [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) , который также реализует `GetTypeInfoCount` и `GetTypeLibCache`.

##  <a name="gettypelibcache"></a>От CCmdTarget:: Жеттипелибкаче

Возвращает кэш библиотеки типов.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CTypeLibCache`.

### <a name="remarks"></a>Remarks

Производные классы должны переопределять эту функцию-член (если она не была переопределена, `GetTypeLibCache` возвращает значение NULL). Используйте макрос [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) , который также реализует `GetTypeInfoCount` и `GetTypeLib`.

##  <a name="isinvokeallowed"></a>От CCmdTarget:: Исинвокеалловед

Эта функция вызывается реализацией `IDispatch::Invoke` MFC, чтобы определить, может ли быть вызван данный метод автоматизации (идентифицируемый *DISPID*).

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор диспетчеризации.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод может быть вызван; в противном случае — значение FALSE.

### <a name="remarks"></a>Remarks

Если `IsInvokeAllowed` возвращает значение TRUE, `Invoke` продолжает вызывать метод. в противном случае `Invoke` завершится ошибкой, возвращая E_UNEXPECTED.

Производные классы могут переопределить эту функцию для возврата соответствующих значений (если не переопределить, `IsInvokeAllowed` возвращает значение TRUE). См. раздел в определенных [COleControl:: исинвокеалловед](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

##  <a name="isresultexpected"></a>От CCmdTarget:: Исресултекспектед

Используйте `IsResultExpected`, чтобы определить, будет ли клиент получать возвращаемое значение из своего вызова функции автоматизации.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевой, если функция автоматизации должна возвращать значение; в противном случае — 0.

### <a name="remarks"></a>Remarks

OLE-интерфейс предоставляет сведения в MFC о том, использует ли клиент или игнорирует результат вызова функции, а MFC, в свою очередь, использует эти сведения для определения результата вызова `IsResultExpected`. Если производство возвращаемого значения занимает много времени или ресурсов, можно повысить эффективность, вызвав эту функцию перед вычислением возвращаемого значения.

Эта функция возвращает 0 только один раз, чтобы получить допустимые возвращаемые значения от других функций автоматизации, если они вызываются из функции автоматизации, вызванной клиентом.

`IsResultExpected` возвращает ненулевое значение, если вызов функции автоматизации не выполняется.

##  <a name="oncmdmsg"></a>От CCmdTarget:: OnCmdMsg

Вызывается платформой для маршрутизации и диспетчеризации командных сообщений, а также для обработки обновления объектов пользовательского интерфейса команды.

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Содержит идентификатор команды.

*нкоде*<br/>
Идентифицирует код уведомления команды. Дополнительные сведения о значениях для *нкоде*см. в разделе **Примечания** .

*пекстра*<br/>
Используется в соответствии со значением *нкоде*. Дополнительные сведения о *пекстра*см. в разделе **Примечания** .

*фандлеринфо*<br/>
Если значение не равно NULL, `OnCmdMsg` заполняет элементы *птаржет* и *PMF* структуры *фандлеринфо* вместо диспетчеризации команды. Как правило, этот параметр должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение обрабатывается; в противном случае — 0.

### <a name="remarks"></a>Remarks

Это основная подпрограммы реализации архитектуры команд платформы.

Во время выполнения `OnCmdMsg` отправляет команду другим объектам или обрабатывает саму команду, вызывая корневой класс `CCmdTarget::OnCmdMsg`, который выполняет фактическую подстановку в схеме сообщений. Полное описание маршрутизации команд по умолчанию см. в [разделах обработка и сопоставление сообщений](../../mfc/message-handling-and-mapping.md).

В редких случаях может потребоваться переопределить эту функцию-член, чтобы расширить стандартную маршрутизацию команд в платформе. Дополнительные сведения об архитектуре маршрутизации команд см. в [техническом примечании 21](../../mfc/tn021-command-and-message-routing.md) .

При переопределении `OnCmdMsg`необходимо указать соответствующее значение для *нкоде*, код уведомления команды и *пекстра*, который зависит от значения *нкоде*. В следующей таблице перечислены соответствующие значения.

|значение *нкоде*|значение *пекстра*|
|-------------------|--------------------|
|CN_COMMAND|[Поддержка ccmdui](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|Поддержка CCmdUI\*|
|CN_OLECOMMAND|[Колекмдуи](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

##  <a name="onfinalrelease"></a>От CCmdTarget:: Онфиналрелеасе

Вызывается платформой при освобождении последней ссылки OLE на или из объекта.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>Remarks

Переопределите эту функцию, чтобы обеспечить специальную обработку для этой ситуации. Реализация по умолчанию удаляет объект.

##  <a name="restorewaitcursor"></a>От CCmdTarget:: Рестореваиткурсор

Вызывайте эту функцию для восстановления соответствующего курсора песочных часов после изменения системного курсора (например, после открытия окна сообщения и его закрытия в ходе длительной операции).

```
void RestoreWaitCursor();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Пример ACDUAL библиотеки MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdUI](../../mfc/reference/ccmdui-class.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Класс COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)
