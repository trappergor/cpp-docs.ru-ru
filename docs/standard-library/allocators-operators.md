---
title: "Операторы &lt;allocators&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6185bc74c530d6327d0ac37a5425a7653ba36841
ms.lasthandoff: 02/24/2017

---
# <a name="ltallocatorsgt-operators"></a>Операторы &lt;allocator&gt;
|||  
|-|-|  
|[operator!=](#operator_neq)|[оператор==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 Проверяет на неравенство между объектами распределителя указанного класса.  
  
```
template <class Type, class Sync>  
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Один из объектов allocator для проверки на неравенство.|  
|`right`|Один из объектов allocator для проверки на неравенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если объекты allocator не равны; значение **false**, если объекты allocator равны.  
  
### <a name="remarks"></a>Примечания  
 Оператор шаблона возвращает `!(left == right)`.  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 Проверяет на равенство объекты распределителя указанного класса.  
  
```
template <class Type, class Sync>  
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Один из объектов allocator для проверки на равенство.|  
|`right`|Один из объектов allocator для проверки на равенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если объекты allocator равны; значение **false**, если объекты allocator не равны.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор шаблона возвращает `left.equals(right)`.  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)




