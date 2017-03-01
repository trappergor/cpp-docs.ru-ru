---
title: "Глобальные функции идентификатор безопасности | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9e51fe30b0519514df34f1a77b1e731f51047520
ms.lasthandoff: 02/24/2017

---
# <a name="security-identifier-global-functions"></a>Глобальные функции идентификатор безопасности
Эти функции возвращают объекты общих хорошо известного SID.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

##  <a name="a-nameaccountopsa--sidsaccountops"></a><a name="accountops"></a>SIDs::AccountOps  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ACCOUNT_OPS.    
  
```
CSid AccountOps() throw(...);
```  
  
##  <a name="a-nameadminsa--sidsadmins"></a><a name="admins"></a>SIDs::Admins  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_ADMINS.  
```
CSid Admins() throw(...);
```  
  
##  <a name="a-nameanonymouslogona--sidsanonymouslogon"></a><a name="anonymouslogon"></a>SIDs::AnonymousLogon  
 Возвращает идентификатор безопасности SECURITY_ANONYMOUS_LOGON_RID.  
```
CSid AnonymousLogon() throw(...);
```  
  
##  <a name="a-nameauthenticatedusera--sidsauthenticateduser"></a><a name="authenticateduser"></a>SIDs::AuthenticatedUser  
 Возвращает идентификатор безопасности SECURITY_AUTHENTICATED_USER_RID.  
```
CSid AuthenticatedUser() throw(...);
```  
  
##  <a name="a-namebackupopsa--sidsbackupops"></a><a name="backupops"></a>SIDs::BackupOps  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_BACKUP_OPS.  
```
CSid BackupOps() throw(...);
```  
  
##  <a name="a-namebatcha--sidsbatch"></a><a name="batch"></a>SIDs::Batch  
 Возвращает идентификатор безопасности SECURITY_BATCH_RID.  
```
CSid Batch() throw(...);
```  
  
##  <a name="a-namecreatorgroupa--sidscreatorgroup"></a><a name="creatorgroup"></a>SIDs::CreatorGroup  
 Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_RID.  
```
CSid CreatorGroup() throw(...);
```  
  
##  <a name="a-namecreatorgroupservera--sidscreatorgroupserver"></a><a name="creatorgroupserver"></a>SIDs::CreatorGroupServer  
 Возвращает идентификатор безопасности SECURITY_CREATOR_GROUP_SERVER_RID.  
```
CSid CreatorGroupServer() throw(...);
```  
  
##  <a name="a-namecreatorownera--sidscreatorowner"></a><a name="creatorowner"></a>SIDs::CreatorOwner  
 Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_RID.  
```
CSid CreatorOwner() throw(...);
```  
  
##  <a name="a-namecreatorownerservera--sidscreatorownerserver"></a><a name="creatorownerserver"></a>SIDs::CreatorOwnerServer  
 Возвращает идентификатор безопасности SECURITY_CREATOR_OWNER_SERVER_RID.  
```
CSid CreatorOwnerServer() throw(...);
```  
  
##  <a name="a-namedialupa--sidsdialup"></a><a name="dialup"></a>SIDs::Dialup  
 Возвращает идентификатор безопасности SECURITY_DIALUP_RID.  
```
CSid Dialup() throw(...);
```  
  
##  <a name="a-nameguestsa--sidsguests"></a><a name="guests"></a>SIDs::Guests  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_GUESTS.  
```
CSid Guests() throw(...);
```  
  
##  <a name="a-nameinteractivea--sidsinteractive"></a><a name="interactive"></a>SIDs::Interactive  
 Возвращает идентификатор безопасности SECURITY_INTERACTIVE_RID.  
```
CSid Interactive() throw(...);
```  
  
##  <a name="a-namelocala--sidslocal"></a><a name="local"></a>SIDs::Local  
 Возвращает идентификатор безопасности SECURITY_LOCAL_RID.  
```
CSid Local() throw(...);
```  
  
##  <a name="a-namenetworka--sidsnetwork"></a><a name="network"></a>SIDs::Network  
 Возвращает идентификатор безопасности SECURITY_NETWORK_RID.  
```
CSid Network() throw(...);
```  
  
##  <a name="a-namenetworkservicea--sidsnetworkservice"></a><a name="networkservice"></a>SIDs::NetworkService  
 Возвращает идентификатор безопасности SECURITY_NETWORK_SERVICE_RID.  
```
CSid NetworkService() throw(...);
```  
  
