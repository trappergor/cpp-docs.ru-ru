---
title: Класс CAutoVectorPtrElementTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52c450a1a261224cf87ea125a6f01259da0e9f1b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357887"
---
# <a name="cautovectorptrelementtraits-class"></a>Класс CAutoVectorPtrElementTraits
Этот класс предоставляет методы, статических функций и определения типов, полезных при создании коллекции интеллектуальных указателей, используя новый вектор и удалять операторов.  
  
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
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|Тип данных, используемый для добавления элементов к такому объекту класса коллекции.|  
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|Тип данных для использования для получения элементов из объекта класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы, статических функций и определения типов для State и используется для создания объектов класса коллекции, содержащее интеллектуальных указателей. В отличие от [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md), этот класс использует новые векторные и удаление операторов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoVectorPtrElementTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="inargtype"></a>  CAutoVectorPtrElementTraits::INARGTYPE  
 Тип данных, используемый для добавления элементов к такому объекту класса коллекции.  
  
```
typedef CAutoVectorPtr<T>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CAutoVectorPtrElementTraits::OUTARGTYPE  
 Тип данных для использования для получения элементов из объекта класса коллекции.  
  
```
typedef T*& OUTARGTYPE;
```  
  
## <a name="see-also"></a>См. также  
 [Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
 [Класс CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
