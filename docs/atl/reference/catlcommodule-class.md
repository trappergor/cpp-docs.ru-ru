---
title: "CAtlComModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlComModule"
  - "CAtlComModule"
  - "ATL::CAtlComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlComModule class"
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlComModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует модуль сервера модели COM.  
  
## Синтаксис  
  
```  
  
   class CAtlComModule :  
public _ATL_COM_MODULE  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlComModule::CAtlComModule](../Topic/CAtlComModule::CAtlComModule.md)|Конструктор.|  
|[CAtlComModule::~CAtlComModule](../Topic/CAtlComModule::~CAtlComModule.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlComModule::RegisterServer](../Topic/CAtlComModule::RegisterServer.md)|Вызовите этот метод, чтобы обновить реестр системы для каждого объекта в сопоставлении объекта.|  
|[CAtlComModule::RegisterTypeLib](../Topic/CAtlComModule::RegisterTypeLib.md)|Вызовите этот метод, чтобы зарегистрировать библиотеку типов.|  
|[CAtlComModule::UnregisterServer](../Topic/CAtlComModule::UnregisterServer.md)|Вызовите этот метод, чтобы отменить регистрацию всех объектов в сопоставлении объекта.|  
|[CAtlComModule::UnRegisterTypeLib](../Topic/CAtlComModule::UnRegisterTypeLib.md)|Этот метод вызывается для отмены регистрации библиотекой типов.|  
  
## Заметки  
 `CAtlComModule` реализующий модуль сервера модели COM, что клиент для доступа к компонентам модуля.  
  
 Этот класс устарел [CComModule](../../atl/reference/ccommodule-class.md) заменяет класс, используемый в предыдущих версиях библиотеки ATL.  Дополнительные сведения см. в разделе [Классы модуля библиотеки ATL](../Topic/ATL%20Module%20Classes.md).  
  
## Иерархия наследования  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)  
  
 `CAtlComModule`  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)   
 [Class Overview](../../atl/atl-class-overview.md)