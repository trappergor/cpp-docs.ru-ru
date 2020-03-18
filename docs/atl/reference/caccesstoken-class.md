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
ms.openlocfilehash: 33fbaae5dafaccdf7f7e6880eaa42dd68352e840
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423522"
---
# <a name="caccesstoken-class"></a>Класс CAccessToken

Этот класс является оболочкой для маркера доступа.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAccessToken
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CAccessToken:: ~ CAccessToken](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CAccessToken:: Attach](#attach)|Вызовите этот метод, чтобы стать владельцем заданного маркера маркера доступа.|
|[CAccessToken:: Чекктокенмембершип](#checktokenmembership)|Вызовите этот метод, чтобы определить, включен ли указанный идентификатор безопасности в объекте `CAccessToken`.|
|[CAccessToken:: Креатеимперсонатионтокен](#createimpersonationtoken)|Вызовите этот метод, чтобы создать новый маркер доступа олицетворения.|
|[CAccessToken:: Креатепримаритокен](#createprimarytoken)|Вызовите этот метод, чтобы создать новый первичный токен.|
|[CAccessToken:: параметр CreateProcessAsUser](#createprocessasuser)|Вызовите этот метод, чтобы создать новый процесс, выполняемый в контексте безопасности пользователя, представленного объектом `CAccessToken`.|
|[CAccessToken:: CreateRestrictedToken](#createrestrictedtoken)|Вызовите этот метод, чтобы создать новый, ограниченный `CAccessToken` объект.|
|[CAccessToken::D етач](#detach)|Вызовите этот метод, чтобы отменить владение маркером доступа.|
|[CAccessToken::D Исаблепривилеже](#disableprivilege)|Вызовите этот метод, чтобы отключить привилегию в объекте `CAccessToken`.|
|[CAccessToken::D Исаблепривилежес](#disableprivileges)|Вызовите этот метод, чтобы отключить один или несколько привилегий в объекте `CAccessToken`.|
|[CAccessToken:: Енаблепривилеже](#enableprivilege)|Вызовите этот метод, чтобы включить привилегию в объекте `CAccessToken`.|
|[CAccessToken:: Енаблепривилежес](#enableprivileges)|Вызовите этот метод, чтобы включить один или несколько привилегий в объекте `CAccessToken`.|
|[CAccessToken:: Жетдефаултдакл](#getdefaultdacl)|Вызовите этот метод, чтобы вернуть список DACL по умолчанию для объекта `CAccessToken`.|
|[CAccessToken:: Жетеффективетокен](#geteffectivetoken)|Вызовите этот метод, чтобы получить объект `CAccessToken`, равный маркеру доступа, который действует для текущего потока.|
|[CAccessToken:: группы](#getgroups)|Вызовите этот метод, чтобы получить группы токенов объекта `CAccessToken`.|
|[CAccessToken:: getHandler](#gethandle)|Вызовите этот метод, чтобы получить маркер маркера доступа.|
|[CAccessToken:: Жетимперсонатионлевел](#getimpersonationlevel)|Вызовите этот метод, чтобы получить уровень олицетворения из маркера доступа.|
|[CAccessToken:: Жетлогонсессионид](#getlogonsessionid)|Вызовите этот метод, чтобы получить идентификатор сеанса входа, связанный с объектом `CAccessToken`.|
|[CAccessToken:: Жетлогонсид](#getlogonsid)|Вызовите этот метод, чтобы получить идентификатор безопасности входа, связанный с объектом `CAccessToken`.|
|[CAccessToken:: owner](#getowner)|Вызовите этот метод, чтобы получить владельца, связанного с объектом `CAccessToken`.|
|[CAccessToken:: Жетпримариграуп](#getprimarygroup)|Вызовите этот метод, чтобы получить основную группу, связанную с объектом `CAccessToken`.|
|[CAccessToken:: Privileges](#getprivileges)|Вызовите этот метод, чтобы получить привилегии, связанные с объектом `CAccessToken`.|
|[CAccessToken:: Жетпроцесстокен](#getprocesstoken)|Вызовите этот метод, чтобы инициализировать `CAccessToken` с маркером доступа из данного процесса.|
|[CAccessToken::/Profile](#getprofile)|Вызовите этот метод, чтобы получить маркер, указывающий на профиль пользователя, связанный с объектом `CAccessToken`.|
|[CAccessToken:: \ Source](#getsource)|Вызовите этот метод, чтобы получить источник объекта `CAccessToken`.|
|[CAccessToken:: Statistics](#getstatistics)|Вызовите этот метод, чтобы получить сведения, связанные с объектом `CAccessToken`.|
|[CAccessToken:: Жеттерминалсервицессессионид](#getterminalservicessessionid)|Вызовите этот метод, чтобы получить идентификатор сеанса служб терминалов, связанный с объектом `CAccessToken`.|
|[CAccessToken:: Жетсреадтокен](#getthreadtoken)|Вызовите этот метод, чтобы инициализировать `CAccessToken` с маркером из данного потока.|
|[CAccessToken:: Жеттокенид](#gettokenid)|Вызовите этот метод, чтобы получить идентификатор маркера, связанный с объектом `CAccessToken`.|
|[CAccessToken:: GetType](#gettype)|Вызовите этот метод, чтобы получить тип токена объекта `CAccessToken`.|
|[CAccessToken:: пользователь](#getuser)|Вызовите этот метод, чтобы обозначить пользователя, связанного с объектом `CAccessToken`.|
|[CAccessToken:: Хкэйкуррентусер](#hkeycurrentuser)|Вызовите этот метод, чтобы получить маркер, указывающий на профиль пользователя, связанный с объектом `CAccessToken`.|
|[CAccessToken:: IMPERSONATE](#impersonate)|Вызовите этот метод, чтобы назначить потоку `CAccessToken` олицетворения.|
|[CAccessToken:: Имперсонателогжедонусер](#impersonateloggedonuser)|Вызовите этот метод, чтобы вызывающий поток олицетворять контекст безопасности вошедшего в систему пользователя.|
|[CAccessToken:: Истокенрестриктед](#istokenrestricted)|Вызовите этот метод, чтобы проверить, содержит ли объект `CAccessToken` список ограниченных идентификаторов безопасности.|
|[CAccessToken:: LoadUserProfile](#loaduserprofile)|Вызовите этот метод, чтобы загрузить профиль пользователя, связанный с объектом `CAccessToken`.|
|[CAccessToken:: LogonUser](#logonuser)|Вызовите этот метод, чтобы создать сеанс входа для пользователя, связанного с заданными учетными данными.|
|[CAccessToken:: Опенкомклиенттокен](#opencomclienttoken)|Вызовите этот метод из COM-сервера, обрабатывающего вызов от клиента, чтобы инициализировать `CAccessToken` с маркером доступа из клиента COM.|
|[CAccessToken:: Опеннамедпипеклиенттокен](#opennamedpipeclienttoken)|Вызовите этот метод из сервера, принимающего запросы через именованный канал, чтобы инициализировать `CAccessToken` с маркером доступа от клиента.|
|[CAccessToken:: Опенрпкклиенттокен](#openrpcclienttoken)|Вызовите этот метод из сервера, обрабатывающего вызов от клиента RPC, чтобы инициализировать `CAccessToken` с маркером доступа от клиента.|
|[CAccessToken:: Опенсреадтокен](#openthreadtoken)|Вызовите этот метод, чтобы задать уровень олицетворения, а затем инициализировать `CAccessToken` с маркером из данного потока.|
|[CAccessToken::P Ривилежечекк](#privilegecheck)|Вызовите этот метод, чтобы определить, включен ли указанный набор привилегий в объект `CAccessToken`.|
|[CAccessToken:: revert](#revert)|Вызовите этот метод, чтобы прерывать поток, использующий токен олицетворения.|
|[CAccessToken:: Сетдефаултдакл](#setdefaultdacl)|Вызовите этот метод, чтобы задать список DACL по умолчанию для объекта `CAccessToken`.|
|[CAccessToken:: Сетовнер](#setowner)|Вызовите этот метод, чтобы задать владельца объекта `CAccessToken`.|
|[CAccessToken:: Сетпримариграуп](#setprimarygroup)|Вызовите этот метод, чтобы задать основную группу объекта `CAccessToken`.|

## <a name="remarks"></a>Remarks

[Маркер доступа](/windows/win32/SecAuthZ/access-tokens) — это объект, который описывает контекст безопасности процесса или потока и выделяется каждому пользователю, вошедшему в систему Windows.

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/win32/SecAuthZ/access-control) в Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити. h

##  <a name="attach"></a>CAccessToken:: Attach

Вызовите этот метод, чтобы стать владельцем заданного маркера маркера доступа.

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>Параметры

*хтокен*<br/>
Маркер маркера доступа.

### <a name="remarks"></a>Remarks

В отладочных сборках возникнет ошибка утверждения, если объект `CAccessToken` уже владеет маркером доступа.

##  <a name="dtor"></a>CAccessToken:: ~ CAccessToken

Деструктор

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы.

##  <a name="checktokenmembership"></a>CAccessToken:: Чекктокенмембершип

Вызовите этот метод, чтобы определить, включен ли указанный идентификатор безопасности в объекте `CAccessToken`.

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>Параметры

*рсид*<br/>
Ссылка на объект [класса CSid](../../atl/reference/csid-class.md) .

*пбисмембер*<br/>
Указатель на переменную, которая получает результаты проверки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Метод `CheckTokenMembership` проверяет наличие идентификатора безопасности в идентификаторах безопасности пользователя и группы маркера доступа. Если идентификатор безопасности существует и имеет атрибут SE_GROUP_ENABLED, *пбисмембер* имеет значение true. в противном случае для него задается значение FALSE.

В отладочных сборках возникнет ошибка утверждения, если *пбисмембер* не является допустимым указателем.

> [!NOTE]
>  Объект `CAccessToken` должен быть маркером олицетворения, а не основным токеном.

##  <a name="createimpersonationtoken"></a>CAccessToken:: Креатеимперсонатионтокен

Вызовите этот метод, чтобы создать маркер доступа для олицетворения.

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>Параметры

*Раскрасьте*<br/>
Указатель на новый объект `CAccessToken`.

*SIL*<br/>
Задает [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) перечислимый тип, который предоставляет уровень олицетворения нового маркера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

`CreateImpersonationToken` вызывает [сбой duplicatetoken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetoken) для создания нового маркера олицетворения.

##  <a name="createprimarytoken"></a>CAccessToken:: Креатепримаритокен

Вызовите этот метод, чтобы создать новый первичный токен.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*ппри*<br/>
Указатель на новый объект `CAccessToken`.

*двдесиредакцесс*<br/>
Указывает запрошенные права доступа для нового маркера. По умолчанию MAXIMUM_ALLOWED запрашивает все права доступа, допустимые для вызывающей стороны. Дополнительные сведения о правах доступа см. в разделе [права доступа и маски доступа](/windows/win32/SecAuthZ/access-rights-and-access-masks) .

*птокенаттрибутес*<br/>
Указатель на структуру [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) , указывающую дескриптор безопасности для нового маркера, и определяет, могут ли дочерние процессы наследовать маркер. Если *птокенаттрибутес* имеет значение null, маркер получает дескриптор безопасности по умолчанию и дескриптор не может быть унаследован.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

`CreatePrimaryToken` вызывает [дупликатетокенекс](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex) для создания нового первичного маркера.

##  <a name="createprocessasuser"></a>CAccessToken:: параметр CreateProcessAsUser

Вызовите этот метод, чтобы создать новый процесс, выполняемый в контексте безопасности пользователя, представленного объектом `CAccessToken`.

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

*паппликатионнаме*<br/>
Указатель на строку, завершающуюся нулем, которая указывает модуль для выполнения. Этот параметр не может иметь значение NULL.

*пкоммандлине*<br/>
Указатель на строку, завершающуюся нулем, которая указывает командную строку для выполнения.

*ппроцессинформатион*<br/>
Указатель на [структуру PROCESS_INFORMATION](/windows/win32/api/processthreadsapi/ns-processthreadsapi-process_information) , которая получает идентификационные сведения о новом процессе.

*пстартупинфо*<br/>
Указатель на структуру [стартупинфо](/windows/win32/api/processthreadsapi/ns-processthreadsapi-startupinfow) , которая указывает, как должно отобразиться главное окно для нового процесса.

*двкреатионфлагс*<br/>
Задает дополнительные флаги, управляющие классом приоритета и процессом создания процесса. Список флагов см. в описании функции Win32 [параметр CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) .

*блоадпрофиле*<br/>
Если значение — TRUE, профиль пользователя загружается с помощью [LoadUserProfile](/windows/win32/api/userenv/nf-userenv-loaduserprofilew).

*ппроцессаттрибутес*<br/>
Указатель на структуру [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) , указывающую дескриптор безопасности для нового процесса, и определяет, могут ли дочерние процессы наследовать возвращенный дескриптор. Если *ппроцессаттрибутес* имеет значение null, процесс получает дескриптор безопасности по умолчанию, и дескриптор не может быть унаследован.

*псреадаттрибутес*<br/>
Указатель на структуру [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) , указывающую дескриптор безопасности для нового потока, и определяет, могут ли дочерние процессы наследовать возвращенный дескриптор. Если *псреадаттрибутес* имеет значение null, то поток получает дескриптор безопасности по умолчанию, и дескриптор не может быть унаследован.

*бинхерит*<br/>
Указывает, наследует ли новый процесс дескрипторы из вызывающего процесса. Если значение — TRUE, каждый наследуемый открытый маркер в вызывающем процессе наследуется новым процессом. Унаследованные дескрипторы имеют те же значения и привилегии доступа, что и исходные дескрипторы.

*пкуррентдиректори*<br/>
Указатель на строку, завершающуюся нулем, которая указывает текущий диск и каталог для нового процесса. Строка должна быть полным путем, содержащим букву диска. Если этот параметр имеет значение NULL, то новый процесс будет иметь тот же текущий диск и каталог, что и вызывающий процесс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

`CreateProcessAsUser` использует `CreateProcessAsUser` функцию Win32 для создания нового процесса, который выполняется в контексте безопасности пользователя, представленного объектом `CAccessToken`. Ознакомьтесь с описанием функции [параметр CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) , чтобы получить полное описание необходимых параметров.

Чтобы этот метод был выполнен, объект `CAccessToken` должен содержать Ассигнпримаритокен (если только он не является ограничивающим маркером) и привилегии Инкреасекуота.

##  <a name="createrestrictedtoken"></a>CAccessToken:: CreateRestrictedToken

Вызовите этот метод, чтобы создать новый, ограниченный `CAccessToken` объект.

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>Параметры

*престриктедтокен*<br/>
Новый, ограниченный `CAccessToken` объект.

*сидстодисабле*<br/>
Объект `CTokenGroups`, указывающий идентификаторы безопасности только для запрета.

*сидсторестрикт*<br/>
Объект `CTokenGroups`, указывающий идентификаторы SID.

*привилежестоделете*<br/>
Объект `CTokenPrivileges`, указывающий права на удаление в маркере с ограниченным доступом. По умолчанию создается пустой объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

`CreateRestrictedToken` использует функцию Win32 [CreateRestrictedToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) для создания нового объекта `CAccessToken` с ограничениями.

> [!IMPORTANT]
>  При использовании `CreateRestrictedToken`убедитесь в следующем: существующий токен является допустимым (и не указывается пользователем), а *сидстодисабле* и *привилежестоделете* являются допустимыми (и не указаны пользователем). Если метод возвращает значение FALSE, функция Deny.

##  <a name="detach"></a>CAccessToken::D етач

Вызовите этот метод, чтобы отменить владение маркером доступа.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер `CAccessToken`, который был отсоединен.

### <a name="remarks"></a>Remarks

Этот метод отменяет владение маркером доступа `CAccessToken`.

##  <a name="disableprivilege"></a>CAccessToken::D Исаблепривилеже

Вызовите этот метод, чтобы отключить привилегию в объекте `CAccessToken`.

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*псзпривилеже*<br/>
Указатель на строку, содержащую привилегию, которую необходимо отключить в объекте `CAccessToken`.

*ппревиаусстате*<br/>
Указатель на объект `CTokenPrivileges`, который будет содержать предыдущее состояние привилегий.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="disableprivileges"></a>CAccessToken::D Исаблепривилежес

Вызовите этот метод, чтобы отключить один или несколько привилегий в объекте `CAccessToken`.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*рпривилежес*<br/>
Указатель на массив строк, содержащий привилегии для отключения в объекте `CAccessToken`.

*ппревиаусстате*<br/>
Указатель на объект `CTokenPrivileges`, который будет содержать предыдущее состояние привилегий.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="enableprivilege"></a>CAccessToken:: Енаблепривилеже

Вызовите этот метод, чтобы включить привилегию в объекте `CAccessToken`.

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*псзпривилеже*<br/>
Указатель на строку, содержащую привилегию, которую необходимо включить в объекте `CAccessToken`.

*ппревиаусстате*<br/>
Указатель на объект `CTokenPrivileges`, который будет содержать предыдущее состояние привилегий.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="enableprivileges"></a>CAccessToken:: Енаблепривилежес

Вызовите этот метод, чтобы включить один или несколько привилегий в объекте `CAccessToken`.

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*рпривилежес*<br/>
Указатель на массив строк, содержащий привилегии, которые должны быть включены в объекте `CAccessToken`.

*ппревиаусстате*<br/>
Указатель на объект `CTokenPrivileges`, который будет содержать предыдущее состояние привилегий.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="getdefaultdacl"></a>CAccessToken:: Жетдефаултдакл

Вызовите этот метод, чтобы вернуть список DACL по умолчанию для объекта `CAccessToken`.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>Параметры

*пдакл*<br/>
Указатель на объект [класса кдакл](../../atl/reference/cdacl-class.md) , который будет принимать DACL по умолчанию для объекта `CAccessToken`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если DACL по умолчанию восстановлен, и FALSE в противном случае.

##  <a name="geteffectivetoken"></a>CAccessToken:: Жетеффективетокен

Вызовите этот метод, чтобы получить объект `CAccessToken`, равный маркеру доступа, который действует для текущего потока.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>Параметры

*двдесиредакцесс*<br/>
Задает маску доступа, указывающую запрошенные типы доступа к маркеру доступа. Эти запрошенные типы доступа сравниваются с DACL маркера для определения того, какие доступ предоставлен или запрещен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="getgroups"></a>CAccessToken:: группы

Вызовите этот метод, чтобы получить группы токенов объекта `CAccessToken`.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>Параметры

*пграупс*<br/>
Указатель на объект [класса ктокенграупс](../../atl/reference/ctokengroups-class.md) , который будет принимать сведения о группе.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="gethandle"></a>CAccessToken:: getHandler

Вызовите этот метод, чтобы получить маркер маркера доступа.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер для маркера доступа объекта `CAccessToken`.

##  <a name="getimpersonationlevel"></a>CAccessToken:: Жетимперсонатионлевел

Вызовите этот метод, чтобы получить уровень олицетворения из маркера доступа.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>Параметры

*пимперсонатионлевел*<br/>
Указатель на тип перечисления [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) , который будет принимать сведения об уровне олицетворения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="getlogonsessionid"></a>CAccessToken:: Жетлогонсессионид

Вызовите этот метод, чтобы получить идентификатор сеанса входа, связанный с объектом `CAccessToken`.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Параметры

*плуид*<br/>
Указатель на [LUID](/windows/win32/api/winnt/ns-winnt-luid) , который получит идентификатор сеанса входа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

В отладочных сборках возникнет ошибка утверждения, если *плуид* имеет недопустимое значение.

##  <a name="getlogonsid"></a>CAccessToken:: Жетлогонсид

Вызовите этот метод, чтобы получить идентификатор безопасности входа, связанный с объектом `CAccessToken`.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*Пустой pSid*<br/>
Указатель на объект [класса CSid](../../atl/reference/csid-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

В отладочных сборках возникнет ошибка утверждения, если *пустой pSid* имеет недопустимое значение.

##  <a name="getowner"></a>CAccessToken:: owner

Вызовите этот метод, чтобы получить владельца, связанного с объектом `CAccessToken`.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*Пустой pSid*<br/>
Указатель на объект [класса CSid](../../atl/reference/csid-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Владелец задается по умолчанию для всех объектов, созданных во время действия маркера доступа.

##  <a name="getprimarygroup"></a>CAccessToken:: Жетпримариграуп

Вызовите этот метод, чтобы получить основную группу, связанную с объектом `CAccessToken`.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*Пустой pSid*<br/>
Указатель на объект [класса CSid](../../atl/reference/csid-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Группа по умолчанию задается для всех объектов, созданных в данный период действия маркера доступа.

##  <a name="getprivileges"></a>CAccessToken:: Privileges

Вызовите этот метод, чтобы получить привилегии, связанные с объектом `CAccessToken`.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>Параметры

*ппривилежес*<br/>
Указатель на объект [класса ктокенпривилежес](../../atl/reference/ctokenprivileges-class.md) , который будет принимать привилегии.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="getprocesstoken"></a>CAccessToken:: Жетпроцесстокен

Вызовите этот метод, чтобы инициализировать `CAccessToken` с маркером доступа из данного процесса.

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>Параметры

*двдесиредакцесс*<br/>
Задает маску доступа, указывающую запрошенные типы доступа к маркеру доступа. Эти запрошенные типы доступа сравниваются с DACL маркера для определения того, какие доступ предоставлен или запрещен.

*хпроцесс*<br/>
Обработка процесса, маркер доступа к которому открыт. Если используется значение по умолчанию NULL, используется текущий процесс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Вызывает функцию Win32 [OpenProcessToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-openprocesstoken) .

##  <a name="getprofile"></a>CAccessToken::/Profile

Вызовите этот метод, чтобы получить маркер, указывающий на профиль пользователя, связанный с объектом `CAccessToken`.

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер, указывающий на профиль пользователя, или значение NULL, если профиль не существует.

##  <a name="getsource"></a>CAccessToken:: \ Source

Вызовите этот метод, чтобы получить источник объекта `CAccessToken`.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>Параметры

*псаурце*<br/>
Указатель на структуру [TOKEN_SOURCE](/windows/win32/api/winnt/ns-winnt-token_source) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="getstatistics"></a>CAccessToken:: Statistics

Вызовите этот метод, чтобы получить сведения, связанные с объектом `CAccessToken`.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>Параметры

*пстатистикс*<br/>
Указатель на структуру [TOKEN_STATISTICS](/windows/win32/api/winnt/ns-winnt-token_statistics) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="getterminalservicessessionid"></a>CAccessToken:: Жеттерминалсервицессессионид

Вызовите этот метод, чтобы получить идентификатор сеанса служб терминалов, связанный с объектом `CAccessToken`.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>Параметры

*пдвсессионид*<br/>
Идентификатор сеанса служб терминалов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="getthreadtoken"></a>CAccessToken:: Жетсреадтокен

Вызовите этот метод, чтобы инициализировать `CAccessToken` с маркером из данного потока.

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>Параметры

*двдесиредакцесс*<br/>
Задает маску доступа, указывающую запрошенные типы доступа к маркеру доступа. Эти запрошенные типы доступа сравниваются с DACL маркера для определения того, какие доступ предоставлен или запрещен.

*хсреад*<br/>
Обработчик потока, маркер доступа к которому открыт.

*бопенасселф*<br/>
Указывает, должна ли проверка доступа выполняться в контексте безопасности потока, вызывающего метод `GetThreadToken`, или контекста безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть таким же, как у клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="gettokenid"></a>CAccessToken:: Жеттокенид

Вызовите этот метод, чтобы получить идентификатор маркера, связанный с объектом `CAccessToken`.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Параметры

*плуид*<br/>
Указатель на [LUID](/windows/win32/api/winnt/ns-winnt-luid) , который получит идентификатор токена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="gettype"></a>CAccessToken:: GetType

Вызовите этот метод, чтобы получить тип токена объекта `CAccessToken`.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>Параметры

*птипе*<br/>
Адрес переменной [TOKEN_TYPE](/windows/win32/api/winnt/ne-winnt-token_type) , которая в случае успеха получает тип токена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Тип перечисления TOKEN_TYPE содержит значения, которые различают между основным маркером и токеном олицетворения.

##  <a name="getuser"></a>CAccessToken:: пользователь

Вызовите этот метод, чтобы обозначить пользователя, связанного с объектом `CAccessToken`.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Параметры

*Пустой pSid*<br/>
Указатель на объект [класса CSid](../../atl/reference/csid-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

##  <a name="hkeycurrentuser"></a>CAccessToken:: Хкэйкуррентусер

Вызовите этот метод, чтобы получить маркер, указывающий на профиль пользователя, связанный с объектом `CAccessToken`.

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер, указывающий на профиль пользователя, или значение NULL, если профиль не существует.

##  <a name="impersonate"></a>CAccessToken:: IMPERSONATE

Вызовите этот метод, чтобы назначить потоку `CAccessToken` олицетворения.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*хсреад*<br/>
Обработчик потока, которому назначается маркер олицетворения. Этот обработчик должен быть открыт с TOKEN_IMPERSONATE правами доступа. Если *хсреад* имеет значение null, метод приводит к остановке потока с помощью токена олицетворения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

В отладочных сборках возникнет ошибка утверждения, если `CAccessToken` не имеет допустимого указателя на маркер.

[Класс кауторевертимперсонатион](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматического возврата олицетворенных маркеров доступа.

##  <a name="impersonateloggedonuser"></a>CAccessToken:: Имперсонателогжедонусер

Вызовите этот метод, чтобы вызывающий поток олицетворять контекст безопасности вошедшего в систему пользователя.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

> [!IMPORTANT]
>  Если вызов функции олицетворения по какой-либо причине завершается неудачей, то клиент не олицетворяется, а клиентский запрос выполняется в контексте безопасности процесса, из которого был сделан вызов. Если процесс выполняется от имени привилегированной учетной записи или является членом административной группы, он может выполнять действия, которые в противном случае будут запрещены. Таким образом, возвращаемое значение для этой функции всегда должно быть подтверждено.

##  <a name="istokenrestricted"></a>CAccessToken:: Истокенрестриктед

Вызовите этот метод, чтобы проверить, содержит ли объект `CAccessToken` список ограниченных идентификаторов безопасности.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объект содержит список идентификаторов SID, и FALSE, если идентификаторы SID отсутствуют или если метод завершается с ошибкой.

##  <a name="loaduserprofile"></a>CAccessToken:: LoadUserProfile

Вызовите этот метод, чтобы загрузить профиль пользователя, связанный с объектом `CAccessToken`.

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

В отладочных сборках возникнет ошибка утверждения, если `CAccessToken` не содержит допустимого маркера или если профиль пользователя уже существует.

##  <a name="logonuser"></a>CAccessToken:: LogonUser

Вызовите этот метод, чтобы создать сеанс входа для пользователя, связанного с заданными учетными данными.

```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```

### <a name="parameters"></a>Параметры

*псзусернаме*<br/>
Указатель на строку, завершающуюся нулем, которая указывает имя пользователя. Это имя учетной записи пользователя для входа в систему.

*псздомаин*<br/>
Указатель на строку, завершающуюся нулем, которая указывает имя домена или сервера, для которого база данных учетных записей содержит учетную запись *псзусернаме* .

*псзпассворд*<br/>
Указатель на строку, завершающуюся нулем, которая указывает пароль в виде открытого текста для учетной записи пользователя, указанной параметром *псзусернаме*.

*dwLogonType*<br/>
Указывает тип выполняемой операции входа. Дополнительные сведения см. в разделе [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

*двлогонпровидер*<br/>
Указывает поставщика входа в систему. Дополнительные сведения см. в разделе [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Маркер доступа, полученный при входе в систему, будет связан с `CAccessToken`. Чтобы этот метод был выполнен, объект `CAccessToken` должен содержать привилегии SE_TCB_NAME, определяя владельца как часть базы доверенного компьютера. Дополнительные сведения о необходимых привилегиях см. в разделе [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

##  <a name="opencomclienttoken"></a>CAccessToken:: Опенкомклиенттокен

Вызовите этот метод из COM-сервера, обрабатывающего вызов от клиента, чтобы инициализировать `CAccessToken` с маркером доступа из клиента COM.

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Параметры

*двдесиредакцесс*<br/>
Задает маску доступа, указывающую запрошенные типы доступа к маркеру доступа. Эти запрошенные типы доступа сравниваются с DACL маркера для определения того, какие доступ предоставлен или запрещен.

*бимперсонате*<br/>
Если значение — TRUE, текущий поток будет олицетворять вызывающий клиент COM, если этот вызов завершается успешно. Если значение равно FALSE, маркер доступа будет открыт, но при завершении этого вызова поток не будет иметь маркер олицетворения.

*бопенасселф*<br/>
Указывает, должна ли проверка доступа выполняться в контексте безопасности потока, вызывающего метод [жетсреадтокен](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) , или контекста безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть таким же, как у клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

[Класс кауторевертимперсонатион](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматического изменения олицетворенных маркеров доступа, созданных путем установки флага *бимперсонате* в значение true.

##  <a name="opennamedpipeclienttoken"></a>CAccessToken:: Опеннамедпипеклиенттокен

Вызовите этот метод из сервера, принимающего запросы через именованный канал, чтобы инициализировать `CAccessToken` с маркером доступа от клиента.

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Параметры

*хпипе*<br/>
Обработчик именованного канала.

*двдесиредакцесс*<br/>
Задает маску доступа, указывающую запрошенные типы доступа к маркеру доступа. Эти запрошенные типы доступа сравниваются с DACL маркера для определения того, какие доступ предоставлен или запрещен.

*бимперсонате*<br/>
Если значение — TRUE, текущий поток будет олицетворять клиент вызывающего канала, если этот вызов завершается успешно. Если значение равно FALSE, маркер доступа будет открыт, но при завершении этого вызова поток не будет иметь маркер олицетворения.

*бопенасселф*<br/>
Указывает, должна ли проверка доступа выполняться в контексте безопасности потока, вызывающего метод [жетсреадтокен](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) , или контекста безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть таким же, как у клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

[Класс кауторевертимперсонатион](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматического изменения олицетворенных маркеров доступа, созданных путем установки флага *бимперсонате* в значение true.

##  <a name="openrpcclienttoken"></a>CAccessToken:: Опенрпкклиенттокен

Вызовите этот метод из сервера, обрабатывающего вызов от клиента RPC, чтобы инициализировать `CAccessToken` с маркером доступа от клиента.

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Параметры

*биндингхандле*<br/>
Маркер привязки на сервере, представляющий привязку к клиенту.

*двдесиредакцесс*<br/>
Задает маску доступа, указывающую запрошенные типы доступа к маркеру доступа. Эти запрошенные типы доступа сравниваются с DACL маркера для определения того, какие доступ предоставлен или запрещен.

*бимперсонате*<br/>
Если значение — TRUE, текущий поток будет олицетворять вызывающий клиент RPC, если этот вызов завершается успешно. Если значение равно FALSE, маркер доступа будет открыт, но при завершении этого вызова поток не будет иметь маркер олицетворения.

*бопенасселф*<br/>
Указывает, должна ли проверка доступа выполняться в контексте безопасности потока, вызывающего метод [жетсреадтокен](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) , или контекста безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть таким же, как у клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

[Класс кауторевертимперсонатион](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматического изменения олицетворенных маркеров доступа, созданных путем установки флага *бимперсонате* в значение true.

##  <a name="openthreadtoken"></a>CAccessToken:: Опенсреадтокен

Вызовите этот метод, чтобы задать уровень олицетворения, а затем инициализировать `CAccessToken` с маркером из данного потока.

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>Параметры

*двдесиредакцесс*<br/>
Задает маску доступа, указывающую запрошенные типы доступа к маркеру доступа. Эти запрошенные типы доступа сравниваются с DACL маркера для определения того, какие доступ предоставлен или запрещен.

*бимперсонате*<br/>
Если значение — TRUE, поток будет оставлен на запрошенном уровне олицетворения после завершения этого метода. Если значение равно FALSE, то поток вернется к исходному уровню олицетворения.

*бопенасселф*<br/>
Указывает, должна ли проверка доступа выполняться в контексте безопасности потока, вызывающего метод [жетсреадтокен](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) , или контекста безопасности процесса для вызывающего потока.

Если этот параметр имеет значение FALSE, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть таким же, как у клиентского процесса. Если этот параметр имеет значение TRUE, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.

*SIL*<br/>
Указывает [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) перечислимый тип, который предоставляет уровень олицетворения маркера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

`OpenThreadToken` похож на [CAccessToken:: жетсреадтокен](#getthreadtoken), но задает уровень олицетворения перед инициализацией `CAccessToken` из маркера доступа потока.

[Класс кауторевертимперсонатион](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для автоматического изменения олицетворенных маркеров доступа, созданных путем установки флага *бимперсонате* в значение true.

##  <a name="privilegecheck"></a>CAccessToken::P Ривилежечекк

Вызовите этот метод, чтобы определить, включен ли указанный набор привилегий в объект `CAccessToken`.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>Параметры

*рекуиредпривилежес*<br/>
Указатель на структуру [PRIVILEGE_SET](/windows/win32/api/winnt/ns-winnt-privilege_set) .

*пбресулт*<br/>
Указатель на значение, которое задает метод, чтобы указать, включены ли какие-либо из указанных прав в объекте `CAccessToken`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Когда `PrivilegeCheck` возвращает, `Attributes` элемент каждой структуры [LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes) имеет значение SE_PRIVILEGE_USED_FOR_ACCESS, если соответствующие привилегии включены. Этот метод вызывает функцию Win32 [привилежечекк](/windows/win32/api/securitybaseapi/nf-securitybaseapi-privilegecheck) .

##  <a name="revert"></a>CAccessToken:: revert

Вызовите этот метод, чтобы предотвратить использование токена олицетворения потоком.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>Параметры

*хсреад*<br/>
Обработайте поток, чтобы отменить олицетворение. Если *хсреад* имеет значение null, предполагается текущий поток.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Переверсия токенов олицетворения может быть выполнена автоматически с помощью [класса кауторевертимперсонатион](../../atl/reference/cautorevertimpersonation-class.md).

##  <a name="setdefaultdacl"></a>CAccessToken:: Сетдефаултдакл

Вызовите этот метод, чтобы задать список DACL по умолчанию для объекта `CAccessToken`.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>Параметры

*рдакл*<br/>
Новые сведения о [классе кдакл](../../atl/reference/cdacl-class.md) по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

DACL по умолчанию — список DACL, используемый по умолчанию при создании новых объектов с помощью этого маркера доступа.

##  <a name="setowner"></a>CAccessToken:: Сетовнер

Вызовите этот метод, чтобы задать владельца объекта `CAccessToken`.

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*рсид*<br/>
Объект [класса CSid](../../atl/reference/csid-class.md) , содержащий сведения о владельце.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Владелец является владельцем по умолчанию, который используется для новых объектов, созданных, пока этот маркер доступа действует.

##  <a name="setprimarygroup"></a>CAccessToken:: Сетпримариграуп

Вызовите этот метод, чтобы задать основную группу объекта `CAccessToken`.

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*рсид*<br/>
Объект [класса CSid](../../atl/reference/csid-class.md) , содержащий сведения о первичной группе.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Remarks

Основная группа является группой по умолчанию для новых объектов, созданных во время действия маркера доступа.

## <a name="see-also"></a>См. также раздел

[Пример Атлсекурити](../../overview/visual-cpp-samples.md)<br/>
[Маркеры доступа](/windows/win32/SecAuthZ/access-tokens)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
