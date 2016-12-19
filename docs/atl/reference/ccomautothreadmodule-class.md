---
title: "CComAutoThreadModule Class | Microsoft Docs"
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
  - "CComAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "apartment model modules"
  - "CComAutoThreadModule class"
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComAutoThreadModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Из библиотеки ATL 7,0, `CComAutoThreadModule` устарел. дополнительные сведения см. в разделе [Классы модуля библиотеки ATL](../Topic/ATL%20Module%20Classes.md).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
class ThreadAllocator= CComSimpleThreadAllocator   
>  
class CComAutoThreadModule :  
public CComModule  
```  
  
#### Параметры  
 `ThreadAllocator`  
 \[in\] Класс, выделение потока.  Значение по умолчанию [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CreateInstance](../Topic/CComAutoThreadModule::CreateInstance.md)|Выбирает поток, а затем создает объект в связанной подразделении.|  
|[GetDefaultThreads](../Topic/CComAutoThreadModule::GetDefaultThreads.md)|\(Статический\) Динамически вычисляет количество потоков для модуля на основе количества процессоров.|  
|[Init](../Topic/CComAutoThreadModule::Init.md)|Создает потоки модуля.|  
|[Блокировка](../Topic/CComAutoThreadModule::Lock.md)|Увеличивает возлагать жизни на блокировки модуля и в текущем потоке.|  
|[Unlock](../Topic/CComAutoThreadModule::Unlock.md)|Уменьшает возлагать жизни на блокировки модуля и в текущем потоке.|  
  
### Элементы данных  
  
### Элементы данных  
  
|||  
|-|-|  
|[dwThreadID](../Topic/CComAutoThreadModule::dwThreadID.md)|Содержит идентификатор текущего потока.|  
|[m\_Allocator](../Topic/CComAutoThreadModule::m_Allocator.md)|Выделение потока управления.|  
|[m\_nThreads](../Topic/CComAutoThreadModule::m_nThreads.md)|Содержит количество потоков в модуле.|  
|[m\_pApartments](../Topic/CComAutoThreadModule::m_pApartments.md)|Управляет подразделения модуля.|  
  
## Заметки  
  
> [!NOTE]
>  Этот класс устарел, заменимый производными классами [Класса CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) и [CAtlModule](../../atl/reference/catlmodule-class.md).  Сведения, которые следуют для использования с предыдущими версиями библиотеки ATL.  
  
 `CComAutoThreadModule` является производным от [CComModule](../../atl/reference/ccommodule-class.md) для реализации сервер поток\- вместе скложенный модель COM для изоляции служб Exe и Windows.  `CComAutoThreadModule` использует [CComApartment](../../atl/reference/ccomapartment-class.md) для управления подразделение для каждого потока в модуле.  
  
 Создайте модуль с `CComAutoThreadModule`, когда нужно создать объекты в нескольких подразделениях.  Необходимо также включить макрос [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) в определении класса объекта, чтобы определить [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрика класса.  
  
 По умолчанию модель COM AppWizard библиотеки ATL \(мастер проекта библиотеки ATL в Visual Studio .NET\) был производным от `CComModule` модуль.  Для использования `CComAutoThreadModule` измените определение класса.  Примеры.  
  
 [!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/CPP/ccomautothreadmodule-class_1.cpp)]  
  
## Иерархия наследования  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## Требования  
 **Header:**  atlbase.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Модульные классы](../Topic/ATL%20Module%20Classes.md)