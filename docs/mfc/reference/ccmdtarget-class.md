---
title: CCmdTarget-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b76e4a0c0533ceb0200757f86f332d77c3b39ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356496"
---
# <a name="ccmdtarget-class"></a>CCmdTarget-класс
Базовый класс для архитектуры схемы сообщений библиотеки классов Microsoft Foundation.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCmdTarget : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCmdTarget::CCmdTarget](#ccmdtarget)|Создает объект `CCmdTarget`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|Отображает курсор в виде курсор с песочными часами.|  
|[CCmdTarget::DoOleVerb](#dooleverb)|Вызывает действие, определенное командой OLE для выполнения.|  
|[CCmdTarget::EnableAutomation](#enableautomation)|Позволяет OLE-автоматизации для `CCmdTarget` объекта.|  
|[CCmdTarget::EnableConnections](#enableconnections)|Включает события через точки подключения.|  
|[CCmdTarget::EnableTypeLib](#enabletypelib)|Включает библиотеку типов объекта.|  
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|Возврат к предыдущей курсора.|  
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Перечисляет команды объекта OLE.|  
|[CCmdTarget::FromIDispatch](#fromidispatch)|Возвращает указатель на `CCmdTarget` объекта, связанного с `IDispatch` указателя.|  
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Возвращает идентификатор диспетчера основной интерфейс.|  
|[CCmdTarget::GetIDispatch](#getidispatch)|Возвращает указатель на `IDispatch` объекта, связанного с `CCmdTarget` объекта.|  
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|Возвращает число интерфейсов сведения о типе, предоставляемых объектом.|  
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|Извлекает описание типа, соответствующее заданному идентификатору GUID.|  
|[CCmdTarget::GetTypeLib](#gettypelib)|Возвращает указатель на библиотеку типов.|  
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|Возвращает кэш библиотеки типов.|  
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Включает вызов метода автоматизации.|  
|[CCmdTarget::IsResultExpected](#isresultexpected)|Возвращает ненулевое значение, если функцию автоматизации должны возвращать значение.|  
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|Маршруты и отправляет сообщения команд.|  
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Производит очистку после выпуска последняя ссылка OLE.|  
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|Восстанавливает курсор с песочными часами.|  
  
## <a name="remarks"></a>Примечания  
 Схемы сообщений направляет команды или сообщения функции-члены, предназначенный для их обработки. (Команды — это сообщение из пункта меню, кнопки или сочетание клавиш).  
  
 Структура ключей классы, производные от `CCmdTarget` включают [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), и [ CFrameWnd](../../mfc/reference/cframewnd-class.md). Если необходимо реализовать для нового класса для обработки сообщений, создайте класс, производный от одного из этих `CCmdTarget`-производные классы. Вы редко являются производными от класса `CCmdTarget` напрямую.  
  
 Общие сведения о цели команды и `OnCmdMsg` маршрутизации, в разделе [целей команды](../../mfc/command-targets.md), [маршрутизация команд](../../mfc/command-routing.md), и [сопоставление сообщений](../../mfc/mapping-messages.md).  
  
 `CCmdTarget` включает функции-члены, управления отображением курсор с песочными часами. Курсор с песочными часами отображаются в том случае, если предполагается, что команду, чтобы стать заметным интервал до выполнения.  
  
 Съемы, аналогично схемы сообщений, использующиеся для поддержки OLE-автоматизации `IDispatch` функциональные возможности. Путем предоставления доступа к этот интерфейс, приложение может вызывать другими приложениями (например, Visual Basic).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="beginwaitcursor"></a>  CCmdTarget::BeginWaitCursor  
 Эта функция используется для отображения курсора как песочные часы, если ожидается команду, чтобы стать заметным интервал до выполнения.  
  
```  
void BeginWaitCursor();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию для представления пользователю, что он занят, например когда **CDocument** объекта загрузки или сохранения сам файл.  
  
 Действия `BeginWaitCursor` не всегда действующие вне обработчика одно сообщение как другие действия, такие как `OnSetCursor` обработки, может изменить курсор.  
  
 Вызовите `EndWaitCursor` для восстановления предыдущего курсора.  
  
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
 `iVerb`  
 Числовой идентификатор команды.  
  
 `lpMsg`  
 Указатель на [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) структура описания события (например, двойным щелчком), которое вызвало команду.  
  
 `hWndParent`  
 Дескриптор окна документа, содержащего объект.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая координаты в пикселях, которые определяют объект ограничивающий прямоугольник в *hwndParent*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно, в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член по сути является реализацией [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508). Перечисление возможных действий по [CCmdTarget::EnumOleVerbs](#enumoleverbs).  
  
##  <a name="enableautomation"></a>  CCmdTarget::EnableAutomation  
 Вызывайте эту функцию, чтобы включить для объекта OLE-автоматизации.  
  
```  
void EnableAutomation();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается из конструктора объекта и должен вызываться только если карту диспетчеризации был объявлен для класса. Дополнительные сведения об автоматизации см. в статьях [клиенты автоматизации](../../mfc/automation-clients.md) и [серверы автоматизации](../../mfc/automation-servers.md).  
  
##  <a name="enableconnections"></a>  CCmdTarget::EnableConnections  
 Включает события через точки подключения.  
  
```  
void EnableConnections();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы включить точки подключения, вызовите эту функцию-член в конструкторе производного класса.  
  
##  <a name="enabletypelib"></a>  CCmdTarget::EnableTypeLib  
 Включает библиотеку типов объекта.  
  
```  
void EnableTypeLib();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член в конструкторе вашей `CCmdTarget`-производного объекта, если оно предоставляет информацию о типе. Дополнительные сведения см. в статье базы знаний Q185720, «Практическое руководство: предоставления сведений о типе из сервера автоматизации MFC.» Статьи базы знаний можно найти по адресу [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="endwaitcursor"></a>  CCmdTarget::EndWaitCursor  
 Эта функция вызывается после вызова `BeginWaitCursor` функции-члена возвращать курсор с песочными часами в предыдущем курсора.  
  
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
 `ppenumOleVerb`  
 Указатель на указатель на [IEnumOLEVERB](http://msdn.microsoft.com/library/windows/desktop/ms695084) интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если объект поддерживает по крайней мере один команды OLE (в этом случае \* `ppenumOleVerb` указывает **IEnumOLEVERB** интерфейс перечислителя), в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член по сути является реализацией [IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781).  
  
##  <a name="fromidispatch"></a>  CCmdTarget::FromIDispatch  
 Вызывайте эту функцию для сопоставления `IDispatch` указателя, полученные от автоматизации функций-членов класса, в `CCmdTarget` объект, реализующий интерфейсы `IDispatch` объекта.  
  
```  
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDispatch`  
 Указатель на объект `IDispatch`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CCmdTarget` объекта, связанного с `lpDispatch`. Эта функция возвращает **NULL** Если `IDispatch` объект не является Microsoft Foundation Class `IDispatch` объекта.  
  
### <a name="remarks"></a>Примечания  
 Результат этой функции является обратным для вызова функции-члена `GetIDispatch`.  
  
##  <a name="getdispatchiid"></a>  CCmdTarget::GetDispatchIID  
 Возвращает идентификатор диспетчера основной интерфейс.  
  
```  
virtual BOOL GetDispatchIID(IID* pIID);
```  
  
### <a name="parameters"></a>Параметры  
 *pIID*  
 Указатель на идентификатор интерфейса ( [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931)).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно, в противном случае — значение FALSE. В случае успешного выполнения \* *pIID* присваивается идентификатор диспетчера основной интерфейс.  
  
### <a name="remarks"></a>Примечания  
 Производные классы должны переопределить эту функцию-член (если не переопределен, `GetDispatchIID` возвращает значение FALSE). В разделе [COleControl](../../mfc/reference/colecontrol-class.md).  
  
 Дополнительные сведения см. в статье базы знаний Q185720, «Практическое руководство: предоставления сведений о типе из сервера автоматизации MFC.» Статьи базы знаний можно найти по адресу [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="getidispatch"></a>  CCmdTarget::GetIDispatch  
 Вызовите эту функцию-член для извлечения `IDispatch` указатель методом автоматизации, либо возвращает `IDispatch` указателя или принимает `IDispatch` указатель по ссылке.  
  
```  
LPDISPATCH GetIDispatch(BOOL bAddRef);
```  
  
### <a name="parameters"></a>Параметры  
 *bAddRef*  
 Указывает, следует ли увеличить счетчик ссылок для объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IDispatch` Указатель, связанный с объектом.  
  
### <a name="remarks"></a>Примечания  
 Для объектов, вызывающих метод `EnableAutomation` их конструкторы, делая их автоматизации включена, эта функция возвращает указатель на реализацию Foundation Class `IDispatch` , используемый клиентами, которые связь через `IDispatch` интерфейса. Автоматически при вызове этой функции добавляет ссылку на указатель, поэтому нет необходимости вызвать [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379).  
  
##  <a name="gettypeinfocount"></a>  CCmdTarget::GetTypeInfoCount  
 Возвращает число интерфейсов сведения о типе, предоставляемых объектом.  
  
```  
virtual UINT GetTypeInfoCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество интерфейсов сведения о типе.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член в основном реализуется [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12).  
  
 Производные классы должны переопределить эту функцию для возврата числа интерфейсов тип сведений, предоставляемых (0 или 1). Если не переопределен, **GetTypeInfoCount** возвращает 0. Чтобы переопределить, используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макросом, который также реализует `GetTypeLib` и `GetTypeLibCache`.  
  
##  <a name="gettypeinfoofguid"></a>  CCmdTarget::GetTypeInfoOfGuid  
 Извлекает описание типа, соответствующее заданному идентификатору GUID.  
  
```  
HRESULT GetTypeInfoOfGuid(
    LCID lcid,  
    const GUID& guid,  
    LPTYPEINFO* ppTypeInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `lcid`  
 Идентификатор языкового стандарта ( `LCID`).  
  
 `guid`  
 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931) описания типа.  
  
 `ppTypeInfo`  
 Указатель на указатель на `ITypeInfo` интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение HRESULT, указывающее, успешно ли выполнен вызов. В случае успешного выполнения * `ppTypeInfo` указывает на интерфейс типа сведений.  
  
##  <a name="gettypelib"></a>  CCmdTarget::GetTypeLib  
 Возвращает указатель на библиотеку типов.  
  
```  
virtual HRESULT GetTypeLib(
    LCID lcid,  
    LPTYPELIB* ppTypeLib);
```  
  
### <a name="parameters"></a>Параметры  
 `lcid`  
 Идентификатор языкового стандарта ( `LCID`).  
  
 `ppTypeLib`  
 Указатель на указатель на `ITypeLib` интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение HRESULT, указывающее, успешно ли выполнен вызов. В случае успешного выполнения * `ppTypeLib` указывает на интерфейс библиотеки типов.  
  
### <a name="remarks"></a>Примечания  
 Производные классы должны переопределить эту функцию-член (если не переопределен, `GetTypeLib` возвращает TYPE_E_CANTLOADLIBRARY). Используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макросом, который также реализует `GetTypeInfoCount` и `GetTypeLibCache`.  
  
##  <a name="gettypelibcache"></a>  CCmdTarget::GetTypeLibCache  
 Возвращает кэш библиотеки типов.  
  
```  
virtual CTypeLibCache* GetTypeLibCache();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **CTypeLibCache** объекта.  
  
### <a name="remarks"></a>Примечания  
 Производные классы должны переопределить эту функцию-член (если не переопределен, **GetTypeLibCache** возвращает значение NULL). Используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макросом, который также реализует `GetTypeInfoCount` и `GetTypeLib`.  
  
##  <a name="isinvokeallowed"></a>  CCmdTarget::IsInvokeAllowed  
 Эта функция вызывается с реализации MFC **IDispatch::Invoke** для определения метода данного автоматизации (определяется `dispid`) может быть вызван.  
  
```  
virtual BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод может быть вызванным, в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Если `IsInvokeAllowed` возвращает значение TRUE, **Invoke** выполняет вызов метода; в противном случае `Invoke` завершится ошибкой, возвращая E_UNEXPECTED.  
  
 Производные классы могут переопределить эту функцию для возврата соответствующего значения (если не переопределен, `IsInvokeAllowed` возвращает значение TRUE). См. в частности [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).  
  
##  <a name="isresultexpected"></a>  CCmdTarget::IsResultExpected  
 Используйте `IsResultExpected` чтобы выяснить, является ли клиент ожидает значение, возвращаемое из вызова его функции автоматизации.  
  
```  
BOOL IsResultExpected();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция автоматизации должна возвращать значение; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Интерфейс OLE предоставляет информацию о ли клиент с помощью или без учета результата вызова функции MFC, а MFC, в свою очередь, использует эти сведения для определения результата вызова `IsResultExpected`. Если производства, возвращаемое значение или ресурсов много времени, можно повысить эффективность путем вызова этой функции перед вычислением возвращаемое значение.  
  
 Эта функция возвращает 0 только в том случае, когда, что позволяет получить допустимый возвращаемые значения от других функций автоматизации при вызове их из функции автоматизации, называется клиента.  
  
 `IsResultExpected` возвращает ненулевое значение, если вызывается, когда вызов функции автоматизации не выполняется.  
  
##  <a name="oncmdmsg"></a>  CCmdTarget::OnCmdMsg  
 Вызывается платформой для маршрутизации и отправления сообщения команд и для обработки обновление объектов пользовательского интерфейса команд.  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Содержит идентификатор команды.  
  
 `nCode`  
 Определяет код команды уведомления. В разделе **примечания** Дополнительные сведения о значениях `nCode`.  
  
 `pExtra`  
 Используется в соответствии со значением `nCode`. В разделе **примечания** Дополнительные сведения о `pExtra`.  
  
 `pHandlerInfo`  
 В противном случае **NULL**, `OnCmdMsg` заполняет **pTarget** и **pmf** члены `pHandlerInfo` структуры вместо команды диспетчеризации. Как правило, этот параметр должен быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение обработано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это процедура реализации архитектуры команда framework.  
  
 Во время выполнения `OnCmdMsg` отправляет команды на другие объекты или обрабатывает самой команде, вызвав корневой класс `CCmdTarget::OnCmdMsg`, который выполняет Просмотр фактических схему сообщений. Полное описание маршрутизация команд по умолчанию см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
 В редких случаях может потребоваться переопределить эту функцию-член для расширения framework стандартной маршрутизации команд. Ссылаться на [Технические заметки 21](../../mfc/tn021-command-and-message-routing.md) расширенные сведения архитектура маршрутизации команд.  
  
 При переопределении `OnCmdMsg`, необходимо указать соответствующее значение для `nCode`, кода команды уведомления и `pExtra`, которая зависит от значения `nCode`. В следующей таблице перечислены соответствующие им значения:  
  
|Значение `nCode`|Значение `pExtra`|  
|-------------------|--------------------|  
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)*|  
|CN_EVENT|AFX_EVENT *|  
|CN_UPDATE_COMMAND_UI|CCmdUI *|  
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)*|  
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
 Эта функция вызывается для восстановления соответствующий курсор с песочными часами после изменения системного курсора (например, после окно сообщения открытых и закрытых затем в середине длительной операции).  
  
```  
void RestoreWaitCursor();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC ACDUAL](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdUI-класс](../../mfc/reference/ccmdui-class.md)   
 [CDocument-класс](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [CWinApp-класс](../../mfc/reference/cwinapp-class.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Класс COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)
