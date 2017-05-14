---
title: "Операторы &lt;allocators&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 0a2da6c72e8900c0cea86c30c6b8511e6b256ff9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

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




