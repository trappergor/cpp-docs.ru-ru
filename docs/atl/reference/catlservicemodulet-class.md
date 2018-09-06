---
title: Класс CAtlServiceModuleT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fff071ad298d379dd8d063d5f71287da9a567b49
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755567"
---
# <a name="catlservicemodulet-class"></a>Класс CAtlServiceModuleT

Этот класс реализует службу.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T, UINT nServiceNameID>  
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

#### <a name="parameters"></a>Параметры

*T*  
Ваш класс, производный от `CAtlServiceModuleT`.

*nServiceNameID*  
Идентификатор ресурса службы.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlServiceModuleT::Handler](#handler)|Подпрограмму обработчика для службы.|
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|Предоставляет значение по умолчанию параметры безопасности для службы.|
|[CAtlServiceModuleT::Install](#install)|Устанавливает и создает службу.|
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|Подтверждает, что служба установлена.|
|[CAtlServiceModuleT::LogEvent](#logevent)|Записывает в журнал событий.|
|[CAtlServiceModuleT::OnContinue](#oncontinue)|Переопределите этот метод для продолжения работы службы.|
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|Переопределите этот метод для запроса службы.|
|[CAtlServiceModuleT::OnPause](#onpause)|Переопределите этот метод, чтобы приостановить службу.|
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|Переопределите этот метод, чтобы завершить работу службы|
|[CAtlServiceModuleT::OnStop](#onstop)|Переопределите этот метод, чтобы остановить службу|
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Переопределите этот метод для обработки неизвестных запросов к службе|
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Выполняет синтаксический анализ командной строки и при необходимости выполняет регистрацию.|
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Этот метод вызывается непосредственно перед ввода цикл обработки сообщений.|
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Регистрирует службу в реестре.|
|[CAtlServiceModuleT::Run](#run)|Запущена служба.|
|[CAtlServiceModuleT::ServiceMain](#servicemain)|Метод, вызываемый с помощью диспетчера управления службами.|
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Обновляет состояние службы.|
|[CAtlServiceModuleT::Start](#start)|Вызывается средой `CAtlServiceModuleT::WinMain` при запуске службы.|
|[CAtlServiceModuleT::Uninstall](#uninstall)|Останавливает и удаляет службу.|
|[CAtlServiceModuleT::Unlock](#unlock)|Уменьшает счетчик блокировки службы.|
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Удаляет службу из реестра.|
|[CAtlServiceModuleT::WinMain](#winmain)|Этот метод реализует код, необходимый для запуска службы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlServiceModuleT::m_bService](#m_bservice)|Флаг, указывающий, что программа выполняется как служба.|
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|Переменная-член хранения идентификатор потока.|
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Переменная-член хранения дескриптор структуры сведения о состоянии для текущей службы.|
|[CAtlServiceModuleT::m_status](#m_status)|Структура информации о состоянии текущей службы хранения переменной-члена.|
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Имя регистрируемой службы.|

## <a name="remarks"></a>Примечания

`CAtlServiceModuleT`, производный от [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), реализует модуль ATL службы. `CAtlServiceModuleT` Предоставляет методы для обработки в командной строке, установки, регистрации и удаления. При необходимости дополнительные функциональные возможности, можно переопределить эти и другие методы.

Этот класс заменяет устаревшее [класс CComModule](../../atl/reference/ccommodule-class.md) применялся в предыдущих версиях библиотеки ATL. См. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="catlservicemodulet"></a>  CAtlServiceModuleT::CAtlServiceModuleT

Конструктор.

```
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует элементы данных и задает состояние начальной службы.

##  <a name="handler"></a>  CAtlServiceModuleT::Handler

Подпрограмму обработчика для службы.

```
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>Параметры

*dwOpcode*  
Переключатель, который определяет операцию обработчика. Дополнительные сведения см. в разделе "Примечания".

### <a name="remarks"></a>Примечания

Это код, который вызывает диспетчер управления службами (SCM), чтобы получить состояние инструкции службы и проблемы, например, остановка или приостановка. Диспетчер управления Службами передает код операции, показанный ниже, до `Handler` для указания, что должен делать.

|Код операции|Значение|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|Останавливает службу. Переопределите метод [CAtlServiceModuleT::OnStop](#onstop) в atlbase.h, чтобы изменить поведение.|
|SERVICE_CONTROL_PAUSE|Пользователь реализации. Переопределить пустого метода [CAtlServiceModuleT::OnPause](#onpause) в atlbase.h на приостановку этой службы.|
|SERVICE_CONTROL_CONTINUE|Пользователь реализации. Переопределить пустого метода [CAtlServiceModuleT::OnContinue](#oncontinue) в atlbase. h для продолжения работы службы.|
|SERVICE_CONTROL_INTERROGATE|Пользователь реализации. Переопределить пустого метода [CAtlServiceModuleT::OnInterrogate](#oninterrogate) в atlbase. h для опроса службы.|
|SERVICE_CONTROL_SHUTDOWN|Пользователь реализации. Переопределить пустого метода [CAtlServiceModuleT::OnShutdown](#onshutdown) в atlbase.h к завершению работы службы.|

Если код операции не распознается, метод [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) вызывается.

Услуга созданный ATL по умолчанию обрабатывает только инструкция stop. Если диспетчер управления Службами передает инструкция stop, службы показывает диспетчера управления Службами, что программа является остановка. Затем вызывается службой `PostThreadMessage` Чтобы отправить сообщение на самого себя. Это завершает цикл обработки сообщений и службы в конечном счете будет закрыт.

##  <a name="initializesecurity"></a>  CAtlServiceModuleT::InitializeSecurity

Предоставляет значение по умолчанию параметры безопасности для службы.

```
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

В Visual Studio .NET 2003 этот метод не реализован в базовом классе. Мастер создания проекта Visual Studio включает в себя этот метод в созданном коде, но ошибка компиляции возникнет в том случае, если проект, созданный в более ранней версии Visual C++ компилируется с помощью ATL 7.1. Любой класс, производный от `CAtlServiceModuleT` необходимо реализовать этот метод в производном классе.

Использовать проверку подлинности уровне PKT, уровень олицетворения для RPC_C_IMP_LEVEL_IDENTIFY и подходящий ненулевой дескриптор безопасности в вызове `CoInitializeSecurity`.

Для проектов без атрибутов службы, созданные мастером это будет в

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

Для проектов службы с атрибутами это будет в

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

##  <a name="install"></a>  CAtlServiceModuleT::Install

Устанавливает и создает службу.

```
BOOL Install() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Устанавливает службу в базу данных диспетчера управления службами (SCM), а затем создает объект службы. Если не удалось создать службу, отображается окно сообщения, и метод возвращает значение FALSE.

##  <a name="isinstalled"></a>  CAtlServiceModuleT::IsInstalled

Подтверждает, что служба установлена.

```
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если служба не установлена, FALSE в противном случае.

##  <a name="logevent"></a>  CAtlServiceModuleT::LogEvent

Записывает в журнал событий.

```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>Параметры

*pszFormat*  
Строка для записи в журнал событий.

...  
Необязательный дополнительный строки для записи в журнал событий.

### <a name="remarks"></a>Примечания

Этот метод записывает сведения в журнал событий, используя функцию [reportevent из комплекта](/windows/desktop/api/winbase/nf-winbase-reporteventa). Если служба не работает, строка отправляется на консоль.

##  <a name="m_bservice"></a>  CAtlServiceModuleT::m_bService

Флаг, указывающий, что программа выполняется как служба.

```
BOOL m_bService;
```

### <a name="remarks"></a>Примечания

Используются для различения EXE службы из exe-ФАЙЛ приложения.

##  <a name="m_dwthreadid"></a>  CAtlServiceModuleT::m_dwThreadID

Идентификатор потока службы хранения переменной-члена.

```
DWORD m_dwThreadID;
```

### <a name="remarks"></a>Примечания

Эта переменная содержит идентификатор текущего потока.

##  <a name="m_hservicestatus"></a>  CAtlServiceModuleT::m_hServiceStatus

Переменная-член хранения дескриптор структуры сведения о состоянии для текущей службы.

```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>Примечания

[SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) структура содержит сведения о службе.

##  <a name="m_status"></a>  CAtlServiceModuleT::m_status

Структура информации о состоянии текущей службы хранения переменной-члена.

```
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>Примечания

[SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) структура содержит сведения о службе.

##  <a name="m_szservicename"></a>  CAtlServiceModuleT::m_szServiceName

Имя регистрируемой службы.

```
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>Примечания

Заканчивающуюся нулем строку, которая хранит имя службы.

##  <a name="oncontinue"></a>  CAtlServiceModuleT::OnContinue

Переопределите этот метод для продолжения работы службы.

```
void OnContinue() throw();
```

##  <a name="oninterrogate"></a>  CAtlServiceModuleT::OnInterrogate

Переопределите этот метод для запроса службы.

```
void OnInterrogate() throw();
```

##  <a name="onpause"></a>  CAtlServiceModuleT::OnPause

Переопределите этот метод, чтобы приостановить службу.

```
void OnPause() throw();
```

##  <a name="onshutdown"></a>  CAtlServiceModuleT::OnShutdown

Переопределите этот метод, чтобы приостановить работу службы.

```
void OnShutdown() throw();
```

##  <a name="onstop"></a>  CAtlServiceModuleT::OnStop

Переопределите этот метод, чтобы остановить службу.

```
void OnStop() throw();
```

##  <a name="onunknownrequest"></a>  CAtlServiceModuleT::OnUnknownRequest

Переопределите этот метод для обработки неизвестных запросов к службе.

```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>Параметры

*dwOpcode*  
Зарезервировано.

##  <a name="parsecommandline"></a>  CAtlServiceModuleT::ParseCommandLine

Выполняет синтаксический анализ командной строки и при необходимости выполняет регистрацию.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Параметры

*lpCmdLine*  
Командная строка.

*pnRetCode*  
Значение HRESULT, соответствующее регистрации (если она была выполнена).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true в случае успеха или значение false, если не удалось зарегистрировать RGS-файл, указанный в командной строке.

### <a name="remarks"></a>Примечания

Выполняет синтаксический анализ командной строки и регистрирует или отменяет регистрацию предоставленного RGS-файл при необходимости. Этот метод вызывает метод [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) на наличие **/regserver** и **параметром/Register**. Добавляет аргумент **- / Service** зарегистрирует службу.

##  <a name="premessageloop"></a>  CAtlServiceModuleT::PreMessageLoop

Этот метод вызывается непосредственно перед ввода цикл обработки сообщений.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*  
Этот параметр передается [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы добавить пользовательский код инициализации для службы.

##  <a name="registerappid"></a>  CAtlServiceModuleT::RegisterAppId

Регистрирует службу в реестре.

```
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>Параметры

*bService*  
Должно быть значение true, чтобы зарегистрировать в качестве службы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="run"></a>  CAtlServiceModuleT::Run

Запущена служба.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*  
Определяет, как будет отображаться окно. Этот параметр может принимать одно из значений, рассматриваемые в [WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559) раздел. Значение по умолчанию — SW_HIDE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

После вызова, `Run` вызовы [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), и [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).

##  <a name="servicemain"></a>  CAtlServiceModuleT::ServiceMain

Этот метод вызывается с помощью диспетчера управления службами.

```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>Параметры

*dwArgc*  
Argc-аргумент.

*lpszArgv*  
Argv-аргумент.

### <a name="remarks"></a>Примечания

Диспетчер управления службами (SCM) вызовы `ServiceMain` при открытии приложение «службы» на панели управления, выберите службу и нажмите кнопку Пуск.

После SCM вызывает `ServiceMain`, службы необходимо предоставить диспетчер управления Службами функцию обработчика событий. Эта функция позволяет диспетчера управления Службами для получения сведений о состоянии службы и передать конкретные инструкции (например, приостановка или остановка). Как следствие [CAtlServiceModuleT::Run](#run) вызывается для выполнения основной рабочей службы. `Run` продолжает выполняться до остановки службы.

##  <a name="setservicestatus"></a>  CAtlServiceModuleT::SetServiceStatus

Этот метод обновляет состояние службы.

```
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>Параметры

*dwState*  
Новое состояние. См. в разделе [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) возможные значения.

### <a name="remarks"></a>Примечания

Обновляет сведения о состоянии диспетчера управления службами для службы. Он вызывается методом [CAtlServiceModuleT::Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) и другие методы обработчика. Состояние также сохраняется в переменной-члене [CAtlServiceModuleT::m_status](#m_status).

##  <a name="start"></a>  CAtlServiceModuleT::Start

Вызывается средой `CAtlServiceModuleT::WinMain` при запуске службы.

```
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*  
Определяет, как будет отображаться окно. Этот параметр может принимать одно из значений, рассматриваемые в [WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559) раздел.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

[CAtlServiceModuleT::WinMain](#winmain) метод регистрации и установки, а также задачи, участвующих в удаление записей реестра и удаление модуля. При запуске службы `WinMain` вызовы `Start`.

##  <a name="uninstall"></a>  CAtlServiceModuleT::Uninstall

Останавливает и удаляет службу.

```
BOOL Uninstall() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Останавливает службу запуска и удаляет его из базы данных диспетчера управления службами.

##  <a name="unlock"></a>  CAtlServiceModuleT::Unlock

Уменьшает счетчик блокировки службы.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число блокировок, который может быть полезно для диагностики и отладки.

##  <a name="unregisterappid"></a>  CAtlServiceModuleT::UnregisterAppId

Удаляет службу из реестра.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="winmain"></a>  CAtlServiceModuleT::WinMain

Этот метод реализует код, необходимый для запуска службы.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*  
Определяет, как будет отображаться окно. Этот параметр может принимать одно из значений, рассматриваемые в [WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559) раздел.

### <a name="return-value"></a>Возвращаемое значение

Возвращает возвращаемое значение службы.

### <a name="remarks"></a>Примечания

Этот метод обрабатывает командной строки (с [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) и затем запускает службу (с помощью [CAtlServiceModuleT::Start](#start)).

## <a name="see-also"></a>См. также

[Класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
