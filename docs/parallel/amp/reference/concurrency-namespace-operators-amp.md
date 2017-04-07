---
title: "Операторы пространство имен Concurrency (AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: 
dev_langs:
- C++
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: 676f3e836082dc3286a45f8d59db83c969964058
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-operators-amp"></a>Операторы пространство имен Concurrency (AMP)
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[оператор%](#operator_mod)|[оператор*](#operator_star)|  
|[оператор+](#operator_add)|[оператор-](#operator-)|[оператор/](#operator_div)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_eq_eq"></a> operator==   
 Определяет, равны ли указанные аргументы.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг кортежа аргументы.  
  
 `_Lhs`  
 Одно из кортежей для сравнения.  
  
 `_Rhs`  
 Одно из кортежей для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если кортежи равны; в противном случае — `false`.  
  
##  <a name="operator_neq"></a> operator!=   
 Определяет, равны ли указанные аргументы.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг кортежа аргументы.  
  
 `_Lhs`  
 Одно из кортежей для сравнения.  
  
 `_Rhs`  
 Одно из кортежей для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если кортежи не равны. в противном случае — `false`.  
  
##  <a name="operator_add"></a> operator+   

 Вычисляет сумму component-wise указанные аргументы.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг кортежа аргументы.  
  
 `_Lhs`  
 Один из аргументов для добавления.  
  
 `_Rhs`  
 Один из аргументов для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Component-wise сумма указанные аргументы.  
  
##  <a name="operator-"></a>  оператор-   

 Component-wise расхождения между указанными аргументами.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг кортежа аргументы.  
  
 `_Lhs`  
 Аргумент Уменьшаемое.  
  
 `_Rhs`  
 Аргумент для вычитания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Component-wise различие между указанными аргументами.  
  
##  <a name="operator_star"></a>  оператор*   

 Вычисляет произведение component-wise указанные аргументы.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг кортежа аргументы.  
  
 `_Lhs`  
 Одно из кортежей для умножения.  
  
 `_Rhs`  
 Одно из кортежей для умножения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Component-wise произведение заданных аргументов.  
  

##  <a name="operator_div"></a>  оператор/   
 Вычисляет частное component-wise указанных аргументов.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг кортежа аргументы.  
  
 `_Lhs`  
 Кортеж, которое необходимо разделить.  
  
 `_Rhs`  
 Кортеж, который необходимо разделить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Component-wise частное указанные аргументы.  
  
##  <a name="operator_mod"></a>  оператор%   

 Вычисляет модуль первого указанного аргумента с помощью второго заданного аргумента.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг кортежа аргументы.  
  
 `_Lhs`  
 Кортеж, из которого вычисляется остаток от деления.  
  
 `_Rhs`  
 Кортеж остаток от деления по.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат первого модуля указанный аргумент второго заданного аргумента.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency](concurrency-namespace-cpp-amp.md)

