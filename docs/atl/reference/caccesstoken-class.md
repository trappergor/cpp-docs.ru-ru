---
title: Класс CAccessToken | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3157db05d183ab9ada2ad53443ca5b20bcfbcba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136326"
---
# <a name="caccesstoken-class"></a>Класс CAccessToken

Этот класс является оболочкой для маркера доступа.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAccessToken
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAccessToken:: ~ CAccessToken](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAccessToken::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем дескриптора маркера доступ.|
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|Вызовите этот метод, чтобы определить, включен ли указанный идентификатор SID в `CAccessToken` объекта.|
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Этот метод используется для создания нового маркера доступа олицетворения.|
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Этот метод используется для создания нового основного маркера.|
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Вызовите этот метод для создания нового процесса в контексте безопасности пользователя, представленного `CAccessToken` объекта.|
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Вызовите этот метод, чтобы создать новую, ограниченные `CAccessToken` объекта.|
|[CAccessToken::Detach](#detach)|Вызовите этот метод, чтобы отозвать права владения маркера доступа.|
|[CAccessToken::DisablePrivilege](#disableprivilege)|Вызовите этот метод, чтобы отключить привилегии в `CAccessToken` объекта.|
|[CAccessToken::DisablePrivileges](#disableprivileges)|Вызовите этот метод, чтобы отключить один или несколько привилегии в `CAccessToken` объекта.|
|[CAccessToken::EnablePrivilege](#enableprivilege)|Вызовите этот метод, чтобы включить привилегию в `CAccessToken` объекта.|
|[CAccessToken::EnablePrivileges](#enableprivileges)|Вызовите этот метод, чтобы включить один или несколько привилегии в `CAccessToken` объекта.|
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Вызовите этот метод для возврата `CAccessToken` объекта по умолчанию DACL.|
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Вызовите этот метод для получения `CAccessToken` равное в маркер доступа, установленный для текущего потока.|
|[CAccessToken::GetGroups](#getgroups)|Вызовите этот метод для возврата `CAccessToken` объекта маркера групп.|
|[CAccessToken::GetHandle](#gethandle)|Этот метод используется для получения дескриптора в маркер доступа.|
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Этот метод используется для получения маркера доступа уровень олицетворения.|
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|Вызовите этот метод, чтобы получить идентификатор сеанса входа в систему, связанных с `CAccessToken` объекта.|
|[CAccessToken::GetLogonSid](#getlogonsid)|Вызовите этот метод для получения идентификатора безопасности входа в систему, связанных с `CAccessToken` объекта.|
|[CAccessToken::GetOwner](#getowner)|Вызовите этот метод для получения владельца, связанный с `CAccessToken` объекта.|
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|Вызовите этот метод, чтобы получить основную группу, связанную с `CAccessToken` объекта.|
|[CAccessToken::GetPrivileges](#getprivileges)|Вызовите этот метод, чтобы получить разрешения, связанные с `CAccessToken` объекта.|
|[CAccessToken::GetProcessToken](#getprocesstoken)|Вызовите этот метод для инициализации `CAccessToken` с маркером доступа из указанного процесса.|
|[CAccessToken::GetProfile](#getprofile)|Вызовите этот метод, чтобы получить дескриптор, указывающий на профиль пользователя, связанный с `CAccessToken` объекта.|
|[CAccessToken::GetSource](#getsource)|Вызовите этот метод для получения источника `CAccessToken` объекта.|
|[CAccessToken::GetStatistics](#getstatistics)|Вызовите этот метод для получения сведений, связанных с `CAccessToken` объекта.|
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|Вызовите этот метод, чтобы получить идентификатор сеанса служб терминалов, связанные с `CAccessToken` объекта.|
|[CAccessToken::GetThreadToken](#getthreadtoken)|Вызовите этот метод для инициализации `CAccessToken` с маркером из данного потока.|
|[CAccessToken::GetTokenId](#gettokenid)|Вызовите этот метод, чтобы получить идентификатор токена, связанный с `CAccessToken` объекта.|
|[CAccessToken::GetType](#gettype)|Вызовите этот метод для получения маркера типа `CAccessToken` объекта.|
|[CAccessToken::GetUser](#getuser)|Вызовите этот метод для идентификации пользователя, связанного с `CAccessToken` объекта.|
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|Вызовите этот метод, чтобы получить дескриптор, указывающий на профиль пользователя, связанный с `CAccessToken` объекта.|
|[CAccessToken::Impersonate](#impersonate)|Вызовите этот метод, чтобы назначить олицетворение `CAccessToken` потоку.|
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Этот метод позволяет вызывающему потоку олицетворять контекст безопасности пользователя, вошедшего в систему.|
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Вызовите этот метод для проверки, если `CAccessToken` объект содержит список ограниченных SID.|
|[CAccessToken::LoadUserProfile](#loaduserprofile)|Вызовите этот метод для загрузки профиля пользователя, связанный с `CAccessToken` объекта.|
|[CAccessToken::LogonUser](#logonuser)|Этот метод используется для создания сеанса входа в систему для пользователя, связанного с заданными учетными данными.|
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Вызов этого метода в COM-сервера, обрабатывающего вызов от клиента, чтобы инициализировать `CAccessToken` с маркером доступа COM-клиент.|
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Этот метод из на сервере запросов выполняется по именованному каналу для инициализации `CAccessToken` с маркером доступа от клиента.|
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Вызовите этот метод из сервера обработки вызов из клиента RPC для инициализации `CAccessToken` с маркером доступа от клиента.|
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Вызовите этот метод для установки уровня олицетворения, а затем инициализировать `CAccessToken` с маркером из данного потока.|
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Вызовите этот метод, чтобы определить, включены ли в указанный набор привилегий, `CAccessToken` объекта.|
|[CAccessToken::Revert](#revert)|Этот метод используется для остановки потока, который использует маркер олицетворения.|
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Вызовите этот метод, чтобы задать значение по умолчанию список DACL `CAccessToken` объекта.|
|[CAccessToken::SetOwner](#setowner)|Вызовите этот метод, чтобы задать владельца `CAccessToken` объекта.|
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Вызовите этот метод для установки на основную группу `CAccessToken` объекта.|

## <a name="remarks"></a>Примечания

[Маркер доступа](/windows/desktop/SecAuthZ/access-tokens) — это объект, описывающий контекст безопасности процесса или потока и выделяется для каждого вошедшего в систему Windows.

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="attach"></a>  CAccessToken::Attach

Вызовите этот метод, чтобы стать владельцем дескриптора маркера доступ.

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>Параметры

*hToken*<br/>
Дескриптор маркера доступа.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет ошибка утверждения, если `CAccessToken` объект уже имеет права владения маркера доступа.

##  <a name="dtor"></a>  CAccessToken:: ~ CAccessToken

Деструктор

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="checktokenmembership"></a>  CAccessToken::CheckTokenMembership

Вызовите этот метод, чтобы определить, включен ли указанный идентификатор SID в `CAccessToken` объекта.

```
bool CheckTokenMembership(
    const CSid& rSid, 
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>Параметры

*rSid*<br/>
Ссылка на [класс CSid](../../atl/reference/csid-class.md) объекта.

*pbIsMember*<br/>
Указатель на переменную, получающую результаты проверки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`CheckTokenMembership` Метод проверяет на наличие идентификатора безопасности пользователей и группы идентификаторов безопасности маркера доступа. Если идентификатор безопасности существует и имеет атрибут SE_GROUP_ENABLED *pbIsMember* — задать значение TRUE; в противном случае — значение, он имеет значение FALSE.

В отладочных сборках, произойдет ошибка утверждения, если *pbIsMember* не является допустимым указателем.

> [!NOTE]
>  `CAccessToken` Объект должен быть маркер олицетворения и не основной маркер.

##  <a name="createimpersonationtoken"></a>  CAccessToken::CreateImpersonationToken

Этот метод используется для создания маркера доступа олицетворения.

```
bool CreateImpersonationToken(
    CAccessToken* pImp, 
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>Параметры

*pImp*<br/>
Указатель на новый `CAccessToken` объекта.

*инвентаризацию программного обеспечения*<br/>
Указывает [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) перечислимый тип, который предоставляет уровень олицетворения новый маркер.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`CreateImpersonationToken` вызовы [DuplicateToken](https://msdn.microsoft.com/library/windows/desktop/aa446616) создать новый маркер олицетворения.

##  <a name="createprimarytoken"></a>  CAccessToken::CreatePrimaryToken

Этот метод используется для создания нового основного маркера.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pPri*<br/>
Указатель на новый `CAccessToken` объекта.

*dwDesiredAccess*<br/>
Указывает права доступа, запрошенный для нового токена. По умолчанию, MAXIMUM_ALLOWED, запрашивает все права доступа, которые являются допустимыми для вызывающего объекта. См. в разделе [права доступа и масок доступа](/windows/desktop/SecAuthZ/access-rights-and-access-masks) дополнительные права на доступ.

*pTokenAttributes*<br/>
Указатель на [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) структура, которая указывает дескриптор безопасности для нового токена и определяет, могут ли дочерние процессы наследуют маркер. Если *pTokenAttributes* имеет значение NULL, маркер возвращает дескриптор безопасности по умолчанию и не может быть унаследован дескриптор.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`CreatePrimaryToken` вызовы [DuplicateTokenEx](https://msdn.microsoft.com/library/windows/desktop/aa446617) для создания нового основного маркера.

##  <a name="createprocessasuser"></a>  CAccessToken::CreateProcessAsUser

Вызовите этот метод для создания нового процесса в контексте безопасности пользователя, представленного `CAccessToken` объекта.

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

*pApplicationName*<br/>
Указатель на заканчивающуюся нулем строку, указывающую модуле выполнялись. Этот параметр не может иметь значение NULL.

*pCommandLine*<br/>
Указатель на заканчивающуюся нулем строку, которая указывает командную строку для выполнения.

*pProcessInformation*<br/>
Указатель на [PROCESS_INFORMATION](/windows/desktop/api/processthreadsapi/ns-processthreadsapi-_process_information) структуру, которая получает идентификационную информацию о новом процессе.

*pStartupInfo*<br/>
Указатель на [STARTUPINFO](/windows/desktop/api/processthreadsapi/ns-processthreadsapi-_startupinfoa) структуру, которая указывает, как должно выглядеть главного окна для нового процесса.

*dwCreationFlags*<br/>
Задает дополнительные флаги, определяющие с приоритетом и создание процесса. Функция Win32 см. в разделе [CreateProcessAsUser](https://msdn.microsoft.com/library/windows/desktop/ms682429) список флагов.

*bLoadProfile*<br/>
Значение TRUE, если профиль пользователя загружен с [LoadUserProfile](/windows/desktop/api/userenv/nf-userenv-loaduserprofilea).

*pProcessAttributes*<br/>
Указатель на [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) структура, которая указывает дескриптор безопасности для нового процесса и определяет, могут ли дочерние процессы наследуют возвращенный дескриптор. Если *pProcessAttributes* имеет значение NULL, процесс получает дескриптор безопасности по умолчанию и не может быть унаследован дескриптор.

*pThreadAttributes*<br/>
Указатель на [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) структура, которая указывает дескриптор безопасности для нового потока и определяет, могут ли дочерние процессы наследуют возвращенный дескриптор. Если *pThreadAttributes* имеет значение NULL, поток получает дескриптор безопасности по умолчанию и не может быть унаследован дескриптор.

*bInherit*<br/>
Указывает, является ли новый процесс наследует маркеры из вызывающего процесса. Значение TRUE, если каждый наследуемые открытый дескриптор в вызывающий процесс наследуется новый процесс. Унаследованные дескрипторы обладают теми же привилегиями значение и доступа исходные дескрипторы.

*pCurrentDirectory*<br/>
Указатель на заканчивающуюся нулем строку, которая указывает текущий диск и каталог для нового процесса. Строка должна быть полный путь, который содержит букву диска. Если этот параметр имеет значение NULL, новый процесс будет иметь диск и каталог как вызывающий процесс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`CreateProcessAsUser` использует `CreateProcessAsUser` функцию Win32 для создания нового процесса, который выполняется в контексте безопасности пользователя, представленного `CAccessToken` объекта. См. в описании [CreateProcessAsUser](https://msdn.microsoft.com/library/windows/desktop/ms682429) функция полное описание параметров, необходимых.

Для успешного выполнения этого метода `CAccessToken` должен храниться в объекте AssignPrimaryToken (если он является ограниченным маркером) и IncreaseQuota привилегии.

##  <a name="createrestrictedtoken"></a>  CAccessToken::CreateRestrictedToken

Вызовите этот метод, чтобы создать новую, ограниченные `CAccessToken` объекта.

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>Параметры

*pRestrictedToken*<br/>
Новый, ограниченные `CAccessToken` объекта.

*SidsToDisable*<br/>
Объект `CTokenGroups` , указывающий только идентификаторы безопасности.

*SidsToRestrict*<br/>
Объект `CTokenGroups` , указывающий ограничивающими идентификаторами безопасности.

*PrivilegesToDelete*<br/>
Объект `CTokenPrivileges` , указывающий удаляемых прав в маркер ограничения. Значение по умолчанию создает пустой объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`CreateRestrictedToken` использует [CreateRestrictedToken](https://msdn.microsoft.com/library/windows/desktop/aa446583) функцию Win32 для создания нового `CAccessToken` объект с ограничениями.

> [!IMPORTANT]
>  При использовании `CreateRestrictedToken`, проверьте следующие: существующий маркер является допустимым (и не введенное пользователем) и *SidsToDisable* и *PrivilegesToDelete* допустимым (и не введенное пользователем). Если метод возвращает значение FALSE, запретите функциональные возможности.

##  <a name="detach"></a>  CAccessToken::Detach

Вызовите этот метод, чтобы отозвать права владения маркера доступа.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор `CAccessToken` которого была отсоединена.

### <a name="remarks"></a>Примечания

Этот метод отменяет `CAccessToken`на владение маркер доступа.

##  <a name="disableprivilege"></a>  CAccessToken::DisablePrivilege

Вызовите этот метод, чтобы отключить привилегии в `CAccessToken` объекта.

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*pszPrivilege*<br/>
Указатель на строку, содержащую привилегий, чтобы отключить в `CAccessToken` объекта.

*pPreviousState*<br/>
Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние прав доступа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="disableprivileges"></a>  CAccessToken::DisablePrivileges

Вызовите этот метод, чтобы отключить один или несколько привилегии в `CAccessToken` объекта.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*rPrivileges*<br/>
Указатель на массив строк, содержащий привилегии, чтобы отключить в `CAccessToken` объекта.

*pPreviousState*<br/>
Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние прав доступа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="enableprivilege"></a>  CAccessToken::EnablePrivilege

Вызовите этот метод, чтобы включить привилегию в `CAccessToken` объекта.

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*pszPrivilege*<br/>
Указатель на строку, содержащую привилегий, чтобы включить в `CAccessToken` объекта.

*pPreviousState*<br/>
Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние прав доступа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="enableprivileges"></a>  CAccessToken::EnablePrivileges

Вызовите этот метод, чтобы включить один или несколько привилегии в `CAccessToken` объекта.

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*rPrivileges*<br/>
Указатель на массив строк, содержащий привилегии, чтобы включить в `CAccessToken` объекта.

*pPreviousState*<br/>
Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние прав доступа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="getdefaultdacl"></a>  CAccessToken::GetDefaultDacl

Вызовите этот метод для возврата `CAccessToken` объекта по умолчанию DACL.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>Параметры

*pDacl*<br/>
Указатель на [класс CDacl](../../atl/reference/cdacl-class.md) объект, который будет получать `CAccessToken` объекта по умолчанию DACL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если DACL по умолчанию был восстановленный, и FALSE в противном случае.

##  <a name="geteffectivetoken"></a>  CAccessToken::GetEffectiveToken

Вызовите этот метод для получения `CAccessToken` равное в маркер доступа, установленный для текущего потока.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Указывает маски доступа, указывающее запрошенных типов доступа к маркеру доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="getgroups"></a>  CAccessToken::GetGroups

Вызовите этот метод для возврата `CAccessToken` объекта маркера групп.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>Параметры

*pGroups*<br/>
Указатель на [класс CTokenGroups](../../atl/reference/ctokengroups-class.md) объект, который будет получать сведения о группе.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="gethandle"></a>  CAccessToken::GetHandle

Этот метод используется для получения дескриптора в маркер доступа.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор `CAccessToken` маркер доступа для объекта.

##  <a name="getimpersonationlevel"></a>  CAccessToken::GetImpersonationLevel

Этот метод используется для получения маркера доступа уровень олицетворения.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>Параметры

*pImpersonationLevel*<br/>
Указатель на [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) тип перечисления, который будет получать информацию об уровне олицетворения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="getlogonsessionid"></a>  CAccessToken::GetLogonSessionId

Вызовите этот метод, чтобы получить идентификатор сеанса входа в систему, связанных с `CAccessToken` объекта.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Параметры

*pluid*<br/>
Указатель на [LUID](/windows/desktop/api/winnt/ns-winnt-_luid) которого будет получать идентификатор сеанса входа в систему.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет ошибка утверждения, если *pluid* является недопустимым значением.

##  <a name="getlogonsid"></a>  CAccessToken::GetLogonSid

Вызовите этот метод для получения идентификатора безопасности входа в систему, связанных с `CAccessToken` объекта.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSid*<br/>
Указатель на [класс CSid](../../atl/reference/csid-class.md) объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет ошибка утверждения, если *pSid* является недопустимым значением.

##  <a name="getowner"></a>  CAccessToken::GetOwner

Вызовите этот метод для получения владельца, связанный с `CAccessToken` объекта.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSid*<br/>
Указатель на [класс CSid](../../atl/reference/csid-class.md) объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Владелец устанавливается по умолчанию на любые объекты, созданные, когда действует этот маркер доступа.

##  <a name="getprimarygroup"></a>  CAccessToken::GetPrimaryGroup

Вызовите этот метод, чтобы получить основную группу, связанную с `CAccessToken` объекта.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSid*<br/>
Указатель на [класс CSid](../../atl/reference/csid-class.md) объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Группы имеет значение по умолчанию на любые объекты, созданные, когда действует этот маркер доступа.

##  <a name="getprivileges"></a>  CAccessToken::GetPrivileges

Вызовите этот метод, чтобы получить разрешения, связанные с `CAccessToken` объекта.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>Параметры

*pPrivileges*<br/>
Указатель на [класс CTokenPrivileges](../../atl/reference/ctokenprivileges-class.md) объект, который будет получать привилегии.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="getprocesstoken"></a>  CAccessToken::GetProcessToken

Вызовите этот метод для инициализации `CAccessToken` с маркером доступа из указанного процесса.

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Указывает маски доступа, указывающее запрошенных типов доступа к маркеру доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.

*hProcess*<br/>
Дескриптор процесса открыт которого маркер доступа. Если используется значение по умолчанию NULL, используется текущий процесс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Вызовы [OpenProcessToken](https://msdn.microsoft.com/library/aa379295\(vs.85\).aspx) функции Win32.

##  <a name="getprofile"></a>  CAccessToken::GetProfile

Вызовите этот метод, чтобы получить дескриптор, указывающий на профиль пользователя, связанный с `CAccessToken` объекта.

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор, указывающий на профиль пользователя, или значение NULL, если профиль не существует.

##  <a name="getsource"></a>  CAccessToken::GetSource

Вызовите этот метод для получения источника `CAccessToken` объекта.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSource*<br/>
Указатель на [TOKEN_SOURCE](/windows/desktop/api/winnt/ns-winnt-_token_source) структуры.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="getstatistics"></a>  CAccessToken::GetStatistics

Вызовите этот метод для получения сведений, связанных с `CAccessToken` объекта.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>Параметры

*pStatistics*<br/>
Указатель на [TOKEN_STATISTICS](/windows/desktop/api/winnt/ns-winnt-_token_statistics) структуры.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="getterminalservicessessionid"></a>  CAccessToken::GetTerminalServicesSessionId

Вызовите этот метод, чтобы получить идентификатор сеанса служб терминалов, связанные с `CAccessToken` объекта.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>Параметры

*pdwSessionId*<br/>
Идентификатор сеанса служб терминалов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="getthreadtoken"></a>  CAccessToken::GetThreadToken

Вызовите этот метод для инициализации `CAccessToken` с маркером из данного потока.

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Указывает маски доступа, указывающее запрошенных типов доступа к маркеру доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.

*hThread*<br/>
Дескриптор потока, открывается которого маркер доступа.

*bOpenAsSelf*<br/>
Указывает, является ли проверка доступа, которые должны выполняться контекст безопасности вызывающего потока `GetThreadToken` метода или в контексте безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с помощью контекста безопасности для вызывающего потока. Если олицетворение потока выполняется в клиент, этот контекст безопасности может быть имя клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа с помощью контекст безопасности процесса для вызывающего потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="gettokenid"></a>  CAccessToken::GetTokenId

Вызовите этот метод, чтобы получить идентификатор токена, связанный с `CAccessToken` объекта.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Параметры

*pluid*<br/>
Указатель на [LUID](/windows/desktop/api/winnt/ns-winnt-_luid) которого будет получать идентификатор маркера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="gettype"></a>  CAccessToken::GetType

Вызовите этот метод для получения маркера типа `CAccessToken` объекта.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>Параметры

*pType*<br/>
Адрес [TOKEN_TYPE](/windows/desktop/api/winnt/ne-winnt-_token_type) переменную, которая, в случае успешного выполнения получает тип токена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Тип перечисления TOKEN_TYPE содержит значения, различать основной маркер и маркер олицетворения.

##  <a name="getuser"></a>  CAccessToken::GetUser

Вызовите этот метод для идентификации пользователя, связанного с `CAccessToken` объекта.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSid*<br/>
Указатель на [класс CSid](../../atl/reference/csid-class.md) объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="hkeycurrentuser"></a>  CAccessToken::HKeyCurrentUser

Вызовите этот метод, чтобы получить дескриптор, указывающий на профиль пользователя, связанный с `CAccessToken` объекта.

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор, указывающий на профиль пользователя, или значение NULL, если профиль не существует.

##  <a name="impersonate"></a>  CAccessToken::Impersonate

Вызовите этот метод, чтобы назначить олицетворение `CAccessToken` потоку.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*hThread*<br/>
Дескриптор потока, чтобы присвоить маркер олицетворения для. Этот дескриптор должен быть открыт с правами доступа TOKEN_IMPERSONATE. Если *hThread* имеет значение NULL, метод приводит к прекращению использования маркер олицетворения потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет ошибка утверждения, если `CAccessToken` не имеет допустимый указатель на маркер.

[Класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) может использоваться для автоматической отмены маркеров олицетворенного доступа.

##  <a name="impersonateloggedonuser"></a>  CAccessToken::ImpersonateLoggedOnUser

Этот метод позволяет вызывающему потоку олицетворять контекст безопасности пользователя, вошедшего в систему.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

> [!IMPORTANT]
>  Если какой-либо причине произошел сбой вызова функции олицетворения, не олицетворить клиент и запрос клиента выполняется в контексте безопасности процесса, из которого был выполнен вызов. Если процесс выполняется как учетная запись с широким, или как член группы администраторов, пользователь может выполнять действия он или она будет в противном случае запрещено. Таким образом возвращаемое значение для этой функции следует всегда подтвердить.

##  <a name="istokenrestricted"></a>  CAccessToken::IsTokenRestricted

Вызовите этот метод для проверки, если `CAccessToken` объект содержит список ограниченных SID.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объект содержит список ограничивающих идентификаторов безопасности, FALSE в том случае, если нет ограничивающими идентификаторами безопасности или при сбое метода.

##  <a name="loaduserprofile"></a>  CAccessToken::LoadUserProfile

Вызовите этот метод для загрузки профиля пользователя, связанный с `CAccessToken` объекта.

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет ошибка утверждения, если `CAccessToken` не содержит допустимый токен, или если профиль пользователя, уже существует.

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

*pszUserName*<br/>
Указатель на заканчивающуюся нулем строку, которая указывает имя пользователя. Это имя учетной записи пользователя, войдите в систему.

*pszDomain*<br/>
Указатель на заканчивающуюся нулем строку, указывающее имя домена или сервера, базу данных которой учетная запись содержит *pszUserName* учетной записи.

*pszPassword*<br/>
Указатель на заканчивающуюся нулем строку, указывающее пароль для учетной записи пользователя, открытый текст *pszUserName*.

*dwLogonType*<br/>
Указывает тип выполняемой операции входа в систему. См. в разделе [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) для получения дополнительных сведений.

*dwLogonProvider*<br/>
Указывает поставщика входа в систему. См. в разделе [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) для получения дополнительных сведений.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Доступа, маркеров полученный в результате входа в систему будет связан с `CAccessToken`. Для успешного выполнения этого метода `CAccessToken` привилегии SE_TCB_NAME, идентификации держателя как часть базового доверенного компьютера должен храниться в объекте. См. в разделе [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) Дополнительные сведения о необходимых прав.

##  <a name="opencomclienttoken"></a>  CAccessToken::OpenCOMClientToken

Вызов этого метода в COM-сервера, обрабатывающего вызов от клиента, чтобы инициализировать `CAccessToken` с маркером доступа COM-клиент.

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Указывает маски доступа, указывающее запрошенных типов доступа к маркеру доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.

*bImpersonate*<br/>
Значение TRUE, если текущий поток будет олицетворять вызывающий клиент COM, если этот вызов завершается успешно. Если значение равно FALSE, маркер доступа будет открыт, но поток не получит маркер олицетворения после завершения этого вызова.

*bOpenAsSelf*<br/>
Указывает, является ли проверка доступа, которые должны выполняться контекст безопасности вызывающего потока [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) метода или в контексте безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с помощью контекста безопасности для вызывающего потока. Если олицетворение потока выполняется в клиент, этот контекст безопасности может быть имя клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа с помощью контекст безопасности процесса для вызывающего потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

[Класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) может использоваться для автоматической отмены маркеры олицетворенного доступа, созданные, задав *bImpersonate* флаг в значение TRUE.

##  <a name="opennamedpipeclienttoken"></a>  CAccessToken::OpenNamedPipeClientToken

Этот метод из на сервере запросов выполняется по именованному каналу для инициализации `CAccessToken` с маркером доступа от клиента.

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Параметры

*hPipe*<br/>
Дескриптор именованного канала.

*dwDesiredAccess*<br/>
Указывает маски доступа, указывающее запрошенных типов доступа к маркеру доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.

*bImpersonate*<br/>
Значение TRUE, если текущий поток будет олицетворять вызывающий клиент канала, если этот вызов завершается успешно. Если значение равно FALSE, маркер доступа будет открыт, но поток не получит маркер олицетворения после завершения этого вызова.

*bOpenAsSelf*<br/>
Указывает, является ли проверка доступа, которые должны выполняться контекст безопасности вызывающего потока [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) метода или в контексте безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с помощью контекста безопасности для вызывающего потока. Если олицетворение потока выполняется в клиент, этот контекст безопасности может быть имя клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа с помощью контекст безопасности процесса для вызывающего потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

[Класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) может использоваться для автоматической отмены маркеры олицетворенного доступа, созданные, задав *bImpersonate* флаг в значение TRUE.

##  <a name="openrpcclienttoken"></a>  CAccessToken::OpenRPCClientToken

Вызовите этот метод из сервера обработки вызов из клиента RPC для инициализации `CAccessToken` с маркером доступа от клиента.

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Параметры

*BindingHandle*<br/>
Дескриптор привязки на сервере, представляющий привязку к клиенту.

*dwDesiredAccess*<br/>
Указывает маски доступа, указывающее запрошенных типов доступа к маркеру доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.

*bImpersonate*<br/>
Значение TRUE, если текущий поток будет олицетворять вызывающий клиент RPC, если этот вызов завершается успешно. Если значение равно FALSE, маркер доступа будет открыт, но поток не получит маркер олицетворения после завершения этого вызова.

*bOpenAsSelf*<br/>
Указывает, является ли проверка доступа, которые должны выполняться контекст безопасности вызывающего потока [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) метода или в контексте безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с помощью контекста безопасности для вызывающего потока. Если олицетворение потока выполняется в клиент, этот контекст безопасности может быть имя клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа с помощью контекст безопасности процесса для вызывающего потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

[Класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) может использоваться для автоматической отмены маркеры олицетворенного доступа, созданные, задав *bImpersonate* флаг в значение TRUE.

##  <a name="openthreadtoken"></a>  CAccessToken::OpenThreadToken

Вызовите этот метод для установки уровня олицетворения, а затем инициализировать `CAccessToken` с маркером из данного потока.

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Указывает маски доступа, указывающее запрошенных типов доступа к маркеру доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.

*bImpersonate*<br/>
Значение TRUE, если поток остается на уровне запрошенного олицетворения после завершения этого метода. Если значение равно FALSE, поток вернется к исходный уровень олицетворения.

*bOpenAsSelf*<br/>
Указывает, является ли проверка доступа, которые должны выполняться контекст безопасности вызывающего потока [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) метода или в контексте безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с помощью контекста безопасности для вызывающего потока. Если олицетворение потока выполняется в клиент, этот контекст безопасности может быть имя клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа с помощью контекст безопасности процесса для вызывающего потока.

*инвентаризацию программного обеспечения*<br/>
Указывает [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) перечислимый тип, который предоставляет уровень олицетворения маркера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`OpenThreadToken` аналогичен [CAccessToken::GetThreadToken](#getthreadtoken), но задает уровень олицетворения перед инициализацией `CAccessToken` из потока маркер доступа.

[Класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) может использоваться для автоматической отмены маркеры олицетворенного доступа, созданные, задав *bImpersonate* флаг в значение TRUE.

##  <a name="privilegecheck"></a>  CAccessToken::PrivilegeCheck

Вызовите этот метод, чтобы определить, включены ли в указанный набор привилегий, `CAccessToken` объекта.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
     bool* pbResult) const throw();
```

### <a name="parameters"></a>Параметры

*RequiredPrivileges*<br/>
Указатель на [PRIVILEGE_SET](/windows/desktop/api/winnt/ns-winnt-_privilege_set) структуры.

*pbResult*<br/>
Указатель на значение задает метод, чтобы указать любые или все из заданного права, включены ли в `CAccessToken` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Когда `PrivilegeCheck` возвращении `Attributes` члены каждой [подробности](/windows/desktop/api/winnt/ns-winnt-_luid_and_attributes) структуры присваивается SE_PRIVILEGE_USED_FOR_ACCESS, если включен соответствующий привилегий. Этот метод вызывает метод [PrivilegeCheck](https://msdn.microsoft.com/library/windows/desktop/aa379304) функции Win32.

##  <a name="revert"></a>  CAccessToken::Revert

Вызовите этот метод, чтобы остановить поток из используется маркер олицетворения.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>Параметры

*hThread*<br/>
Дескриптор потока для возврата от олицетворения. Если *hThread* имеет значение NULL, предполагается, что текущий поток.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Редакция маркеры олицетворения может выполняться автоматически с [класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md).

##  <a name="setdefaultdacl"></a>  CAccessToken::SetDefaultDacl

Вызовите этот метод, чтобы задать значение по умолчанию список DACL `CAccessToken` объекта.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>Параметры

*rDacl*<br/>
Новое значение по умолчанию [класс CDacl](../../atl/reference/cdacl-class.md) сведения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

DACL по умолчанию используется DACL, который используется по умолчанию в том случае, когда создаются новые объекты с помощью этого маркера доступа в силе.

##  <a name="setowner"></a>  CAccessToken::SetOwner

Вызовите этот метод, чтобы задать владельца `CAccessToken` объекта.

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*rSid*<br/>
[Класс CSid](../../atl/reference/csid-class.md) объект, содержащий сведения о владельце.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Владелец является владельца по умолчанию, который используется для новых объектов, созданы, пока действует этот маркер доступа.

##  <a name="setprimarygroup"></a>  CAccessToken::SetPrimaryGroup

Вызовите этот метод для установки на основную группу `CAccessToken` объекта.

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*rSid*<br/>
[Класс CSid](../../atl/reference/csid-class.md) объект, содержащий сведения основную группу.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Основная группа является группой по умолчанию для новых объектов, созданы, пока действует этот маркер доступа.

## <a name="see-also"></a>См. также

[Пример ATLSecurity](../../visual-cpp-samples.md)<br/>
[Маркеры доступа](/windows/desktop/SecAuthZ/access-tokens)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
