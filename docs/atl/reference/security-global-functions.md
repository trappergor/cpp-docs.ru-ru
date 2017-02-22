---
title: "Security Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ACL object global functions"
  - "security IDs [C++]"
  - "SIDs [C++], modifying SID objects"
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Security Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эти функции предоставляют поддержку для изменения объектов идентификатор безопасности и ACL.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlGetDacl](../Topic/AtlGetDacl.md)|Эта функция вызывается, чтобы получить данные списка управления доступом на уровне пользователей \(DACL\) указанного объекта.|  
|[AtlSetDacl](../Topic/AtlSetDacl.md)|Эта функция вызывается для задания сведений о список управления доступом на уровне пользователей \(DACL\) указанного объекта.|  
|[AtlGetGroupSid](../Topic/AtlGetGroupSid.md)|Эта функция вызывается, чтобы получить идентификатор безопасности группы \(sid\) объекта.|  
|[AtlSetGroupSid](../Topic/AtlSetGroupSid.md)|Эта функция вызывается, чтобы задать идентификатор безопасности группы \(sid\) объекта.|  
|[AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md)|Эта функция вызывается для получения идентификатора безопасности \(sid\) владелец объекта.|  
|[AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md)|Эта функция вызывается, чтобы задать идентификатор безопасности \(sid\) владелец объекта.|  
|[AtlGetSacl](../Topic/AtlGetSacl.md)|Эта функция вызывается для получения данных системного списка управления доступом \(sacl\) указанного объекта.|  
|[AtlSetSacl](../Topic/AtlSetSacl.md)|Эта функция вызывается, чтобы задать данные системного списка управления доступом \(sacl\) указанного объекта.|  
|[AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md)|Эта функция вызывается для получения дескриптора безопасности для данного объекта.|  
  
## См. также  
 [Функции](../../atl/reference/atl-functions.md)