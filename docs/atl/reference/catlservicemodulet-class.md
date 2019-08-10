---
title: Класс функция CAtlServiceModuleT
ms.date: 05/06/2019
f1_keywords:
- CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::Handler
- ATLBASE/ATL::CAtlServiceModuleT::InitializeSecurity
- ATLBASE/ATL::CAtlServiceModuleT::Install
- ATLBASE/ATL::CAtlServiceModuleT::IsInstalled
- ATLBASE/ATL::CAtlServiceModuleT::LogEvent
- ATLBASE/ATL::CAtlServiceModuleT::OnContinue
- ATLBASE/ATL::CAtlServiceModuleT::OnInterrogate
- ATLBASE/ATL::CAtlServiceModuleT::OnPause
- ATLBASE/ATL::CAtlServiceModuleT::OnShutdown
- ATLBASE/ATL::CAtlServiceModuleT::OnStop
- ATLBASE/ATL::CAtlServiceModuleT::OnUnknownRequest
- ATLBASE/ATL::CAtlServiceModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlServiceModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlServiceModuleT::RegisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::Run
- ATLBASE/ATL::CAtlServiceModuleT::ServiceMain
- ATLBASE/ATL::CAtlServiceModuleT::SetServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::Start
- ATLBASE/ATL::CAtlServiceModuleT::Uninstall
- ATLBASE/ATL::CAtlServiceModuleT::Unlock
- ATLBASE/ATL::CAtlServiceModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::WinMain
- ATLBASE/ATL::CAtlServiceModuleT::m_bService
- ATLBASE/ATL::CAtlServiceModuleT::m_dwThreadID
- ATLBASE/ATL::CAtlServiceModuleT::m_hServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::m_status
- ATLBASE/ATL::CAtlServiceModuleT::m_szServiceName
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
ms.openlocfilehash: 095d909fefe0053b742368f260cf61937c2f5426
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915872"
---
# <a name="catlservicemodulet-class"></a>Класс функция CAtlServiceModuleT

Этот класс реализует службу.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T, UINT nServiceNameID>
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный `CAtlServiceModuleT`от.

