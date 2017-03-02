---
title: "пространство имен Concurrency операторы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 7fc7b500d882bb4e023904a147a7736996b5c5de
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-operators"></a>пространство имен Concurrency операторы
||||  
|-|-|-|  
|[оператор! =-оператор](#operator_neq)|[оператор&amp; &amp; оператор](#operator_amp_amp)|[оператор&gt; оператор](#operator_gt)|  
|[оператор&gt;=-оператор](#operator_gt_eq)|[оператор&lt; оператор](#operator_lt)|[оператор&lt;=-оператор](#operator_lt_eq)|  
|[оператор ==-оператор](#operator_eq_eq)|[оператор|| Operator](#operator_lor)|  
  
##  <a name="a-nameoperatorlora--operator124124-operator"></a><a name="operator_lor"></a>оператор || Оператор  
 Создает задачу, которая завершается успешно, если любая из задач, предоставленных в качестве аргументов, завершается успешно.  
  
```  
template<
    typename _ReturnType  
>  
task<_ReturnType>   operator||(
    const task<_ReturnType>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>   operator||(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>   operator||(
    const task<_ReturnType>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
inline task<void>   operator||(
    const task<void>& _Lhs,  
    const task<void>& _Rhs);
```  
  
### <a name="parameters"></a>Параметры  
 `_ReturnType`  
 Тип возвращаемой задачи.  
  
 `_Lhs`  
 Первая задача для объединения в результирующую задачу.  
  
 `_Rhs`  
 Вторая задача для объединения в результирующую задачу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задача, которая завершается успешно, если одна из входных задач завершилась успешно. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>`. Если входные задачи относятся к типу `void`, выходная задача также будет `task<void>`.  
  
### <a name="remarks"></a>Примечания  
 Если обе задачи отменяются или создают исключения, возвращенная задача завершится в отмененном состоянии, и одно из исключений, если таковое встречено, возникнет при вызове `get()` или `wait()` для этой задачи.  
  
##  <a name="a-nameoperatorampampa--operatorampamp-operator"></a><a name="operator_amp_amp"></a>оператор&amp; &amp; оператор  
 Создает задачу, которая завершается успешно, если обе задачи, предоставленные в качестве аргументов, завершаются успешно.  
  
```  
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<_ReturnType>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<_ReturnType>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
inline task<void>    operator&&(
    const task<void>& _Lhs,  
    const task<void>& _Rhs);
```  
  
### <a name="parameters"></a>Параметры  
 `_ReturnType`  
 Тип возвращаемой задачи.  
  
 `_Lhs`  
 Первая задача для объединения в результирующую задачу.  
  
 `_Rhs`  
 Вторая задача для объединения в результирующую задачу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задача, которая завершается успешно, если обе входные задачи завершены успешно. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>>`. Если входные задачи относятся к типу `void`, выходная задача также будет `task<void>`.  
  
### <a name="remarks"></a>Примечания  
 Если одна из задач отменяется или создает исключение, возвращенная задача завершится рано, в отмененном состоянии, и исключение, если таковое встречено, возникнет при вызове `get()` или `wait()` для этой задачи.  
  
##  <a name="a-nameoperatoreqeqa--operator-operator"></a><a name="operator_eq_eq"></a>оператор ==-оператор  
 Проверяет равенство объекта `concurrent_vector` слева от оператора объекту `concurrent_vector` справа от оператора.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator== (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных элементов, хранящихся в параллельных векторах.  
  
 `A1`  
 Тип распределителя первого `concurrent_vector` объекта.  
  
 `A2`  
 Тип распределителя второго `concurrent_vector` объекта.  
  
 `_A`  
 Объект типа `concurrent_vector`.  
  
 `_B`  
 Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если параллельный вектор в левой части оператора равен параллельный вектор в правой части оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Два параллельных вектора равны, если они имеют одинаковое число элементов и их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
 Этот метод не является безопасным в режиме параллелизма относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="a-nameoperatorneqa--operator-operator"></a><a name="operator_neq"></a>оператор! =-оператор  
 Проверяет неравенство объекта `concurrent_vector` слева от оператора объекту `concurrent_vector` справа от оператора.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных элементов, хранящихся в параллельных векторах.  
  
 `A1`  
 Тип распределителя первого `concurrent_vector` объекта.  
  
 `A2`  
 Тип распределителя второго `concurrent_vector` объекта.  
  
 `_A`  
 Объект типа `concurrent_vector`.  
  
 `_B`  
 Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если параллельные векторы не равны; `false` Если параллельные векторы равны.  
  
### <a name="remarks"></a>Примечания  
 Два параллельных вектора равны, если они имеют одинаковое число элементов и их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
 Этот метод не является безопасным в режиме параллелизма относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="a-nameoperatorlta--operatorlt-operator"></a><a name="operator_lt"></a>оператор&lt; оператор  
 Проверяет, меньше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator<(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных элементов, хранящихся в параллельных векторах.  
  
 `A1`  
 Тип распределителя первого `concurrent_vector` объекта.  
  
 `A2`  
 Тип распределителя второго `concurrent_vector` объекта.  
  
 `_A`  
 Объект типа `concurrent_vector`.  
  
 `_B`  
 Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если параллельный вектор в левой части оператора меньше, чем параллельный вектор в правой части оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Поведение данного оператора идентично поведению эквивалентного оператора для `vector` класса в `std` пространства имен.  
  
 Этот метод не является безопасным в режиме параллелизма относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="a-nameoperatorlteqa--operatorlt-operator"></a><a name="operator_lt_eq"></a>оператор&lt;=-оператор  
 Проверяет, меньше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора, или равен ему.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных элементов, хранящихся в параллельных векторах.  
  
 `A1`  
 Тип распределителя первого `concurrent_vector` объекта.  
  
 `A2`  
 Тип распределителя второго `concurrent_vector` объекта.  
  
 `_A`  
 Объект типа `concurrent_vector`.  
  
 `_B`  
 Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если параллельный вектор в левой части оператора меньше или равно параллельный вектор в правой части оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Поведение данного оператора идентично поведению эквивалентного оператора для `vector` класса в `std` пространства имен.  
  
 Этот метод не является безопасным в режиме параллелизма относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="a-nameoperatorgta--operatorgt-operator"></a><a name="operator_gt"></a>оператор&gt; оператор  
 Проверяет больше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator>(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных элементов, хранящихся в параллельных векторах.  
  
 `A1`  
 Тип распределителя первого `concurrent_vector` объекта.  
  
 `A2`  
 Тип распределителя второго `concurrent_vector` объекта.  
  
 `_A`  
 Объект типа `concurrent_vector`.  
  
 `_B`  
 Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если параллельный вектор в левой части оператора больше, чем параллельный вектор в правой части оператора; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Поведение данного оператора идентично поведению эквивалентного оператора для `vector` класса в `std` пространства имен.  
  
 Этот метод не является безопасным в режиме параллелизма относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
##  <a name="a-nameoperatorgteqa--operatorgt-operator"></a><a name="operator_gt_eq"></a>оператор&gt;=-оператор  
 Проверяет больше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора, или равен ему.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных элементов, хранящихся в параллельных векторах.  
  
 `A1`  
 Тип распределителя первого `concurrent_vector` объекта.  
  
 `A2`  
 Тип распределителя второго `concurrent_vector` объекта.  
  
 `_A`  
 Объект типа `concurrent_vector`.  
  
 `_B`  
 Объект типа `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если параллельный вектор в левой части оператора больше или равно параллельный вектор в правой части оператора; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Поведение данного оператора идентично поведению эквивалентного оператора для `vector` класса в `std` пространства имен.  
  
 Этот метод не является безопасным в режиме параллелизма относительно других методов, которые могут изменять любой из параллельных векторов `_A` или `_B`.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

