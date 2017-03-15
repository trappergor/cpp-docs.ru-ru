---
title: "IPropertyNotifySinkCP Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPropertyNotifySinkCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "точки подключения [C++], управление"
  - "IPropertyNotifySinkCP class"
  - "sinks, notifying of changes"
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# IPropertyNotifySinkCP Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет интерфейс [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) как исходящий интерфейс на доступный для соединения объект.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template< class   
      T  
      , class  
      CDV   
      = CComDynamicUnkArray >  
class IPropertyNotifySinkCP :   
public IConnectionPointImpl< T, &IID_IPropertyNotifySink, CDV>  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IPropertyNotifySinkCP`.  
  
 `CDV`  
 Класс, который управляет связью между точка подключения и его приемники.  Значение по умолчанию [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md), который разрешает неограниченные соединения.  Можно также использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), задает фиксированное число подключений.  
  
## Заметки  
 `IPropertyNotifySinkCP` наследует все методы через базовый класс, [IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md).  
  
 Интерфейс [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) позволяет объекту получателя для получения уведомлений об изменениях свойств.  Класс `IPropertyNotifySinkCP` этот интерфейс предоставляет как исходящий интерфейс на доступный для соединения объект.  Клиент должен реализовать методы `IPropertyNotifySink` в приемник.  
  
 Создайте производный класс от `IPropertyNotifySinkCP`, когда нужно создать точку подключения, представляющий интерфейс `IPropertyNotifySink`.  
  
 Дополнительные сведения об использовании точек соединения в библиотеке ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [IConnectionPointImpl Class](../Topic/IConnectionPointImpl%20Class.md)   
 [IConnectionPointContainerImpl Class](../Topic/IConnectionPointContainerImpl%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)