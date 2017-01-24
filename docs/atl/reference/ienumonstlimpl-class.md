---
title: "IEnumOnSTLImpl Class | Microsoft Docs"
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
  - "IEnumOnSTLImpl"
  - "ATL.IEnumOnSTLImpl"
  - "ATL::IEnumOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IEnumOnSTLImpl class"
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IEnumOnSTLImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс определяет интерфейс перечислителя на основе коллекций STL.  
  
## Синтаксис  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType  
>  
class ATL_NO_VTABLE IEnumOnSTLImpl :  
   public Base  
```  
  
#### Параметры  
 `Base`  
 Интерфейс перечислителя модели COM \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\).  
  
 `piid`  
 Указатель на идентификатор интерфейса интерфейса перечислителя.  
  
 `T`  
 Тип элемента, предоставляемый интерфейсом перечислителя.  
  
 `Copy`  
 [класс политики копирования](../Topic/ATL%20Copy%20Policy%20Classes.md).  
  
 `CollType`  
 Класс контейнеров STL.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IEnumOnSTLImpl::Clone](../Topic/IEnumOnSTLImpl::Clone.md)|Реализация [IEnumXXXX::Clone](https://msdn.microsoft.com/en-us/library/ms690336.aspx).|  
|[IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md)|Инициализация перечислителя.|  
|[IEnumOnSTLImpl::Next](../Topic/IEnumOnSTLImpl::Next.md)|Реализация [IEnumXXXX::Next](https://msdn.microsoft.com/en-us/library/ms695273.aspx).|  
|[IEnumOnSTLImpl::Reset](../Topic/IEnumOnSTLImpl::Reset.md)|Реализация [IEnumXXXX::Reset](https://msdn.microsoft.com/en-us/library/ms693414.aspx).|  
|[IEnumOnSTLImpl::Skip](../Topic/IEnumOnSTLImpl::Skip.md)|Реализация [IEnumXXXX::Skip](https://msdn.microsoft.com/en-us/library/ms690392.aspx).|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[IEnumOnSTLImpl::m\_iter](../Topic/IEnumOnSTLImpl::m_iter.md)|Итератор, который представляет текущую позицию перечислителя в коллекции.|  
|[IEnumOnSTLImpl::m\_pcollection](../Topic/IEnumOnSTLImpl::m_pcollection.md)|Указатель к контейнеру STL, содержащий элементы для перечисления.|  
|[IEnumOnSTLImpl::m\_spUnk](../Topic/IEnumOnSTLImpl::m_spUnk.md)|Указатель **IUnknown** объекта, предоставляющего коллекцию.|  
  
## Заметки  
 `IEnumOnSTLImpl` предоставляет реализацию интерфейса перечислителя модели COM, где, перечисленными элементы хранятся в контейнере STL\- совместимости.  Этот класс аналогичн к классу [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md), который предоставляет реализацию интерфейса перечислителя на основе массива.  
  
> [!NOTE]
>  Дополнительные сведения см. в разделе [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md) на более дополнительных различиях между `CComEnumImpl` и `IEnumOnSTLImpl`.  
  
 Обычно *не* требуется создавать собственный класс перечислителя путем наследования от этой реализации интерфейса.  Если необходимо использовать библиотеку ATL\- указанный перечислитель на основе контейнере STL, оно более общие для создания экземпляра [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) или создать класс коллекции, возвращает перечислитель путем наследования от [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  
  
 Однако если необходимо предоставить пользовательский перечислитель \(например, одно которая предоставляет интерфейсы в дополнение к интерфейсу перечислителя\), то можно наследовать от этого класса.  В этой ситуации, вероятно, потребуется переопределить метод [Clone](../Topic/IEnumOnSTLImpl::Clone.md) для реализации собственной реализации.  
  
## Иерархия наследования  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)