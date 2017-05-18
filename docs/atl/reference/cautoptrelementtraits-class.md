---
title: "Класс CAutoPtrElementTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 1c543eaa678d86e083207915bcb4f43766ee23c5
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объекте класса коллекции.|  
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|Тип данных, использовать для получения элементов из объекта класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы, статических функций и определения типов для State и используется для создания объектов класса коллекции, содержащие смарт-указатели. Классы [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) и [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) являются производными от `CAutoPtrElementTraits`. Если для создания коллекции интеллектуальных указателей, требуется вектор new и delete операторов, используйте [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) вместо.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoPtrElementTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="inargtype"></a>CAutoPtrElementTraits::INARGTYPE  
 Тип данных для добавления элементов в объекте класса коллекции.  
  
```
typedef CAutoPtr<T>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CAutoPtrElementTraits::OUTARGTYPE  
 Тип данных, использовать для получения элементов из объекта класса коллекции.  
  
```
typedef T *& OUTARGTYPE;
```  
  
## <a name="see-also"></a>См. также  
 [Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

