---
title: Идентификатор безопасности Глобальные функции
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::Sids::AccountOps
- atlsecurity/ATL::Sids::Admins
- atlsecurity/ATL::Sids::AnonymousLogon
- atlsecurity/ATL::Sids::AuthenticatedUser
- atlsecurity/ATL::Sids::BackupOps
- atlsecurity/ATL::Sids::Batch
- atlsecurity/ATL::Sids::CreatorGroup
- atlsecurity/ATL::Sids::CreatorGroupServer
- atlsecurity/ATL::Sids::CreatorOwner
- atlsecurity/ATL::Sids::CreatorOwnerServer
- atlsecurity/ATL::Sids::Dialup
- atlsecurity/ATL::Sids::Guests
- atlsecurity/ATL::Sids::Interactive
- atlsecurity/ATL::Sids::Local
- atlsecurity/ATL::Sids::Network
- atlsecurity/ATL::Sids::NetworkService
- atlsecurity/ATL::Sids::Null
- atlsecurity/ATL::Sids::PowerUsers
- atlsecurity/ATL::Sids::PrintOps
- atlsecurity/ATL::Sids::Proxy
- atlsecurity/ATL::Sids::RasServers
- atlsecurity/ATL::Sids::Replicator
- atlsecurity/ATL::Sids::RestrictedCode
- atlsecurity/ATL::Sids::Self
- atlsecurity/ATL::Sids::ServerLogon
- atlsecurity/ATL::Sids::Service
- atlsecurity/ATL::Sids::System
- atlsecurity/ATL::Sids::SystemOps
- atlsecurity/ATL::Sids::TerminalServer
- atlsecurity/ATL::Sids::Users
- atlsecurity/ATL::Sids::World
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
ms.openlocfilehash: 83326c13de7585806ab841f728f587f1131b5e8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325993"
---
# <a name="security-identifier-global-functions"></a>Идентификатор безопасности Глобальные функции

Эти функции возвращают общеизвестные объекты SID.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, не могут использоваться в приложениях, выполняемых в Windows Runtime.

