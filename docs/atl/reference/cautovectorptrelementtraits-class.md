---
title: "Класс CAutoVectorPtrElementTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAutoVectorPtrElementTraits<T>
- ATL.CAutoVectorPtrElementTraits
- ATL.CAutoVectorPtrElementTraits<T>
- ATL::CAutoVectorPtrElementTraits
- CAutoVectorPtrElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: d7b7418b713993f539f56e70715296d5af265d28
ms.lasthandoff: 02/24/2017

---
# <a name="cautovectorptrelementtraits-class"></a>Класс CAutoVectorPtrElementTraits
Этот класс предоставляет методы, статических функций и определения типов, полезных при создании коллекции интеллектуальных указателей, используя новый вектор и удаление операторов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CAutoVectorPtrElementTraits : 
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```    
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип указателя.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объекте класса коллекции.|  
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|Тип данных, использовать для получения элементов из объекта класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы, статических функций и определения типов для State и используется для создания объектов класса коллекции, содержащие смарт-указатели. В отличие от [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md), данный класс использует новые векторные и удаление операторов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoVectorPtrElementTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="a-nameinargtypea--cautovectorptrelementtraitsinargtype"></a><a name="inargtype"></a>CAutoVectorPtrElementTraits::INARGTYPE  
 Тип данных для добавления элементов в объекте класса коллекции.  
  
```
typedef CAutoVectorPtr<T>& INARGTYPE;
```  
  
##  <a name="a-nameoutargtypea--cautovectorptrelementtraitsoutargtype"></a><a name="outargtype"></a>CAutoVectorPtrElementTraits::OUTARGTYPE  
 Тип данных, использовать для получения элементов из объекта класса коллекции.  
  
```
typedef T*& OUTARGTYPE;
```  
  
## <a name="see-also"></a>См. также  
 [Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
 [Класс CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

