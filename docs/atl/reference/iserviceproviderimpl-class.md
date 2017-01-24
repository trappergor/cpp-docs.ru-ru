---
title: "IServiceProviderImpl Class | Microsoft Docs"
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
  - "ATL::IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl"
  - "ATL::IServiceProviderImpl"
  - "IServiceProviderImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IServiceProvider - интерфейс, ATL -реализация"
  - "IServiceProviderImpl class"
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IServiceProviderImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет реализацию по умолчанию для интерфейса `IServiceProvider`.  
  
## Синтаксис  
  
```  
  
      template <  
   class T  
>   
class ATL_NO_VTABLE IServiceProviderImpl :  
   public IServiceProvider  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IServiceProviderImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IServiceProviderImpl::QueryService](../Topic/IServiceProviderImpl::QueryService.md)|Создает или получает доступ к конкретной службе и возвращает указатель интерфейса на указанный интерфейс для службы.|  
  
## Заметки  
 Интерфейс `IServiceProvider` находящий службу, определенному его GUID и возвращает указатель интерфейса для запрашиваемого интерфейса на стороне службы.  Класс `IServiceProviderImpl` предоставляет реализацию по умолчанию для интерфейса.  
  
 **IServiceProviderImpl**  определяет один метод: [QueryService](../Topic/IServiceProviderImpl::QueryService.md), который создает или получает доступ к конкретной службе и возвращает указатель интерфейса на указанный интерфейс для службы.  
  
 `IServiceProviderImpl` использует сопоставление службы, начиная с [BEGIN\_SERVICE\_MAP](../Topic/BEGIN_SERVICE_MAP.md) и законцовкой с [END\_SERVICE\_MAP](../Topic/END_SERVICE_MAP.md).  
  
 Сопоставление службы содержащий 2 записей. [SERVICE\_ENTRY](../Topic/SERVICE_ENTRY.md), указывающее идентификатор конкретной службы \(sid\), поддерживаемых объектом, и [SERVICE\_ENTRY\_CHAIN](../Topic/SERVICE_ENTRY_CHAIN.md), который вызывает `QueryService` для привязан к другому объекту.  
  
## Иерархия наследования  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)