---
title: "Класс CAtlServiceModuleT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlServiceModuleT
- ATL.CAtlServiceModuleT
- CAtlServiceModuleT
dev_langs:
- C++
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c8fcadca667b618d9e5f112d7910c8e6e6f6c65d
ms.lasthandoff: 02/24/2017

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
 `T`  
 Ваш класс, производный от `CAtlServiceModuleT`.  
  
 *nServiceNameID*  
 Идентификатор ресурса службы.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlServiceModuleT::Handler](#handler)|Процедуры обработчика для службы.|  
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|Предоставляет значение по умолчанию параметры безопасности для службы.|  
|[CAtlServiceModuleT::Install](#install)|Устанавливает и создает службу.|  
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|Подтверждает, что служба установлена.|  
|[CAtlServiceModuleT::LogEvent](#logevent)|Записывает в журнал событий.|  
|[CAtlServiceModuleT::OnContinue](#oncontinue)|Переопределите этот метод, чтобы продолжить работу службы.|  
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|Переопределите этот метод, чтобы запросить службу.|  
|[CAtlServiceModuleT::OnPause](#onpause)|Переопределите этот метод, чтобы приостановить службу.|  
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|Переопределите этот метод, чтобы завершить работу службы|  
|[CAtlServiceModuleT::OnStop](#onstop)|Переопределите этот метод, чтобы остановить службу|  
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Переопределите этот метод для обработки неизвестных запросов к службе|  
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Анализирует командную строку и выполняет регистрацию, при необходимости.|  
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Этот метод вызывается сразу перед вводом в цикл обработки сообщений.|  
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Регистрирует службы в реестре.|  
|[CAtlServiceModuleT::Run](#run)|Служба работает.|  
|[CAtlServiceModuleT::ServiceMain](#servicemain)|Метод вызывается диспетчером управления службами.|  
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Обновляет состояние службы.|  
|[CAtlServiceModuleT::Start](#start)|Вызывается методом `CAtlServiceModuleT::WinMain` при запуске службы.|  
|[CAtlServiceModuleT::Uninstall](#uninstall)|Останавливает и удаляет службу.|  
|[CAtlServiceModuleT::Unlock](#unlock)|Уменьшает счетчик блокировок службы.|  
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Удаляет службу из реестра.|  
|[CAtlServiceModuleT::WinMain](#winmain)|Этот метод реализует код, необходимый для запуска службы.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlServiceModuleT::m_bService](#m_bservice)|Флаг, указывающий программа выполняется как служба.|  
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|Идентификатор потока хранения переменной-члена.|  
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Дескриптор структуры сведения о состоянии для текущей службы хранения переменной-члена.|  
|[CAtlServiceModuleT::m_status](#m_status)|Структура информации состояния текущей службы хранения переменной-члена.|  
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Имя регистрируемого службы.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlServiceModuleT`, производный от [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), реализующего модуль ATL службы. `CAtlServiceModuleT`Предоставляет методы для обработки в командной строке, установки, регистрации и удаления. При необходимости дополнительные функциональные возможности, можно переопределить эти и другие методы.  
  
 Этот класс заменяет устаревшие [CComModule-класс](../../atl/reference/ccommodule-class.md) использовался в предыдущих версиях библиотеки ATL. В разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="a-namecatlservicemoduleta--catlservicemoduletcatlservicemodulet"></a><a name="catlservicemodulet"></a>CAtlServiceModuleT::CAtlServiceModuleT  
 Конструктор.  
  
```
CAtlServiceModuleT() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует элементы данных и устанавливает состояние исходной службы.  
  
##  <a name="a-namehandlera--catlservicemodulethandler"></a><a name="handler"></a>CAtlServiceModuleT::Handler  
 Процедуры обработчика для службы.  
  
```
void Handler(DWORD dwOpcode) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *dwOpcode*  
 Параметр, который определяет обработчик операции. Дополнительные сведения см.  
  
### <a name="remarks"></a>Примечания  
 Это код, который вызывает диспетчер управления службами (SCM), чтобы получить состояние инструкции службы и проблемы, например остановка или приостановка. Диспетчер управления Службами передает код операции, показанным ниже, чтобы `Handler` для указания, что следует сделать.  
  
|Код операции|Значение|  
|--------------------|-------------|  
|SERVICE_CONTROL_STOP|Останавливает службу. Переопределите метод [CAtlServiceModuleT::OnStop](#onstop) в atlbase.h, чтобы изменить поведение.|  
|SERVICE_CONTROL_PAUSE|Пользователь реализации. Переопределение метода пустой [CAtlServiceModuleT::OnPause](#onpause) в atlbase.h, чтобы приостановить службу.|  
|SERVICE_CONTROL_CONTINUE|Пользователь реализации. Переопределение метода пустой [CAtlServiceModuleT::OnContinue](#oncontinue) в atlbase.h, чтобы продолжить работу службы.|  
|SERVICE_CONTROL_INTERROGATE|Пользователь реализации. Переопределение метода пустой [CAtlServiceModuleT::OnInterrogate](#oninterrogate) в atlbase.h может запросить службу.|  
|SERVICE_CONTROL_SHUTDOWN|Пользователь реализации. Переопределение метода пустой [CAtlServiceModuleT::OnShutdown](#onshutdown) в atlbase.h на завершение работы службы.|  
  
 Если не распознается код операции, метод [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) вызывается.  
  
 Службу созданный ATL по умолчанию обрабатывает только инструкция stop. Если диспетчер управления Службами передает инструкция stop, служба сообщает SCM, программа является остановка. Затем вызывает службу `PostThreadMessage` для учета quit сообщение самому себе. Это завершает цикл обработки сообщений и службы в конечном счете будет закрыт.  
  
##  <a name="a-nameinitializesecuritya--catlservicemoduletinitializesecurity"></a><a name="initializesecurity"></a>CAtlServiceModuleT::InitializeSecurity  
 Предоставляет значение по умолчанию параметры безопасности для службы.  
  
```
HRESULT InitializeSecurity() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 В Visual Studio .NET 2003 этот метод не реализован в базовом классе. Мастер проекта Visual Studio включает этот метод в созданном коде, но ошибка компиляции возникает, если в проект, созданный в более ранней версии Visual C++ компилируется с помощью ATL 7.1. Любой класс, производный от `CAtlServiceModuleT` необходимо реализовать этот метод в производном классе.  
  
 Используйте PKT уровень проверки подлинности, уровень олицетворения RPC_C_IMP_LEVEL_IDENTIFY и подходящий ненулевой дескриптор безопасности в вызове **CoInitializeSecurity**.  
  
 Для проектов без атрибутов службы, созданный мастером это было бы в  
  
 [!code-cpp[NVC_ATL_Service&#1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]  
  
 Для проектов, службы с атрибутами это было бы в  
  
 [!code-cpp[NVC_ATL_ServiceAttrib&#1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]  
  
##  <a name="a-nameinstalla--catlservicemoduletinstall"></a><a name="install"></a>CAtlServiceModuleT::Install  
 Устанавливает и создает службу.  
  
```
BOOL Install() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Устанавливает службу в базу данных диспетчера управления службами (SCM), а затем создает объект службы. Если не удается создать службу, отображается окно сообщения, и метод возвращает значение FALSE.  
  
##  <a name="a-nameisinstalleda--catlservicemoduletisinstalled"></a><a name="isinstalled"></a>CAtlServiceModuleT::IsInstalled  
 Подтверждает, что служба установлена.  
  
```
BOOL IsInstalled() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если служба установлена, значение FALSE в противном случае.  
  
##  <a name="a-namelogeventa--catlservicemoduletlogevent"></a><a name="logevent"></a>CAtlServiceModuleT::LogEvent  
 Записывает в журнал событий.  
  
```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Строка для записи в журнал событий.  
  
 ...  
 Необязательные дополнительные строки для записи в журнал событий.  
  
### <a name="remarks"></a>Примечания  
 Этот метод записывает сведения в журнал событий, используя функцию [ReportEvent](http://msdn.microsoft.com/library/windows/desktop/aa363679). Если служба не работает, строка отправляется на консоль.  
  
##  <a name="a-namembservicea--catlservicemoduletmbservice"></a><a name="m_bservice"></a>CAtlServiceModuleT::m_bService  
 Флаг, указывающий программа выполняется как служба.  
  
```
BOOL m_bService;
```  
  
### <a name="remarks"></a>Примечания  
 Используются для различения EXE службы из EXE-файла приложения.  
  
##  <a name="a-namemdwthreadida--catlservicemoduletmdwthreadid"></a><a name="m_dwthreadid"></a>CAtlServiceModuleT::m_dwThreadID  
 Идентификатор потока службы хранения переменной-члена.  
  
```
DWORD m_dwThreadID;
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная хранит идентификатор текущего потока.  
  
##  <a name="a-namemhservicestatusa--catlservicemoduletmhservicestatus"></a><a name="m_hservicestatus"></a>CAtlServiceModuleT::m_hServiceStatus  
 Дескриптор структуры сведения о состоянии для текущей службы хранения переменной-члена.  
  
```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```  
  
### <a name="remarks"></a>Примечания  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) структура содержит сведения о службе.  
  
##  <a name="a-namemstatusa--catlservicemoduletmstatus"></a><a name="m_status"></a>CAtlServiceModuleT::m_status  
 Структура информации состояния текущей службы хранения переменной-члена.  
  
```
SERVICE_STATUS m_status;
```  
  
### <a name="remarks"></a>Примечания  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) структура содержит сведения о службе.  
  
##  <a name="a-namemszservicenamea--catlservicemoduletmszservicename"></a><a name="m_szservicename"></a>CAtlServiceModuleT::m_szServiceName  
 Имя регистрируемого службы.  
  
```
TCHAR [256] m_szServiceName;
```  
  
### <a name="remarks"></a>Примечания  
 Завершающим нулем строку, которая содержит имя службы.  
  
##  <a name="a-nameoncontinuea--catlservicemoduletoncontinue"></a><a name="oncontinue"></a>CAtlServiceModuleT::OnContinue  
 Переопределите этот метод, чтобы продолжить работу службы.  
  
```
void OnContinue() throw();
```  
  
##  <a name="a-nameoninterrogatea--catlservicemoduletoninterrogate"></a><a name="oninterrogate"></a>CAtlServiceModuleT::OnInterrogate  
 Переопределите этот метод, чтобы запросить службу.  
  
```
void OnInterrogate() throw();
```  
  
##  <a name="a-nameonpausea--catlservicemoduletonpause"></a><a name="onpause"></a>CAtlServiceModuleT::OnPause  
 Переопределите этот метод, чтобы приостановить службу.  
  
```
void OnPause() throw();
```  
  
##  <a name="a-nameonshutdowna--catlservicemoduletonshutdown"></a><a name="onshutdown"></a>CAtlServiceModuleT::OnShutdown  
 Переопределите этот метод, чтобы завершить работу службы.  
  
```
void OnShutdown() throw();
```  
  
##  <a name="a-nameonstopa--catlservicemoduletonstop"></a><a name="onstop"></a>CAtlServiceModuleT::OnStop  
 Переопределите этот метод, чтобы остановить службу.  
  
```
void OnStop() throw();
```  
  
##  <a name="a-nameonunknownrequesta--catlservicemoduletonunknownrequest"></a><a name="onunknownrequest"></a>CAtlServiceModuleT::OnUnknownRequest  
 Переопределите этот метод для обработки неизвестных запросов к службе.  
  
```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```  
  
### <a name="parameters"></a>Параметры  
 */\*dwOpcode\*/*  
 Зарезервировано.  
  
##  <a name="a-nameparsecommandlinea--catlservicemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlServiceModuleT::ParseCommandLine  
 Анализирует командную строку и выполняет регистрацию, при необходимости.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpCmdLine`  
 Командная строка.  
  
 `pnRetCode`  
 Значение HRESULT, соответствующее регистрации (если она выполнялась).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, успех, или false, если не удается зарегистрировать RGS-файл, указанный в командной строке.  
  
### <a name="remarks"></a>Примечания  
 Анализирует командную строку и регистрирует или отменяет регистрацию указанного RGS-файл, если это необходимо. Этот метод вызывает метод [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) для проверки **/regserver** и **/UnregServer**. Добавляет аргумент **- / службы** зарегистрирует службу.  
  
##  <a name="a-namepremessageloopa--catlservicemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlServiceModuleT::PreMessageLoop  
 Этот метод вызывается сразу перед вводом в цикл обработки сообщений.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Этот параметр передается [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы добавить пользовательский код инициализации для службы.  
  
##  <a name="a-nameregisterappida--catlservicemoduletregisterappid"></a><a name="registerappid"></a>CAtlServiceModuleT::RegisterAppId  
 Регистрирует службы в реестре.  
  
```
inline HRESULT RegisterAppId(bool bService = false) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *bService*  
 Должно быть значение true, чтобы зарегистрироваться в качестве службы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-nameruna--catlservicemoduletrun"></a><a name="run"></a>CAtlServiceModuleT::Run  
 Служба работает.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Указывает, как будет отображаться окно. Этот параметр может иметь одно из значений, описанных в [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) раздел. Значение по умолчанию — SW_HIDE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 После вызова, **запуска** вызовов [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), и [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).  
  
##  <a name="a-nameservicemaina--catlservicemoduletservicemain"></a><a name="servicemain"></a>CAtlServiceModuleT::ServiceMain  
 Этот метод вызывается диспетчером управления службами.  
  
```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *dwArgc*  
 Argc-аргумент.  
  
 *lpszArgv*  
 Argv-аргумент.  
  
### <a name="remarks"></a>Примечания  
 Диспетчер управления службами (SCM) вызывает `ServiceMain` при открытии приложение «службы» на панели управления, выберите службу и нажмите кнопку Пуск.  
  
 После SCM вызывает `ServiceMain`, службы необходимо предоставить SCM функцию обработчика событий. Эта функция позволяет получить состояние службы и передать конкретные инструкции (например, приостановка или остановка) диспетчера управления Службами. Следовательно [CAtlServiceModuleT::Run](#run) вызывается для выполнения основных операций службы. **Запустите** продолжает выполняться, пока служба остановлена.  
  
##  <a name="a-namesetservicestatusa--catlservicemoduletsetservicestatus"></a><a name="setservicestatus"></a>CAtlServiceModuleT::SetServiceStatus  
 Этот метод обновляет состояние службы.  
  
```
void SetServiceStatus(DWORD dwState) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwState`  
 Новое состояние. В разделе [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241) возможные значения.  
  
### <a name="remarks"></a>Примечания  
 Обновляет сведения о состоянии диспетчера управления службами для службы. Вызывается методом [CAtlServiceModuleT::Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) и другие методы обработчика. Состояние также сохраняется в переменной-члена [CAtlServiceModuleT::m_status](#m_status).  
  
##  <a name="a-namestarta--catlservicemoduletstart"></a><a name="start"></a>CAtlServiceModuleT::Start  
 Вызывается методом `CAtlServiceModuleT::WinMain` при запуске службы.  
  
```
HRESULT Start(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Указывает, как будет отображаться окно. Этот параметр может иметь одно из значений, описанных в [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) раздел.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 [CAtlServiceModuleT::WinMain](#winmain) метод регистрации и установки, а также задачи, участвующие в удаление записей реестра и удаление модуля. При запуске служба `WinMain` вызовов **запустить**.  
  
##  <a name="a-nameuninstalla--catlservicemoduletuninstall"></a><a name="uninstall"></a>CAtlServiceModuleT::Uninstall  
 Останавливает и удаляет службу.  
  
```
BOOL Uninstall() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Останавливает службу запуска и удаляет его из базы данных диспетчера управления службами.  
  
##  <a name="a-nameunlocka--catlservicemoduletunlock"></a><a name="unlock"></a>CAtlServiceModuleT::Unlock  
 Уменьшает счетчик блокировок службы.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество блокировок, которое может быть полезно для диагностики и отладки.  
  
##  <a name="a-nameunregisterappida--catlservicemoduletunregisterappid"></a><a name="unregisterappid"></a>CAtlServiceModuleT::UnregisterAppId  
 Удаляет службу из реестра.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namewinmaina--catlservicemoduletwinmain"></a><a name="winmain"></a>CAtlServiceModuleT::WinMain  
 Этот метод реализует код, необходимый для запуска службы.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Указывает, как будет отображаться окно. Этот параметр может иметь одно из значений, описанных в [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) раздел.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает возвращаемое значение службы.  
  
### <a name="remarks"></a>Примечания  
 Этот метод обрабатывает командной строки (с [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)), а затем запускает службы (с помощью [CAtlServiceModuleT::Start](#start)).  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

