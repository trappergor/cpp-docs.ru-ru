---
title: "ISupportErrorInfoImpl Class | Microsoft Docs"
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
  - "ATL::ISupportErrorInfoImpl<piid>"
  - "ATL::ISupportErrorInfoImpl"
  - "ISupportErrorInfoImpl"
  - "ATL.ISupportErrorInfoImpl<piid>"
  - "ATL.ISupportErrorInfoImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error information, ATL - библиотека"
  - "ISupportErrorInfo ATL implementation"
  - "ISupportErrorInfoImpl class"
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ISupportErrorInfoImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет реализацию по умолчанию [ISupportErrorInfo Interface](http://msdn.microsoft.com/ru-ru/42d33066-36b4-4a5b-aa5d-46682e560f32) и может использоваться, только если один интерфейс формирует ошибки для объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template<  
const IID* piid   
>  
class ATL_NO_VTABLE ISupportErrorInfoImpl :  
public ISupportErrorInfo  
```  
  
#### Параметры  
 `piid`  
 Указатель на идентификатор IID интерфейса, который поддерживает [IErrorInfo](http://msdn.microsoft.com/ru-ru/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](../Topic/ISupportErrorInfoImpl::InterfaceSupportsErrorInfo.md)|Указывает, поддерживает ли указанный интерфейс `riid` интерфейс [IErrorInfo](http://msdn.microsoft.com/ru-ru/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).|  
  
## Заметки  
 [ISupportErrorInfo Interface](http://msdn.microsoft.com/ru-ru/42d33066-36b4-4a5b-aa5d-46682e560f32) гарантирует, что сведения об ошибке могут быть возвращены клиенту.  Объекты, использующие **IErrorInfo**, должны реализовывать **ISupportErrorInfo**.  
  
 Класс `ISupportErrorInfoImpl` предоставляет реализацию по умолчанию **ISupportErrorInfo** и может использоваться, только если один интерфейс формирует ошибки для объекта.  Примеры.  
  
 [!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/CPP/isupporterrorinfoimpl-class_1.h)]  
  
## Иерархия наследования  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)