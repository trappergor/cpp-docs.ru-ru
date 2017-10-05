---
title: "Операторы &lt;allocators&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: c6b19eb0c4f8d63ce288ce47a759e949714daf5e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="ltallocatorsgt-operators"></a>Операторы &lt;allocator&gt;
|||  
|-|-|  
|[operator!=](#op_neq)|[оператор==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  operator!=  
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
  
##  <a name="op_eq_eq"></a>  operator==  
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




