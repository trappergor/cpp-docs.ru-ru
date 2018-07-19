---
title: Класс CPrimitiveElementTraits | Документация Майкрософт
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
ms.openlocfilehash: 2219be699e879afb6ec19ad84acc50f18d93a9a9
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885813"
---
# <a name="cprimitiveelementtraits-class"></a>Класс CPrimitiveElementTraits
Этот класс предоставляет методы по умолчанию и функции для класса коллекции состоят из примитивных типов данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Тип данных для сохранения в объекте класса коллекции.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.|  
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет статические функции по умолчанию и методы для перемещения, копирования, сравнение и хэширования элементов типа примитивных данных, хранящихся в объекте класса коллекции.  
  
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
 Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.  
  
```
typedef T INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CPrimitiveElementTraits::OUTARGTYPE  
 Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>См. также  
 [Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
