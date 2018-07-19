---
title: Операторы пространство имен Concurrency (AMP) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d3bb77599fc81fa29f2c8155a6fd491ed2d639c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686712"
---
# <a name="concurrency-namespace-operators-amp"></a>Операторы пространство имен Concurrency (AMP)
||||  
|-|-|-|  
|[оператор!=](#operator_neq)|[оператор%](#operator_mod)|[оператор*](#operator_star)|  
|[operator+](#operator_add)|[operator-](#operator-)|[оператор/](#operator_div)|  
|[оператор==](#operator_eq_eq)|  
  
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
 Ранг аргументы кортежа.  
  
 `_Lhs`  
 Одно из кортежей для сравнения.  
  
 `_Rhs`  
 Одно из кортежей для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если кортежи равны. в противном случае `false`.  
  
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
 Ранг аргументы кортежа.  
  
 `_Lhs`  
 Одно из кортежей для сравнения.  
  
 `_Rhs`  
 Одно из кортежей для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если кортежи не равны. в противном случае `false`.  
  
##  <a name="operator_add"></a> operator+   

 Вычисляет сумму component-wise указанных аргументов.  
  
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
 Ранг аргументы кортежа.  
  
 `_Lhs`  
 Один из аргументов для добавления.  
  
 `_Rhs`  
 Один из аргументов для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сумма component-wise указанные аргументы.  
  
##  <a name="operator-"></a>  оператор-   

 Вычисляет component-wise различие между указанными аргументами.  
  
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
 Ранг аргументы кортежа.  
  
 `_Lhs`  
 Аргумент, которое вычитается из.  
  
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
 Ранг аргументы кортежа.  
  
 `_Lhs`  
 Одно из кортежей для умножения.  
  
 `_Rhs`  
 Одно из кортежей для умножения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Component-wise произведение указанных аргументов.  
  

##  <a name="operator_div"></a>  оператор/   
 Вычисляет частное component-wise указанные аргументы.  
  
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
 Ранг аргументы кортежа.  
  
 `_Lhs`  
 Кортеж, которое необходимо разделить.  
  
 `_Rhs`  
 Кортеж, необходимо разделить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Component-wise частное указанных аргументов.  
  
##  <a name="operator_mod"></a>  оператор%   

 Вычисляет модуль первого аргумента, указанного с помощью второго заданного аргумента.  
  
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
 Ранг аргументы кортежа.  
  
 `_Lhs`  
 Кортеж, из которого вычисляется остаток от деления.  
  
 `_Rhs`  
 Кортеж остаток от деления по.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат первого указанного аргумента модуля второго заданного аргумента.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency ](concurrency-namespace-cpp-amp.md)
