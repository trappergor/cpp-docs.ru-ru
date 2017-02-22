---
title: "CComEnumImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComEnumImpl"
  - "ATL::CComEnumImpl"
  - "CComEnumImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumImpl class"
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComEnumImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет реализацию интерфейса перечислителя, перечисленными элементы модели COM, где хранятся в массиве.  
  
## Синтаксис  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy  
>  
class ATL_NO_VTABLE CComEnumImpl :   
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
 Однотиповое [скопируйте класс политик](../Topic/ATL%20Copy%20Policy%20Classes.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComEnumImpl::CComEnumImpl](../Topic/CComEnumImpl::CComEnumImpl.md)|Конструктор.|  
|[CComEnumImpl::~CComEnumImpl](../Topic/CComEnumImpl::~CComEnumImpl.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md)|Реализация [IEnumXXXX::Clone](https://msdn.microsoft.com/en-us/library/ms690336.aspx).|  
|[CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md)|Инициализация перечислителя.|  
|[CComEnumImpl::Next](../Topic/CComEnumImpl::Next.md)|Реализация [IEnumXXXX::Next](https://msdn.microsoft.com/en-us/library/ms695273.aspx).|  
|[CComEnumImpl::Reset](../Topic/CComEnumImpl::Reset.md)|Реализация [IEnumXXXX::Reset](https://msdn.microsoft.com/en-us/library/ms693414.aspx).|  
|[CComEnumImpl::Skip](../Topic/CComEnumImpl::Skip.md)|Реализация [IEnumXXXX::Skip](https://msdn.microsoft.com/en-us/library/ms690392.aspx).|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComEnumImpl::m\_begin](../Topic/CComEnumImpl::m_begin.md)|Указатель на первый элемент в массиве.|  
|[CComEnumImpl::m\_dwFlags](../Topic/CComEnumImpl::m_dwFlags.md)|Флаги копии поток через `Init`.|  
|[CComEnumImpl::m\_end](../Topic/CComEnumImpl::m_end.md)|Указатель на место только за последним элементом в массиве.|  
|[CComEnumImpl::m\_iter](../Topic/CComEnumImpl::m_iter.md)|Указатель на текущий элемент в массиве.|  
|[CComEnumImpl::m\_spUnk](../Topic/CComEnumImpl::m_spUnk.md)|Указатель **IUnknown** объекта, предоставляющего, перечислянным коллекцию.|  
  
## Заметки  
 `CComEnumImpl` предоставляет реализацию интерфейса перечислителя, перечисленными элементы модели COM, где хранятся в массиве.  Этот класс аналогичн к классу `IEnumOnSTLImpl`, который предоставляет реализацию интерфейса перечислителя на основе контейнере STL.  
  
> [!NOTE]
>  Дополнительные сведения о различиях между `CComEnumImpl` и другие `IEnumOnSTLImpl` см. в разделе [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md).  
  
 Обычно *не* требуется создавать собственный класс перечислителя путем наследования от этой реализации интерфейса.  Если необходимо использовать библиотеку ATL\- указанный перечислитель на основе массива, оно более общие для создания экземпляра [CComEnum](../../atl/reference/ccomenum-class.md).  
  
 Однако если необходимо предоставить пользовательский перечислитель \(например, одно которая предоставляет интерфейсы в дополнение к интерфейсу перечислителя\), то можно наследовать от этого класса.  В такой ситуации, вероятно, потребуется переопределить метод [CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md) для реализации собственной реализации.  
  
 Дополнительные сведения см. в разделе [Коллекции и перечислители библиотеки ATL](../../atl/atl-collections-and-enumerators.md).  
  
## Иерархия наследования  
 `Base`  
  
 `CComEnumImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [IEnumOnSTLImpl Class](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum Class](../../atl/reference/ccomenum-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)