---
title: Класс CCmdTarget
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
ms.openlocfilehash: 9314717fab53b1a89b87d657ec617a4c6bd45b8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206445"
---
# <a name="ccmdtarget-class"></a>Класс CCmdTarget

Базовый класс для архитектуры схемы сообщений библиотеки классов Microsoft Foundation.

## <a name="syntax"></a>Синтаксис

```
class CCmdTarget : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CCmdTarget::CCmdTarget](#ccmdtarget)|Создает объект `CCmdTarget`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|Отображает курсор в виде курсор с песочными часами.|
|[CCmdTarget::DoOleVerb](#dooleverb)|Вызывает действие, определенное командой OLE для выполнения.|
|[CCmdTarget::EnableAutomation](#enableautomation)|Позволяет OLE-автоматизации для `CCmdTarget` объекта.|
|[CCmdTarget::EnableConnections](#enableconnections)|Обеспечивает срабатывание события через точки подключения.|
|[CCmdTarget::EnableTypeLib](#enabletypelib)|Позволяет библиотеку типов объекта.|
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|Возврат к предыдущей курсор.|
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Перечисляет команды объекта OLE.|
|[CCmdTarget::FromIDispatch](#fromidispatch)|Возвращает указатель на `CCmdTarget` объект, связанный с `IDispatch` указатель.|
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Получает идентификатор диспетчера основной интерфейс.|
|[CCmdTarget::GetIDispatch](#getidispatch)|Возвращает указатель на `IDispatch` объект, связанный с `CCmdTarget` объекта.|
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|Возвращает число интерфейсов сведения о типе, предоставляемых объектом.|
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|Извлекает описание типа, соответствующее заданному идентификатору GUID.|
|[CCmdTarget::GetTypeLib](#gettypelib)|Возвращает указатель на библиотеку типов.|
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|Возвращает кэш библиотеки типов.|
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Включает вызов метода автоматизации.|
|[CCmdTarget::IsResultExpected](#isresultexpected)|Возвращает ненулевое значение, если функцию автоматизации должна вернуть значение.|
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|Направляет и отправляет сообщения на команды.|
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Очищает после выпуска последняя ссылка OLE.|
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|Восстанавливает курсор с песочными часами.|

## <a name="remarks"></a>Примечания

Схему сообщений направляет команды или сообщения для функций-членов, предназначенный для их обработки. (Команда — это сообщение из пункта меню, кнопки или сочетания клавиш.)

Структура ключей классы, производные от `CCmdTarget` включают [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), и [ CFrameWnd](../../mfc/reference/cframewnd-class.md). Если для нового класса для обработки сообщений, наследуйте класс от одного из этих `CCmdTarget`-производные классы. Вы редко являются производными от класса `CCmdTarget` напрямую.

Общие сведения о цели команды и `OnCmdMsg` маршрутизации, см. в разделе [целей команды](../../mfc/command-targets.md), [маршрутизация команд](../../mfc/command-routing.md), и [сопоставление сообщений](../../mfc/mapping-messages.md).

`CCmdTarget` включает в себя функции-члены, которые обрабатывают отображения курсор с песочными часами. Курсор с песочными часами отображаются в том случае, если предполагается, что команду, чтобы занять заметное интервал для выполнения.

Съемы, аналогичную схемы сообщений, использующиеся для поддержки OLE-автоматизации `IDispatch` функциональные возможности. Предоставляя этот интерфейс, другие приложения (например, Visual Basic) можно вызвать в приложении.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="beginwaitcursor"></a>  CCmdTarget::BeginWaitCursor

Вызывайте эту функцию для отображения курсора как песочные часы, когда предполагается, что команду, чтобы занять заметное интервал для выполнения.

```
void BeginWaitCursor();
```

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию, чтобы показать пользователю, что он занят, например, когда `CDocument` объект загрузки или сохранения сам файл.

Действия `BeginWaitCursor` неэффективны всегда за пределами обработчика одно сообщение как другие действия, такие как `OnSetCursor` обработки, может измениться курсор.

Вызовите `EndWaitCursor` для восстановления предыдущего курсор.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="ccmdtarget"></a>  CCmdTarget::CCmdTarget

Создает объект `CCmdTarget`.

```
CCmdTarget();
```

##  <a name="dooleverb"></a>  CCmdTarget::DoOleVerb

Вызывает действие, определенное командой OLE для выполнения.

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Числовой идентификатор команды.

*lpMsg*<br/>
Указатель на [MSG](/windows/desktop/api/winuser/ns-winuser-msg) структуру, описывающую событие (например, как двойной щелчок), которое вызвало команду.

*hWndParent*<br/>
Дескриптор окна документа, содержащего объект.

*lpRect*<br/>
Указатель на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, содержащая координаты в пикселях, определяющие ограничивающий прямоугольник в *hwndParent*.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно, в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член, по сути, представляет собой реализацию [функция IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb). Перечисление возможных действий по [CCmdTarget::EnumOleVerbs](#enumoleverbs).

##  <a name="enableautomation"></a>  CCmdTarget::EnableAutomation

Вызывайте эту функцию, чтобы включить OLE-автоматизации для объекта.

```
void EnableAutomation();
```

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается из конструктора объекта и должен вызываться только если схема подготовки к отправке был объявлен для класса. Дополнительные сведения об автоматизации см. в статьях [клиенты автоматизации](../../mfc/automation-clients.md) и [серверы автоматизации](../../mfc/automation-servers.md).

##  <a name="enableconnections"></a>  CCmdTarget::EnableConnections

Обеспечивает срабатывание события через точки подключения.

```
void EnableConnections();
```

### <a name="remarks"></a>Примечания

Чтобы включить точки подключения, вызовите эту функцию-член в конструкторе производного класса.

##  <a name="enabletypelib"></a>  CCmdTarget::EnableTypeLib

Позволяет библиотеку типов объекта.

```
void EnableTypeLib();
```

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член в конструкторе вашего `CCmdTarget`-производного объекта, если он предоставляет сведения о типе.

##  <a name="endwaitcursor"></a>  CCmdTarget::EndWaitCursor

Вызывайте эту функцию после вызова `BeginWaitCursor` функция-член возвращаемый курсор с песочными часами до предыдущей позиции курсора.

```
void EndWaitCursor();
```

### <a name="remarks"></a>Примечания

Эта функция-член вызывается платформой также после вызова курсор с песочными часами.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="enumoleverbs"></a>  CCmdTarget::EnumOleVerbs

Перечисляет команды объекта OLE.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>Параметры

*ppenumOleVerb*<br/>
Указатель на указатель на [IEnumOLEVERB](/windows/desktop/api/oleidl/nn-oleidl-ienumoleverb) интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект поддерживает по крайней мере один команды OLE (в этом случае \* *ppenumOleVerb* указывает `IEnumOLEVERB` интерфейс перечислителя), в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член, по сути, представляет собой реализацию [IOleObject::EnumVerbs](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumverbs).

##  <a name="fromidispatch"></a>  CCmdTarget::FromIDispatch

Вызывайте эту функцию для сопоставления `IDispatch` указатель, полученные от автоматизации функций-членов класса, в `CCmdTarget` объект, реализующий интерфейсы `IDispatch` объекта.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>Параметры

*lpDispatch*<br/>
Указатель на объект `IDispatch` .

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CCmdTarget` объект, связанный с *lpDispatch*. Эта функция возвращает значение NULL, если `IDispatch` объект не распознан как Microsoft Foundation Class `IDispatch` объекта.

