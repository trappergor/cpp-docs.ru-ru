---
title: "CAtlModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlModule"
  - "CAtlModule"
  - "ATL.CAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlModule class"
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы, используемые несколькими классами модуля библиотеки ATL.  
  
## Синтаксис  
  
```  
  
   class ATL_NO_VTABLE CAtlModule :  
public _ATL_MODULE  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlModule::CAtlModule](../Topic/CAtlModule::CAtlModule.md)|Конструктор.|  
|[CAtlModule::~CAtlModule](../Topic/CAtlModule::~CAtlModule.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlModule::AddCommonRGSReplacements](../Topic/CAtlModule::AddCommonRGSReplacements.md)|Переопределите этот метод, чтобы добавить параметры к сопоставлению замены реестра библиотеки ATL \(регистратор\) компонента.|  
|[CAtlModule::AddTermFunc](../Topic/CAtlModule::AddTermFunc.md)|Добавляет новую функцию, вызываемый при завершении модуль.|  
|[CAtlModule::GetGITPtr](../Topic/CAtlModule::GetGITPtr.md)|Возвращает глобальный указатель интерфейса.|  
|[CAtlModule::GetLockCount](../Topic/CAtlModule::GetLockCount.md)|Возвращает количество блокировок.|  
|[CAtlModule::Lock](../Topic/CAtlModule::Lock.md)|Увеличивает число блокировок.|  
|[CAtlModule::Term](../Topic/CAtlModule::Term.md)|Освобождает все элементы данных.|  
|[CAtlModule::Unlock](../Topic/CAtlModule::Unlock.md)|Уменьшает на единицу счетчик блокировок.|  
|[CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md)|Запускает скрипт, содержащегося в указанном ресурсе для регистрации и отмены регистрации объект.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](../Topic/CAtlModule::UpdateRegistryFromResourceDHelper.md)|Этот метод вызывается `UpdateRegistryFromResourceD` выполнить обновление реестра.|  
|[CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md)|Запускает скрипт, содержащегося в указанном ресурсе для регистрации и отмены регистрации объект.  Этот метод является статически скомпонована в компонент реестра библиотеки ATL.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlModule::m\_libid](../Topic/CAtlModule::m_libid.md)|Содержит идентификатор GUID текущего модуля.|  
|[CAtlModule::m\_pGIT](../Topic/CAtlModule::m_pGIT.md)|Указатель на глобальную таблице интерфейса.|  
  
## Заметки  
 Этот класс используется [класс CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md), [класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md) и [класс CAtlServiceModuleT](../Topic/CAtlServiceModuleT%20Class.md) для обеспечения поддержки приложений DLL и EXE приложений служб Windows соответственно.  
  
 Дополнительные сведения о модулях в библиотеке ATL см. в разделе [Классы модуля библиотеки ATL](../Topic/ATL%20Module%20Classes.md).  
  
 Этот класс заменяет устаревший [класс CComModule](../../atl/reference/ccommodule-class.md), используемое в более ранних версиях библиотеки ATL.  
  
## Иерархия наследования  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 `CAtlModule`  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Модульные классы](../Topic/ATL%20Module%20Classes.md)   
 [Компонент реестра \(регистратор\)](../../atl/atl-registry-component-registrar.md)