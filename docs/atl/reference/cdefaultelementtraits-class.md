---
title: "Класс CDefaultElementTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
dev_langs: C++
helpviewer_keywords: CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb6731913d10402016f2148e1ae7705a73e98944
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdefaultelementtraits-class"></a>Класс CDefaultElementTraits
Этот класс предоставляет функции и методы по умолчанию для класса коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет по умолчанию статические функции и методы для перемещения, копирования, сравнение и хэширования элементов, хранящихся в объекте класса коллекции. Этот класс является производным, его функции и методы из [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md), [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md), и [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)и используемой [ CElementTraits](../../atl/reference/celementtraits-class.md), [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md), и [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md).  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
