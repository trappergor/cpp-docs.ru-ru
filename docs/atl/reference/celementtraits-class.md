---
title: Класс CElementTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c530622f096ef14d4eb3de56e5219e8f7df4f082
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359749"
---
# <a name="celementtraits-class"></a>Класс CElementTraits
Этот класс используется классами коллекции для обеспечения функции и методы для перемещения, копирования, сравнения и операций хэширования.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CElementTraits : public CDefaultElementTraits<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет по умолчанию статические функции и методы для перемещения, копирования, сравнение и хэширования элементов, хранящихся в объекте класса коллекции. `CElementTraits` указывается как поставщик по умолчанию эти операции в классах коллекций [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), и [CRBTree](../../atl/reference/crbtree-class.md).  
  
 Реализация по умолчанию будет достаточно для простых типов данных, но при использовании классов коллекций для хранения более сложные объекты функций и методов должны быть переопределены пользовательские реализации.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
