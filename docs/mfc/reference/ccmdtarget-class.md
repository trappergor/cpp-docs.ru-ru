---
title: "CCmdTarget-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdTarget
dev_langs:
- C++
helpviewer_keywords:
- message maps, CCmdTarget base class
- command targets
- CCmdTarget class
- command routing, command targets
- targets, command
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0b5b7617f6b3d89e454e31c9f95b5d4455569114
ms.lasthandoff: 02/24/2017

---
# <a name="ccmdtarget-class"></a>CCmdTarget-класс
Базовый класс для архитектуры схемы сообщений библиотеки классов Microsoft Foundation.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCmdTarget : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCmdTarget::CCmdTarget](#ccmdtarget)|Создает объект `CCmdTarget`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|Отображает курсор в виде курсор с песочными часами.|  
|[CCmdTarget::DoOleVerb](#dooleverb)|Вызывает определенное командой OLE, выполняемое действие.|  
|[CCmdTarget::EnableAutomation](#enableautomation)|Позволяет OLE-автоматизации для `CCmdTarget` объекта.|  
|[CCmdTarget::EnableConnections](#enableconnections)|Позволяет события через точки подключения.|  
|[CCmdTarget::EnableTypeLib](#enabletypelib)|Включает библиотеку типов объекта.|  
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|Возврат к предыдущей курсора.|  
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Перечисляет команды OLE-объекта.|  
|[CCmdTarget::FromIDispatch](#fromidispatch)|Возвращает указатель на `CCmdTarget` объекта, связанного с `IDispatch` указателя.|  
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Возвращает идентификатор диспетчера основной интерфейс.|  
|[CCmdTarget::GetIDispatch](#getidispatch)|Возвращает указатель на `IDispatch` объекта, связанного с `CCmdTarget` объекта.|  
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|Получает число типа сведения интерфейсов, предоставляемых объектом.|  
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|Извлекает описание типа, соответствующее заданному идентификатору GUID.|  
|[CCmdTarget::GetTypeLib](#gettypelib)|Возвращает указатель на библиотеку типов.|  
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|Возвращает кэш библиотеки типов.|  
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Включает вызов метода автоматизации.|  
|[CCmdTarget::IsResultExpected](#isresultexpected)|Возвращает ненулевое значение, если функцию автоматизации должны возвращать значение.|  
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|Маршруты и отправляет сообщения команд.|  
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Очищает после выпуска последней ссылки OLE.|  
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|Восстанавливает курсор с песочными часами.|  
  
## <a name="remarks"></a>Примечания  
 Схемы сообщений направляет команды или сообщения функции-члены, предназначенный для их обработки. (Команда — сообщение из пункта меню, кнопки или клавиши).  
  
 Структура ключей классы, производные от `CCmdTarget` включают [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), и [CFrameWnd](../../mfc/reference/cframewnd-class.md). Если требуется, чтобы новый класс для обработки сообщений, создайте производный класс от одного из этих `CCmdTarget`-производные классы. Вы редко являются производными от класса `CCmdTarget` напрямую.  
  
 Общие сведения о цели команды и `OnCmdMsg` маршрутизации, в разделе [целей команды](../../mfc/command-targets.md), [маршрутизация команд](../../mfc/command-routing.md), и [сопоставление сообщений](../../mfc/mapping-messages.md).  
  
 `CCmdTarget`включает функции-члены, обработки отображения курсор с песочными часами. Курсор с песочными часами отображаются в том случае, если предполагается, что команду, чтобы занять заметное временной интервал для выполнения.  
  
 Съемы, аналогично схемы сообщений, используются для предоставления OLE-автоматизации `IDispatch` функциональные возможности. Предоставляя этот интерфейс, другими приложениями (например, Visual Basic) можно вызвать в приложении.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namebeginwaitcursora--ccmdtargetbeginwaitcursor"></a><a name="beginwaitcursor"></a>CCmdTarget::BeginWaitCursor  
 Эта функция используется для отображения курсора как песочные часы, когда предполагается, что команду, чтобы занять заметное временной интервал для выполнения.  
  
```  
void BeginWaitCursor();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию, чтобы показать пользователю, что он занят, например при **CDocument** объект загрузки или сохранения самого файла.  
  
 Действия `BeginWaitCursor` не всегда действующие вне обработчика одно сообщение как другие действия, такие как `OnSetCursor` обработки, можно изменить курсор.  
  
 Вызов `EndWaitCursor` для восстановления предыдущего курсора.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="a-nameccmdtargeta--ccmdtargetccmdtarget"></a><a name="ccmdtarget"></a>CCmdTarget::CCmdTarget  
 Создает объект `CCmdTarget`.  
  
```  
CCmdTarget();
```  
  
##  <a name="a-namedooleverba--ccmdtargetdooleverb"></a><a name="dooleverb"></a>CCmdTarget::DoOleVerb  
 Вызывает определенное командой OLE, выполняемое действие.  
  
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
 Указатель на [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) структуру, описывающую событие (например, щелчок), которое вызвало команду.  
  
 `hWndParent`  
 Дескриптор окна документа, содержащего объект.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая координаты в пикселях, определяющие ограничивающий прямоугольник в *hwndParent*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно; в противном случае — FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член по сути является реализацией [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508). Перечисление возможных действий по [CCmdTarget::EnumOleVerbs](#enumoleverbs).  
  
##  <a name="a-nameenableautomationa--ccmdtargetenableautomation"></a><a name="enableautomation"></a>CCmdTarget::EnableAutomation  
 Эта функция вызывается для включения OLE-автоматизации для объекта.  
  
```  
void EnableAutomation();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается из конструктора объекта и должен вызываться только если для класса объявлена карты распределения. Дополнительные сведения об автоматизации см. в статьях [клиентам автоматизации](../../mfc/automation-clients.md) и [серверы автоматизации](../../mfc/automation-servers.md).  
  
##  <a name="a-nameenableconnectionsa--ccmdtargetenableconnections"></a><a name="enableconnections"></a>CCmdTarget::EnableConnections  
 Позволяет события через точки подключения.  
  
```  
void EnableConnections();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы включить точки подключения, вызовите эту функцию-член в конструкторе производного класса.  
  
##  <a name="a-nameenabletypeliba--ccmdtargetenabletypelib"></a><a name="enabletypelib"></a>CCmdTarget::EnableTypeLib  
 Включает библиотеку типов объекта.  
  
```  
void EnableTypeLib();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов функции-члена в конструкторе вашего `CCmdTarget`-производного объекта, если он предоставляет сведения о типе. Дополнительные сведения см. в статье базы знаний Q185720, «Практическое руководство: предоставления сведений о типе из сервера автоматизации MFC.» Статьи базы знаний, доступны в документации по Visual Studio библиотеки MSDN или в [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="a-nameendwaitcursora--ccmdtargetendwaitcursor"></a><a name="endwaitcursor"></a>CCmdTarget::EndWaitCursor  
 Эта функция вызывается после вызова `BeginWaitCursor` функция-член для возврата предыдущего курсора с курсор с песочными часами.  
  
```  
void EndWaitCursor();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа также вызывает эту функцию-член, после вызова курсор с песочными часами.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="a-nameenumoleverbsa--ccmdtargetenumoleverbs"></a><a name="enumoleverbs"></a>CCmdTarget::EnumOleVerbs  
 Перечисляет команды OLE-объекта.  
  
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
  
##  <a name="a-namefromidispatcha--ccmdtargetfromidispatch"></a><a name="fromidispatch"></a>CCmdTarget::FromIDispatch  
 Эта функция вызывается для сопоставления `IDispatch` указателя, полученные от автоматизации функций-членов класса, в `CCmdTarget` объект, реализующий интерфейсы `IDispatch` объекта.  
  
```  
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDispatch`  
 Указатель на объект `IDispatch`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CCmdTarget` объекта, связанного с `lpDispatch`. Эта функция возвращает **NULL** Если `IDispatch` объект не распознан как Microsoft Foundation Class `IDispatch` объекта.  
  
### <a name="remarks"></a>Примечания  
 Результат этой функции является обратным для вызова функции-члена `GetIDispatch`.  
  
##  <a name="a-namegetdispatchiida--ccmdtargetgetdispatchiid"></a><a name="getdispatchiid"></a>CCmdTarget::GetDispatchIID  
 Возвращает идентификатор диспетчера основной интерфейс.  
  
```  
virtual BOOL GetDispatchIID(IID* pIID);
```  
  
### <a name="parameters"></a>Параметры  
 *pIID*  
 Указатель на идентификатор интерфейса ( [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931)).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно; в противном случае — FALSE. В случае успешного выполнения \* *pIID* присваивается идентификатор диспетчера основной интерфейс.  
  
### <a name="remarks"></a>Примечания  
 Производные классы должны переопределять эту функцию-член (если не переопределен, `GetDispatchIID` возвращает значение FALSE). В разделе [COleControl](../../mfc/reference/colecontrol-class.md).  
  
 Дополнительные сведения см. в статье базы знаний Q185720, «Практическое руководство: предоставления сведений о типе из сервера автоматизации MFC.» Статьи базы знаний, доступны в документации по Visual Studio библиотеки MSDN или в [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="a-namegetidispatcha--ccmdtargetgetidispatch"></a><a name="getidispatch"></a>CCmdTarget::GetIDispatch  
 Вызовите эту функцию-член для получения `IDispatch` указатель методом автоматизации, либо возвращает `IDispatch` указателя или принимает `IDispatch` указатель по ссылке.  
  
```  
LPDISPATCH GetIDispatch(BOOL bAddRef);
```  
  
### <a name="parameters"></a>Параметры  
 *bAddRef*  
 Указывает необходимость увеличить счетчик ссылок для объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IDispatch` Указатель, связанный с объектом.  
  
### <a name="remarks"></a>Примечания  
 Для объектов этого вызова `EnableAutomation` их конструкторы, делая их автоматизации включен, эта функция возвращает указатель на реализацию Foundation Class `IDispatch` , используемый клиентами, которые обмениваются данными через `IDispatch` интерфейса. Автоматически при вызове этой функции добавляет ссылку на указатель, поэтому нет необходимости вызова с [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379).  
  
##  <a name="a-namegettypeinfocounta--ccmdtargetgettypeinfocount"></a><a name="gettypeinfocount"></a>CCmdTarget::GetTypeInfoCount  
 Получает число типа сведения интерфейсов, предоставляемых объектом.  
  
```  
virtual UINT GetTypeInfoCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество интерфейсов сведения о типе.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член в основном реализуется [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12).  
  
 Производные классы должны переопределять эту функцию для возврата числа интерфейсов сведения о типе (0 или 1). Если не переопределен, **GetTypeInfoCount** возвращает 0. Чтобы переопределить, используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макросом, который также реализует `GetTypeLib` и `GetTypeLibCache`.  
  
##  <a name="a-namegettypeinfoofguida--ccmdtargetgettypeinfoofguid"></a><a name="gettypeinfoofguid"></a>CCmdTarget::GetTypeInfoOfGuid  
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
  
##  <a name="a-namegettypeliba--ccmdtargetgettypelib"></a><a name="gettypelib"></a>CCmdTarget::GetTypeLib  
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
 Производные классы должны переопределять эту функцию-член (если не переопределен, `GetTypeLib` возвращает TYPE_E_CANTLOADLIBRARY). Используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макросом, который также реализует `GetTypeInfoCount` и `GetTypeLibCache`.  
  
##  <a name="a-namegettypelibcachea--ccmdtargetgettypelibcache"></a><a name="gettypelibcache"></a>CCmdTarget::GetTypeLibCache  
 Возвращает кэш библиотеки типов.  
  
```  
virtual CTypeLibCache* GetTypeLibCache();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **CTypeLibCache** объекта.  
  
### <a name="remarks"></a>Примечания  
 Производные классы должны переопределять эту функцию-член (если не переопределен, **GetTypeLibCache** возвращает значение NULL). Используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макросом, который также реализует `GetTypeInfoCount` и `GetTypeLib`.  
  
##  <a name="a-nameisinvokealloweda--ccmdtargetisinvokeallowed"></a><a name="isinvokeallowed"></a>CCmdTarget::IsInvokeAllowed  
 Эта функция вызывается с MFC реализации **IDispatch::Invoke** для определения метода данного автоматизации (идентифицируются `dispid`) может быть вызван.  
  
```  
virtual BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если этот метод может быть вызываемого, в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Если `IsInvokeAllowed` возвращает значение TRUE, **Invoke** вызывает метод; в противном случае — `Invoke` завершится ошибкой, возвращая E_UNEXPECTED.  
  
 Производные классы могут переопределять эту функцию для возврата соответствующего значения (если не переопределен, `IsInvokeAllowed` возвращает значение TRUE). См. в частности [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).  
  
##  <a name="a-nameisresultexpecteda--ccmdtargetisresultexpected"></a><a name="isresultexpected"></a>CCmdTarget::IsResultExpected  
 Используйте `IsResultExpected` для выяснения, является ли клиент ожидает значение, возвращаемое из вызова функции автоматизации.  
  
```  
BOOL IsResultExpected();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функцию автоматизации должны возвращать значение; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 OLE-интерфейс предоставляет информацию о ли клиент с использованием или без учета результата вызова функции MFC и MFC, в свою очередь, использует эти сведения для определения результата вызова функции `IsResultExpected`. Если производства, возвращаемое значение или ресурсов много времени, можно повысить эффективность путем вызова этой функции перед вычислением возвращаемое значение.  
  
 Эта функция возвращает 0 только в том случае, когда, что позволяет получить допустимые значения, возвращаемого из других функций автоматизации при вызове их из функции автоматизации, называется клиентом.  
  
 `IsResultExpected`возвращает ненулевое значение, если вызывается, когда не выполняется вызов функции автоматизации.  
  
##  <a name="a-nameoncmdmsga--ccmdtargetoncmdmsg"></a><a name="oncmdmsg"></a>CCmdTarget::OnCmdMsg  
 Вызывается платформой для маршрутизации и диспетчеризации сообщений команды и производить обновление объектов пользовательского интерфейса команд.  
  
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
 Если не **NULL**, `OnCmdMsg` заполняет **pTarget** и **pmf** члены `pHandlerInfo` структуры вместо отправки команды. Как правило, этот параметр должен быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение обработано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это процедура реализации архитектуры команду framework.  
  
 Во время выполнения `OnCmdMsg` отправляет команды на другие объекты или обрабатывает самой команды путем вызова корневой класс `CCmdTarget::OnCmdMsg`, который выполняет Просмотр фактических схемы сообщений. Полное описание маршрутизация команд по умолчанию, в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
 В редких случаях может потребоваться переопределить эту функцию-член расширения этой среды стандартной маршрутизации команд. См. [Технические заметки 21](../../mfc/tn021-command-and-message-routing.md) дополнительные подробности архитектуры маршрутизация команд.  
  
 При переопределении `OnCmdMsg`, необходимо указать соответствующее значение для `nCode`, команда код уведомления, и `pExtra`, которых зависит от значения `nCode`. В следующей таблице перечислены соответствующие значения:  
  
|Значение `nCode`|Значение `pExtra`|  
|-------------------|--------------------|  
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)*|  
|CN_EVENT|AFX_EVENT *|  
|CN_UPDATE_COMMAND_UI|CCmdUI *|  
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)*|  
|CN_OLE_UNREGISTER|NULL|  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#44;](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#45;](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]  
  
##  <a name="a-nameonfinalreleasea--ccmdtargetonfinalrelease"></a><a name="onfinalrelease"></a>CCmdTarget::OnFinalRelease  
 Вызывается платформой, когда освобождается последняя ссылка OLE в или из объекта.  
  
```  
virtual void OnFinalRelease();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для обеспечения специальной обработки для данной ситуации. Реализация по умолчанию удаляет объект.  
  
##  <a name="a-namerestorewaitcursora--ccmdtargetrestorewaitcursor"></a><a name="restorewaitcursor"></a>CCmdTarget::RestoreWaitCursor  
 Эта функция вызывается для восстановления соответствующий курсор с песочными часами после изменения системного курсора (например, после установки окно сообщения открытых и закрытых затем в середине длительной операции).  
  
```  
void RestoreWaitCursor();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
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

