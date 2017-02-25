---
title: "Registry and TypeLib Global Functions | Microsoft Docs"
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
  - "RegistryDataExchange function, глобальные функции"
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# Registry and TypeLib Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эти функции предоставляют поддержку для загрузки и зарегистрировать библиотеку типов.  
  
> [!IMPORTANT]
>  Функции, список которых приведен в следующих таблицах нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](../Topic/AtlRegisterTypeLib.md)|Эта функция называется, чтобы зарегистрировать библиотеку типов.|  
|[AtlUnRegisterTypeLib](../Topic/AtlUnRegisterTypeLib.md)|Эта функция называется для отмены регистрации библиотеки типов|  
|[AtlLoadTypeLib](../Topic/AtlLoadTypeLib.md)|Эта функция называется, чтобы загрузить библиотеку типов.|  
|[AtlUpdateRegistryFromResourceD](../Topic/AtlUpdateRegistryFromResourceD.md)|Эта функция называется, чтобы обновить реестр из указанного ресурса.|  
|[RegistryDataExchange](../Topic/RegistryDataExchange.md)|Эта функция называется для чтения или записи в реестре системы.  Вызываемый [макросы обмена данными реестра](../../atl/reference/registry-data-exchange-macros.md).|  
  
 Управление этих функций, узел в реестре программа использует для хранения сведений.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](../Topic/AtlGetPerUserRegistration.md)|Извлекает перенаправляет приложения доступ к реестру к узлу **HKEY\_CURRENT\_USER** \(**HKCU**\).|  
|[AtlSetPerUserRegistration](../Topic/AtlSetPerUserRegistration.md)|Наборы, доступна ли приложение к реестра в узел **HKEY\_CURRENT\_USER** \(**HKCU**\).|  
  
## См. также  
 [Функции](../../atl/reference/atl-functions.md)