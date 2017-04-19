---
title: "Операторы &lt;forward_list&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a560de0a7587b5552fc663bdd2b44734a66b5f73
ms.lasthandoff: 02/24/2017

---
# <a name="ltforwardlistgt-operators"></a>Операторы &lt;forward_list&gt;
||||  
|-|-|-|  
|[оператор!=](#operator_neq)|[оператор&gt;](#operator_gt_)|[оператор&gt;=](#operator_gt__eq)|  
|[оператор&lt;](#operator_lt_)|[оператор&lt;=](#operator_lt__eq)|[оператор==](#operator_eq_eq)|  
  
##  <a name="operator_eq_eq"></a>  оператор==  
 Проверяет, равен ли объект прямого списка слева от оператора объекту прямого списка справа от оператора.  
  
```
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Объект типа `forward_list`.|  
|`right`|Объект типа `forward_list`.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция шаблона перегружает `operator==` для сравнения двух объектов класса шаблона `forward_list`. Функция возвращает `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())`.  
  
##  <a name="operator_neq"></a>  оператор!=  
 Проверяет, не равен ли объект прямого списка слева от оператора объекту прямого списка справа от оператора.  
  
```
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Объект типа `forward_list`.|  
|`right`|Объект типа `forward_list`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если списки не равны; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция шаблона возвращает `!(left == right)`.  
  
##  <a name="operator_lt_"></a>  оператор&lt;  
 Проверяет, меньше ли объект прямого списка слева от оператора объекта прямого списка справа от оператора.  
  
```
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Объект типа `forward_list`.|  
|`right`|Объект типа `forward_list`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если список слева от оператора меньше (но не равен) списка справа от оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция шаблона перегружает `operator<` для сравнения двух объектов класса шаблона `forward_list`. Функция возвращает `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())`.  
  
##  <a name="operator_lt__eq"></a>  оператор&lt;=  
 Проверяет, меньше ли (или равен) объект прямого списка слева от оператора объекта прямого списка справа от оператора.  
  
```
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Объект типа `forward_list`.|  
|`right`|Объект типа `forward_list`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если список слева от оператора меньше или равен списку справа от оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция шаблона возвращает `!(right < left)`.  
  
##  <a name="operator_gt_"></a>  оператор&gt;  
 Проверяет, больше ли объект прямого списка слева от оператора объекта прямого списка справа от оператора.  
  
```
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Объект типа `forward_list`.|  
|`right`|Объект типа `forward_list`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если список слева от оператора больше списка справа от оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция шаблона возвращает `right < left`.  
  
##  <a name="operator_gt__eq"></a>  оператор&gt;=  
 Проверяет, больше ли (или равен) объект прямого списка слева от оператора объекта прямого списка справа от оператора.  
  
```
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Объект типа `forward_list`.|  
|`right`|Объект типа `forward_list`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если список слева от оператора больше или равен списку справа от оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона возвращает `!(left < right)`.  
  
## <a name="see-also"></a>См. также  
 [<forward_list>](../standard-library/forward-list.md)




