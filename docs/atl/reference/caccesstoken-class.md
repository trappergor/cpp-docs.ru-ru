---
title: Класс CAccessToken
ms.date: 07/02/2019
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
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
ms.openlocfilehash: 9ae63946dfa6244e97c376f9eccd9bab93586990
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319037"
---
# <a name="caccesstoken-class"></a>Класс CAccessToken

Этот класс является оберткой для токена доступа.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CAccessToken
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAccessToken::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAccessToken::Attach](#attach)|Вызовите этот метод, чтобы взять на себя ответственность за данную ручку маркера доступа.|
|[CAccessToken::CheckTokenЧленство](#checktokenmembership)|Вызовите этот метод, чтобы определить, `CAccessToken` включен ли указанный SID в объекте.|
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Вызовите этот метод, чтобы создать новый маркер доступа олицетворения.|
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Вызовите этот метод, чтобы создать новый основной маркер.|
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Вызовите этот метод для создания нового процесса, работаемого `CAccessToken` в контексте безопасности пользователя, представленного объектом.|
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Вызовите этот метод, `CAccessToken` чтобы создать новый, ограниченный объект.|
|[CAccessToken: :Detach](#detach)|Вызовите этот метод, чтобы отозвать право собственности на токен доступа.|
|[CAccessToken: :DisablePrivilege](#disableprivilege)|Вызовите этот метод, чтобы `CAccessToken` отключить привилегию в объекте.|
|[CAccessToken: :DуправляемыеПривилегии](#disableprivileges)|Вызовите этот метод, чтобы отключить одну `CAccessToken` или несколько привилегий в объекте.|
|[CAccessToken:EnablePrivilege](#enableprivilege)|Вызовите этот метод, `CAccessToken` чтобы включить привилегию в объекте.|
|[CAccessToken:EnablePrivileges](#enableprivileges)|Вызовите этот метод, чтобы включить `CAccessToken` одну или несколько привилегий в объекте.|
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Вызовите этот `CAccessToken` метод, чтобы вернуть DACL объекта по умолчанию.|
|[CAccessToken:GetEffectiveToken](#geteffectivetoken)|Вызовите этот `CAccessToken` метод, чтобы получить объект, равный токену доступа, фактическидлянию для текущего потока.|
|[CAccessToken:GetGroups](#getgroups)|Вызовите этот `CAccessToken` метод, чтобы вернуть группы маркеров объекта.|
|[CAccessToken::GetHandle](#gethandle)|Вызовите этот метод, чтобы получить ручку к маркеру доступа.|
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Вызовите этот метод, чтобы получить уровень олицетворения из токена доступа.|
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|Вызовите этот метод, чтобы получить `CAccessToken` идентификатор сеанса Logon, связанный с объектом.|
|[CAccessToken::GetLogonSid](#getlogonsid)|Вызовите этот метод, чтобы получить `CAccessToken` Logon SID, связанный с объектом.|
|[CAccessToken::GetOwner](#getowner)|Вызовите этот метод, чтобы `CAccessToken` получить владельца, связанного с объектом.|
|[CAccessToken:GetPrimaryGroup](#getprimarygroup)|Вызовите этот метод, чтобы `CAccessToken` получить основную группу, связанную с объектом.|
|[CAccessToken::GetPrivileges](#getprivileges)|Вызовите этот метод, чтобы `CAccessToken` получить привилегии, связанные с объектом.|
|[CAccessToken:GetProcessToken](#getprocesstoken)|Вызовите этот метод, чтобы инициализировать `CAccessToken` токен доступа из данного процесса.|
|[CAccessToken:GetProfile](#getprofile)|Вызовите этот метод, чтобы получить ручку, указывающую на профиль пользователя, связанный с объектом. `CAccessToken`|
|[CAccessToken::GetSource](#getsource)|Вызовите этот метод, `CAccessToken` чтобы получить источник объекта.|
|[CAccessToken::GetStatistics](#getstatistics)|Вызовите этот метод, `CAccessToken` чтобы получить информацию, связанную с объектом.|
|[CAccessToken::GetTerminalServicesSessionid](#getterminalservicessessionid)|Вызовите этот метод, чтобы получить `CAccessToken` идентификатор сеанса терминалов, связанный с объектом.|
|[CAccessToken::GetThreadToken](#getthreadtoken)|Вызовите этот метод, чтобы инициализировать `CAccessToken` токен из данного потока.|
|[CAccessToken:GetTokenid](#gettokenid)|Вызовите этот метод, чтобы получить `CAccessToken` идентификатор маркеров, связанный с объектом.|
|[CAccessToken:GetType](#gettype)|Вызовите этот метод, чтобы `CAccessToken` получить тип маркера объекта.|
|[CAccessToken::GetUser](#getuser)|Вызовите этот метод, чтобы `CAccessToken` идентифицировать пользователя, связанного с объектом.|
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|Вызовите этот метод, чтобы получить ручку, указывающую на профиль пользователя, связанный с объектом. `CAccessToken`|
|[CAccessToken::Imperson](#impersonate)|Вызовите этот метод, чтобы `CAccessToken` назначить олицетворение потоку.|
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Вызовите этот метод, чтобы позволить потоку вызовов выдать себя за контекст безопасности зарегистрированного пользователя.|
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Вызовите этот метод `CAccessToken` для проверки, содержит ли объект список ограниченных СИДов.|
|[CAccessToken::LoadUserProfile](#loaduserprofile)|Вызовите этот метод для загрузки профиля пользователя, связанного с объектом. `CAccessToken`|
|[CAccessToken::LogonUser](#logonuser)|Вызовите этот метод, чтобы создать сеанс входа для пользователя, связанного с данными учетными данными.|
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Вызов этого метода из сервера COM обработки вызова `CAccessToken` от клиента, чтобы инициализировать с токеном доступа от клиента COM.|
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Вызов этого метода из сервера, принимая запросы по названной трубе, чтобы инициализировать `CAccessToken` токен доступа от клиента.|
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Вызов этого метода из сервера обработки вызова от `CAccessToken` клиента RPC для инициализации с токендоступа доступа от клиента.|
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Вызовите этот метод, чтобы установить уровень олицетворения, а затем инициализировать `CAccessToken` с токеном из данного потока.|
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Вызовите этот метод, чтобы определить, включен `CAccessToken` ли определенный набор привилегий в объекте.|
|[CAccessToken::Revert](#revert)|Вызовите этот метод, чтобы остановить поток, использующий маркер олицетворения.|
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Вызовите этот метод, чтобы установить DACL по умолчанию `CAccessToken` объекта.|
|[CAccessToken::Set](#setowner)|Вызовите этот метод, `CAccessToken` чтобы установить владельца объекта.|
|[CAccessToken:SetPrimaryGroup](#setprimarygroup)|Вызовите этот метод, чтобы `CAccessToken` установить основную группу объекта.|

## <a name="remarks"></a>Remarks

[Токен доступа](/windows/win32/SecAuthZ/access-tokens) — это объект, описывающий контекст безопасности процесса или потока и выделенный каждому пользователю, зарегистрированного на систему Windows.

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="caccesstokenattach"></a><a name="attach"></a>CAccessToken::Attach

Вызовите этот метод, чтобы взять на себя ответственность за данную ручку маркера доступа.

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>Параметры

*hToken*<br/>
Ручка к маркеру доступа.

### <a name="remarks"></a>Remarks

В отладке сборки возникает `CAccessToken` ошибка утверждения, если объект уже владеет маркером доступа.

## <a name="caccesstokencaccesstoken"></a><a name="dtor"></a>CAccessToken::

Деструктор

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы.

## <a name="caccesstokenchecktokenmembership"></a><a name="checktokenmembership"></a>CAccessToken::CheckTokenЧленство

Вызовите этот метод, чтобы определить, `CAccessToken` включен ли указанный SID в объекте.

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Ссылка на объект [класса CSid.](../../atl/reference/csid-class.md)

*pbIsMember*<br/>
Указатель на переменную, которая получает результаты проверки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Метод `CheckTokenMembership` проверки на наличие SID в пользовательском и групповом СИД токена доступа. Если SID присутствует и имеет SE_GROUP_ENABLED атрибут, *pbIsMember* установлен на TRUE; в противном случае, он установлен на FALSE.

В отладке сборки произойдет ошибка утверждения, если *pbIsMember* не является действительным указателем.

> [!NOTE]
> Объект `CAccessToken` должен быть токеном олицетворения, а не основным маркером.

## <a name="caccesstokencreateimpersonationtoken"></a><a name="createimpersonationtoken"></a>CAccessToken::CreateImpersonationToken

Вызовите этот метод, чтобы создать токен доступа олицетворения.

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>Параметры

*Сутенер*<br/>
Указатель на `CAccessToken` новый объект.

*Sil*<br/>
Обращаем SECURITY_IMPERSONATION_LEVEL [перечисленный](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) тип, который обеспечивает уровень олицетворения нового токена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

`CreateImpersonationToken`вызывает [DuplicateToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetoken) для создания нового токена олицетворения.

## <a name="caccesstokencreateprimarytoken"></a><a name="createprimarytoken"></a>CAccessToken::CreatePrimaryToken

Вызовите этот метод, чтобы создать новый основной маркер.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pPri*<br/>
Указатель на `CAccessToken` новый объект.

*dwDesiredAccess*<br/>
Упоняет запрашиваемые права доступа для нового токена. По умолчанию, MAXIMUM_ALLOWED запросы всех прав доступа, которые действительны для вызываемого абонента. Подробнее о правах доступа [и масках доступа](/windows/win32/SecAuthZ/access-rights-and-access-masks) читайте в подробностях.

*pTokenАстры*<br/>
Указатель на [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) структуру, которая определяет дескриптор безопасности для нового маркера и определяет, могут ли детские процессы унаследовать токен. Если *pTokenAttributes* является NULL, токен получает дескриптор безопасности по умолчанию, и ручка не может быть унаследована.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

`CreatePrimaryToken`вызывает [DuplicateTokenEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex) для создания нового основного токена.

## <a name="caccesstokencreateprocessasuser"></a><a name="createprocessasuser"></a>CAccessToken::CreateProcessAsUser

Вызовите этот метод для создания нового процесса, работаемого `CAccessToken` в контексте безопасности пользователя, представленного объектом.

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
Указатель на нулевую строку, которая определяет модуль для выполнения. Этот параметр не может быть NULL.

*pCommandLine*<br/>
Указатель на нулевую строку, определяющую строку команды для выполнения.

*pProcessInformation*<br/>
Указатель на [PROCESS_INFORMATION структуру,](/windows/win32/api/processthreadsapi/ns-processthreadsapi-process_information) которая получает идентификационную информацию о новом процессе.

*pStartupInfo*<br/>
Указатель на структуру [STARTUPINFO,](/windows/win32/api/processthreadsapi/ns-processthreadsapi-startupinfow) которая определяет, как должно отображаться основное окно для нового процесса.

*dwCreationFlags*<br/>
Определяет дополнительные флаги, контролирующие класс приоритетов и создание процесса. Список флагов можно осмотреть функцию Win32 [CreateProcessAsUser.](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw)

*bLoadProfile*<br/>
Если true, профиль пользователя загружается с [LoadUserProfile](/windows/win32/api/userenv/nf-userenv-loaduserprofilew).

*pПроцессАтрибуты*<br/>
Указатель на [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) структуру, которая определяет дескриптор безопасности для нового процесса и определяет, могут ли детские процессы унаследовать возвращенную ручку. Если *pProcessAttributes* является NULL, процесс получает дескриптор безопасности по умолчанию и ручка не может быть унаследована.

*pThreadAttributes*<br/>
Указатель на [структуру SECURITY_ATTRIBUTES,](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) которая определяет дескриптор безопасности для нового потока и определяет, могут ли детские процессы унаследовать возвращенную ручку. Если *pThreadAttributes* является NULL, поток получает дескриптор безопасности по умолчанию, а ручка не может быть унаследована.

*bНаследы*<br/>
Указывает, наследует ли новый процесс от процесса вызова. Если true, каждая наследуемая открытая ручка в процессе вызова наследуется новым процессом. Унаследованные ручки имеют такое же значение и привилегии доступа, как и исходные ручки.

*pCurrentDirectory*<br/>
Указатель на строку с нулевым завершением, которая определяет текущий диск и каталог для нового процесса. Строка должна быть полным путем, который включает в себя диск овечку. Если этот параметр NULL, новый процесс будет иметь тот же текущий диск и каталог, что и процесс вызова.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

`CreateProcessAsUser`использует `CreateProcessAsUser` функцию Win32 для создания нового процесса, который выполняется в `CAccessToken` контексте безопасности пользователя, представленного объектом. Ознакомьтесь с описанием функции [CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) для полного обсуждения необходимых параметров.

Для успешного достижения `CAccessToken` этого метода объект должен иметь привилегии AssignPrimaryToken (за исключением тех случаев, когда это не является ограниченным токеном) и привилегий увеличения квоты.

## <a name="caccesstokencreaterestrictedtoken"></a><a name="createrestrictedtoken"></a>CAccessToken::CreateRestrictedToken

Вызовите этот метод, `CAccessToken` чтобы создать новый, ограниченный объект.

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>Параметры

*prestrictedToken*<br/>
Новый, `CAccessToken` ограниченный объект.

*SidsToDisable*<br/>
Объект, `CTokenGroups` который определяет отказ только SIDs.

*SidsToОграничено*<br/>
Объект, `CTokenGroups` опознавающий ограничивающие SID.

*ПривилегииУдалить*<br/>
Объект, `CTokenPrivileges` опознававший привилегии для удаления в ограниченном маркере. По умолчанию создается пустой объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

`CreateRestrictedToken`использует функцию [CreateRestrictedToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) Win32 `CAccessToken` для создания нового объекта с ограничениями.

> [!IMPORTANT]
> При `CreateRestrictedToken`использовании, убедитесь следующее: существующий маркер действителен (и не введен пользователем) и *SidsToDisable* и *PrivilegesToDelete* являются действительными (и не введены пользователем). Если метод возвращает FALSE, ототрицайте функциональность.

## <a name="caccesstokendetach"></a><a name="detach"></a>CAccessToken: :Detach

Вызовите этот метод, чтобы отозвать право собственности на токен доступа.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку, `CAccessToken` которая была отсоединена.

### <a name="remarks"></a>Remarks

Этот метод отменяет право собственности на `CAccessToken`токен доступа.

## <a name="caccesstokendisableprivilege"></a><a name="disableprivilege"></a>CAccessToken: :DisablePrivilege

Вызовите этот метод, чтобы `CAccessToken` отключить привилегию в объекте.

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*pszPrivilege*<br/>
Указатель на строку, содержащую привилегию для отстранить `CAccessToken` объект.

*pPreviousState*<br/>
Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние привилегий.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokendisableprivileges"></a><a name="disableprivileges"></a>CAccessToken: :DуправляемыеПривилегии

Вызовите этот метод, чтобы отключить одну `CAccessToken` или несколько привилегий в объекте.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*rПривилегии*<br/>
Указатель на массив строк, содержащих привилегии для отправления в объекте. `CAccessToken`

*pPreviousState*<br/>
Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние привилегий.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokenenableprivilege"></a><a name="enableprivilege"></a>CAccessToken:EnablePrivilege

Вызовите этот метод, `CAccessToken` чтобы включить привилегию в объекте.

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*pszPrivilege*<br/>
Указатель на строку, содержащую `CAccessToken` привилегию включения объекта.

*pPreviousState*<br/>
Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние привилегий.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokenenableprivileges"></a><a name="enableprivileges"></a>CAccessToken:EnablePrivileges

Вызовите этот метод, чтобы включить `CAccessToken` одну или несколько привилегий в объекте.

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*rПривилегии*<br/>
Указатель на массив строк, содержащих привилегии для `CAccessToken` включения объекта.

*pPreviousState*<br/>
Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние привилегий.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengetdefaultdacl"></a><a name="getdefaultdacl"></a>CAccessToken::GetDefaultDacl

Вызовите этот `CAccessToken` метод, чтобы вернуть DACL объекта по умолчанию.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>Параметры

*pDacl*<br/>
Указатель на объект [класса CDacl,](../../atl/reference/cdacl-class.md) который получит DACL `CAccessToken` объекта по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если DACL по умолчанию был восстановлен, FALSE в противном случае.

## <a name="caccesstokengeteffectivetoken"></a><a name="geteffectivetoken"></a>CAccessToken:GetEffectiveToken

Вызовите этот `CAccessToken` метод, чтобы получить объект, равный токену доступа, фактическидлянию для текущего потока.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Упогоняет маску доступа, которая определяет запрашиваемые типы доступа к токену доступа. Эти запрашиваемые типы доступа сравниваются с dACL токена, чтобы определить, какие доступы предоставляются или отказано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengetgroups"></a><a name="getgroups"></a>CAccessToken:GetGroups

Вызовите этот `CAccessToken` метод, чтобы вернуть группы маркеров объекта.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>Параметры

*pGroups*<br/>
Указатель на объект [класса CTokenGroups,](../../atl/reference/ctokengroups-class.md) который будет получать информацию о группе.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengethandle"></a><a name="gethandle"></a>CAccessToken::GetHandle

Вызовите этот метод, чтобы получить ручку к маркеру доступа.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку `CAccessToken` в маркер доступа объекта.

## <a name="caccesstokengetimpersonationlevel"></a><a name="getimpersonationlevel"></a>CAccessToken::GetImpersonationLevel

Вызовите этот метод, чтобы получить уровень олицетворения из токена доступа.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>Параметры

*pImpersonationLevel*<br/>
Указатель на [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) тип перечисления, который будет получать информацию об уровне олицетворения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengetlogonsessionid"></a><a name="getlogonsessionid"></a>CAccessToken::GetLogonSessionId

Вызовите этот метод, чтобы получить `CAccessToken` идентификатор сеанса Logon, связанный с объектом.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Параметры

*плуид*<br/>
Указатель на [LUID,](/windows/win32/api/winnt/ns-winnt-luid) который получит идентификатор сессии logon.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

В отладочных сборках возникает ошибка утверждения, если *pluid* является недействительным значением.

## <a name="caccesstokengetlogonsid"></a><a name="getlogonsid"></a>CAccessToken::GetLogonSid

Вызовите этот метод, чтобы получить `CAccessToken` Logon SID, связанный с объектом.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*Psid*<br/>
Указатель на объект [класса CSid.](../../atl/reference/csid-class.md)

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

В отладке сборки возникает ошибка утверждения, если *pSid* является недействительным значением.

## <a name="caccesstokengetowner"></a><a name="getowner"></a>CAccessToken::GetOwner

Вызовите этот метод, чтобы `CAccessToken` получить владельца, связанного с объектом.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*Psid*<br/>
Указатель на объект [класса CSid.](../../atl/reference/csid-class.md)

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Владелец устанавливается по умолчанию на любые объекты, созданные в то время как этот маркер доступа в силе.

## <a name="caccesstokengetprimarygroup"></a><a name="getprimarygroup"></a>CAccessToken:GetPrimaryGroup

Вызовите этот метод, чтобы `CAccessToken` получить основную группу, связанную с объектом.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*Psid*<br/>
Указатель на объект [класса CSid.](../../atl/reference/csid-class.md)

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Группа устанавливается по умолчанию на любые объекты, созданные в то время как этот маркер доступа в силе.

## <a name="caccesstokengetprivileges"></a><a name="getprivileges"></a>CAccessToken::GetPrivileges

Вызовите этот метод, чтобы `CAccessToken` получить привилегии, связанные с объектом.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>Параметры

*pPrivileges*<br/>
Указатель на объект [класса CTokenPrivileges,](../../atl/reference/ctokenprivileges-class.md) который получит привилегии.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengetprocesstoken"></a><a name="getprocesstoken"></a>CAccessToken:GetProcessToken

Вызовите этот метод, чтобы инициализировать `CAccessToken` токен доступа из данного процесса.

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Упогоняет маску доступа, которая определяет запрашиваемые типы доступа к токену доступа. Эти запрашиваемые типы доступа сравниваются с dACL токена, чтобы определить, какие доступы предоставляются или отказано.

*hПроцесс*<br/>
Ручка к процессу, токен доступа которого открыт. При использовании значения NULL по умолчанию используется текущий процесс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Вызывает функцию [OpenProcessToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-openprocesstoken) Win32.

## <a name="caccesstokengetprofile"></a><a name="getprofile"></a>CAccessToken:GetProfile

Вызовите этот метод, чтобы получить ручку, указывающую на профиль пользователя, связанный с объектом. `CAccessToken`

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку, указывающую на профиль пользователя, или NULL, если не существует профиля.

## <a name="caccesstokengetsource"></a><a name="getsource"></a>CAccessToken::GetSource

Вызовите этот метод, `CAccessToken` чтобы получить источник объекта.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>Параметры

*pИсточник*<br/>
Указатель на [TOKEN_SOURCE](/windows/win32/api/winnt/ns-winnt-token_source) структуру.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengetstatistics"></a><a name="getstatistics"></a>CAccessToken::GetStatistics

Вызовите этот метод, `CAccessToken` чтобы получить информацию, связанную с объектом.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>Параметры

*pСтатистика*<br/>
Указатель на [TOKEN_STATISTICS](/windows/win32/api/winnt/ns-winnt-token_statistics) структуру.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengetterminalservicessessionid"></a><a name="getterminalservicessessionid"></a>CAccessToken::GetTerminalServicesSessionid

Вызовите этот метод, чтобы получить `CAccessToken` идентификатор сеанса терминалов, связанный с объектом.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>Параметры

*pdwSessionId*<br/>
Идентификатор сеанса обслуживания терминала.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengetthreadtoken"></a><a name="getthreadtoken"></a>CAccessToken::GetThreadToken

Вызовите этот метод, чтобы инициализировать `CAccessToken` токен из данного потока.

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Упогоняет маску доступа, которая определяет запрашиваемые типы доступа к токену доступа. Эти запрашиваемые типы доступа сравниваются с dACL токена, чтобы определить, какие доступы предоставляются или отказано.

*hThread*<br/>
Ручка к потоку, токен доступа которого открыт.

*bOpenAsSelf*<br/>
Указывает, должна ли проверка доступа быть выполнена в `GetThreadToken` контексте безопасности потока вызова метода или в контексте безопасности процесса вызова потока.

Если этот параметр FALSE, проверка доступа выполняется с использованием контекста безопасности для потока вызова. Если поток выдает себя за клиента, этот контекст безопасности может быть контекстом процесса клиента. Если этот параметр является истинным, проверка доступа производится с использованием контекста безопасности процесса для потока вызова.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengettokenid"></a><a name="gettokenid"></a>CAccessToken:GetTokenid

Вызовите этот метод, чтобы получить `CAccessToken` идентификатор маркеров, связанный с объектом.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Параметры

*плуид*<br/>
Указатель на [LUID,](/windows/win32/api/winnt/ns-winnt-luid) который получит идентификатор токена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokengettype"></a><a name="gettype"></a>CAccessToken:GetType

Вызовите этот метод, чтобы `CAccessToken` получить тип маркера объекта.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>Параметры

*pType*<br/>
Адрес [TOKEN_TYPE](/windows/win32/api/winnt/ne-winnt-token_type) переменной, которая, по успеху, получает тип токена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Тип TOKEN_TYPE перечисления содержит значения, которые различают основной маркер и токен олицетворения.

## <a name="caccesstokengetuser"></a><a name="getuser"></a>CAccessToken::GetUser

Вызовите этот метод, чтобы `CAccessToken` идентифицировать пользователя, связанного с объектом.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*Psid*<br/>
Указатель на объект [класса CSid.](../../atl/reference/csid-class.md)

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="caccesstokenhkeycurrentuser"></a><a name="hkeycurrentuser"></a>CAccessToken::HKeyCurrentUser

Вызовите этот метод, чтобы получить ручку, указывающую на профиль пользователя, связанный с объектом. `CAccessToken`

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку, указывающую на профиль пользователя, или NULL, если не существует профиля.

## <a name="caccesstokenimpersonate"></a><a name="impersonate"></a>CAccessToken::Imperson

Вызовите этот метод, чтобы `CAccessToken` назначить олицетворение потоку.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*hThread*<br/>
Ручка к потоку, чтобы назначить маркер олицетворения. Эта ручка должна быть открыта с TOKEN_IMPERSONATE правами доступа. Если *hThread* является NULL, метод заставляет поток прекратить использование маркера олицетворения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

В отладке сборки возникает `CAccessToken` ошибка утверждения, если не будет действительного указателя на маркер.

[Класс CAutoRevertImpersonможет](../../atl/reference/cautorevertimpersonation-class.md) быть использован для автоматического возврата олицетворения токенов доступа.

## <a name="caccesstokenimpersonateloggedonuser"></a><a name="impersonateloggedonuser"></a>CAccessToken::ImpersonateLoggedOnUser

Вызовите этот метод, чтобы позволить потоку вызовов выдать себя за контекст безопасности зарегистрированного пользователя.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

> [!IMPORTANT]
> Если вызов функции олицетворения по какой-либо причине не выполняется, клиент не выдает себя за клиента, а запрос клиента выполняется в контексте безопасности процесса, из которого был сделан вызов. Если процесс выполняется как привилегированная учетная запись или как член административной группы, пользователь может выполнять действия, которые он или она в противном случае были бы запрещены. Таким образом, значение возврата для этой функции всегда должно быть подтверждено.

## <a name="caccesstokenistokenrestricted"></a><a name="istokenrestricted"></a>CAccessToken::IsTokenRestricted

Вызовите этот метод `CAccessToken` для проверки, содержит ли объект список ограниченных СИДов.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если объект содержит список ограничивающих SID, FALSE, если нет ограничения SID или если метод не удается.

## <a name="caccesstokenloaduserprofile"></a><a name="loaduserprofile"></a>CAccessToken::LoadUserProfile

Вызовите этот метод для загрузки профиля пользователя, связанного с объектом. `CAccessToken`

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

В отладке сборки возникает `CAccessToken` ошибка утверждения, если ошибка не содержит допустимого маркера или если профиль пользователя уже существует.

## <a name="caccesstokenlogonuser"></a><a name="logonuser"></a>CAccessToken::LogonUser

Вызовите этот метод, чтобы создать сеанс входа для пользователя, связанного с данными учетными данными.

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
Указатель на строку с нулевым завершением, определяющую имя пользователя. Это имя учетной записи пользователя для входа в систему.

*pszDomain*<br/>
Указатель на строку с нулевым завершением, которая определяет имя домена или сервера, база данных учетной записи которого содержит учетную запись *pszUserName.*

*pszPassword*<br/>
Указатель на строку с нулевым завершением, которая определяет четкий текстовый пароль для учетной записи пользователя, указанной *pszUserName.*

*dwLogonType*<br/>
Определяет тип операции logon для выполнения. Подробнее о ней читайте в [материале LogonUser.](/windows/win32/api/winbase/nf-winbase-logonuserw)

*dwLogonProvider*<br/>
Определяет поставщика логонов. Подробнее о ней читайте в [материале LogonUser.](/windows/win32/api/winbase/nf-winbase-logonuserw)

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Токен доступа, полученный от логона, `CAccessToken`будет связан с . Для успешного достижения `CAccessToken` этого метода объект должен хранить SE_TCB_NAME привилегий, идентифицируя владельца как часть доверенной компьютерной базы. Дополнительную информацию о требуемых привилегиях можно узнать в [журнале LogonUser.](/windows/win32/api/winbase/nf-winbase-logonuserw)

## <a name="caccesstokenopencomclienttoken"></a><a name="opencomclienttoken"></a>CAccessToken::OpenCOMClientToken

Вызов этого метода из сервера COM обработки вызова `CAccessToken` от клиента, чтобы инициализировать с токеном доступа от клиента COM.

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Упогоняет маску доступа, которая определяет запрашиваемые типы доступа к токену доступа. Эти запрашиваемые типы доступа сравниваются с dACL токена, чтобы определить, какие доступы предоставляются или отказано.

*bImpersonate*<br/>
Если истина, текущий поток будет выдавать себя за вызова COM клиента, если этот вызов завершаетуспешно. Если FALSE, токен доступа будет открыт, но поток не будет иметь токен олицетворения, когда этот вызов завершается.

*bOpenAsSelf*<br/>
Указывает, должна ли проверка доступа быть выполнена в контексте безопасности потока вызова метода [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) или в контексте безопасности процесса вызова потока.

Если этот параметр FALSE, проверка доступа выполняется с использованием контекста безопасности для потока вызова. Если поток выдает себя за клиента, этот контекст безопасности может быть контекстом процесса клиента. Если этот параметр является истинным, проверка доступа производится с использованием контекста безопасности процесса для потока вызова.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

[Класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) может быть использован для автоматического возврата олицетворения токенов доступа, созданных путем установки флага *bImpersonate* в TRUE.

## <a name="caccesstokenopennamedpipeclienttoken"></a><a name="opennamedpipeclienttoken"></a>CAccessToken::OpenNamedPipeClientToken

Вызов этого метода из сервера, принимая запросы по названной трубе, чтобы инициализировать `CAccessToken` токен доступа от клиента.

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Параметры

*hPipe*<br/>
Ручка к названной трубе.

*dwDesiredAccess*<br/>
Упогоняет маску доступа, которая определяет запрашиваемые типы доступа к токену доступа. Эти запрашиваемые типы доступа сравниваются с dACL токена, чтобы определить, какие доступы предоставляются или отказано.

*bImpersonate*<br/>
Если истина, текущий поток будет выдавать себя за клиента трубы вызова, если этот вызов завершаетуспешно. Если FALSE, токен доступа будет открыт, но поток не будет иметь токен олицетворения, когда этот вызов завершается.

*bOpenAsSelf*<br/>
Указывает, должна ли проверка доступа быть выполнена в контексте безопасности потока вызова метода [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) или в контексте безопасности процесса вызова потока.

Если этот параметр FALSE, проверка доступа выполняется с использованием контекста безопасности для потока вызова. Если поток выдает себя за клиента, этот контекст безопасности может быть контекстом процесса клиента. Если этот параметр является истинным, проверка доступа производится с использованием контекста безопасности процесса для потока вызова.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

[Класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) может быть использован для автоматического возврата олицетворения токенов доступа, созданных путем установки флага *bImpersonate* в TRUE.

## <a name="caccesstokenopenrpcclienttoken"></a><a name="openrpcclienttoken"></a>CAccessToken::OpenRPCClientToken

Вызов этого метода из сервера обработки вызова от `CAccessToken` клиента RPC для инициализации с токендоступа доступа от клиента.

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Параметры

*Связывание*<br/>
Связывание ручки на сервере, представляющее собой привязку к клиенту.

*dwDesiredAccess*<br/>
Упогоняет маску доступа, которая определяет запрашиваемые типы доступа к токену доступа. Эти запрашиваемые типы доступа сравниваются с dACL токена, чтобы определить, какие доступы предоставляются или отказано.

*bImpersonate*<br/>
Если истина, текущий поток будет выдавать себя за вызова клиента RPC, если этот вызов завершаетуспешно. Если FALSE, токен доступа будет открыт, но поток не будет иметь токен олицетворения, когда этот вызов завершается.

*bOpenAsSelf*<br/>
Указывает, должна ли проверка доступа быть выполнена в контексте безопасности потока вызова метода [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) или в контексте безопасности процесса вызова потока.

Если этот параметр FALSE, проверка доступа выполняется с использованием контекста безопасности для потока вызова. Если поток выдает себя за клиента, этот контекст безопасности может быть контекстом процесса клиента. Если этот параметр является истинным, проверка доступа производится с использованием контекста безопасности процесса для потока вызова.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

[Класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) может быть использован для автоматического возврата олицетворения токенов доступа, созданных путем установки флага *bImpersonate* в TRUE.

## <a name="caccesstokenopenthreadtoken"></a><a name="openthreadtoken"></a>CAccessToken::OpenThreadToken

Вызовите этот метод, чтобы установить уровень олицетворения, а затем инициализировать `CAccessToken` с токеном из данного потока.

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>Параметры

*dwDesiredAccess*<br/>
Упогоняет маску доступа, которая определяет запрашиваемые типы доступа к токену доступа. Эти запрашиваемые типы доступа сравниваются с dACL токена, чтобы определить, какие доступы предоставляются или отказано.

*bImpersonate*<br/>
Если истина, поток будет оставлен на уровне запрашиваемого олицетворения после завершения этого метода. Если FALSE, поток вернется к исходному уровню олицетворения.

*bOpenAsSelf*<br/>
Указывает, должна ли проверка доступа быть выполнена в контексте безопасности потока вызова метода [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) или в контексте безопасности процесса вызова потока.

Если этот параметр FALSE, проверка доступа выполняется с использованием контекста безопасности для потока вызова. Если поток выдает себя за клиента, этот контекст безопасности может быть контекстом процесса клиента. Если этот параметр является истинным, проверка доступа производится с использованием контекста безопасности процесса для потока вызова.

*Sil*<br/>
Обращаем SECURITY_IMPERSONATION_LEVEL [перечисленный](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) тип, который обеспечивает уровень олицетворения токена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

`OpenThreadToken`похож на [CAccessToken::GetThreadToken](#getthreadtoken), но устанавливает уровень олицетворения до инициализации `CAccessToken` из токена доступа потока.

[Класс CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) может быть использован для автоматического возврата олицетворения токенов доступа, созданных путем установки флага *bImpersonate* в TRUE.

## <a name="caccesstokenprivilegecheck"></a><a name="privilegecheck"></a>CAccessToken::PrivilegeCheck

Вызовите этот метод, чтобы определить, включен `CAccessToken` ли определенный набор привилегий в объекте.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>Параметры

*ТребуемыеПривилегии*<br/>
Указатель на [PRIVILEGE_SET](/windows/win32/api/winnt/ns-winnt-privilege_set) структуру.

*pbResult*<br/>
Указатель на значение, установленное методом, чтобы указать, `CAccessToken` включена ли в объекте какая-либо или вся указанная привилегия.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

При `PrivilegeCheck` возврате `Attributes` член каждой структуры [LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes) настроен SE_PRIVILEGE_USED_FOR_ACCESS, если включена соответствующая привилегия. Этот метод вызывает функцию [PrivilegeCheck](/windows/win32/api/securitybaseapi/nf-securitybaseapi-privilegecheck) Win32.

## <a name="caccesstokenrevert"></a><a name="revert"></a>CAccessToken::Revert

Вызовите этот метод, чтобы остановить поток от использования маркера олицетворения.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>Параметры

*hThread*<br/>
Ручка к потоку, чтобы вернуться из олицетворения. Если *hThread* является NULL, предполагается текущий поток.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Реверсия токенов олицетворения может быть выполнена автоматически с [помощью класса CAutoRevertImperson.](../../atl/reference/cautorevertimpersonation-class.md)

## <a name="caccesstokensetdefaultdacl"></a><a name="setdefaultdacl"></a>CAccessToken::SetDefaultDacl

Вызовите этот метод, чтобы установить DACL по умолчанию `CAccessToken` объекта.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>Параметры

*rDacl*<br/>
Новая информация [cDacl Class](../../atl/reference/cdacl-class.md) по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

DACL по умолчанию — это DACL, который используется по умолчанию при создании новых объектов с помощью этого токена доступа.

## <a name="caccesstokensetowner"></a><a name="setowner"></a>CAccessToken::Set

Вызовите этот метод, `CAccessToken` чтобы установить владельца объекта.

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Объект [класса CSid,](../../atl/reference/csid-class.md) содержащий информацию о владельце.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Владелец — это владелец по умолчанию, который используется для новых объектов, созданных в то время как этот маркер доступа действует.

## <a name="caccesstokensetprimarygroup"></a><a name="setprimarygroup"></a>CAccessToken:SetPrimaryGroup

Вызовите этот метод, чтобы `CAccessToken` установить основную группу объекта.

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Объект [класса CSid,](../../atl/reference/csid-class.md) содержащий основную групповую информацию.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Основная группа — это группа по умолчанию для новых объектов, созданных во время действия этого токена доступа.

## <a name="see-also"></a>См. также раздел

[Образец ATLSecurity](../../overview/visual-cpp-samples.md)<br/>
[Токены доступа](/windows/win32/SecAuthZ/access-tokens)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