### <a name="remarks"></a>Примечания  
 Используйте NetworkService для предоставления пользователю прав на чтение объекта безопасности CPerfMon NT AUTHORITY\NetworkService. Сетевая служба добавляет SecurityAttribute ATLServer кода, которая позволит DLL для входа в систему под учетной записью NetworkService на [!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)] и больше операционной системы.  
  
 При создании пользовательского журнала счетчиков с классом ATLServer CPerfMon в Perfmon MMC счетчики могут не отображаться при просмотре файла журнала, несмотря на то, что они будут правильно отображаться в режиме реального времени. CPerfMon пользовательские счетчики производительности нет необходимых разрешений для запуска службы «Оповещения и журналы производительности» (smlogsvc.exe) [!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)] (или выше) операционных систем. Эта служба работает под учетной записью «NT AUTHORITY\NetworkService».  
  
##  <a name="a-namenulla--sidsnull"></a><a name="null"></a>SIDs::NULL  
 Возвращает идентификатор безопасности SECURITY_NULL_RID.  
```
CSid Null() throw(...);
```  
  
##  <a name="a-nameprew2kaccessa--sidsprew2kaccess"></a><a name="prew2kaccess"></a>SIDs::PreW2KAccess  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PREW2KCOMPACCESS.  
```
CSid PreW2KAccess() throw(...);
```  
  
##  <a name="a-namepowerusersa--sidspowerusers"></a><a name="powerusers"></a>SIDs::PowerUsers  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_POWER_USERS.  
```
CSid PowerUsers() throw(...);
```  
  
##  <a name="a-nameprintopsa--sidsprintops"></a><a name="printops"></a>SIDs::PrintOps  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_PRINT_OPS.  
```
CSid PrintOps() throw(...);
```  
  
##  <a name="a-nameproxya--sidsproxy"></a><a name="proxy"></a>SIDs::Proxy  
 Возвращает идентификатор безопасности SECURITY_PROXY_RID.  
```
CSid Proxy() throw(...);
```  
  
##  <a name="a-namerasserversa--sidsrasservers"></a><a name="rasservers"></a>SIDs::RasServers  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_RAS_SERVERS.  
```
CSid RasServers() throw(...);
```  
  
##  <a name="a-namereplicatora--sidsreplicator"></a><a name="replicator"></a>SIDs::Replicator  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_REPLICATOR.  
```
CSid Replicator() throw(...);
```  
  
##  <a name="a-namerestrictedcodea--sidsrestrictedcode"></a><a name="restrictedcode"></a>SIDs::RestrictedCode  
 Возвращает идентификатор безопасности SECURITY_RESTRICTED_CODE_RID.  
```
CSid RestrictedCode() throw(...);
```  
  
##  <a name="a-nameselfa--sidsself"></a><a name="self"></a>SIDs::SELF  
 Возвращает идентификатор безопасности SECURITY_PRINCIPAL_SELF_RID.  
```
CSid Self() throw(...);
```  
  
##  <a name="a-nameserverlogona--sidsserverlogon"></a><a name="serverlogon"></a>SIDs::ServerLogon  
 Возвращает идентификатор безопасности SECURITY_SERVER_LOGON_RID.  
```
CSid ServerLogon() throw(...);
```  
  
##  <a name="a-nameservicea--sidsservice"></a><a name="service"></a>SIDs::Service  
 Возвращает идентификатор безопасности SECURITY_SERVICE_RID.  
```
CSid Service() throw(...);
```  
  
##  <a name="a-namesystema--sidssystem"></a><a name="system"></a>SIDs::System  
 Возвращает идентификатор безопасности SECURITY_LOCAL_SYSTEM_RID.  
```
CSid System() throw(...);
```  
  
##  <a name="a-namesystemopsa--sidssystemops"></a><a name="systemops"></a>SIDs::SystemOps  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_SYSTEM_OPS.  
```
CSid SystemOps() throw(...);
```  
  
##  <a name="a-nameterminalservera--sidsterminalserver"></a><a name="terminalserver"></a>SIDs::TerminalServer  
 Возвращает идентификатор безопасности SECURITY_TERMINAL_SERVER_RID.  
```
CSid TerminalServer() throw(...);
```  
  
##  <a name="a-nameusersa--sidsusers"></a><a name="users"></a>SIDs::Users  
 Возвращает идентификатор безопасности DOMAIN_ALIAS_RID_USERS.  
```
CSid Users() throw(...);
```  
  
##  <a name="a-nameworlda--sidsworld"></a><a name="world"></a>SIDs::World  
 Возвращает идентификатор безопасности SECURITY_WORLD_RID.  
```
CSid World() throw(...);
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)