### <a name="remarks"></a>Примечания

Результат этой функции — обратное значение для вызова функции-члена `GetIDispatch`.

##  <a name="getdispatchiid"></a>  CCmdTarget::GetDispatchIID

Получает идентификатор диспетчера основной интерфейс.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>Параметры

*pIID*<br/>
Указатель на идентификатор интерфейса ( [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931)).

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно, в противном случае — значение FALSE. В случае успешного выполнения \* *pIID* присваивается идентификатор диспетчера основной интерфейс.

### <a name="remarks"></a>Примечания

Производные классы должны переопределить эту функцию-член (если не переопределен, `GetDispatchIID` возвращает значение FALSE). См. в разделе [COleControl](../../mfc/reference/colecontrol-class.md).

##  <a name="getidispatch"></a>  CCmdTarget::GetIDispatch

Вызовите эту функцию-член для извлечения `IDispatch` указатель методом автоматизации, либо возвращает `IDispatch` указателя или принимает `IDispatch` указатель по ссылке.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>Параметры

*bAddRef*<br/>
Указывает, следует ли увеличить счетчик ссылок для объекта.

### <a name="return-value"></a>Возвращаемое значение

`IDispatch` Указатель, связанный с объектом.

### <a name="remarks"></a>Примечания

Для объектов этого вызова `EnableAutomation` их конструкторы, что делает их автоматизации включена, эта функция возвращает указатель на реализацию в классе Foundation `IDispatch` , используемый клиентами, которые обмениваются данными через `IDispatch` интерфейс. Вызов этой функции автоматически добавляет ссылку на указатель, поэтому нет необходимости для выполнения вызова к [IUnknown::AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref).

