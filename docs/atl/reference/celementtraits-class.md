---
title: "Класс CElementTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: 17
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
ms.sourcegitcommit: 6664a73967d3bdf9859556f21744737718018e74
ms.openlocfilehash: 8b7b91bd9e027a3946160d95da1199c24af3502d
ms.contentlocale: ru-ru
ms.lasthandoff: 03/29/2017

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
 Этот класс предоставляет по умолчанию статические функции и методы для перемещения, копирования, сравнение и хэширования элементов, хранящихся в объекте класса коллекции. `CElementTraits`указывается как поставщик по умолчанию эти операции в классах коллекций [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), и [CRBTree](../../atl/reference/crbtree-class.md).  
  
 Реализация по умолчанию будет достаточно для простых типов данных, но при использовании классов коллекций для хранения более сложные объекты функций и методов должны быть переопределены пользовательские реализации.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

