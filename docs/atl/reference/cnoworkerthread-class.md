---
title: "CNoWorkerThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CNoWorkerThread"
  - "ATL.CNoWorkerThread"
  - "CNoWorkerThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoWorkerThread class"
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CNoWorkerThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс используется в качестве аргумента для параметра шаблона `MonitorClass` для кэширования классы в кэше если требуется отключить динамическое обслуживание кэша.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CNoWorkerThread  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CNoWorkerThread::AddHandle](../Topic/CNoWorkerThread::AddHandle.md)|Нефункциональное число [CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md).|  
|[CNoWorkerThread::AddTimer](../Topic/CNoWorkerThread::AddTimer.md)|Нефункциональное число [CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md).|  
|[CNoWorkerThread::GetThreadHandle](../Topic/CNoWorkerThread::GetThreadHandle.md)|Нефункциональное число [CWorkerThread::GetThreadHandle](../Topic/CWorkerThread::GetThreadHandle.md).|  
|[CNoWorkerThread::GetThreadId](../Topic/CNoWorkerThread::GetThreadId.md)|Нефункциональное число [CWorkerThread::GetThreadId](../Topic/CWorkerThread::GetThreadId.md).|  
|[CNoWorkerThread::Initialize](../Topic/CNoWorkerThread::Initialize.md)|Нефункциональное число [CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md).|  
|[CNoWorkerThread::RemoveHandle](../Topic/CNoWorkerThread::RemoveHandle.md)|Нефункциональное число [CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md).|  
|[CNoWorkerThread::Shutdown](../Topic/CNoWorkerThread::Shutdown.md)|Нефункциональное число [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md).|  
  
## Заметки  
 Этот класс предоставляет тот же общий интерфейс в качестве [CWorkerThread](../Topic/CWorkerThread%20Class.md).  Предполагается, что этот интерфейс реализуется параметром шаблона `MonitorClass` классы кэша.  
  
 Методы в этом классе реализованы не делать ничего.  Методы, возвращающие всегда возвращают S\_ОК HRESULT и методы, которые возвращают равен 0, всегда идентификатор ДЕСКРИПТОРА или потока.  
  
## Требования  
 **Header:** atlutil.h