##  <a name="gettypeinfocount"></a>  CCmdTarget::GetTypeInfoCount

Возвращает число интерфейсов сведения о типе, предоставляемых объектом.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число интерфейсов, сведения о типе.

### <a name="remarks"></a>Примечания

По сути, эта функция-член реализуется [IDispatch::GetTypeInfoCount](/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount).

Производные классы должны переопределить эту функцию для возврата числа интерфейсов сведения о типе (0 или 1). Если не переопределен, `GetTypeInfoCount` возвращает 0. Для переопределения используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макросом, который также реализует `GetTypeLib` и `GetTypeLibCache`.

##  <a name="gettypeinfoofguid"></a>  CCmdTarget::GetTypeInfoOfGuid

Извлекает описание типа, соответствующее заданному идентификатору GUID.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>Параметры

*lcid*<br/>
Код языка ( `LCID`).

*Идентификатор GUID*<br/>
[GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931) описания типа.

*ppTypeInfo*<br/>
Указатель на указатель на `ITypeInfo` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, указывающее, успешно ли выполнен вызов. В случае успешного выполнения \* *ppTypeInfo* указывает на интерфейс типа сведений.

##  <a name="gettypelib"></a>  CCmdTarget::GetTypeLib

Возвращает указатель на библиотеку типов.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>Параметры

*lcid*<br/>
Идентификатор языка (LCID).

*ppTypeLib*<br/>
Указатель на указатель на `ITypeLib` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, указывающее, успешно ли выполнен вызов. В случае успешного выполнения \* *ppTypeLib* указывает на интерфейс библиотеки типов.

### <a name="remarks"></a>Примечания

Производные классы должны переопределить эту функцию-член (если не переопределен, `GetTypeLib` возвращает TYPE_E_CANTLOADLIBRARY). Используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макросом, который также реализует `GetTypeInfoCount` и `GetTypeLibCache`.

##  <a name="gettypelibcache"></a>  CCmdTarget::GetTypeLibCache

