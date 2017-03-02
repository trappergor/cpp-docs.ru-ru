---
title: "Класс CAccessToken | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATLSECURITY/CAccessToken
- ATL.CAccessToken
- CAccessToken
- ATL::CAccessToken
dev_langs:
- C++
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
caps.latest.revision: 24
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 79845a2be4f79a1ee94a9440e8508bcb0e38bcdd
ms.lasthandoff: 02/24/2017

---
# <a name="caccesstoken-class"></a>Класс CAccessToken
Этот класс является оболочкой для маркера доступа.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAccessToken
```  
  
## <a name="members"></a>Члены  
  
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
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Этот метод вызывается для создания нового процесса, запущенная в контексте безопасности пользователя, представленного `CAccessToken` объекта.|  
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Этот метод вызывается для создания нового, ограниченные `CAccessToken` объекта.|  
|[CAccessToken::Detach](#detach)|Этот метод вызывается для отмены владения маркер доступа.|  
|[CAccessToken::DisablePrivilege](#disableprivilege)|Этот метод вызывается для отключения привилегии в `CAccessToken` объекта.|  
|[CAccessToken::DisablePrivileges](#disableprivileges)|Вызовите этот метод, чтобы отключить один или несколько привилегии в `CAccessToken` объекта.|  
|[CAccessToken::EnablePrivilege](#enableprivilege)|Этот метод вызывается для включения права в `CAccessToken` объекта.|  
|[CAccessToken::EnablePrivileges](#enableprivileges)|Вызовите этот метод, чтобы включить один или несколько привилегии в `CAccessToken` объекта.|  
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Вызовите этот метод для возврата `CAccessToken` объекта по умолчанию DACL.|  
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Этот метод вызывается для получения `CAccessToken` равное маркер доступа, применяемые для текущего потока.|  
|[CAccessToken::GetGroups](#getgroups)|Вызовите этот метод для возврата `CAccessToken` объекта маркера групп.|  
|[CAccessToken::GetHandle](#gethandle)|Вызовите этот метод, чтобы получить дескриптор маркера доступа.|  
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Вызовите этот метод, чтобы получить маркер доступа уровень олицетворения.|  
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|Вызовите этот метод, чтобы получить идентификатор сеанса входа в систему, связанного с `CAccessToken` объекта.|  
|[CAccessToken::GetLogonSid](#getlogonsid)|Этот метод вызывается для получения идентификатора безопасности входа в систему, связанные с `CAccessToken` объекта.|  
|[CAccessToken::GetOwner](#getowner)|Этот метод вызывается для получения владельца, связанный с `CAccessToken` объекта.|  
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|Этот метод вызывается для получения основной группы, связанные с `CAccessToken` объекта.|  
|[CAccessToken::GetPrivileges](#getprivileges)|Этот метод вызывается для получения права, связанные с `CAccessToken` объекта.|  
|[CAccessToken::GetProcessToken](#getprocesstoken)|Этот метод вызывается для инициализации `CAccessToken` с маркером доступа из указанного процесса.|  
|[CAccessToken::GetProfile](#getprofile)|Вызовите этот метод, чтобы получить дескриптор, указывающий профиль пользователя, связанный с `CAccessToken` объекта.|  
|[CAccessToken::GetSource](#getsource)|Этот метод вызывается для получения источника `CAccessToken` объекта.|  
|[CAccessToken::GetStatistics](#getstatistics)|Этот метод вызывается для получения сведений, связанных с `CAccessToken` объекта.|  
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|Вызовите этот метод, чтобы получить идентификатор сеанса служб терминалов, связанный с `CAccessToken` объекта.|  
|[CAccessToken::GetThreadToken](#getthreadtoken)|Этот метод вызывается для инициализации `CAccessToken` с маркера из данного потока.|  
|[CAccessToken::GetTokenId](#gettokenid)|Этот метод вызывается для получения маркера идентификатор, связанный с `CAccessToken` объекта.|  
|[CAccessToken::GetType](#gettype)|Этот метод вызывается для получения маркера типа `CAccessToken` объекта.|  
|[CAccessToken::GetUser](#getuser)|Этот метод вызывается для идентификации пользователя, связанного с `CAccessToken` объекта.|  
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|Вызовите этот метод, чтобы получить дескриптор, указывающий профиль пользователя, связанный с `CAccessToken` объекта.|  
|[CAccessToken::Impersonate](#impersonate)|Вызовите этот метод, чтобы назначить олицетворение `CAccessToken` потоку.|  
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Этот метод позволяет вызывающему потоку олицетворять контекст безопасности вошедшего в систему пользователя.|  
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Этот метод вызывается для проверки, если `CAccessToken` объект содержит список ограниченных SID.|  
|[CAccessToken::LoadUserProfile](#loaduserprofile)|Этот метод вызывается для загрузки профиля пользователя, связанные с `CAccessToken` объекта.|  
|[CAccessToken::LogonUser](#logonuser)|Этот метод используется для создания сеанса входа в систему для пользователя, связанного с заданными учетными данными.|  
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Вызов этого метода в COM-сервера, обрабатывающего вызов от клиента для инициализации `CAccessToken` с маркером доступа из COM-клиент.|  
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Вызовите этот метод из сервера принимая запросы по именованному каналу для инициализации `CAccessToken` с маркером доступа от клиента.|  
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Вызовите этот метод из сервера обработки вызов из клиента RPC для инициализации `CAccessToken` с маркером доступа от клиента.|  
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Этот метод вызывается для настройки уровня олицетворения, а затем инициализируйте `CAccessToken` с маркера из данного потока.|  
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Вызовите этот метод, чтобы определить, включены ли в указанный набор прав **CAccessToken** объекта.|  
|[CAccessToken::Revert](#revert)|Этот метод используется для остановки потока, который использует маркер олицетворения.|  
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Этот метод по умолчанию список DACL `CAccessToken` объекта.|  
|[CAccessToken::SetOwner](#setowner)|Вызовите этот метод, чтобы задать владельца `CAccessToken` объекта.|  
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Вызовите этот метод, чтобы задать основной группы `CAccessToken` объекта.|  
  
## <a name="remarks"></a>Примечания  
 [Маркер доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909) — это объект, который описывает контекст безопасности процесса или потока и выделяется для каждого пользователя, входившего в системе Windows NT или Windows 2000.  
  
 Введение в модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="a-nameattacha--caccesstokenattach"></a><a name="attach"></a>CAccessToken::Attach  
 Вызовите этот метод, чтобы стать владельцем дескриптора маркера доступ.  
  
```
void Attach(HANDLE hToken) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *hToken*  
 Дескриптор маркера доступа.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `CAccessToken` объект уже владеет маркер доступа.  
  
