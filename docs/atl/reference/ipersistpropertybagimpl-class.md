---
title: "IPersistPropertyBagImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPersistPropertyBagImpl"
  - "ATL.IPersistPropertyBagImpl<T>"
  - "ATL::IPersistPropertyBagImpl"
  - "ATL::IPersistPropertyBagImpl<T>"
  - "ATL.IPersistPropertyBagImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistPropertyBagImpl class"
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IPersistPropertyBagImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** и позволяет объекту сохранить его свойства в клиент\- предоставленным контейнер свойств.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template <   
class T   
>  
class ATL_NO_VTABLE IPersistPropertyBagImpl :  
public IPersistPropertyBag  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IPersistPropertyBagImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IPersistPropertyBagImpl::GetClassID](../Topic/IPersistPropertyBagImpl::GetClassID.md)|Извлекает идентификатор CLSID объекта.|  
|[IPersistPropertyBagImpl::InitNew](../Topic/IPersistPropertyBagImpl::InitNew.md)|Инициализирует только что созданный объект.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IPersistPropertyBagImpl::Load](../Topic/IPersistPropertyBagImpl::Load.md)|Загружает свойства объекта из клиент\- предоставленного контейнера свойств.|  
|[IPersistPropertyBagImpl::Save](../Topic/IPersistPropertyBagImpl::Save.md)|Сохраняет свойства объекта в клиент\- указанный контейнер свойства.|  
  
## Заметки  
 Интерфейс [IPersistPropertyBag](https://msdn.microsoft.com/en-us/library/aa768205.aspx) позволяет объекту сохранить его свойства в клиент\- предоставленным контейнер свойств.  Класс `IPersistPropertyBagImpl` предоставляет реализацию по умолчанию для интерфейса и реализуется **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 Рабочие **IPersistPropertyBag** совместно с [IPropertyBag](https://msdn.microsoft.com/en-us/library/aa768196.aspx) и [IErrorLog](https://msdn.microsoft.com/en-us/library/aa768231.aspx).  Эти последние 2 интерфейса должны быть реализованы клиентом.  С помощью `IPropertyBag` клиент сохраняет и загружает отдельные свойства объекта.  С помощью **IErrorLog**, и клиент может информировать объект и все, обнаруженные ошибки.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [BEGIN\_PROP\_MAP](../Topic/BEGIN_PROP_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)