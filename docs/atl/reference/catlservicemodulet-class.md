---
title: Класс CAtlServiceModuleT
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
ms.openlocfilehash: 6d1985384c2d9a324abac548f27be6be5f0cacf5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748589"
---
# <a name="catlservicemodulet-class"></a>Класс CAtlServiceModuleT

Этот класс реализует службу.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T, UINT nServiceNameID>
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс происходит `CAtlServiceModuleT`от .

*nServiceNameID*<br/>
Идентификатор ресурса службы.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlServiceModuleT:::CAtlServiceModuleT](#catlservicemodulet)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlServiceModuleT::Handler](#handler)|Режим обработчика для службы.|
|[CAtlServiceModuleT::Первоначальнаябезопасность](#initializesecurity)|Обеспечивает настройки безопасности службы по умолчанию.|
|[CAtlServiceModuleT::Установка](#install)|Устанавливает и создает сервис.|
|[CAtlServiceModuleT::Устанавливается](#isinstalled)|Подтверждает, что услуга установлена.|
|[CAtlServiceModuleT::LogEvent](#logevent)|Записывает журнал событий.|
|[CAtlServiceModulet::Oncontinue](#oncontinue)|Переопределить этот метод для продолжения службы.|
|[CAtlServiceModuleT::На допросе](#oninterrogate)|Переопределить этот метод, чтобы допросить службу.|
|[CAtlServiceModulet::OnPause](#onpause)|Переопределить этот метод, чтобы приостановить службу.|
|[CAtlServiceModulet::Onshutdown](#onshutdown)|Переопределить этот метод, чтобы отключить службу|
|[CAtlServiceModulet::Onstop](#onstop)|Переопределить этот метод, чтобы остановить службу|
|[CAtlServiceModulet::Запрос](#onunknownrequest)|Переопределить этот метод для обработки неизвестных запросов в службу|
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Сравнивает командную строку и при необходимости выполняет регистрацию.|
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Этот метод вызывается непосредственно перед входом в цикл сообщения.|
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Регистрирует услугу в реестре.|
|[CAtlServiceModuleT::Run](#run)|Запускает службу.|
|[CAtlServiceModuleT::ServiceMain](#servicemain)|Метод, вызванный менеджером управления службой.|
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Обновление статуса службы.|
|[CAtlServiceModuleT::Начало](#start)|Вызывается, `CAtlServiceModuleT::WinMain` когда служба начинается.|
|[CAtlServiceModuleT::Uninstall](#uninstall)|Останавливает и удаляет службу.|
|[CAtlServiceModuleT::Разблокировка](#unlock)|Декретирует количество блокировки службы.|
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Удаляет службу из реестра.|
|[CAtlServiceModuleT::WinMain](#winmain)|Этот метод реализует код, необходимый для запуска службы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlServiceModuleT:::m_bService](#m_bservice)|Пометить, указывающую на запуск программы как службу.|
|[CAtlServiceModuleT:::m_dwThreadID](#m_dwthreadid)|Переменная переменная, хранят идентификатор потока.|
|[CAtlServiceModuleT:::m_hServiceStatus](#m_hservicestatus)|Переменная переменная, хратрансющая ручку в структуре информации о состоянии для текущей службы.|
|[CAtlServiceModuleT:::m_status](#m_status)|Переменная переменная, хратрансющая структуру информации о состоянии для текущей службы.|
|[CAtlServiceModuleT:::m_szServiceName](#m_szservicename)|Название зарегистрированной службы.|

## <a name="remarks"></a>Remarks

`CAtlServiceModuleT`, полученные от [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), реализует модуль службы ATL. `CAtlServiceModuleT`предоставляет методы обработки, установки, регистрации и удаления командной строки. Если требуется дополнительная функциональность, эти и другие методы могут быть переопределены.

Этот класс заменяет устаревший [класс CComModule,](../../atl/reference/ccommodule-class.md) используемый в более ранних версиях ATL. Более подробную информацию можно узнать на [примере классов atL Module.](../../atl/atl-module-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlservicemoduletcatlservicemodulet"></a><a name="catlservicemodulet"></a>CAtlServiceModuleT:::CAtlServiceModuleT

Конструктор.

```
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>Remarks

Инициализирует членов данных и устанавливает исходный статус службы.

## <a name="catlservicemodulethandler"></a><a name="handler"></a>CAtlServiceModuleT::Handler

Режим обработчика для службы.

```cpp
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>Параметры

*dwOpcode*<br/>
Переключатель, определяющий операцию обработчика. Для получения подробной информации, см.

### <a name="remarks"></a>Remarks

Это код, который вызывает диспетчер службы (SCM) для получения статуса службы и выдачи инструкций, таких как остановка или пауза. SCM передает код операции, показанный `Handler` ниже, чтобы указать, что служба должна делать.

|Код операции|Значение|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|останавливает службу. Переопределить метод [CAtlServiceModuleT::OnStop](#onstop) в atlbase.h, чтобы изменить поведение.|
|SERVICE_CONTROL_PAUSE|Пользователь реализован. Переопределить пустой метод [CAtlServiceModuleT::OnPause](#onpause) в atlbase.h, чтобы приостановить обслуживание.|
|SERVICE_CONTROL_CONTINUE|Пользователь реализован. Переопределить пустой метод [CAtlServiceModuleT::Продолжить](#oncontinue) в atlbase.h, чтобы продолжить обслуживание.|
|SERVICE_CONTROL_INTERROGATE|Пользователь реализован. Переопределить пустой метод [CAtlServiceModuleT::OnInterrogate](#oninterrogate) в atlbase.h, чтобы допросить службу.|
|SERVICE_CONTROL_SHUTDOWN|Пользователь реализован. Переопределить пустой метод [CAtlServiceModuleT::OnShutdown](#onshutdown) в atlbase.h для выключения службы.|

Если код операции не распознается, называется метод [CAtlServiceModuleT::OnUnknownRequest.](#onunknownrequest)

Служба ATL, генерируемая по умолчанию, обрабатывает только инструкцию stop. Если SCM проходит инструкцию остановки, служба сообщает SCM, что программа вот-вот остановится. Затем служба `PostThreadMessage` призывает опубликовать сообщение о выходе из эксплуатации. Это завершает цикл сообщения, и служба в конечном счете закроется.

## <a name="catlservicemoduletinitializesecurity"></a><a name="initializesecurity"></a>CAtlServiceModuleT::Первоначальнаябезопасность

Обеспечивает настройки безопасности службы по умолчанию.

```
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Любой класс, `CAtlServiceModuleT` полученный от должен реализовать этот метод в производном классе.

Используйте проверку подлинности уровня PKT, уровень олицетворения RPC_C_IMP_LEVEL_IDENTIFY и соответствующий дескриптор безопасности без нулевых в вызове. `CoInitializeSecurity`

Для проектов несвязанных услуг, генерируемых мастерами, это

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

Для приписываемых проектов обслуживания это будет в

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

## <a name="catlservicemoduletinstall"></a><a name="install"></a>CAtlServiceModuleT::Установка

Устанавливает и создает сервис.

```
BOOL Install() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Устанавливает службу в базу данных диспетчера службы (SCM), а затем создает объект службы. Если служба не может быть создана, отображается окно сообщений и метод возвращает FALSE.

## <a name="catlservicemoduletisinstalled"></a><a name="isinstalled"></a>CAtlServiceModuleT::Устанавливается

Подтверждает, что услуга установлена.

```
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если услуга установлена, FALSE в противном случае.

## <a name="catlservicemoduletlogevent"></a><a name="logevent"></a>CAtlServiceModuleT::LogEvent

Записывает журнал событий.

```cpp
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>Параметры

*pszFormat*<br/>
Строка для записи в журнал событий.

*...*<br/>
Дополнительные дополнительные строки для записания в журнал событий.

### <a name="remarks"></a>Remarks

Этот метод записывает детали в журнал событий, используя функцию [ReportEvent.](/windows/win32/api/winbase/nf-winbase-reporteventw) Если служба не работает, строка отправляется на консоль.

## <a name="catlservicemoduletm_bservice"></a><a name="m_bservice"></a>CAtlServiceModuleT:::m_bService

Пометить, указывающую на запуск программы как службу.

```
BOOL m_bService;
```

### <a name="remarks"></a>Remarks

Используется для отличия службы EXE от приложения EXE.

## <a name="catlservicemoduletm_dwthreadid"></a><a name="m_dwthreadid"></a>CAtlServiceModuleT:::m_dwThreadID

Переменная переменная, хранят идентификатор потока Службы.

```
DWORD m_dwThreadID;
```

### <a name="remarks"></a>Remarks

Эта переменная хранит идентификатор потока текущего потока.

## <a name="catlservicemoduletm_hservicestatus"></a><a name="m_hservicestatus"></a>CAtlServiceModuleT:::m_hServiceStatus

Переменная переменная, хратрансющая ручку в структуре информации о состоянии для текущей службы.

```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>Remarks

Структура [SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) содержит информацию об услуге.

## <a name="catlservicemoduletm_status"></a><a name="m_status"></a>CAtlServiceModuleT:::m_status

Переменная переменная, хратрансющая структуру информации о состоянии для текущей службы.

```
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>Remarks

Структура [SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) содержит информацию об услуге.

## <a name="catlservicemoduletm_szservicename"></a><a name="m_szservicename"></a>CAtlServiceModuleT:::m_szServiceName

Название зарегистрированной службы.

```
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>Remarks

Нулевая строка, в которой хранится название службы.

## <a name="catlservicemoduletoncontinue"></a><a name="oncontinue"></a>CAtlServiceModulet::Oncontinue

Переопределить этот метод для продолжения службы.

```cpp
void OnContinue() throw();
```

## <a name="catlservicemoduletoninterrogate"></a><a name="oninterrogate"></a>CAtlServiceModuleT::На допросе

Переопределить этот метод, чтобы допросить службу.

```cpp
void OnInterrogate() throw();
```

## <a name="catlservicemoduletonpause"></a><a name="onpause"></a>CAtlServiceModulet::OnPause

Переопределить этот метод, чтобы приостановить службу.

```cpp
void OnPause() throw();
```

## <a name="catlservicemoduletonshutdown"></a><a name="onshutdown"></a>CAtlServiceModulet::Onshutdown

Переопределить этот метод, чтобы отключить службу.

```cpp
void OnShutdown() throw();
```

## <a name="catlservicemoduletonstop"></a><a name="onstop"></a>CAtlServiceModulet::Onstop

Переопределить этот метод, чтобы остановить службу.

```cpp
void OnStop() throw();
```

## <a name="catlservicemoduletonunknownrequest"></a><a name="onunknownrequest"></a>CAtlServiceModulet::Запрос

Переопределить этот метод для обработки неизвестных запросов в службу.

```cpp
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>Параметры

*dwOpcode*<br/>
Зарезервировано.

## <a name="catlservicemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlServiceModuleT::ParseCommandLine

Сравнивает командную строку и при необходимости выполняет регистрацию.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Параметры

*lpCmdLine*<br/>
Командная строка.

*pnRetCode*<br/>
HRESULT, соответствующий регистрации (если она состоялась).

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно на успех, или ложные, если файл RGS поставляется в командной строке не может быть зарегистрирован.

### <a name="remarks"></a>Remarks

При необходимости сравнивает командную строку и регистрирует или отменяет предоставленный файл RGS. Этот метод вызывает [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) для того чтобы проверить для **/RegServer** и **/UnregServer**. Добавление аргумента **-/Сервис** зарегистрирует службу.

## <a name="catlservicemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlServiceModuleT::PreMessageLoop

Этот метод вызывается непосредственно перед входом в цикл сообщения.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Этот параметр передается [в CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Переопределить этот метод, чтобы добавить пользовательский код инициализации для Службы.

## <a name="catlservicemoduletregisterappid"></a><a name="registerappid"></a>CAtlServiceModuleT::RegisterAppId

Регистрирует услугу в реестре.

```
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>Параметры

*bService*<br/>
Должно быть верно зарегистрироваться в качестве службы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catlservicemoduletrun"></a><a name="run"></a>CAtlServiceModuleT::Run

Запускает службу.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Определяет, как будет отображаться окно. Этот параметр может быть одним из значений, обсуждаемых в разделе [WinMain.](/windows/win32/api/winbase/nf-winbase-winmain) Значение по умолчанию является SW_HIDE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

После вызова, `Run` звонки [CAtlServiceModuleT: :PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), и [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).

## <a name="catlservicemoduletservicemain"></a><a name="servicemain"></a>CAtlServiceModuleT::ServiceMain

Этот метод вызывается менеджером управления службой.

```cpp
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>Параметры

*dwArgc*<br/>
Аргумент аргка.

*lpszArgv*<br/>
Аргумент аргова.

### <a name="remarks"></a>Remarks

Менеджер управления службой (SCM) звонит `ServiceMain` при открытии приложения Службы в панели управления, выберите службу и нажмите Кнопка «Старт».

После вызова `ServiceMain`SCM служба должна дать SCM функцию обработчика. Эта функция позволяет SCM получить статус службы и передать конкретные инструкции (например, приостановка или остановка). Впоследствии [CAtlServiceModuleT::Run](#run) призван выполнять основную работу сервиса. `Run`продолжает выполняться до тех пор, пока служба не будет остановлена.

## <a name="catlservicemoduletsetservicestatus"></a><a name="setservicestatus"></a>CAtlServiceModuleT::SetServiceStatus

Этот метод обновляет статус службы.

```cpp
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>Параметры

*dwState*<br/>
Новое состояние. Смотрите [SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus) для возможных значений.

### <a name="remarks"></a>Remarks

Обновление информации о состоянии менеджера службы. Он называется [CAtlServiceModuleT::Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) и другие методы обработчика. Статус также хранится в переменной [cAtlServiceModuleT::m_status](#m_status).

## <a name="catlservicemoduletstart"></a><a name="start"></a>CAtlServiceModuleT::Начало

Вызывается, `CAtlServiceModuleT::WinMain` когда служба начинается.

```
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Определяет, как будет отображаться окно. Этот параметр может быть одним из значений, обсуждаемых в разделе [WinMain.](/windows/win32/api/winbase/nf-winbase-winmain)

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

[Метод CAtlServiceModuleT::WinMain](#winmain) обрабатывает как регистрацию, так и установку, а также задачи, связанные с удалением записей реестра и удалением модуля. При запуске `WinMain` службы `Start`звонят.

## <a name="catlservicemoduletuninstall"></a><a name="uninstall"></a>CAtlServiceModuleT::Uninstall

Останавливает и удаляет службу.

```
BOOL Uninstall() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Останавливает работу службы и удаляет ее из базы данных диспетчера службы.

## <a name="catlservicemoduletunlock"></a><a name="unlock"></a>CAtlServiceModuleT::Разблокировка

Декретирует количество блокировки службы.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает счет блокировки, который может быть полезен для диагностики и отладки.

## <a name="catlservicemoduletunregisterappid"></a><a name="unregisterappid"></a>CAtlServiceModuleT::UnregisterAppId

Удаляет службу из реестра.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catlservicemoduletwinmain"></a><a name="winmain"></a>CAtlServiceModuleT::WinMain

Этот метод реализует код, необходимый для запуска службы.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Определяет, как будет отображаться окно. Этот параметр может быть одним из значений, обсуждаемых в разделе [WinMain.](/windows/win32/api/winbase/nf-winbase-winmain)

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение возврата службы.

### <a name="remarks"></a>Remarks

Этот метод обрабатывает командную строку (с [CAtlServiceModuleT: :ParseCommandLine),](#parsecommandline)а затем запускает службу (с помощью [CAtlServiceModuleT::Start](#start)).

## <a name="see-also"></a>См. также раздел

[Класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
