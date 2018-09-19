---
title: Операторы пространства имен Concurrency | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
dev_langs:
- C++
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13b9288e39e372ecb23299d355abc921353444b7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059879"
---
# <a name="concurrency-namespace-operators"></a>Операторы пространства имен Concurrency
||||  
|-|-|-|  
|[оператор!=](#operator_neq)|[operator&amp;&amp;](#operator_amp_amp)|[оператор&gt;](#operator_gt)|  
|[operator&gt;=](#operator_gt_eq)|[оператор&lt;](#operator_lt)|[operator&lt;=](#operator_lt_eq)|  
|[оператор==](#operator_eq_eq)|[оператор||](#operator_lor)|  
  
##  <a name="operator_lor"></a>  оператор&#124; &#124; оператор  
 Создает задачу, которая завершается успешно, если любая из задач, предоставленных в качестве аргументов, завершается успешно.  
  
```  
template<typename ReturnType>  
task<ReturnType> operator||(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void> operator||(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>Параметры  
*ReturnType*<br/>
Тип возвращаемой задачи.  
  
*lhs*<br/>
Первая задача для объединения в результирующую задачу.  
  
*правая часть*<br/>
Вторая задача для объединения в результирующую задачу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задача, которая завершается успешно, если одна из входных задач завершилась успешно. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>`. Если входные задачи относятся к типу `void`, выходная задача также будет `task<void>`.  
  
### <a name="remarks"></a>Примечания  
 Если обе задачи отменяются или создают исключения, возвращенная задача завершится в отмененном состоянии, и одно из исключений, если таковое встречено, возникнет при вызове `get()` или `wait()` для этой задачи.  
  
##  <a name="operator_amp_amp"></a>  оператор&amp; &amp; оператор  
 Создает задачу, которая завершается успешно, если обе задачи, предоставленные в качестве аргументов, завершаются успешно.  
  
```  
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void>  operator&&(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>Параметры  
*ReturnType*<br/>
Тип возвращаемой задачи.  
  
*lhs*<br/>
Первая задача для объединения в результирующую задачу.  
  
*правая часть*<br/>
Вторая задача для объединения в результирующую задачу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задача, которая завершается успешно, если обе входные задачи завершены успешно. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>>`. Если входные задачи относятся к типу `void`, выходная задача также будет `task<void>`.  
  
### <a name="remarks"></a>Примечания  
 Если одна из задач отменяется или создает исключение, возвращенная задача завершится рано, в отмененном состоянии, и исключение, если таковое встречено, возникнет при вызове `get()` или `wait()` для этой задачи.  
  
##  <a name="operator_eq_eq"></a>  оператор ==-оператор  
 Проверяет равенство объекта `concurrent_vector` слева от оператора объекту `concurrent_vector` справа от оператора.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator== (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
*T*<br/>
Тип данных для элементов, хранящихся в параллельных векторах.  
  
*A1*<br/>
Тип распределителя первого `concurrent_vector` объекта.  
  
*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.  
  
*_A*<br/>
Объект типа `concurrent_vector`.  
  
*_B*<br/>
Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если параллельный вектор в левой части оператора равен параллельный вектор в правой части оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Два параллельных вектора равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
 Этот метод не нарушающих параллельность относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="operator_neq"></a>  оператор! =-оператор  
 Проверяет неравенство объекта `concurrent_vector` слева от оператора объекту `concurrent_vector` справа от оператора.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
*T*<br/>
Тип данных для элементов, хранящихся в параллельных векторах.  
  
*A1*<br/>
Тип распределителя первого `concurrent_vector` объекта.  
  
*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.  
  
*_A*<br/>
Объект типа `concurrent_vector`.  
  
*_B*<br/>
Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если параллельные векторы не равны; `false` Если параллельные векторы равны.  
  
### <a name="remarks"></a>Примечания  
 Два параллельных вектора равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
 Этот метод не нарушающих параллельность относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="operator_lt"></a>  оператор&lt; оператор  
 Проверяет, меньше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
*T*<br/>
Тип данных для элементов, хранящихся в параллельных векторах.  
  
*A1*<br/>
Тип распределителя первого `concurrent_vector` объекта.  
  
*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.  
  
*_A*<br/>
Объект типа `concurrent_vector`.  
  
*_B*<br/>
Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если параллельный вектор в левой части оператора меньше, чем параллельный вектор в правой части оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Поведение данного оператора идентично поведению эквивалентного оператора для `vector` в класс `std` пространства имен.  
  
 Этот метод не нарушающих параллельность относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="operator_lt_eq"></a>  оператор&lt;=-оператор  
 Проверяет, меньше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора, или равен ему.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
*T*<br/>
Тип данных для элементов, хранящихся в параллельных векторах.  
  
*A1*<br/>
Тип распределителя первого `concurrent_vector` объекта.  
  
*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.  
  
*_A*<br/>
Объект типа `concurrent_vector`.  
  
*_B*<br/>
Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если параллельный вектор в левой части оператора меньше или равно параллельный вектор в правой части оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Поведение данного оператора идентично поведению эквивалентного оператора для `vector` в класс `std` пространства имен.  
  
 Этот метод не нарушающих параллельность относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="operator_gt"></a>  оператор&gt; оператор  
 Проверяет больше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
*T*<br/>
Тип данных для элементов, хранящихся в параллельных векторах.  
  
*A1*<br/>
Тип распределителя первого `concurrent_vector` объекта.  
  
*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.  
  
*_A*<br/>
Объект типа `concurrent_vector`.  
  
*_B*<br/>
Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если параллельный вектор в левой части оператора больше, чем параллельный вектор в правой части оператора; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Поведение данного оператора идентично поведению эквивалентного оператора для `vector` в класс `std` пространства имен.  
  
 Этот метод не нарушающих параллельность относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="operator_gt_eq"></a>  оператор&gt;=-оператор  
 Проверяет больше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора, или равен ему.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
*T*<br/>
Тип данных для элементов, хранящихся в параллельных векторах.  
  
*A1*<br/>
Тип распределителя первого `concurrent_vector` объекта.  
  
*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.  
  
*_A*<br/>
Объект типа `concurrent_vector`.  
  
*_B*<br/>
Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если параллельный вектор в левой части оператора больше или равно параллельный вектор в правой части оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Поведение данного оператора идентично поведению эквивалентного оператора для `vector` в класс `std` пространства имен.  
  
 Этот метод не нарушающих параллельность относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
