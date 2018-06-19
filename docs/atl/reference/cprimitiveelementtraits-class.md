---
title: Класс CPrimitiveElementTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bec944c4b9a505cc817dbe7aa3ce09a317954f7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359147"
---
# <a name="cprimitiveelementtraits-class"></a>Класс CPrimitiveElementTraits
Этот класс предоставляет методы по умолчанию и функции для класса коллекции, составленный из примитивных типов данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранимых в объекте класса коллекции.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|Тип данных, используемый для добавления элементов к такому объекту класса коллекции.|  
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|Тип данных для использования для получения элементов из объекта класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет по умолчанию статические функции и методы для перемещения, копирования, сравнение и хэширования элементы типа примитивных данных, хранящихся в объекте класса коллекции.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CPrimitiveElementTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="inargtype"></a>  CPrimitiveElementTraits::INARGTYPE  
 Тип данных, используемый для добавления элементов к такому объекту класса коллекции.  
  
```
typedef T INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CPrimitiveElementTraits::OUTARGTYPE  
 Тип данных для использования для получения элементов из объекта класса коллекции.  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>См. также  
 [Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
