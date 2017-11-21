---
title: "Класс CAutoPtrElementTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
dev_langs: C++
helpviewer_keywords: CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1b7d09894e7258ab740e09fb45008a4eeb8a3ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cautoptrelementtraits-class"></a>Класс CAutoPtrElementTraits
Этот класс предоставляет методы, статических функций и определения типов полезны при создании коллекции интеллектуальных указателей.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CAutoPtrElementTraits 
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```    
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип указателя.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|Тип данных, используемый для добавления элементов к такому объекту класса коллекции.|  
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|Тип данных для использования для получения элементов из объекта класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы, статических функций и определения типов для State и используется для создания объектов класса коллекции, содержащее интеллектуальных указателей. Классы [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) и [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) являются производными от `CAutoPtrElementTraits`. При создании коллекции интеллектуальных указателей, который требует вектор new и delete операторов, использовать [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) вместо него.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoPtrElementTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="inargtype"></a>CAutoPtrElementTraits::INARGTYPE  
 Тип данных, используемый для добавления элементов к такому объекту класса коллекции.  
  
```
typedef CAutoPtr<T>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CAutoPtrElementTraits::OUTARGTYPE  
 Тип данных для использования для получения элементов из объекта класса коллекции.  
  
```
typedef T *& OUTARGTYPE;
```  
  
## <a name="see-also"></a>См. также  
 [Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