##  <a name="a-namedtora--caccesstokencaccesstoken"></a><a name="dtor"></a>CAccessToken:: ~ CAccessToken  
 Деструктор  
  
```
virtual ~CAccessToken() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="a-namechecktokenmembershipa--caccesstokenchecktokenmembership"></a><a name="checktokenmembership"></a>CAccessToken::CheckTokenMembership  
 Вызовите этот метод, чтобы определить, включен ли указанный идентификатор SID в `CAccessToken` объекта.  
  
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
 `CheckTokenMembership` Метод проверяет на наличие идентификатора безопасности пользователя и SID группы маркер доступа. Если идентификатор безопасности существует и имеет атрибут SE_GROUP_ENABLED *pbIsMember* имеет значение true; в противном случае, он имеет значение false.  
  
 В отладочных построениях, произойдет ошибка утверждения, если `pbIsMember` не является допустимым указателем.  
  
> [!NOTE]
>  `CAccessToken` Объект должен быть маркер олицетворения и основного маркера.  
  
##  <a name="a-namecreateimpersonationtokena--caccesstokencreateimpersonationtoken"></a><a name="createimpersonationtoken"></a>CAccessToken::CreateImpersonationToken  
 Этот метод вызывается для создания маркера доступа олицетворения.  
  
```
bool CreateImpersonationToken(
    CAccessToken* pImp, 
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pImp`  
 Указатель на новый `CAccessToken` объекта.  
  
 `sil`  
 Указывает [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) перечислимый тип, предоставляющий уровень олицетворения новый маркер.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `CreateImpersonationToken`вызовы [DuplicateToken](http://msdn.microsoft.com/library/windows/desktop/aa446616) , чтобы создать новый маркер олицетворения.  
  
##  <a name="a-namecreateprimarytokena--caccesstokencreateprimarytoken"></a><a name="createprimarytoken"></a>CAccessToken::CreatePrimaryToken  
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
 Задает права доступа для нового токена. Значение по умолчанию MAXIMUM_ALLOWED, запрашивает все права доступа, которые являются допустимыми для вызывающего объекта. В разделе [прав доступа и маски доступа](http://msdn.microsoft.com/library/windows/desktop/aa374902) дополнительные права на доступ.  
  
 *pTokenAttributes*  
 Указатель на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структуры, который задает дескриптор безопасности для нового токена и определяет, могут ли дочерние процессы наследуют маркер. Если *pTokenAttributes* имеет значение NULL, возвращает токен дескриптор безопасности по умолчанию и дескриптор не наследуется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `CreatePrimaryToken`вызовы [DuplicateTokenEx](http://msdn.microsoft.com/library/windows/desktop/aa446617) для создания нового основного маркера.  
  
##  <a name="a-namecreateprocessasusera--caccesstokencreateprocessasuser"></a><a name="createprocessasuser"></a>CAccessToken::CreateProcessAsUser  
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
 Указатель нулем строка, указывающая модуль для выполнения. Этот параметр не может иметь значение NULL.  
  
 *pCommandLine*  
 Указатель нулем строку, которая задает командную строку для выполнения.  
  
 *pProcessInformation*  
 Указатель на [PROCESS_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/ms684873) структуру, которая получает сведения о новом процессе.  
  
 *pStartupInfo*  
 Указатель на [STARTUPINFO](http://msdn.microsoft.com/library/windows/desktop/ms686331) структура, которая указывает, как должно выглядеть главного окна для нового процесса.  
  
 `dwCreationFlags`  
 Задает дополнительные флаги, управляющие с приоритетом и создания процесса. Функция Win32 в разделе [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) список флагов.  
  
 *bLoadProfile*  
 Если значение равно true, профиль пользователя загружается [LoadUserProfile](http://msdn.microsoft.com/library/windows/desktop/bb762281).  
  
 *pProcessAttributes*  
 Указатель на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структуры, который задает дескриптор безопасности для нового процесса и определяет, могут ли дочерние процессы наследуют возвращенный дескриптор. Если *pProcessAttributes* имеет значение NULL, процесс получает дескриптор безопасности по умолчанию и дескриптор не наследуется.  
  
 *pThreadAttributes*  
 Указатель на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структуры, который задает дескриптор безопасности для нового потока и определяет, могут ли дочерние процессы наследуют возвращенный дескриптор. Если *pThreadAttributes* имеет значение NULL, поток получает дескриптор безопасности по умолчанию и дескриптор не наследуется.  
  
 *bInherit*  
 Указывает, наследует ли новый процесс дескрипторов вызывающего процесса. Значение true, если каждый наследуемые открытый дескриптор в вызывающий процесс наследуется новый процесс. Унаследованные дескрипторы обладают теми же привилегиями значение и доступа исходные дескрипторы.  
  
 *pCurrentDirectory*  
 Указатель на строку с завершающим нулем, указывающее текущий диск и каталог для нового процесса. Строка должна представлять полный путь, который содержит букву диска. Если этот параметр имеет значение NULL, новый процесс будет иметь же текущий диск и каталог, что вызывающий процесс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 **CreateProcessAsUser** использует `CreateProcessAsUser` функцию Win32 для создания нового процесса, который выполняется в контексте безопасности пользователя, представленного `CAccessToken` объекта. См. в описании [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) функция подробное обсуждение необходимых параметров.  
  
 Для успешного выполнения этого метода `CAccessToken` должен храниться в объекте AssignPrimaryToken (если он является ограниченным маркером) и IncreaseQuota права доступа.  
  
##  <a name="a-namecreaterestrictedtokena--caccesstokencreaterestrictedtoken"></a><a name="createrestrictedtoken"></a>CAccessToken::CreateRestrictedToken  
 Этот метод вызывается для создания нового, ограниченные `CAccessToken` объекта.  
  
```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pRestrictedToken*  
 Новый, ограничен `CAccessToken` объекта.  
  
 `SidsToDisable`  
 Объект `CTokenGroups` объект, который указывает только ИД безопасности.  
  
 *SidsToRestrict*  
 Объект `CTokenGroups` , указывающий ограничивающими идентификаторами безопасности.  
  
 `PrivilegesToDelete`  
 Объект `CTokenPrivileges` , указывающий привилегий для удаления в ограниченным маркером. Значение по умолчанию создает пустой объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `CreateRestrictedToken`использует [CreateRestrictedToken](http://msdn.microsoft.com/library/windows/desktop/aa446583) функцию Win32 для создания нового `CAccessToken` объекта с ограничениями.  
  
> [!NOTE]
>  Этот метод является только в Windows 2000 и более поздних версиях.  
  
> [!IMPORTANT]
>  При использовании `CreateRestrictedToken`, убедитесь в следующем: существующий маркер является допустимым (и не введенных пользователем) и `SidsToDisable` и `PrivilegesToDelete` допустимым (и не введенных пользователем). Если метод возвращает значение false, запретите функциональные возможности.  
  
##  <a name="a-namedetacha--caccesstokendetach"></a><a name="detach"></a>CAccessToken::Detach  
 Этот метод вызывается для отмены владения маркер доступа.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор `CAccessToken` которого была отсоединена.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отменяет `CAccessToken`на владение маркер доступа.  
  
##  <a name="a-namedisableprivilegea--caccesstokendisableprivilege"></a><a name="disableprivilege"></a>CAccessToken::DisablePrivilege  
 Этот метод вызывается для отключения привилегии в `CAccessToken` объекта.  
  
```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pszPrivilege`  
 Указатель на строку, содержащую право отключить `CAccessToken` объекта.  
  
 `pPreviousState`  
 Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние привилегии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namedisableprivilegesa--caccesstokendisableprivileges"></a><a name="disableprivileges"></a>CAccessToken::DisablePrivileges  
 Вызовите этот метод, чтобы отключить один или несколько привилегии в `CAccessToken` объекта.  
  
```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rPrivileges`  
 Указатель на массив строк, содержащих привилегии, выключить в `CAccessToken` объекта.  
  
 `pPreviousState`  
 Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние привилегии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-nameenableprivilegea--caccesstokenenableprivilege"></a><a name="enableprivilege"></a>CAccessToken::EnablePrivilege  
 Этот метод вызывается для включения права в `CAccessToken` объекта.  
  
```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pszPrivilege`  
 Указатель на строку, содержащую прав для включения в `CAccessToken` объекта.  
  
 `pPreviousState`  
 Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние привилегии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-nameenableprivilegesa--caccesstokenenableprivileges"></a><a name="enableprivileges"></a>CAccessToken::EnablePrivileges  
 Вызовите этот метод, чтобы включить один или несколько привилегии в `CAccessToken` объекта.  
  
```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rPrivileges`  
 Указатель на массив строк, содержащих привилегии, чтобы включить в `CAccessToken` объекта.  
  
 `pPreviousState`  
 Указатель на `CTokenPrivileges` объект, который будет содержать предыдущее состояние привилегии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegetdefaultdacla--caccesstokengetdefaultdacl"></a><a name="getdefaultdacl"></a>CAccessToken::GetDefaultDacl  
 Вызовите этот метод для возврата `CAccessToken` объекта по умолчанию DACL.  
  
```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pDacl`  
 Указатель на [класса CDacl](../../atl/reference/cdacl-class.md) объекта, который будет получать **CAccessToken** объекта по умолчанию DACL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если значение по умолчанию DACL был восстановленный, и false в противном случае.  
  
##  <a name="a-namegeteffectivetokena--caccesstokengeteffectivetoken"></a><a name="geteffectivetoken"></a>CAccessToken::GetEffectiveToken  
 Этот метод вызывается для получения `CAccessToken` равное маркер доступа, применяемые для текущего потока.  
  
```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Задает маску доступа, указывающее, запрошенного типа доступа к маркер доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegetgroupsa--caccesstokengetgroups"></a><a name="getgroups"></a>CAccessToken::GetGroups  
 Вызовите этот метод для возврата `CAccessToken` объекта маркера групп.  
  
```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pGroups*  
 Указатель на [CTokenGroups класс](../../atl/reference/ctokengroups-class.md) объекта, который будет получать сведения о группе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegethandlea--caccesstokengethandle"></a><a name="gethandle"></a>CAccessToken::GetHandle  
 Вызовите этот метод, чтобы получить дескриптор маркера доступа.  
  
```
HANDLE GetHandle() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор `CAccessToken` объекта маркера доступа.  
  
##  <a name="a-namegetimpersonationlevela--caccesstokengetimpersonationlevel"></a><a name="getimpersonationlevel"></a>CAccessToken::GetImpersonationLevel  
 Вызовите этот метод, чтобы получить маркер доступа уровень олицетворения.  
  
```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pImpersonationLevel*  
 Указатель на [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) тип перечисления, который будет получать данные уровня олицетворения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegetlogonsessionida--caccesstokengetlogonsessionid"></a><a name="getlogonsessionid"></a>CAccessToken::GetLogonSessionId  
 Вызовите этот метод, чтобы получить идентификатор сеанса входа в систему, связанного с `CAccessToken` объекта.  
  
```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pluid`  
 Указатель на [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) которого получит идентификатор сеанса входа в систему.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `pluid` имеет недопустимое значение.  
  
##  <a name="a-namegetlogonsida--caccesstokengetlogonsid"></a><a name="getlogonsid"></a>CAccessToken::GetLogonSid  
 Этот метод вызывается для получения идентификатора безопасности входа в систему, связанные с `CAccessToken` объекта.  
  
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
  
##  <a name="a-namegetownera--caccesstokengetowner"></a><a name="getowner"></a>CAccessToken::GetOwner  
 Этот метод вызывается для получения владельца, связанный с `CAccessToken` объекта.  
  
```
bool GetOwner(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid класс](../../atl/reference/csid-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Владелец устанавливается по умолчанию на любые объекты, созданные при этот маркер доступа.  
  
##  <a name="a-namegetprimarygroupa--caccesstokengetprimarygroup"></a><a name="getprimarygroup"></a>CAccessToken::GetPrimaryGroup  
 Этот метод вызывается для получения основной группы, связанные с `CAccessToken` объекта.  
  
```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid класс](../../atl/reference/csid-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Группы устанавливается по умолчанию на любые объекты, созданные при этот маркер доступа.  
  
##  <a name="a-namegetprivilegesa--caccesstokengetprivileges"></a><a name="getprivileges"></a>CAccessToken::GetPrivileges  
 Этот метод вызывается для получения права, связанные с `CAccessToken` объекта.  
  
```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pPrivileges`  
 Указатель на [CTokenPrivileges класс](../../atl/reference/ctokenprivileges-class.md) объекта, который будет принимать права доступа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegetprocesstokena--caccesstokengetprocesstoken"></a><a name="getprocesstoken"></a>CAccessToken::GetProcessToken  
 Этот метод вызывается для инициализации `CAccessToken` с маркером доступа из указанного процесса.  
  
```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Задает маску доступа, указывающее, запрошенного типа доступа к маркер доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.  
  
 *hProcess*  
 Процесс, маркер доступа которого был открыт дескриптор. Если значение по умолчанию `NULL` — используется, используется текущий процесс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `true` в случае успешного выполнения `false` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [OpenProcessToken](http://msdn.microsoft.com/library/aa379295\(vs.85\).aspx) функции Win32.  
  
##  <a name="a-namegetprofilea--caccesstokengetprofile"></a><a name="getprofile"></a>CAccessToken::GetProfile  
 Вызовите этот метод, чтобы получить дескриптор, указывающий профиль пользователя, связанный с `CAccessToken` объекта.  
  
```
HANDLE GetProfile() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор, указывающий профиля пользователя, или значение NULL, если профиль не существует.  
  
##  <a name="a-namegetsourcea--caccesstokengetsource"></a><a name="getsource"></a>CAccessToken::GetSource  
 Этот метод вызывается для получения источника `CAccessToken` объекта.  
  
```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pSource*  
 Указатель на [TOKEN_SOURCE](http://msdn.microsoft.com/library/windows/desktop/aa379631) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegetstatisticsa--caccesstokengetstatistics"></a><a name="getstatistics"></a>CAccessToken::GetStatistics  
 Этот метод вызывается для получения сведений, связанных с `CAccessToken` объекта.  
  
```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pStatistics*  
 Указатель на [TOKEN_STATISTICS](http://msdn.microsoft.com/library/windows/desktop/aa379632) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegetterminalservicessessionida--caccesstokengetterminalservicessessionid"></a><a name="getterminalservicessessionid"></a>CAccessToken::GetTerminalServicesSessionId  
 Вызовите этот метод, чтобы получить идентификатор сеанса служб терминалов, связанный с `CAccessToken` объекта.  
  
```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pdwSessionId*  
 Идентификатор сеанса служб терминалов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegetthreadtokena--caccesstokengetthreadtoken"></a><a name="getthreadtoken"></a>CAccessToken::GetThreadToken  
 Этот метод вызывается для инициализации `CAccessToken` с маркера из данного потока.  
  
```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Задает маску доступа, указывающее, запрошенного типа доступа к маркер доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.  
  
 `hThread`  
 Дескриптор потока, маркер доступа которого был открыт.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа будет осуществляться в контексте безопасности вызывающего потока `GetThreadToken` метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegettokenida--caccesstokengettokenid"></a><a name="gettokenid"></a>CAccessToken::GetTokenId  
 Этот метод вызывается для получения маркера идентификатор, связанный с `CAccessToken` объекта.  
  
```
bool GetTokenId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pluid`  
 Указатель на [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) которого получит идентификатор маркера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namegettypea--caccesstokengettype"></a><a name="gettype"></a>CAccessToken::GetType  
 Этот метод вызывается для получения маркера типа `CAccessToken` объекта.  
  
```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pType`  
 Адрес [TOKEN_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379633) переменную, которая, в случае успешного выполнения получает тип маркера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 **TOKEN_TYPE** тип перечисления содержит значения, различия между основной маркер и маркер олицетворения.  
  
##  <a name="a-namegetusera--caccesstokengetuser"></a><a name="getuser"></a>CAccessToken::GetUser  
 Этот метод вызывается для идентификации пользователя, связанного с `CAccessToken` объекта.  
  
```
bool GetUser(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid класс](../../atl/reference/csid-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="a-namehkeycurrentusera--caccesstokenhkeycurrentuser"></a><a name="hkeycurrentuser"></a>CAccessToken::HKeyCurrentUser  
 Вызовите этот метод, чтобы получить дескриптор, указывающий профиль пользователя, связанный с `CAccessToken` объекта.  
  
```
HKEY HKeyCurrentUser() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор, указывающий профиля пользователя, или значение NULL, если профиль не существует.  
  
##  <a name="a-nameimpersonatea--caccesstokenimpersonate"></a><a name="impersonate"></a>CAccessToken::Impersonate  
 Вызовите этот метод, чтобы назначить олицетворение `CAccessToken` потоку.  
  
```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `hThread`  
 Дескриптор назначить маркер олицетворения для потока. Этот дескриптор должен быть открыт с TOKEN_IMPERSONATE прав доступа. Если `hThread` имеет значение NULL, метод приводит к прекращение использования маркер олицетворения потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `CAccessToken` имеет допустимый указатель на маркер.  
  
 [CAutoRevertImpersonation класса](../../atl/reference/cautorevertimpersonation-class.md) можно использовать для возврата маркера олицетворения доступа автоматически.  
  
##  <a name="a-nameimpersonateloggedonusera--caccesstokenimpersonateloggedonuser"></a><a name="impersonateloggedonuser"></a>CAccessToken::ImpersonateLoggedOnUser  
 Этот метод позволяет вызывающему потоку олицетворять контекст безопасности вошедшего в систему пользователя.  
  
```
bool ImpersonateLoggedOnUser() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  Если какой-либо причине произошел сбой вызова функции олицетворения, не олицетворение клиента и клиентский запрос выполняется в контексте безопасности процесса, из которого был выполнен вызов. Если процесс выполняется как высоко привилегированной учетной записи, или как член группы администраторов, пользователь может выполнять действия он или она бы в противном случае быть запрещено. Таким образом возвращаемое значение для этой функции всегда быть подтверждено.  
  
##  <a name="a-nameistokenrestricteda--caccesstokenistokenrestricted"></a><a name="istokenrestricted"></a>CAccessToken::IsTokenRestricted  
 Этот метод вызывается для проверки, если `CAccessToken` объект содержит список ограниченных SID.  
  
```
bool IsTokenRestricted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если объект содержит список ограничивающих идентификаторов безопасности, false, если нет ограничивающими идентификаторами безопасности или если происходит сбой метода.  
  
##  <a name="a-nameloaduserprofilea--caccesstokenloaduserprofile"></a><a name="loaduserprofile"></a>CAccessToken::LoadUserProfile  
 Этот метод вызывается для загрузки профиля пользователя, связанные с `CAccessToken` объекта.  
  
```
bool LoadUserProfile() throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `CAccessToken` не содержит действительный маркер, или если профиль пользователя уже существует.  
  
##  <a name="a-namelogonusera--caccesstokenlogonuser"></a><a name="logonuser"></a>CAccessToken::LogonUser  
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
 Указатель нулем строка, указывающая имя пользователя. Это имя учетной записи пользователя для входа в систему.  
  
 *pszDomain*  
 Указатель на нулем строка, указывающая имя домена или сервера, базу данных учетной записи содержит `pszUserName` учетной записи.  
  
 `pszPassword`  
 Указатель на строку с нулем, указывающее открытый текст пароля для учетной записи пользователя, указанной в `pszUserName`.  
  
 *dwLogonType*  
 Указывает тип выполняемой операции входа в систему. В разделе [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) подробнее.  
  
 *dwLogonProvider*  
 Указывает поставщик входа в систему. В разделе [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) подробнее.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Доступ, маркеров входа в систему результатом будет связан с `CAccessToken`. Для успешного выполнения этого метода `CAccessToken` должен храниться в объекте правами SE_TCB_NAME, идентификации держателя как часть доверенного компьютера базовый. В разделе [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) более подробные сведения о необходимых прав.  
  
##  <a name="a-nameopencomclienttokena--caccesstokenopencomclienttoken"></a><a name="opencomclienttoken"></a>CAccessToken::OpenCOMClientToken  
 Вызов этого метода в COM-сервера, обрабатывающего вызов от клиента для инициализации `CAccessToken` с маркером доступа из COM-клиент.  
  
```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Задает маску доступа, указывающее, запрошенного типа доступа к маркер доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.  
  
 `bImpersonate`  
 Значение true, если текущий поток будет олицетворять вызывающий клиент COM, если этот вызов завершается успешно. Если значение равно false, будет открыт маркер доступа, но поток не получит маркер олицетворения после завершения этого вызова.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа будет осуществляться в контексте безопасности вызывающего потока [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 [Класса CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) можно автоматически восстановить маркеры олицетворения доступа, созданные, задав `bImpersonate` флаг *true*.  
  
##  <a name="a-nameopennamedpipeclienttokena--caccesstokenopennamedpipeclienttoken"></a><a name="opennamedpipeclienttoken"></a>CAccessToken::OpenNamedPipeClientToken  
 Вызовите этот метод из сервера принимая запросы по именованному каналу для инициализации `CAccessToken` с маркером доступа от клиента.  
  
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
 Задает маску доступа, указывающее, запрошенного типа доступа к маркер доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.  
  
 `bImpersonate`  
 Значение true, если текущий поток будет олицетворять вызывающий клиент канала, если этот вызов завершается успешно. Если значение равно false, будет открыт маркер доступа, но поток не получит маркер олицетворения после завершения этого вызова.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа будет осуществляться в контексте безопасности вызывающего потока [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 [Класса CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) можно автоматически восстановить маркеры олицетворения доступа, созданные, задав `bImpersonate` флаг *true*.  
  
##  <a name="a-nameopenrpcclienttokena--caccesstokenopenrpcclienttoken"></a><a name="openrpcclienttoken"></a>CAccessToken::OpenRPCClientToken  
 Вызовите этот метод из сервера обработки вызов из клиента RPC для инициализации `CAccessToken` с маркером доступа от клиента.  
  
```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *BindingHandle*  
 Дескриптор привязки на сервере, который представляет связь с клиентом.  
  
 `dwDesiredAccess`  
 Задает маску доступа, указывающее, запрошенного типа доступа к маркер доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.  
  
 `bImpersonate`  
 Значение true, если текущий поток будет олицетворять вызывающий клиент RPC, если этот вызов завершается успешно. Если значение равно false, будет открыт маркер доступа, но поток не получит маркер олицетворения после завершения этого вызова.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа будет осуществляться в контексте безопасности вызывающего потока [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 [Класса CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) можно автоматически восстановить маркеры олицетворения доступа, созданные, задав `bImpersonate` флаг *true*.  
  
##  <a name="a-nameopenthreadtokena--caccesstokenopenthreadtoken"></a><a name="openthreadtoken"></a>CAccessToken::OpenThreadToken  
 Этот метод вызывается для настройки уровня олицетворения, а затем инициализируйте `CAccessToken` с маркера из данного потока.  
  
```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 Задает маску доступа, указывающее, запрошенного типа доступа к маркер доступа. Эти требуемые типы доступа сравниваются с DACL маркера, чтобы определить, какой доступ разрешен или запрещен.  
  
 `bImpersonate`  
 Значение true, если поток остается на уровне олицетворения запрошенного после завершения этого метода. Если значение равно false, поток вернется к его исходный уровень олицетворения.  
  
 `bOpenAsSelf`  
 Указывает, является ли проверка доступа будет осуществляться в контексте безопасности вызывающего потока [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) метода или в контексте безопасности процесса для вызывающего потока.  
  
 Если этот параметр имеет значение false, проверка доступа выполняется с использованием контекста безопасности для вызывающего потока. Если поток олицетворяет клиента, этот контекст безопасности может быть клиентского процесса. Если этот параметр имеет значение true, проверка доступа выполняется с использованием контекста безопасности процесса для вызывающего потока.  
  
 `sil`  
 Указывает [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) перечислимый тип, предоставляющий уровень олицетворения маркера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `OpenThreadToken`Аналогично [CAccessToken::GetThreadToken](#getthreadtoken), но задает уровень олицетворения перед инициализацией `CAccessToken` из маркера доступа потока.  
  
 [Класса CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) можно автоматически восстановить маркеры олицетворения доступа, созданные, задав `bImpersonate` флаг *true*.  
  
##  <a name="a-nameprivilegechecka--caccesstokenprivilegecheck"></a><a name="privilegecheck"></a>CAccessToken::PrivilegeCheck  
 Вызовите этот метод, чтобы определить, включены ли в указанный набор прав **CAccessToken** объекта.  
  
```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
     bool* pbResult) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *RequiredPrivileges*  
 Указатель на [PRIVILEGE_SET](http://msdn.microsoft.com/library/windows/desktop/aa379307) структуры.  
  
 *pbResult*  
 Указатель на значение метода задает для указания того, включены ли одно или все привилегии, указанного в `CAccessToken` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Когда `PrivilegeCheck` возвращает, **атрибуты** каждого элемента [подробности](http://msdn.microsoft.com/library/windows/desktop/aa379263) структура имеет значение SE_PRIVILEGE_USED_FOR_ACCESS, если включена соответствующих прав доступа. Этот метод вызывает метод [PrivilegeCheck](http://msdn.microsoft.com/library/windows/desktop/aa379304) функции Win32.  
  
##  <a name="a-namereverta--caccesstokenrevert"></a><a name="revert"></a>CAccessToken::Revert  
 Этот метод используется для остановки потока с помощью маркер олицетворения.  
  
```
bool Revert(HANDLE hThread = NULL) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hThread`  
 Дескриптор потока для возврата из олицетворения. Если *hThread* имеет значение NULL, подразумевается текущий поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Изменения версии маркеры олицетворения может производиться автоматически с [CAutoRevertImpersonation класса](../../atl/reference/cautorevertimpersonation-class.md).  
  
##  <a name="a-namesetdefaultdacla--caccesstokensetdefaultdacl"></a><a name="setdefaultdacl"></a>CAccessToken::SetDefaultDacl  
 Этот метод по умолчанию список DACL `CAccessToken` объекта.  
  
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
  
##  <a name="a-namesetownera--caccesstokensetowner"></a><a name="setowner"></a>CAccessToken::SetOwner  
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
 Владелец является владельцем по умолчанию, используемый для новых объектов, созданных при этом маркер доступа.  
  
##  <a name="a-namesetprimarygroupa--caccesstokensetprimarygroup"></a><a name="setprimarygroup"></a>CAccessToken::SetPrimaryGroup  
 Вызовите этот метод, чтобы задать основной группы `CAccessToken` объекта.  
  
```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 [Класс CSid](../../atl/reference/csid-class.md) объект, содержащий данные основной группы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Основная группа имеет группу по умолчанию для новых объектов, созданных при этом маркер доступа.  
  
## <a name="see-also"></a>См. также  
 [Пример ATLSecurity](../../visual-cpp-samples.md)   
 [Токены доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

