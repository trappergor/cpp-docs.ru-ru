---
title: "CAtlModuleT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlModuleT<T>"
  - "ATL.CAtlModuleT"
  - "ATL.CAtlModuleT<T>"
  - "ATL::CAtlModuleT"
  - "CAtlModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlModuleT class"
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует модуль библиотеки ATL.  
  
## Синтаксис  
  
```  
  
      template <  
   class T   
>   
class ATL_NO_VTABLE CAtlModuleT :  
   public CAtlModule  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `CAtlModuleT`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlModuleT::CAtlModuleT](../Topic/CAtlModuleT::CAtlModuleT.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlModuleT::InitLibId](../Topic/CAtlModuleT::InitLibId.md)|Инициализирует элемент данных, содержащий идентификатор GUID текущего модуля.|  
|[CAtlModuleT::RegisterAppId](../Topic/CAtlModuleT::RegisterAppId.md)|Добавляет EXE в реестр.|  
|[CAtlModuleT::RegisterServer](../Topic/CAtlModuleT::RegisterServer.md)|Добавляет службу в реестр.|  
|[CAtlModuleT::UnregisterAppId](../Topic/CAtlModuleT::UnregisterAppId.md)|Удаляет EXE из реестра.|  
|[CAtlModuleT::UnregisterServer](../Topic/CAtlModuleT::UnregisterServer.md)|Удаляет службу из реестра.|  
|[CAtlModuleT::UpdateRegistryAppId](../Topic/CAtlModuleT::UpdateRegistryAppId.md)|Обновляет данные EXE в реестре.|  
  
## Заметки  
 `CAtlModuleT`, который является производным от [CAtlModule](../../atl/reference/catlmodule-class.md) реализует исполняемый файл \(EXE\) или модуль библиотеки ATL службы \(EXE\).  Исполняемый модуль локальный сервер вне процесса, в то время как модуль размещения windows\-приложения, которое выполняется в фоновом режиме при запуске Windows.  
  
 `CAtlModuleT` обеспечивает поддержку инициализации, регистрации и отмены регистрации модуля.  
  
## Иерархия наследования  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [CAtlModule Class](../../atl/reference/catlmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Модульные классы](../Topic/ATL%20Module%20Classes.md)