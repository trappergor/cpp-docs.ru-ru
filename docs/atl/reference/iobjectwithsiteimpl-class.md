---
title: "IObjectWithSiteImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl<T>"
  - "IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl"
  - "ATL::IObjectWithSiteImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IObjectWithSiteImpl class"
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# IObjectWithSiteImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы при разрешении объекта для взаимодействия с сайтом.  
  
## Синтаксис  
  
```  
  
      template<  
   class T   
>  
class ATL_NO_VTABLE IObjectWithSiteImpl :  
   public IObjectWithSite  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IObjectWithSiteImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IObjectWithSiteImpl::GetSite](../Topic/IObjectWithSiteImpl::GetSite.md)|Запрашивает сайт для указателя интерфейса.|  
|[IObjectWithSiteImpl::SetChildSite](../Topic/IObjectWithSiteImpl::SetChildSite.md)|Предоставляет объект с указателем **IUnknown**  сайта.|  
|[IObjectWithSiteImpl::SetSite](../Topic/IObjectWithSiteImpl::SetSite.md)|Предоставляет объект с указателем **IUnknown** сайта.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[IObjectWithSiteImpl::m\_spUnkSite](../Topic/IObjectWithSiteImpl::m_spUnkSite.md)|Управляет указателем **IUnknown** сайта.|  
  
## Заметки  
 Интерфейс [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) позволяет объекту для взаимодействия с сайтом.  Класс `IObjectWithSiteImpl` предоставляет реализацию по умолчанию для интерфейса и реализуется **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 `IObjectWithSiteImpl` определяет 2 метода.  Клиент сначала вызывает `SetSite`, указав указатель **IUnknown** сайта.  Этот указатель хранится в объекте, а впоследствии извлечь через вызов `GetSite`.  
  
 Как правило, необходимо создать производный класс от `IObjectWithSiteImpl` при создании объекта, который не является элемента управления.  Для элементов управления, наследуйте класс от [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), который также предоставляет указатель сайта.  Не наследуйте класс из `IObjectWithSiteImpl`, так и из `IOleObjectImpl`.  
  
## Иерархия наследования  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)