Возвращает кэш библиотеки типов.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CTypeLibCache` .

### <a name="remarks"></a>Примечания

Производные классы должны переопределить эту функцию-член (если не переопределен, `GetTypeLibCache` возвращает значение NULL). Используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макросом, который также реализует `GetTypeInfoCount` и `GetTypeLib`.

##  <a name="isinvokeallowed"></a>  CCmdTarget::IsInvokeAllowed

Эта функция вызывается с реализации MFC `IDispatch::Invoke` для определения, если у метода данной службы автоматизации (определяется *dispid*) могут быть вызваны.

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>Параметры

*Идентификатор DISPID*<br/>
Идентификатор диспетчера.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод может быть вызванным, в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если `IsInvokeAllowed` возвращает значение TRUE, `Invoke` выполняет вызов метода; в противном случае `Invoke` завершится ошибкой, возвращая E_UNEXPECTED.

Производные классы могут переопределять эту функцию для возврата соответствующего значения (если не переопределен, `IsInvokeAllowed` возвращает значение TRUE). См. в частности [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

##  <a name="isresultexpected"></a>  CCmdTarget::IsResultExpected

Используйте `IsResultExpected` для выяснения, ожидает ли клиент возвращаемое значение, вызов функции автоматизации.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функцию автоматизации должны возвращать значение; в противном случае 0.

### <a name="remarks"></a>Примечания

OLE-интерфейс предоставляет сведения о ли клиент с помощью или пропуск результат вызова функции MFC, а MFC, в свою очередь, использует эти сведения для определения результата вызова `IsResultExpected`. Если производства, возвращаемое значение или ресурс много времени, можно повысить эффективность путем вызова этой функции перед вычислением возвращаемое значение.

Эта функция возвращает 0 только в том случае, когда таким образом, вы получите допустимых возвращаемых значений из других функций автоматизации при вызове их из функции автоматизации, называется клиента.

`IsResultExpected` возвращает ненулевое значение, если вызывается, когда вызов функции автоматизации не выполняется.

##  <a name="oncmdmsg"></a>  CCmdTarget::OnCmdMsg

Вызывается платформой для маршрутизации и отправления сообщения команд и для обработки обновление объектов пользовательского интерфейса команды.

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

*nCode*<br/>
Определяет код команды уведомления. См. в разделе **"Примечания"** Дополнительные сведения о значениях *nCode*.

*pExtra*<br/>
Использовать согласно значению *nCode*. См. в разделе **"Примечания"** Дополнительные сведения о *pExtra*.

*pHandlerInfo*<br/>
Если значение не NULL, `OnCmdMsg` заполняет *pTarget* и *pmf* членами *pHandlerInfo* структуры вместо отправки команды. Как правило этот параметр должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение обработано; в противном случае 0.

### <a name="remarks"></a>Примечания

Это процедура реализации архитектуры команда framework.

Во время выполнения `OnCmdMsg` отправляет команды на другие объекты или обрабатываемые в саму команду, вызвав корневой класс `CCmdTarget::OnCmdMsg`, который выполняет Просмотр фактических схемы сообщений. Полное описание маршрутизация команд по умолчанию, см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).

В редких случаях может потребоваться переопределить эту функцию-член для расширения платформы стандартной маршрутизации команд. Ссылаться на [технические 21 Примечание](../../mfc/tn021-command-and-message-routing.md) дополнительные подробности архитектуры маршрутизации команд.

При переопределении `OnCmdMsg`, необходимо указать соответствующее значение в параметре *nCode*, кода уведомления команды и *pExtra*, который зависит от значения *nCode* . В следующей таблице перечислены соответствующие значения:

|*nCode* значение|*pExtra* значение|
|-------------------|--------------------|
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|CCmdUI\*|
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

##  <a name="onfinalrelease"></a>  CCmdTarget::OnFinalRelease

Вызывается платформой, когда последняя ссылка OLE на или из объекта освобождается.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>Примечания

Переопределите эту функцию для обеспечения специальной обработки для данной ситуации. Реализация по умолчанию удаляет объект.

##  <a name="restorewaitcursor"></a>  CCmdTarget::RestoreWaitCursor

Вызывайте эту функцию для восстановления соответствующего курсор песочных часов после системного курсора был изменен (например, после окно сообщения открытых и закрытых затем середине длительной операции).

```
void RestoreWaitCursor();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC ACDUAL](../../overview/visual-cpp-samples.md)<br/>
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