|||
|-|-|
|[Sids::AccountOps](#accountops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ACCOUNT_OPS.|
|[Sids::Admins](#admins)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ADMINS.|
|[Sids::AnonymousLogon](#anonymouslogon)|Возвращает идентификатор безопасности SECURITY_ANONYMOUS_LOGON_RID.|
|[Sids::AuthenticatedUser](#authenticateduser)|Возвращает идентификатор безопасности SECURITY_AUTHENTICATED_USER_RID.|
|[Sids::BackupOps](#backupops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_BACKUP_OPS.|
|[Sids::Batch](#batch)|Возвращает идентификатор безопасности SECURITY_BATCH_RID.|
|[Sids::CreatorGroup](#creatorgroup)|Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_RID.|
|[Sids::CreatorGroupServer](#creatorgroupserver)|Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_SERVER_RID.|
|[Sids::CreatorOwner](#creatorowner)|Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_RID.|
|[Sids::CreatorOwnerServer](#creatorownerserver)|Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_SERVER_RID.|
|[Sids::Dialup](#dialup)|Возвращает идентификатор безопасности SECURITY_DIALUP_RID.|
|[Sids::Guests](#guests)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_GUESTS.|
|[Sids::Interactive](#interactive)|Возвращает идентификатор безопасности SECURITY_INTERACTIVE_RID.|
|[Sids::Local](#local)|Возвращает идентификатор безопасности SECURITY_LOCAL_RID.|
|[Sids::Network](#network)|Возвращает идентификатор безопасности SECURITY_NETWORK_RID.|
|[Sids::NetworkService](#networkservice)|Возвращает идентификатор безопасности SECURITY_NETWORK_SERVICE_RID.|
|[Sids::Null](#null)|Возвращает идентификатор безопасности SECURITY_NULL_RID.|
|[Sids::PreW2KAccess](#prew2kaccess)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PREW2KCOMPACCESS.|
|[Sids::PowerUsers](#powerusers)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_POWER_USERS.|
|[Sids::PrintOps](#printops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PRINT_OPS.|
|[Sids::Proxy](#proxy)|Возвращает идентификатор безопасности SECURITY_PROXY_RID.|
|[Sids::RasServers](#rasservers)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_RAS_SERVERS.|
|[Sids::Replicator](#replicator)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_REPLICATOR.|
|[Sids::RestrictedCode](#restrictedcode)|Возвращает идентификатор безопасности SECURITY_RESTRICTED_CODE_RID.|
|[Sids::Self](#self)|Возвращает идентификатор безопасности SECURITY_PRINCIPAL_SELF_RID.|
|[Sids::ServerLogon](#serverlogon)|Возвращает идентификатор безопасности SECURITY_SERVER_LOGON_RID.|
|[Sids::Service](#service)|Возвращает идентификатор безопасности SECURITY_SERVICE_RID.|
|[Sids::System](#system)|Возвращает идентификатор безопасности SECURITY_LOCAL_SYSTEM_RID.|
|[Sids::SystemOps](#systemops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_SYSTEM_OPS.|
|[Sids::TerminalServer](#terminalserver)|Возвращает идентификатор безопасности SECURITY_TERMINAL_SERVER_RID.|
|[Sids::Users](#users)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_USERS.|
|[Сиды::Мир](#world)|Возвращает идентификатор безопасности SECURITY_WORLD_RID.|

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="sidsaccountops"></a><a name="accountops"></a>Сиды::AccountOps

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ACCOUNT_OPS.

```
CSid AccountOps() throw(...);
```

## <a name="sidsadmins"></a><a name="admins"></a>Сиды::Админы

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ADMINS.

```
CSid Admins() throw(...);
```

## <a name="sidsanonymouslogon"></a><a name="anonymouslogon"></a>Сиды::АнонимныйЛог

Возвращает идентификатор безопасности SECURITY_ANONYMOUS_LOGON_RID.

```
CSid AnonymousLogon() throw(...);
```

## <a name="sidsauthenticateduser"></a><a name="authenticateduser"></a>Сиды::Аутентифицированный пользователь

Возвращает идентификатор безопасности SECURITY_AUTHENTICATED_USER_RID.

```
CSid AuthenticatedUser() throw(...);
```

## <a name="sidsbackupops"></a><a name="backupops"></a>Sids::BackupOps

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_BACKUP_OPS.

```
CSid BackupOps() throw(...);
```

## <a name="sidsbatch"></a><a name="batch"></a>Сиды::Batch

Возвращает идентификатор безопасности SECURITY_BATCH_RID.

```
CSid Batch() throw(...);
```

## <a name="sidscreatorgroup"></a><a name="creatorgroup"></a>Сиды::CreatorGroup

Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_RID.

```
CSid CreatorGroup() throw(...);
```

## <a name="sidscreatorgroupserver"></a><a name="creatorgroupserver"></a>Сиды:CreatorGroupServer

Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_SERVER_RID.

```
CSid CreatorGroupServer() throw(...);
```

## <a name="sidscreatorowner"></a><a name="creatorowner"></a>Сиды::СоздательВладелец

Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_RID.

```
CSid CreatorOwner() throw(...);
```

## <a name="sidscreatorownerserver"></a><a name="creatorownerserver"></a>Сиды::CreatorOwnerServer

Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_SERVER_RID.

```
CSid CreatorOwnerServer() throw(...);
```

## <a name="sidsdialup"></a><a name="dialup"></a>Сиды::Dialup

Возвращает идентификатор безопасности SECURITY_DIALUP_RID.

```
CSid Dialup() throw(...);
```

## <a name="sidsguests"></a><a name="guests"></a>Сиды::Гости

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_GUESTS.

```
CSid Guests() throw(...);
```

## <a name="sidsinteractive"></a><a name="interactive"></a>Сиды::Интерактивный

Возвращает идентификатор безопасности SECURITY_INTERACTIVE_RID.

```
CSid Interactive() throw(...);
```

## <a name="sidslocal"></a><a name="local"></a>Сиды::Местные

Возвращает идентификатор безопасности SECURITY_LOCAL_RID.

```
CSid Local() throw(...);
```

## <a name="sidsnetwork"></a><a name="network"></a>Сиды::Сеть

Возвращает идентификатор безопасности SECURITY_NETWORK_RID.

```
CSid Network() throw(...);
```

## <a name="sidsnetworkservice"></a><a name="networkservice"></a>Сиды::СетьСервис

Возвращает идентификатор безопасности SECURITY_NETWORK_SERVICE_RID.

```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>Remarks

Используйте NetworkService, чтобы пользователь NT AUTHORITY-NetworkService мог читать объект безопасности CPerfMon. NetworkService добавляет SecurityAttribute в код ATLServer, который позволит DLL войти под учетную запись NetworkService на Windows XP Home Edition, Windows XP Professional, Windows Server 2003 и большеоперационной операционной системы.

При создании пользовательских счетчиков журналов с классом ATLServer CPerfMon в Perfmon MMC счетчики могут не отображаться при просмотре файла журнала, хотя они будут отображаться правильно в представлении в реальном времени. Пользовательские счетчики производительности CPerfMon не имеют необходимых разрешений для работы в сервисе "Записи и оповещения" (smlogsvc.exe) на Windows XP Home Edition, Windows XP Professional, Windows Server 2003 (или больше) операционных систем. Эта услуга работает в соответствии с учетной записью "NT AUTHORITY-NetworkService".

## <a name="sidsnull"></a><a name="null"></a>Сиды::Null

Возвращает идентификатор безопасности SECURITY_NULL_RID.

```
CSid Null() throw(...);
```

## <a name="sidsprew2kaccess"></a><a name="prew2kaccess"></a>Сиды::PreW2KAccess

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PREW2KCOMPACCESS.

```
CSid PreW2KAccess() throw(...);
```

## <a name="sidspowerusers"></a><a name="powerusers"></a>Sids::PowerUsers

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_POWER_USERS.

```
CSid PowerUsers() throw(...);
```

## <a name="sidsprintops"></a><a name="printops"></a>Сиды::PrintOps

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PRINT_OPS.

```
CSid PrintOps() throw(...);
```

## <a name="sidsproxy"></a><a name="proxy"></a>Сиды::Proxy

Возвращает идентификатор безопасности SECURITY_PROXY_RID.

```
CSid Proxy() throw(...);
```

## <a name="sidsrasservers"></a><a name="rasservers"></a>Сиды::Рассерверы

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_RAS_SERVERS.

```
CSid RasServers() throw(...);
```

## <a name="sidsreplicator"></a><a name="replicator"></a>Сиды::Репликатор

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_REPLICATOR.

```
CSid Replicator() throw(...);
```

## <a name="sidsrestrictedcode"></a><a name="restrictedcode"></a>Сиды::Ограниченный код

Возвращает идентификатор безопасности SECURITY_RESTRICTED_CODE_RID.

```
CSid RestrictedCode() throw(...);
```

## <a name="sidsself"></a><a name="self"></a>Сиды::Self

Возвращает идентификатор безопасности SECURITY_PRINCIPAL_SELF_RID.

```
CSid Self() throw(...);
```

## <a name="sidsserverlogon"></a><a name="serverlogon"></a>Сиды::ServerLogon

Возвращает идентификатор безопасности SECURITY_SERVER_LOGON_RID.

```
CSid ServerLogon() throw(...);
```

## <a name="sidsservice"></a><a name="service"></a>Сиды::Сервис

Возвращает идентификатор безопасности SECURITY_SERVICE_RID.

```
CSid Service() throw(...);
```

## <a name="sidssystem"></a><a name="system"></a>Сиды::Система

Возвращает идентификатор безопасности SECURITY_LOCAL_SYSTEM_RID.

```
CSid System() throw(...);
```

## <a name="sidssystemops"></a><a name="systemops"></a>Сиды::SystemOps

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_SYSTEM_OPS.

```
CSid SystemOps() throw(...);
```

## <a name="sidsterminalserver"></a><a name="terminalserver"></a>Сиды::ТерминалСервер

Возвращает идентификатор безопасности SECURITY_TERMINAL_SERVER_RID.

```
CSid TerminalServer() throw(...);
```

## <a name="sidsusers"></a><a name="users"></a>Сиды::Пользователи

Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_USERS.

```
CSid Users() throw(...);
```

## <a name="sidsworld"></a><a name="world"></a>Сиды::Мир

Возвращает идентификатор безопасности SECURITY_WORLD_RID.

```
CSid World() throw(...);
```

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)
