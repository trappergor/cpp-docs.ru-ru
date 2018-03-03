---
title: "Глобальные функции идентификатор безопасности | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6975b6b73c6d81fc9347a2395cd36747ce235b2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="security-identifier-global-functions"></a>Глобальные функции идентификатор безопасности
Эти функции возвращают общих хорошо известного SID объектов.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[SIDs::AccountOps](#accountops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ACCOUNT_OPS.|  
|[SIDs::Admins](#admins)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ADMINS.|  
|[SIDs::AnonymousLogon](#anonymouslogon)|Возвращает идентификатор безопасности SECURITY_ANONYMOUS_LOGON_RID.|  
|[SIDs::AuthenticatedUser](#authenticateduser)|Возвращает идентификатор безопасности SECURITY_AUTHENTICATED_USER_RID.|  
|[SIDs::BackupOps](#backupops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_BACKUP_OPS.|  
|[SIDs::Batch](#batch)|Возвращает идентификатор безопасности SECURITY_BATCH_RID.|  
|[SIDs::CreatorGroup](#creatorgroup)|Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_RID.|  
|[SIDs::CreatorGroupServer](#creatorgroupserver)|Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_SERVER_RID.|  
|[SIDs::CreatorOwner](#creatorowner)|Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_RID.|  
|[SIDs::CreatorOwnerServer](#creatorownerserver)|Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_SERVER_RID.|  
|[SIDs::Dialup](#dialup)|Возвращает идентификатор безопасности SECURITY_DIALUP_RID.|  
|[SIDs::Guests](#guests)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_GUESTS.|  
|[SIDs::Interactive](#interactive)|Возвращает идентификатор безопасности SECURITY_INTERACTIVE_RID.|  
|[SIDs::Local](#local)|Возвращает идентификатор безопасности SECURITY_LOCAL_RID.|  
|[SIDs::Network](#network)|Возвращает идентификатор безопасности SECURITY_NETWORK_RID.|  
|[SIDs::NetworkService](#networkservice)|Возвращает идентификатор безопасности SECURITY_NETWORK_SERVICE_RID.|  
|[SIDs::NULL](#null)|Возвращает идентификатор безопасности SECURITY_NULL_RID.|  
|[SIDs::PreW2KAccess](#prew2kaccess)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PREW2KCOMPACCESS.|  
|[SIDs::PowerUsers](#powerusers)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_POWER_USERS.|  
|[SIDs::PrintOps](#printops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PRINT_OPS.|  
|[SIDs::Proxy](#proxy)|Возвращает идентификатор безопасности SECURITY_PROXY_RID.|  
|[SIDs::RasServers](#rasservers)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_RAS_SERVERS.|  
|[SIDs::Replicator](#replicator)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_REPLICATOR.|  
|[SIDs::RestrictedCode](#restrictedcode)|Возвращает идентификатор безопасности SECURITY_RESTRICTED_CODE_RID.|  
|[SIDs::SELF](#self)|Возвращает идентификатор безопасности SECURITY_PRINCIPAL_SELF_RID.|  
|[SIDs::ServerLogon](#serverlogon)|Возвращает идентификатор безопасности SECURITY_SERVER_LOGON_RID.|  
|[SIDs::Service](#service)|Возвращает идентификатор безопасности SECURITY_SERVICE_RID.|  
|[SIDs::System](#system)|Возвращает идентификатор безопасности SECURITY_LOCAL_SYSTEM_RID.|  
|[SIDs::SystemOps](#systemops)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_SYSTEM_OPS.|  
|[SIDs::TerminalServer](#terminalserver)|Возвращает идентификатор безопасности SECURITY_TERMINAL_SERVER_RID.|  
|[SIDs::Users](#users)|Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_USERS.|  
|[SIDs::World](#world)|Возвращает идентификатор безопасности SECURITY_WORLD_RID.|  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h 

##  <a name="accountops"></a>SIDs::AccountOps  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ACCOUNT_OPS.    
  
```
CSid AccountOps() throw(...);
```  
  
##  <a name="admins"></a>SIDs::Admins  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ADMINS.  
```
CSid Admins() throw(...);
```  
  
##  <a name="anonymouslogon"></a>SIDs::AnonymousLogon  
 Возвращает идентификатор безопасности SECURITY_ANONYMOUS_LOGON_RID.  
```
CSid AnonymousLogon() throw(...);
```  
  
##  <a name="authenticateduser"></a>SIDs::AuthenticatedUser  
 Возвращает идентификатор безопасности SECURITY_AUTHENTICATED_USER_RID.  
```
CSid AuthenticatedUser() throw(...);
```  
  
##  <a name="backupops"></a>SIDs::BackupOps  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_BACKUP_OPS.  
```
CSid BackupOps() throw(...);
```  
  
##  <a name="batch"></a>SIDs::Batch  
 Возвращает идентификатор безопасности SECURITY_BATCH_RID.  
```
CSid Batch() throw(...);
```  
  
##  <a name="creatorgroup"></a>SIDs::CreatorGroup  
 Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_RID.  
```
CSid CreatorGroup() throw(...);
```  
  
##  <a name="creatorgroupserver"></a>SIDs::CreatorGroupServer  
 Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_SERVER_RID.  
```
CSid CreatorGroupServer() throw(...);
```  
  
##  <a name="creatorowner"></a>SIDs::CreatorOwner  
 Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_RID.  
```
CSid CreatorOwner() throw(...);
```  
  
##  <a name="creatorownerserver"></a>SIDs::CreatorOwnerServer  
 Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_SERVER_RID.  
```
CSid CreatorOwnerServer() throw(...);
```  
  
##  <a name="dialup"></a>SIDs::Dialup  
 Возвращает идентификатор безопасности SECURITY_DIALUP_RID.  
```
CSid Dialup() throw(...);
```  
  
##  <a name="guests"></a>SIDs::Guests  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_GUESTS.  
```
CSid Guests() throw(...);
```  
  
##  <a name="interactive"></a>SIDs::Interactive  
 Возвращает идентификатор безопасности SECURITY_INTERACTIVE_RID.  
```
CSid Interactive() throw(...);
```  
  
##  <a name="local"></a>SIDs::Local  
 Возвращает идентификатор безопасности SECURITY_LOCAL_RID.  
```
CSid Local() throw(...);
```  
  
##  <a name="network"></a>SIDs::Network  
 Возвращает идентификатор безопасности SECURITY_NETWORK_RID.  
```
CSid Network() throw(...);
```  
  
##  <a name="networkservice"></a>SIDs::NetworkService  
 Возвращает идентификатор безопасности SECURITY_NETWORK_SERVICE_RID.  
```
CSid NetworkService() throw(...);
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы включить пользователя NT AUTHORITY\NetworkService для чтения объект безопасности CPerfMon выполните NetworkService. Сетевая служба добавляет SecurityAttribute ATLServer код, который позволит DLL для входа в систему под учетной записью NetworkService на [!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)] и больше операционной системы.  
  
 При создании пользовательского журнала счетчиков с помощью класса ATLServer CPerfMon в Perfmon MMC счетчики могут не отображаться при просмотре файла журнала, несмотря на то, что они будут правильно отображаться в режиме реального времени. CPerfMon пользовательские счетчики производительности не имеет необходимых разрешений для запуска от имени службы «Оповещения и журналы производительности» (smlogsvc.exe) [!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)] (или более поздней) операционных систем. Эта служба работает под учетной записью «NT AUTHORITY\NetworkService».  
  
##  <a name="null"></a>SIDs::NULL  
 Возвращает идентификатор безопасности SECURITY_NULL_RID.  
```
CSid Null() throw(...);
```  
  
##  <a name="prew2kaccess"></a>SIDs::PreW2KAccess  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PREW2KCOMPACCESS.  
```
CSid PreW2KAccess() throw(...);
```  
  
##  <a name="powerusers"></a>SIDs::PowerUsers  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_POWER_USERS.  
```
CSid PowerUsers() throw(...);
```  
  
##  <a name="printops"></a>SIDs::PrintOps  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PRINT_OPS.  
```
CSid PrintOps() throw(...);
```  
  
##  <a name="proxy"></a>SIDs::Proxy  
 Возвращает идентификатор безопасности SECURITY_PROXY_RID.  
```
CSid Proxy() throw(...);
```  
  
##  <a name="rasservers"></a>SIDs::RasServers  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_RAS_SERVERS.  
```
CSid RasServers() throw(...);
```  
  
##  <a name="replicator"></a>SIDs::Replicator  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_REPLICATOR.  
```
CSid Replicator() throw(...);
```  
  
##  <a name="restrictedcode"></a>SIDs::RestrictedCode  
 Возвращает идентификатор безопасности SECURITY_RESTRICTED_CODE_RID.  
```
CSid RestrictedCode() throw(...);
```  
  
##  <a name="self"></a>SIDs::SELF  
 Возвращает идентификатор безопасности SECURITY_PRINCIPAL_SELF_RID.  
```
CSid Self() throw(...);
```  
  
##  <a name="serverlogon"></a>SIDs::ServerLogon  
 Возвращает идентификатор безопасности SECURITY_SERVER_LOGON_RID.  
```
CSid ServerLogon() throw(...);
```  
  
##  <a name="service"></a>SIDs::Service  
 Возвращает идентификатор безопасности SECURITY_SERVICE_RID.  
```
CSid Service() throw(...);
```  
  
##  <a name="system"></a>SIDs::System  
 Возвращает идентификатор безопасности SECURITY_LOCAL_SYSTEM_RID.  
```
CSid System() throw(...);
```  
  
##  <a name="systemops"></a>SIDs::SystemOps  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_SYSTEM_OPS.  
```
CSid SystemOps() throw(...);
```  
  
##  <a name="terminalserver"></a>SIDs::TerminalServer  
 Возвращает идентификатор безопасности SECURITY_TERMINAL_SERVER_RID.  
```
CSid TerminalServer() throw(...);
```  
  
##  <a name="users"></a>SIDs::Users  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_USERS.  
```
CSid Users() throw(...);
```  
  
##  <a name="world"></a>SIDs::World  
 Возвращает идентификатор безопасности SECURITY_WORLD_RID.  
```
CSid World() throw(...);
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
