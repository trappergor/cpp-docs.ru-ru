---
title: "Класс CAccessToken | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccessToken
- ATLSECURITY/ATL::CAccessToken
- ATLSECURITY/ATL::CAccessToken::Attach
- ATLSECURITY/ATL::CAccessToken::CheckTokenMembership
- ATLSECURITY/ATL::CAccessToken::CreateImpersonationToken
- ATLSECURITY/ATL::CAccessToken::CreatePrimaryToken
- ATLSECURITY/ATL::CAccessToken::CreateProcessAsUser
- ATLSECURITY/ATL::CAccessToken::CreateRestrictedToken
- ATLSECURITY/ATL::CAccessToken::Detach
- ATLSECURITY/ATL::CAccessToken::DisablePrivilege
- ATLSECURITY/ATL::CAccessToken::DisablePrivileges
- ATLSECURITY/ATL::CAccessToken::EnablePrivilege
- ATLSECURITY/ATL::CAccessToken::EnablePrivileges
- ATLSECURITY/ATL::CAccessToken::GetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::GetEffectiveToken
- ATLSECURITY/ATL::CAccessToken::GetGroups
- ATLSECURITY/ATL::CAccessToken::GetHandle
- ATLSECURITY/ATL::CAccessToken::GetImpersonationLevel
- ATLSECURITY/ATL::CAccessToken::GetLogonSessionId
- ATLSECURITY/ATL::CAccessToken::GetLogonSid
- ATLSECURITY/ATL::CAccessToken::GetOwner
- ATLSECURITY/ATL::CAccessToken::GetPrimaryGroup
- ATLSECURITY/ATL::CAccessToken::GetPrivileges
- ATLSECURITY/ATL::CAccessToken::GetProcessToken
- ATLSECURITY/ATL::CAccessToken::GetProfile
- ATLSECURITY/ATL::CAccessToken::GetSource
- ATLSECURITY/ATL::CAccessToken::GetStatistics
- ATLSECURITY/ATL::CAccessToken::GetTerminalServicesSessionId
- ATLSECURITY/ATL::CAccessToken::GetThreadToken
- ATLSECURITY/ATL::CAccessToken::GetTokenId
- ATLSECURITY/ATL::CAccessToken::GetType
- ATLSECURITY/ATL::CAccessToken::GetUser
- ATLSECURITY/ATL::CAccessToken::HKeyCurrentUser
- ATLSECURITY/ATL::CAccessToken::Impersonate
- ATLSECURITY/ATL::CAccessToken::ImpersonateLoggedOnUser
- ATLSECURITY/ATL::CAccessToken::IsTokenRestricted
- ATLSECURITY/ATL::CAccessToken::LoadUserProfile
- ATLSECURITY/ATL::CAccessToken::LogonUser
- ATLSECURITY/ATL::CAccessToken::OpenCOMClientToken
- ATLSECURITY/ATL::CAccessToken::OpenNamedPipeClientToken
- ATLSECURITY/ATL::CAccessToken::OpenRPCClientToken
- ATLSECURITY/ATL::CAccessToken::OpenThreadToken
- ATLSECURITY/ATL::CAccessToken::PrivilegeCheck
- ATLSECURITY/ATL::CAccessToken::Revert
- ATLSECURITY/ATL::CAccessToken::SetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::SetOwner
- ATLSECURITY/ATL::CAccessToken::SetPrimaryGroup
dev_langs:
- C++
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b8d2a314ea7697ef4379b899ee6845cd4ceca707
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="caccesstoken-class"></a>Класс CAccessToken
Этот класс является оболочкой для токена доступа.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAccessToken
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAccessToken::~CAccessToken](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAccessToken::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем дескриптора маркера доступ.|  
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|Этот метод вызывается для включения в указанный идентификатор SID `CAccessToken` объекта.|  
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Этот метод используется для создания нового маркера доступа олицетворения.|  
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Этот метод используется для создания нового основного маркера.|  
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Этот метод вызывается для создания нового процесса, запущенная в контексте безопасности пользователя, представленного `CAccessToken` объекта.|  
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Этот метод вызывается для создания нового ограниченного `CAccessToken` объекта.|  
|[CAccessToken::Detach](#detach)|Этот метод вызывается для отмены владения маркер доступа.|  
|[CAccessToken::DisablePrivilege](#disableprivilege)|Этот метод вызывается для отключения доступа в `CAccessToken` объекта.|  
|[CAccessToken::DisablePrivileges](#disableprivileges)|Вызовите этот метод, чтобы отключить один или несколько привилегии в `CAccessToken` объекта.|  
|[CAccessToken::EnablePrivilege](#enableprivilege)|Этот метод вызывается для включения доступа в `CAccessToken` объекта.|  
|[CAccessToken::EnablePrivileges](#enableprivileges)|Вызовите этот метод, чтобы включить один или несколько прав в `CAccessToken` объекта.|  
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Вызовите этот метод для возврата `CAccessToken` объекта по умолчанию DACL.|  
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Этот метод вызывается для получения `CAccessToken` равное маркер доступа, применяемые для текущего потока.|  
|[CAccessToken::GetGroups](#getgroups)|Вызовите этот метод для возврата `CAccessToken` объекта маркера групп.|  
|[CAccessToken::GetHandle](#gethandle)|Этот метод используется для получения дескриптора в маркер доступа.|  
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Этот метод используется для получения из токена доступа уровень олицетворения.|  
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|Вызовите этот метод, чтобы получить идентификатор сеанса входа в систему, связанных с `CAccessToken` объекта.|  
|[CAccessToken::GetLogonSid](#getlogonsid)|Этот метод вызывается для получения идентификатора безопасности входа в систему, связанных с `CAccessToken` объекта.|  
|[CAccessToken::GetOwner](#getowner)|Этот метод вызывается для получения владельца, связанного с `CAccessToken` объекта.|  
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|Вызовите этот метод, чтобы получить основную группу, связанную с `CAccessToken` объекта.|  
|[CAccessToken::GetPrivileges](#getprivileges)|Этот метод получает права доступа, связанные с `CAccessToken` объекта.|  
|[CAccessToken::GetProcessToken](#getprocesstoken)|Этот метод вызывается для инициализации `CAccessToken` с маркером доступа из указанного процесса.|  
|[CAccessToken::GetProfile](#getprofile)|Вызовите этот метод, чтобы получить маркер, указывающий на профиль пользователя, связанный с `CAccessToken` объекта.|  
|[CAccessToken::GetSource](#getsource)|Этот метод вызывается для получения источника `CAccessToken` объекта.|  
|[CAccessToken::GetStatistics](#getstatistics)|Этот метод вызывается для получения сведений, связанных с `CAccessToken` объекта.|  
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|Вызовите этот метод, чтобы получить идентификатор сеанса служб терминалов, связанный с `CAccessToken` объекта.|  
|[CAccessToken::GetThreadToken](#getthreadtoken)|Этот метод вызывается для инициализации `CAccessToken` с маркером из данного потока.|  
|[CAccessToken::GetTokenId](#gettokenid)|Этот метод вызывается для получения маркера идентификатор, связанный с `CAccessToken` объекта.|  
|[CAccessToken::GetType](#gettype)|Этот метод вызывается для получения токена типа `CAccessToken` объекта.|  
|[CAccessToken::GetUser](#getuser)|Этот метод вызывается для идентификации пользователя, связанного с `CAccessToken` объекта.|  
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|Вызовите этот метод, чтобы получить маркер, указывающий на профиль пользователя, связанный с `CAccessToken` объекта.|  
|[CAccessToken::Impersonate](#impersonate)|Вызовите этот метод, чтобы назначить олицетворение `CAccessToken` потоку.|  
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Этот метод позволяет вызывающему потоку олицетворять контекст безопасности пользователя, выполнившего вход.|  
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Этот метод вызывается для проверки, если `CAccessToken` объект содержит список ограниченных идентификаторов безопасности.|  
|[CAccessToken::LoadUserProfile](#loaduserprofile)|Вызовите этот метод, чтобы загрузить профиль пользователя, связанный с `CAccessToken` объекта.|  
|[CAccessToken::LogonUser](#logonuser)|Этот метод используется для создания сеанса входа в систему для пользователя, связанного с заданными учетными данными.|  
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Вызов этого метода в обработке вызов от клиента для инициализации COM-сервера `CAccessToken` с маркером доступа из COM-клиент.|  
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Вызовите этот метод из на сервере запросов на получение по именованному каналу для инициализации `CAccessToken` с маркером доступа от клиента.|  
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Вызовите этот метод из сервера обработки вызовов из клиента RPC для инициализации `CAccessToken` с маркером доступа от клиента.|  
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Вызовите этот метод для настройки уровня олицетворения, а затем инициализировать `CAccessToken` с маркером из данного потока.|  
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Вызовите этот метод, чтобы определить, включены ли в указанный набор прав, **CAccessToken** объекта.|  
|[CAccessToken::Revert](#revert)|Этот метод используется для остановки потока, который использует маркер олицетворения.|  
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Этот метод вызывается для установки по умолчанию список DACL `CAccessToken` объекта.|  
|[CAccessToken::SetOwner](#setowner)|Вызовите этот метод, чтобы задать владельца `CAccessToken` объекта.|  
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Вызовите этот метод для установки основной группы `CAccessToken` объекта.|  
  
## <a name="remarks"></a>Примечания  
 [Маркер доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909) — это объект, который описывает контекст безопасности процесса или потока и выделяется для каждого пользователя, зарегистрированного в системе Windows.  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="attach"></a>  CAccessToken::Attach  
 Вызовите этот метод, чтобы стать владельцем дескриптора маркера доступ.  
  
```
void Attach(HANDLE hToken) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *hToken*  
 Дескриптор токена доступа.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `CAccessToken` объект уже имеет права владения маркер доступа.  
  
##  <a name="dtor"></a>  CAccessToken::~CAccessToken  
 Деструктор  
  
```
virtual ~CAccessToken() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="checktokenmembership"></a>  CAccessToken::CheckTokenMembership  
 Этот метод вызывается для включения в указанный идентификатор SID `CAccessToken` объекта.  
  
```
bool CheckTokenMembership(
    const CSid& rSid, 
    bool* pbIsMember) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 Ссылка на [CSid класс](../../atl/reference/csid-class.md) объекта.  
  
 `pbIsMember`  
 Указатель на переменную, получающую результаты проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `CheckTokenMembership` Метод проверяет на наличие идентификатора безопасности пользователей и идентификаторы безопасности группы токена доступа. Если идентификатор присутствует и имеет атрибут SE_GROUP_ENABLED *pbIsMember* будет задано значение true; в противном случае, он имеет значение false.  
  
 В отладочных построениях, произойдет ошибка утверждения, если `pbIsMember` не является допустимым указателем.  
  
> [!NOTE]
>  `CAccessToken` Объект должен быть маркер олицетворения и основного маркера.  
  
##  <a name="createimpersonationtoken"></a>  CAccessToken::CreateImpersonationToken  
 Этот метод используется для создания токена доступа олицетворения.  
  
```
bool CreateImpersonationToken(
    CAccessToken* pImp, 
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pImp`  
 Указатель на новый `CAccessToken` объекта.  
  
 `sil`  
 Указывает [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) перечисляемый тип, предоставляющий уровень олицетворения новый токен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `CreateImpersonationToken`вызовы [DuplicateToken](http://msdn.microsoft.com/library/windows/desktop/aa446616) , чтобы создать новый маркер олицетворения.  
  
##  <a name="createprimarytoken"></a>  CAccessToken::CreatePrimaryToken  
 Этот метод используется для создания нового основного маркера.  
  
```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pPri*  
 Указатель на новый `CAccessToken` объекта.  
  
 `dwDesiredAccess`  
 Указывает запрошенные права доступа для нового токена. Значение по умолчанию MAXIMUM_ALLOWED, запрашивает все права доступа, которые являются допустимыми для вызывающего объекта. В разделе [права доступа и маски доступа](http://msdn.microsoft.com/library/windows/desktop/aa374902) дополнительные права на доступ.  
  
 *pTokenAttributes*  
 Указатель на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структуру, которая указывает дескриптор безопасности для нового токена и определяет, можно ли дочерние процессы наследуют маркер. Если *pTokenAttributes* имеет значение NULL, дескриптор безопасности по умолчанию возвращает токен и дескриптор не наследуется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `CreatePrimaryToken`вызовы [DuplicateTokenEx](http://msdn.microsoft.com/library/windows/desktop/aa446617) для создания нового основного маркера.  
  
##  <a name="createprocessasuser"></a>  CAccessToken::CreateProcessAsUser  
 Этот метод вызывается для создания нового процесса, запущенная в контексте безопасности пользователя, представленного `CAccessToken` объекта.  
  
```
bool CreateProcessAsUser(
    LPCTSTR pApplicationName,
    LPTSTR pCommandLine,
    LPPROCESS_INFORMATION pProcessInformation,
    LPSTARTUPINFO pStartupInfo,
    DWORD dwCreationFlags = NORMAL_PRIORITY_CLASS,
    bool bLoadProfile = false,
    const CSecurityAttributes* pProcessAttributes = NULL,
    const CSecurityAttributes* pThreadAttributes = NULL,
    bool bInherit = false,
    LPCTSTR pCurrentDirectory = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pApplicationName*  
 Указатель null нулевым байтом строка, указывающая модуль для выполнения. Этот параметр не может иметь значение NULL.  
  
 *pCommandLine*  
 Указатель на строку символом null, указывает командную строку для выполнения.  
  
 *pProcessInformation*  
 Указатель на [PROCESS_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/ms684873) структуру, которая получает сведения, идентифицирующие нового процесса.  
  
 *pStartupInfo*  
 Указатель на [STARTUPINFO](http://msdn.microsoft.com/library/windows/desktop/ms686331) структуру, которая указывает, как должно выглядеть главного окна для нового процесса.  
  
 `dwCreationFlags`  
 Задает дополнительные флаги, управляющие класс приоритета и создания процесса. В описании функции Win32 [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) список флагов.  
  
 *bLoadProfile*  
 Если значение равно true, профиль пользователя, загружается с [LoadUserProfile](http://msdn.microsoft.com/library/windows/desktop/bb762281).  
  
 *pProcessAttributes*  
 Указатель на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структуру, которая указывает дескриптор безопасности для нового процесса и определяет, можно ли дочерние процессы наследуют возвращенный дескриптор. Если *pProcessAttributes* имеет значение NULL, процесс получает дескриптор безопасности по умолчанию и дескриптор не наследуется.  
  
 *pThreadAttributes*  
 Указатель на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структуру, которая указывает дескриптор безопасности для нового потока и определяет, можно ли дочерние процессы наследуют возвращенный дескриптор. Если *pThreadAttributes* имеет значение NULL, поток получает дескриптор безопасности по умолчанию и дескриптор не наследуется.  
  
 *bInherit*  
 Указывает ли новый процесс наследует дескрипторов вызывающего процесса. Значение true, если каждый наследуемые открытый дескриптор в вызывающий процесс наследуется нового процесса. Унаследованные дескрипторы обладают теми же привилегиями значение и доступа исходные дескрипторы.  
  
 *pCurrentDirectory*  
 Указатель на строку с завершающим нулем, указывающее текущий диск и каталог для нового процесса. Строка должна быть полный путь содержит букву диска. Если этот параметр имеет значение NULL, новый процесс будет диск и каталог как вызывающий процесс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 **CreateProcessAsUser** использует `CreateProcessAsUser` функцию Win32 для создания нового процесса, который выполняется в контексте безопасности пользователя, представленного `CAccessToken` объекта. См. в описании [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) функция полное описание параметров, необходимых.  
  
 Для успешного выполнения этого метода `CAccessToken` должен храниться в объекте AssignPrimaryToken (если он не маркером ограниченного доступа) и IncreaseQuota права доступа.  
  
##  <a name="createrestrictedtoken"></a>  CAccessToken::CreateRestrictedToken  
 Этот метод вызывается для создания нового ограниченного `CAccessToken` объекта.  
  
```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pRestrictedToken*  
 Новый, ограниченные `CAccessToken` объекта.  
  
 `SidsToDisable`  
 Объект `CTokenGroups` объект, который указывает только идентификаторы безопасности.  
  
 *SidsToRestrict*  
 Объект `CTokenGroups` объект, который указывает ограничивающие идентификаторы безопасности.  
  
 `PrivilegesToDelete`  
 Объект `CTokenPrivileges` , указывающий в маркере ограниченных привилегий для удаления. Значение по умолчанию создает пустой объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `CreateRestrictedToken`использует [CreateRestrictedToken](http://msdn.microsoft.com/library/windows/desktop/aa446583) функцию Win32 для создания нового `CAccessToken` объект с ограничениями.  
  
> [!IMPORTANT]
>  При использовании `CreateRestrictedToken`, убедитесь в следующем: существующий маркер является допустимым (и не введенное пользователем) и `SidsToDisable` и `PrivilegesToDelete` являются допустимое (и не введенное пользователем). Если метод возвращает значение false, запретите функциональные возможности.  
  
##  <a name="detach"></a>  CAccessToken::Detach  
 Этот метод вызывается для отмены владения маркер доступа.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор `CAccessToken` которого была отсоединена.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отменяет `CAccessToken`его владельца токена доступа.  
  
##  <a name="disableprivilege"></a>  CAccessToken::DisablePrivilege  
 Этот метод вызывается для отключения доступа в `CAccessToken` объекта.  
  
```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pszPrivilege`  
 Указатель на строку, содержащую прав доступа, чтобы отключить в `CAccessToken` объекта.  
  
 `pPreviousState`  
 Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние прав доступа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="disableprivileges"></a>  CAccessToken::DisablePrivileges  
 Вызовите этот метод, чтобы отключить один или несколько привилегии в `CAccessToken` объекта.  
  
```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rPrivileges`  
 Указатель на массив строк, содержащих привилегии, чтобы отключить в `CAccessToken` объекта.  
  
 `pPreviousState`  
 Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние прав доступа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="enableprivilege"></a>  CAccessToken::EnablePrivilege  
 Этот метод вызывается для включения доступа в `CAccessToken` объекта.  
  
```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pszPrivilege`  
 Указатель на строку, содержащую прав доступа для включения в `CAccessToken` объекта.  
  
 `pPreviousState`  
 Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние прав доступа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="enableprivileges"></a>  CAccessToken::EnablePrivileges  
 Вызовите этот метод, чтобы включить один или несколько прав в `CAccessToken` объекта.  
  
```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rPrivileges`  
 Указатель на массив строк, содержащих привилегии, чтобы включить в `CAccessToken` объекта.  
  
 `pPreviousState`  
 Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние прав доступа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="getdefaultdacl"></a>  CAccessToken::GetDefaultDacl  
 Вызовите этот метод для возврата `CAccessToken` объекта по умолчанию DACL.  
  
```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pDacl`  
 Указатель на [класса CDacl](../../atl/reference/cdacl-class.md) объекта, который будет получать **CAccessToken** объекта по умолчанию DACL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если значение по умолчанию DACL было восстановленный, и false в противном случае.  
  
##  <a name="geteffectivetoken"></a>  CAccessToken::GetEffectiveToken  
 Этот метод вызывается для получения `CAccessToken` равное маркер доступа, применяемые для текущего потока.  
  
```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Указывает маску доступа, которая указывает запрошенных типов доступа в маркер доступа. Эти типы доступ к запрошенному ресурсу сравниваются с DACL токена, чтобы определить, какой доступ разрешен или запрещен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="getgroups"></a>  CAccessToken::GetGroups  
 Вызовите этот метод для возврата `CAccessToken` объекта маркера групп.  
  
```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pGroups*  
 Указатель на [CTokenGroups класс](../../atl/reference/ctokengroups-class.md) объекта, который будет получать сведения о группе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="gethandle"></a>  CAccessToken::GetHandle  
 Этот метод используется для получения дескриптора в маркер доступа.  
  
```
HANDLE GetHandle() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор `CAccessToken` объекта маркера доступа.  
  
##  <a name="getimpersonationlevel"></a>  CAccessToken::GetImpersonationLevel  
 Этот метод используется для получения из токена доступа уровень олицетворения.  
  
```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pImpersonationLevel*  
 Указатель на [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) тип перечисления, который будет получать данные уровня олицетворения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="getlogonsessionid"></a>  CAccessToken::GetLogonSessionId  
 Вызовите этот метод, чтобы получить идентификатор сеанса входа в систему, связанных с `CAccessToken` объекта.  
  
```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pluid`  
 Указатель на [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) которого будет получать идентификатор сеанса входа в систему.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `pluid` является недопустимым значением.  
  
##  <a name="getlogonsid"></a>  CAccessToken::GetLogonSid  
 Этот метод вызывается для получения идентификатора безопасности входа в систему, связанных с `CAccessToken` объекта.  
  
```
bool GetLogonSid(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid класс](../../atl/reference/csid-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если *pSid* не является допустимым значением.  
  
##  <a name="getowner"></a>  CAccessToken::GetOwner  
 Этот метод вызывается для получения владельца, связанного с `CAccessToken` объекта.  
  
```
bool GetOwner(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid класс](../../atl/reference/csid-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Владелец устанавливается по умолчанию на любые объекты, созданные, когда действует этот маркер доступа.  
  
##  <a name="getprimarygroup"></a>  CAccessToken::GetPrimaryGroup  
 Вызовите этот метод, чтобы получить основную группу, связанную с `CAccessToken` объекта.  
  
```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid класс](../../atl/reference/csid-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Группы устанавливается по умолчанию на любые объекты, созданные, когда действует этот маркер доступа.  
  
##  <a name="getprivileges"></a>  CAccessToken::GetPrivileges  
 Этот метод получает права доступа, связанные с `CAccessToken` объекта.  
  
```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pPrivileges`  
 Указатель на [CTokenPrivileges класс](../../atl/reference/ctokenprivileges-class.md) объекта, который будет получать права доступа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="getprocesstoken"></a>  CAccessToken::GetProcessToken  
 Этот метод вызывается для инициализации `CAccessToken` с маркером доступа из указанного процесса.  
  
```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Указывает маску доступа, которая указывает запрошенных типов доступа в маркер доступа. Эти типы доступ к запрошенному ресурсу сравниваются с DACL токена, чтобы определить, какой доступ разрешен или запрещен.  
  
 *hProcess*  
 Процесс, маркер доступа которого был открыт дескриптор. Если значение по умолчанию `NULL` — используется, используется текущий процесс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `true` в случае успешного выполнения `false` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [OpenProcessToken](http://msdn.microsoft.com/library/aa379295\(vs.85\).aspx) функции Win32.  
  
##  <a name="getprofile"></a>  CAccessToken::GetProfile  
 Вызовите этот метод, чтобы получить маркер, указывающий на профиль пользователя, связанный с `CAccessToken` объекта.  
  
```
HANDLE GetProfile() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор, указывающий профиль пользователя, или значение NULL, если профиль не существует.  
  
##  <a name="getsource"></a>  CAccessToken::GetSource  
 Этот метод вызывается для получения источника `CAccessToken` объекта.  
  
```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pSource*  
 Указатель на [TOKEN_SOURCE](http://msdn.microsoft.com/library/windows/desktop/aa379631) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="getstatistics"></a>  CAccessToken::GetStatistics  
 Этот метод вызывается для получения сведений, связанных с `CAccessToken` объекта.  
  
```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pStatistics*  
 Указатель на [TOKEN_STATISTICS](http://msdn.microsoft.com/library/windows/desktop/aa379632) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="getterminalservicessessionid"></a>  CAccessToken::GetTerminalServicesSessionId  
 Вызовите этот метод, чтобы получить идентификатор сеанса служб терминалов, связанный с `CAccessToken` объекта.  
  
```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pdwSessionId*  
 Идентификатор сеанса служб терминалов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="getthreadtoken"></a>  CAccessToken::GetThreadToken  
 Этот метод вызывается для инициализации `CAccessToken` с маркером из данного потока.  
  
```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Указывает маску доступа, которая указывает запрошенных типов доступа в маркер доступа. Эти типы доступ к запрошенному ресурсу сравниваются с DACL токена, чтобы определить, какой доступ разрешен или запрещен.  
  
 `hThread`  
 Дескриптор потока, маркер доступа которого был открыт.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа к контекст безопасности вызывающего потока `GetThreadToken` метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="gettokenid"></a>  CAccessToken::GetTokenId  
 Этот метод вызывается для получения маркера идентификатор, связанный с `CAccessToken` объекта.  
  
```
bool GetTokenId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pluid`  
 Указатель на [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) которого будет получать идентификатор маркера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="gettype"></a>  CAccessToken::GetType  
 Этот метод вызывается для получения токена типа `CAccessToken` объекта.  
  
```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pType`  
 Адрес [TOKEN_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379633) переменную, которая, в случае успешного выполнения получает тип маркера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 **TOKEN_TYPE** тип перечисления, который содержит значения, которые отличаются для разных основной маркер и маркер олицетворения.  
  
##  <a name="getuser"></a>  CAccessToken::GetUser  
 Этот метод вызывается для идентификации пользователя, связанного с `CAccessToken` объекта.  
  
```
bool GetUser(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid класс](../../atl/reference/csid-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="hkeycurrentuser"></a>  CAccessToken::HKeyCurrentUser  
 Вызовите этот метод, чтобы получить маркер, указывающий на профиль пользователя, связанный с `CAccessToken` объекта.  
  
```
HKEY HKeyCurrentUser() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор, указывающий профиль пользователя, или значение NULL, если профиль не существует.  
  
##  <a name="impersonate"></a>  CAccessToken::Impersonate  
 Вызовите этот метод, чтобы назначить олицетворение `CAccessToken` потоку.  
  
```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `hThread`  
 Дескриптор потока, чтобы присвоить маркер олицетворения для. Этот дескриптор должен быть открыт с TOKEN_IMPERSONATE правами доступа. Если `hThread` имеет значение NULL, этот метод создает поток, который необходимо прекратить использовать маркер олицетворения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `CAccessToken` имеет допустимый указатель на токен.  
  
 [CAutoRevertImpersonation класса](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматической отмены маркера олицетворенного доступа.  
  
##  <a name="impersonateloggedonuser"></a>  CAccessToken::ImpersonateLoggedOnUser  
 Этот метод позволяет вызывающему потоку олицетворять контекст безопасности пользователя, выполнившего вход.  
  
```
bool ImpersonateLoggedOnUser() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  Если для какой-либо причине не удается вызвать функцию олицетворения, клиент не олицетворяется и запрос клиента выполняется в контексте безопасности процесса, из которого был выполнен вызов. Если процесс выполняется как высоко привилегированной учетной записи, или как член группы администраторов, пользователь может выполнять действия он или она бы в противном случае быть запрещено. Таким образом возвращаемое значение для этой функции всегда быть подтверждено.  
  
##  <a name="istokenrestricted"></a>  CAccessToken::IsTokenRestricted  
 Этот метод вызывается для проверки, если `CAccessToken` объект содержит список ограниченных идентификаторов безопасности.  
  
```
bool IsTokenRestricted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если объект содержит список ограничивающих SID, значение false, если нет ограничивающих идентификаторов, или если метод завершается ошибкой.  
  
##  <a name="loaduserprofile"></a>  CAccessToken::LoadUserProfile  
 Вызовите этот метод, чтобы загрузить профиль пользователя, связанный с `CAccessToken` объекта.  
  
```
bool LoadUserProfile() throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `CAccessToken` не содержит допустимый токен, или если профиль пользователя уже существует.  
  
##  <a name="logonuser"></a>  CAccessToken::LogonUser  
 Этот метод используется для создания сеанса входа в систему для пользователя, связанного с заданными учетными данными.  
  
```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszUserName`  
 Указатель на строку символом null, указывающее имя пользователя. Это имя учетной записи пользователя, войдите в систему.  
  
 *pszDomain*  
 Указатель на строку символом null, указывающее имя домена или сервера, базу данных которой учетная запись содержит `pszUserName` учетной записи.  
  
 `pszPassword`  
 Указатель на строку, завершающуюся значением null, указывающее пароль для учетной записи пользователя, открытым текстом `pszUserName`.  
  
 *dwLogonType*  
 Указывает тип выполняемой операции входа в систему. В разделе [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) для получения дополнительных сведений.  
  
 *dwLogonProvider*  
 Указывает поставщика, вход в систему. В разделе [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) для получения дополнительных сведений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Доступ, маркер, полученный из вход в систему будет связан с `CAccessToken`. Для успешного выполнения этого метода `CAccessToken` должен храниться в объекте SE_TCB_NAME правами, идентификации держателя как часть доверенного компьютера базового. В разделе [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) более подробные сведения о необходимых прав.  
  
##  <a name="opencomclienttoken"></a>  CAccessToken::OpenCOMClientToken  
 Вызов этого метода в обработке вызов от клиента для инициализации COM-сервера `CAccessToken` с маркером доступа из COM-клиент.  
  
```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Указывает маску доступа, которая указывает запрошенных типов доступа в маркер доступа. Эти типы доступ к запрошенному ресурсу сравниваются с DACL токена, чтобы определить, какой доступ разрешен или запрещен.  
  
 `bImpersonate`  
 Значение true, если текущий поток будет олицетворять вызывающий клиент COM, если этот вызов завершается успешно. Если значение равно false, маркер доступа будет открыт, но поток не будет иметь маркер олицетворения после завершения этого вызова.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа к контекст безопасности вызывающего потока [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 [Класса CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматической отмены олицетворенного доступа токены, созданные, задав `bImpersonate` флаг *true*.  
  
##  <a name="opennamedpipeclienttoken"></a>  CAccessToken::OpenNamedPipeClientToken  
 Вызовите этот метод из на сервере запросов на получение по именованному каналу для инициализации `CAccessToken` с маркером доступа от клиента.  
  
```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *hPipe*  
 Дескриптор именованного канала.  
  
 `dwDesiredAccess`  
 Указывает маску доступа, которая указывает запрошенных типов доступа в маркер доступа. Эти типы доступ к запрошенному ресурсу сравниваются с DACL токена, чтобы определить, какой доступ разрешен или запрещен.  
  
 `bImpersonate`  
 Значение true, если текущий поток будет олицетворять вызывающий клиент канала, если этот вызов завершается успешно. Если значение равно false, маркер доступа будет открыт, но поток не будет иметь маркер олицетворения после завершения этого вызова.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа к контекст безопасности вызывающего потока [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 [Класса CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматической отмены олицетворенного доступа токены, созданные, задав `bImpersonate` флаг *true*.  
  
##  <a name="openrpcclienttoken"></a>  CAccessToken::OpenRPCClientToken  
 Вызовите этот метод из сервера обработки вызовов из клиента RPC для инициализации `CAccessToken` с маркером доступа от клиента.  
  
```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *BindingHandle*  
 Дескриптор привязки на сервере, представляющий привязку к клиенту.  
  
 `dwDesiredAccess`  
 Указывает маску доступа, которая указывает запрошенных типов доступа в маркер доступа. Эти типы доступ к запрошенному ресурсу сравниваются с DACL токена, чтобы определить, какой доступ разрешен или запрещен.  
  
 `bImpersonate`  
 Значение true, если текущий поток будет олицетворять вызывающий клиент RPC, если этот вызов завершается успешно. Если значение равно false, маркер доступа будет открыт, но поток не будет иметь маркер олицетворения после завершения этого вызова.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа к контекст безопасности вызывающего потока [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 [Класса CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматической отмены олицетворенного доступа токены, созданные, задав `bImpersonate` флаг *true*.  
  
##  <a name="openthreadtoken"></a>  CAccessToken::OpenThreadToken  
 Вызовите этот метод для настройки уровня олицетворения, а затем инициализировать `CAccessToken` с маркером из данного потока.  
  
```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Указывает маску доступа, которая указывает запрошенных типов доступа в маркер доступа. Эти типы доступ к запрошенному ресурсу сравниваются с DACL токена, чтобы определить, какой доступ разрешен или запрещен.  
  
 `bImpersonate`  
 Значение true, если поток остается на уровне запрошенного олицетворения после завершения этого метода. Если значение равно false, поток будет понижен до его исходный уровень олицетворения.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа к контекст безопасности вызывающего потока [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
 `sil`  
 Указывает [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) перечисляемый тип, предоставляющий уровень олицетворения маркера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `OpenThreadToken`Аналогично [CAccessToken::GetThreadToken](#getthreadtoken), но задает уровень олицетворения перед инициализацией `CAccessToken` из потока маркер доступа.  
  
 [Класса CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматической отмены олицетворенного доступа токены, созданные, задав `bImpersonate` флаг *true*.  
  
##  <a name="privilegecheck"></a>  CAccessToken::PrivilegeCheck  
 Вызовите этот метод, чтобы определить, включены ли в указанный набор прав, **CAccessToken** объекта.  
  
```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
     bool* pbResult) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *RequiredPrivileges*  
 Указатель на [PRIVILEGE_SET](http://msdn.microsoft.com/library/windows/desktop/aa379307) структуры.  
  
 *pbResult*  
 Указатель на значение, задает метод для указания того, включены ли любые или все привилегии, указанного в `CAccessToken` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Когда `PrivilegeCheck` возвращает, **атрибуты** каждого элемента [подробности](http://msdn.microsoft.com/library/windows/desktop/aa379263) структуры задано значение SE_PRIVILEGE_USED_FOR_ACCESS, если включен соответствующий прав доступа. Этот метод вызывает метод [PrivilegeCheck](http://msdn.microsoft.com/library/windows/desktop/aa379304) функции Win32.  
  
##  <a name="revert"></a>  CAccessToken::Revert  
 Вызовите этот метод, чтобы остановить поток из используется маркер олицетворения.  
  
```
bool Revert(HANDLE hThread = NULL) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hThread`  
 Дескриптор потока, чтобы восстановить из олицетворения. Если *hThread* имеет значение NULL, предполагается, что текущий поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Изменения версии олицетворения токенов может производиться автоматически с [CAutoRevertImpersonation класса](../../atl/reference/cautorevertimpersonation-class.md).  
  
##  <a name="setdefaultdacl"></a>  CAccessToken::SetDefaultDacl  
 Этот метод вызывается для установки по умолчанию список DACL `CAccessToken` объекта.  
  
```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rDacl`  
 Новое значение по умолчанию [CDacl класса](../../atl/reference/cdacl-class.md) сведения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию DACL — DACL, который используется по умолчанию, когда создаются новые объекты с маркером доступа в силе.  
  
##  <a name="setowner"></a>  CAccessToken::SetOwner  
 Вызовите этот метод, чтобы задать владельца `CAccessToken` объекта.  
  
```
bool SetOwner(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 [Класс CSid](../../atl/reference/csid-class.md) объект, содержащий сведения о владельце.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Владелец является владельцем по умолчанию, используемый для новых объектов, создаваемых, когда действует этот маркер доступа.  
  
##  <a name="setprimarygroup"></a>  CAccessToken::SetPrimaryGroup  
 Вызовите этот метод для установки основной группы `CAccessToken` объекта.  
  
```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 [Класс CSid](../../atl/reference/csid-class.md) объект, содержащий сведения основную группу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Основная группа является группу по умолчанию для новых объектов, создаваемых, когда действует этот маркер доступа.  
  
## <a name="see-also"></a>См. также  
 [Пример ATLSecurity](../../visual-cpp-samples.md)   
 [Маркеры доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
