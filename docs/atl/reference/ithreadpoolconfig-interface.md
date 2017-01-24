---
title: "IThreadPoolConfig Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IThreadPoolConfig"
  - "ATL::IThreadPoolConfig"
  - "ATL.IThreadPoolConfig"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadPoolConfig interface"
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IThreadPoolConfig Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот интерфейс предоставляет методы для настройки пула потоков.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      __interface  
__declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660"))  
IThreadPoolConfig :  
public IUnknown  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[GetSize](../Topic/IThreadPoolConfig::GetSize.md)|Вызовите этот метод, чтобы получить количество потоков в пуле.|  
|[GetTimeout](../Topic/IThreadPoolConfig::GetTimeout.md)|Вызывайте этот метод для получения максимальное время, в миллисекундах, что пул потоков ожидает поток для закрытия.|  
|[SetSize](../Topic/IThreadPoolConfig::SetSize.md)|Вызывайте этот метод для задания количества потоков в пуле.|  
|[SetTimeout](../Topic/IThreadPoolConfig::SetTimeout.md)|Вызовите этот метод, чтобы установить максимальное время, в миллисекундах, что пул потоков ожидает поток для закрытия.|  
  
## Заметки  
 Этот интерфейс реализуется [CThreadPool](../Topic/CThreadPool%20Class.md).  
  
## Требования  
 **Header:** atlutil.h  
  
## См. также  
 [Классы](../../atl/reference/atl-classes.md)   
 [CThreadPool Class](../Topic/CThreadPool%20Class.md)