---
title: "Класс CDefaultHashTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 932969a5d06a3bd06755ec60d43b3257a4de9785
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="cdefaulthashtraits-class"></a>Класс CDefaultHashTraits
Этот класс предоставляет статическую функцию для вычисления хэш-значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CDefaultHashTraits
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDefaultHashTraits::Hash](#hash)|(Статический) Эта функция вызывается для вычисления хэш-значение для данного элемента.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс содержит один статическую функцию, которая возвращает значение хэша для данного элемента. Этот класс используется [CDefaultElementTraits класса](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="hash"></a>CDefaultHashTraits::Hash  
 Эта функция вызывается для вычисления хэш-значение для данного элемента.  
  
```
static ULONG Hash(const T& element) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `element`  
 Элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает хэш-значения.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию алгоритм хеширования — очень простой: возвращаемое значение — число элементов. Переопределите эту функцию, если требуется более сложный алгоритм.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