*нсервиценамеид*<br/>
Идентификатор ресурса службы.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Функция CAtlServiceModuleT:: функция CAtlServiceModuleT](#catlservicemodulet)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Функция CAtlServiceModuleT:: Handler](#handler)|Подпрограммы обработчика для службы.|
|[Функция CAtlServiceModuleT:: Инитиализесекурити](#initializesecurity)|Предоставляет параметры безопасности по умолчанию для службы.|
|[Функция CAtlServiceModuleT:: install](#install)|Устанавливает и создает службу.|
|[Функция CAtlServiceModuleT:: устанавливаются](#isinstalled)|Подтверждает, что служба установлена.|
|[Функция CAtlServiceModuleT:: LogEvent](#logevent)|Выполняет запись в журнал событий.|
|[Функция CAtlServiceModuleT:: OnContinue](#oncontinue)|Переопределите этот метод, чтобы продолжить работу службы.|
|[Функция CAtlServiceModuleT:: oninterrogat](#oninterrogate)|Переопределите этот метод для опроса службы.|
|[Функция CAtlServiceModuleT:: OnPause](#onpause)|Переопределите этот метод, чтобы приостановить работу службы.|
|[Функция CAtlServiceModuleT:: OnShutdown](#onshutdown)|Переопределите этот метод, чтобы завершить работу службы|
|[Функция CAtlServiceModuleT:: OnStop](#onstop)|Переопределите этот метод, чтобы отключить службу|
|[Функция CAtlServiceModuleT:: Онункновнрекуест](#onunknownrequest)|Переопределите этот метод для обработки неизвестных запросов к службе|
|[Функция CAtlServiceModuleT::P Арсекоммандлине](#parsecommandline)|Анализирует командную строку и при необходимости выполняет регистрацию.|
|[Функция CAtlServiceModuleT::P Ремессажелуп](#premessageloop)|Этот метод вызывается непосредственно перед входом в цикл обработки сообщений.|
|[Функция CAtlServiceModuleT:: Регистераппид](#registerappid)|Регистрирует службу в реестре.|
|[Функция CAtlServiceModuleT:: Run](#run)|Запускает службу.|
|[Функция CAtlServiceModuleT:: ServiceMain](#servicemain)|Метод, вызываемый диспетчером управления службами.|
|[Функция CAtlServiceModuleT:: сбой SetServiceStatus](#setservicestatus)|Обновляет состояние службы.|
|[Функция CAtlServiceModuleT:: Start](#start)|Вызывается `CAtlServiceModuleT::WinMain` при запуске службы.|
|[Функция CAtlServiceModuleT:: Uninstall](#uninstall)|Останавливает и удаляет службу.|
|[Функция CAtlServiceModuleT:: Unlock](#unlock)|Уменьшает счетчик блокировок службы.|
|[Функция CAtlServiceModuleT:: Унрегистераппид](#unregisterappid)|Удаляет службу из реестра.|
|[Функция CAtlServiceModuleT:: WinMain](#winmain)|Этот метод реализует код, необходимый для запуска службы.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Функция CAtlServiceModuleT:: m_bService](#m_bservice)|Флаг, указывающий, что программа запущена как служба.|
|[Функция CAtlServiceModuleT:: m_dwThreadID](#m_dwthreadid)|Переменная члена, в которой хранится идентификатор потока.|
|[Функция CAtlServiceModuleT:: m_hServiceStatus](#m_hservicestatus)|Переменная-член хранит маркер в структуре сведений о состоянии для текущей службы.|
|[Функция CAtlServiceModuleT:: M_STATUS](#m_status)|Переменная члена, в которой хранится структура сведений о состоянии для текущей службы.|
|[Функция CAtlServiceModuleT:: m_szServiceName](#m_szservicename)|Имя регистрируемой службы.|

## <a name="remarks"></a>Примечания

`CAtlServiceModuleT`, производный от [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), реализует модуль службы ATL. `CAtlServiceModuleT`предоставляет методы для обработки, установки, регистрации и удаления из командной строки. Если требуются дополнительные функциональные возможности, эти и другие методы можно переопределить.

Этот класс заменяет устаревший [класс CComModule](../../atl/reference/ccommodule-class.md) , используемый в более ранних версиях ATL. Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[катлмодуле](../../atl/reference/catlmodule-class.md)

[катлмодулет](../../atl/reference/catlmodulet-class.md)

[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="catlservicemodulet"></a>Функция CAtlServiceModuleT:: функция CAtlServiceModuleT

Конструктор.

```
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует элементы данных и задает начальное состояние службы.

##  <a name="handler"></a>Функция CAtlServiceModuleT:: Handler

Подпрограммы обработчика для службы.

```
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>Параметры

*двопкоде*<br/>
Параметр, определяющий операцию обработчика. Дополнительные сведения см. в разделе Примечания.

### <a name="remarks"></a>Примечания

Это код, который вызывает диспетчер управления службами (SCM) для получения состояния службы и выполнения инструкций, таких как остановка или приостановка. SCM передает код операции, показанный ниже, чтобы `Handler` указать, что должна делать служба.

|Код операции|Значение|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|Останавливает службу. Переопределите метод [функция CAtlServiceModuleT:: OnStop](#onstop) в ATLBASE. h, чтобы изменить поведение.|
|SERVICE_CONTROL_PAUSE|Реализовано пользователем. Переопределите пустой метод [функция CAtlServiceModuleT:: OnPause](#onpause) в ATLBASE. h, чтобы приостановить работу службы.|
|SERVICE_CONTROL_CONTINUE|Реализовано пользователем. Переопределите пустой метод [функция CAtlServiceModuleT:: OnContinue](#oncontinue) в ATLBASE. h, чтобы продолжить работу службы.|
|SERVICE_CONTROL_INTERROGATE|Реализовано пользователем. Переопределите пустой метод [функция CAtlServiceModuleT:: oninterrogat](#oninterrogate) в ATLBASE. h для опроса службы.|
|SERVICE_CONTROL_SHUTDOWN|Реализовано пользователем. Переопределите пустой метод [функция CAtlServiceModuleT:: OnShutdown](#onshutdown) в ATLBASE. h, чтобы завершить работу службы.|

Если код операции не распознан, вызывается метод [функция CAtlServiceModuleT:: онункновнрекуест](#onunknownrequest) .

Служба, создаваемая библиотекой ATL по умолчанию, обрабатывает только инструкцию по ошибке. Если SCM передает инструкцию по остановке, служба сообщает SCM о том, что программа собирается остановиться. Затем служба вызывает `PostThreadMessage` метод, чтобы отправить сообщение о выходе на себя. Это завершает цикл обработки сообщений, и служба в конечном итоге будет закрыта.

##  <a name="initializesecurity"></a>Функция CAtlServiceModuleT:: Инитиализесекурити

Предоставляет параметры безопасности по умолчанию для службы.

```
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Любой класс, производный от `CAtlServiceModuleT` , должен реализовывать этот метод в производном классе.

Используйте проверку подлинности на `CoInitializeSecurity`уровне маркера, уровень олицетворения RPC_C_IMP_LEVEL_IDENTIFY и соответствующий дескриптор безопасности, отличный от NULL, в вызове метода.

Для созданных мастером проектов служб, не имеющих атрибута, это будет

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

Для проектов служб с атрибутами это будет в

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

##  <a name="install"></a>Функция CAtlServiceModuleT:: install

Устанавливает и создает службу.

```
BOOL Install() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Устанавливает службу в базу данных диспетчера управления службами (SCM), а затем создает объект службы. Если службу не удалось создать, отображается окно сообщения, а метод возвращает значение FALSE.

##  <a name="isinstalled"></a>Функция CAtlServiceModuleT:: устанавливаются

Подтверждает, что служба установлена.

```
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если служба установлена, и FALSE в противном случае.

##  <a name="logevent"></a>Функция CAtlServiceModuleT:: LogEvent

Выполняет запись в журнал событий.

```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>Параметры

*псзформат*<br/>
Строка для записи в журнал событий.

*...*<br/>
Необязательные дополнительные строки для записи в журнал событий.

### <a name="remarks"></a>Примечания

Этот метод записывает сведения в журнал событий с помощью функции [репортевент](/windows/desktop/api/winbase/nf-winbase-reporteventa). Если служба не запущена, строка отправляется в консоль.

##  <a name="m_bservice"></a>Функция CAtlServiceModuleT:: m_bService

Флаг, указывающий, что программа запущена как служба.

```
BOOL m_bService;
```

### <a name="remarks"></a>Примечания

Используется для различения EXE-файла службы от исполняемого файла приложения.

##  <a name="m_dwthreadid"></a>Функция CAtlServiceModuleT:: m_dwThreadID

Переменная члена, в которой хранится идентификатор потока службы.

```
DWORD m_dwThreadID;
```

### <a name="remarks"></a>Примечания

Эта переменная хранит идентификатор потока текущего потока.

##  <a name="m_hservicestatus"></a>Функция CAtlServiceModuleT:: m_hServiceStatus

Переменная-член хранит маркер в структуре сведений о состоянии для текущей службы.

```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>Примечания

Структура [SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-service_status) содержит сведения о службе.

##  <a name="m_status"></a>Функция CAtlServiceModuleT:: M_STATUS

Переменная члена, в которой хранится структура сведений о состоянии для текущей службы.

```
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>Примечания

Структура [SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-service_status) содержит сведения о службе.

##  <a name="m_szservicename"></a>Функция CAtlServiceModuleT:: m_szServiceName

Имя регистрируемой службы.

```
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>Примечания

Строка, завершающаяся нулем, в которой хранится имя службы.

##  <a name="oncontinue"></a>Функция CAtlServiceModuleT:: OnContinue

Переопределите этот метод, чтобы продолжить работу службы.

```
void OnContinue() throw();
```

##  <a name="oninterrogate"></a>Функция CAtlServiceModuleT:: oninterrogat

Переопределите этот метод для опроса службы.

```
void OnInterrogate() throw();
```

##  <a name="onpause"></a>Функция CAtlServiceModuleT:: OnPause

Переопределите этот метод, чтобы приостановить работу службы.

```
void OnPause() throw();
```

##  <a name="onshutdown"></a>Функция CAtlServiceModuleT:: OnShutdown

Переопределите этот метод, чтобы завершить работу службы.

```
void OnShutdown() throw();
```

##  <a name="onstop"></a>Функция CAtlServiceModuleT:: OnStop

Переопределите этот метод, чтобы отключить службу.

```
void OnStop() throw();
```

##  <a name="onunknownrequest"></a>Функция CAtlServiceModuleT:: Онункновнрекуест

Переопределите этот метод для обработки неизвестных запросов к службе.

```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>Параметры

*двопкоде*<br/>
Зарезервировано.

##  <a name="parsecommandline"></a>Функция CAtlServiceModuleT::P Арсекоммандлине

Анализирует командную строку и при необходимости выполняет регистрацию.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Параметры

*лпкмдлине*<br/>
Командная строка.

*пнреткоде*<br/>
Значение HRESULT, соответствующее регистрации (если оно было принято).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true при успешном выполнении или значение false, если не удалось зарегистрировать RGS файл, указанный в командной строке.

### <a name="remarks"></a>Примечания

Анализирует командную строку и регистрирует или отменяет регистрацию в заданном RGSм файле, если это необходимо. Этот метод вызывает [CAtlExeModuleT::P арсекоммандлине](../../atl/reference/catlexemodulet-class.md#parsecommandline) для проверки **/regserver** и **/UnregServer**. При добавлении аргумента **-свойством/Service** будет зарегистрирована служба.

##  <a name="premessageloop"></a>Функция CAtlServiceModuleT::P Ремессажелуп

Этот метод вызывается непосредственно перед входом в цикл обработки сообщений.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*ншовкмд*<br/>
Этот параметр передается в [CAtlExeModuleT::P ремессажелуп](../../atl/reference/catlexemodulet-class.md#premessageloop).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы добавить пользовательский код инициализации для службы.

##  <a name="registerappid"></a>Функция CAtlServiceModuleT:: Регистераппид

Регистрирует службу в реестре.

```
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>Параметры

*бсервице*<br/>
Для регистрации в качестве службы должно быть задано значение true.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

##  <a name="run"></a>Функция CAtlServiceModuleT:: Run

Запускает службу.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Параметры

*ншовкмд*<br/>
Указывает способ отображения окна. Этот параметр может принимать одно из значений, описанных в разделе [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) . Значение по умолчанию — SW_HIDE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

После `Run` вызова вызывается метод [функция CAtlServiceModuleT::P ремессажелуп](#premessageloop), [CAtlExeModuleT:: рунмессажелуп](../../atl/reference/catlexemodulet-class.md#runmessageloop)и [CAtlExeModuleT::P остмессажелуп](../../atl/reference/catlexemodulet-class.md#postmessageloop).

##  <a name="servicemain"></a>Функция CAtlServiceModuleT:: ServiceMain

Этот метод вызывается диспетчером управления службами.

```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>Параметры

*дваргк*<br/>
Аргумент argc.

*лпсзаргв*<br/>
Аргумент argv.

### <a name="remarks"></a>Примечания

Диспетчер управления службами вызывается `ServiceMain` при открытии приложения службы на панели управления, выборе службы и нажатии кнопки запустить.

После вызова `ServiceMain`SCM служба должна предоставить SCM функцию обработчика. Эта функция позволяет SCM получать состояние службы и передавать конкретные инструкции (такие как приостановка или остановка). Впоследствии метод [функция CAtlServiceModuleT:: Run](#run) вызывается для выполнения основной работы службы. `Run`будет выполняться до тех пор, пока служба не будет остановлена.

##  <a name="setservicestatus"></a>Функция CAtlServiceModuleT:: сбой SetServiceStatus

Этот метод обновляет состояние службы.

```
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>Параметры

*двстате*<br/>
Новое состояние. Возможные значения см. в разделе [сбой SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) .

### <a name="remarks"></a>Примечания

Обновляет сведения о состоянии диспетчера управления службами для службы. Он вызывается методом [функция CAtlServiceModuleT:: Run](#run), [функция CAtlServiceModuleT:: ServiceMain](#servicemain) и другими методами обработчика. Состояние также хранится в переменной-члене [функция CAtlServiceModuleT:: M_STATUS](#m_status).

##  <a name="start"></a>Функция CAtlServiceModuleT:: Start

Вызывается `CAtlServiceModuleT::WinMain` при запуске службы.

```
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*ншовкмд*<br/>
Указывает способ отображения окна. Этот параметр может принимать одно из значений, описанных в разделе [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Метод [функция CAtlServiceModuleT:: WinMain](#winmain) обрабатывает регистрацию и установку, а также задачи, связанные с удалением записей реестра и удаления модуля. При запуске `WinMain` службы вызывает метод `Start`.

##  <a name="uninstall"></a>Функция CAtlServiceModuleT:: Uninstall

Останавливает и удаляет службу.

```
BOOL Uninstall() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Останавливает работу службы и удаляет ее из базы данных диспетчера управления службами.

##  <a name="unlock"></a>Функция CAtlServiceModuleT:: Unlock

Уменьшает счетчик блокировок службы.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает счетчик блокировок, который может быть полезен для диагностики и отладки.

##  <a name="unregisterappid"></a>Функция CAtlServiceModuleT:: Унрегистераппид

Удаляет службу из реестра.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

##  <a name="winmain"></a>Функция CAtlServiceModuleT:: WinMain

Этот метод реализует код, необходимый для запуска службы.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*ншовкмд*<br/>
Указывает способ отображения окна. Этот параметр может принимать одно из значений, описанных в разделе [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает возвращаемое значение службы.

### <a name="remarks"></a>Примечания

Этот метод обрабатывает командную строку (WITH [функция CAtlServiceModuleT::P арсекоммандлине](#parsecommandline)), а затем запускает службу (с помощью [функция CAtlServiceModuleT:: Start](#start)).

## <a name="see-also"></a>См. также

[Класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
