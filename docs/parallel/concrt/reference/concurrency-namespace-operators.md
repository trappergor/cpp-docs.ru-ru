---
title: Операторы пространства имен concurrency
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: aac43a15b09bd792118fbfe7ea51493b73b8ac9d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374383"
---
# <a name="concurrency-namespace-operators"></a>Операторы пространства имен concurrency

||||
|-|-|-|
|[оператора!](#operator_neq)|[Оператор&amp;&amp;](#operator_amp_amp)|[Оператор&gt;](#operator_gt)|
|[Оператор&gt;=](#operator_gt_eq)|[Оператор&lt;](#operator_lt)|[Оператор&lt;=](#operator_lt_eq)|
|[оператора](#operator_eq_eq)|[оператор||](#operator_lor)| |

## <a name="operator124124-operator"></a><a name="operator_lor"></a>оператор&#124;&#124; оператор

Создает задачу, которая завершается успешно, если любая из задач, предоставленных в качестве аргументов, завершается успешно.

```cpp
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

*Returntype*<br/>
Тип возвращаемой задачи.

*Lhs*<br/>
Первая задача для объединения в результирующую задачу.

*rhs*<br/>
Вторая задача для объединения в результирующую задачу.

### <a name="return-value"></a>Возвращаемое значение

Задача, которая успешно выполняется, когда любая из входных задач успешно выполнена. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>`. Если входные задачи относятся к типу `void`, выходная задача также будет `task<void>`.

### <a name="remarks"></a>Remarks

Если обе задачи отменяются или создают исключения, возвращенная задача завершится в отмененном состоянии, и одно из исключений, если таковое встречено, возникнет при вызове `get()` или `wait()` для этой задачи.

## <a name="operatorampamp-operator"></a><a name="operator_amp_amp"></a>Оператор&amp; &amp; оператора

Создает задачу, которая завершится успешно, когда обе задачи, поставленные в качестве аргументов, будут успешно выполнены.

```cpp
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

*Returntype*<br/>
Тип возвращаемой задачи.

*Lhs*<br/>
Первая задача для объединения в результирующую задачу.

*rhs*<br/>
Вторая задача для объединения в результирующую задачу.

### <a name="return-value"></a>Возвращаемое значение

Задача, которая завершается успешно, если обе входные задачи завершены успешно. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>>`. Если входные задачи относятся к типу `void`, выходная задача также будет `task<void>`.

### <a name="remarks"></a>Remarks

Если одна из задач отменена или бросает исключение, возвращенная задача завершится досрочно, в отмененном состоянии, и `get()` `wait()` исключение, если оно происходит, будет брошено, если вы звоните или выполняете эту задачу.

## <a name="operator-operator"></a><a name="operator_eq_eq"></a>Оператор оператора

Проверяет равенство объекта `concurrent_vector` слева от оператора объекту `concurrent_vector` справа от оператора.

```cpp
template<typename T, class A1, class A2>
inline bool operator== (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранящихся в параллельных векторах.

*A1*<br/>
Тип разлесть первого `concurrent_vector` объекта.

*A2*<br/>
Тип разлесть второго `concurrent_vector` объекта.

*_a*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параллельный вектор на левой стороне оператора равен одновременному вектору на правой стороне оператора; в противном случае **ложные**.

### <a name="remarks"></a>Remarks

Два одновременных вектора равны, если они имеют одинаковое количество элементов и их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

Этот метод не является валютным по отношению к другим методам, которые `_A` `_B`могли бы изменить любой из одновременных векторов или .

## <a name="operator-operator"></a><a name="operator_neq"></a>Оператор!

Проверяет неравенство объекта `concurrent_vector` слева от оператора объекту `concurrent_vector` справа от оператора.

```cpp
template<typename T, class A1, class A2>
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранящихся в параллельных векторах.

*A1*<br/>
Тип разлесть первого `concurrent_vector` объекта.

*A2*<br/>
Тип разлесть второго `concurrent_vector` объекта.

*_a*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параллельные векторы не равны; **ложные,** если параллельные векторы равны.

### <a name="remarks"></a>Remarks

Два одновременных вектора равны, если они имеют одинаковое количество элементов и их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

Этот метод не является валютным по отношению к другим методам, которые `_A` `_B`могли бы изменить любой из одновременных векторов или .

## <a name="operatorlt-operator"></a><a name="operator_lt"></a>Оператор&lt; оператора

Проверяет, меньше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора.

```cpp
template<typename T, class A1, class A2>
inline bool operator<(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранящихся в параллельных векторах.

*A1*<br/>
Тип разлесть первого `concurrent_vector` объекта.

*A2*<br/>
Тип разлесть второго `concurrent_vector` объекта.

*_a*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параллельный вектор на левой стороне оператора меньше, чем параллельный вектор на правой стороне оператора; в противном случае **ложные**.

### <a name="remarks"></a>Remarks

Поведение этого оператора идентично эквиваленту `vector` оператора `std` для класса в пространстве имен.

Этот метод не является валютным по отношению к другим методам, которые `_A` `_B`могли бы изменить любой из одновременных векторов или .

## <a name="operatorlt-operator"></a><a name="operator_lt_eq"></a>Оператор&lt;- Оператор

Проверяет, меньше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора, или равен ему.

```cpp
template<typename T, class A1, class A2>
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранящихся в параллельных векторах.

*A1*<br/>
Тип разлесть первого `concurrent_vector` объекта.

*A2*<br/>
Тип разлесть второго `concurrent_vector` объекта.

*_a*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параллельный вектор на левой стороне оператора меньше или равен одновременному вектору на правой стороне оператора; в противном случае **ложные**.

### <a name="remarks"></a>Remarks

Поведение этого оператора идентично эквиваленту `vector` оператора `std` для класса в пространстве имен.

Этот метод не является валютным по отношению к другим методам, которые `_A` `_B`могли бы изменить любой из одновременных векторов или .

## <a name="operatorgt-operator"></a><a name="operator_gt"></a>Оператор&gt; оператора

Проверяет больше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора.

```cpp
template<typename T, class A1, class A2>
inline bool operator>(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранящихся в параллельных векторах.

*A1*<br/>
Тип разлесть первого `concurrent_vector` объекта.

*A2*<br/>
Тип разлесть второго `concurrent_vector` объекта.

*_a*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параллельный вектор на левой стороне оператора больше, чем параллельный вектор на правой стороне оператора; в противном случае **ложные**.

### <a name="remarks"></a>Remarks

Поведение этого оператора идентично эквиваленту `vector` оператора `std` для класса в пространстве имен.

Этот метод не является валютным по отношению к другим методам, которые `_A` `_B`могли бы изменить любой из одновременных векторов или .

## <a name="operatorgt-operator"></a><a name="operator_gt_eq"></a>Оператор&gt;- Оператор

Проверяет больше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора, или равен ему.

```cpp
template<typename T, class A1, class A2>
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранящихся в параллельных векторах.

*A1*<br/>
Тип разлесть первого `concurrent_vector` объекта.

*A2*<br/>
Тип разлесть второго `concurrent_vector` объекта.

*_a*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параллельный вектор на левой стороне оператора больше или равен одновременному вектору на правой стороне оператора; в противном случае **ложные**.

### <a name="remarks"></a>Remarks

Поведение этого оператора идентично эквиваленту `vector` оператора `std` для класса в пространстве имен.

Этот метод не является валютным по отношению к другим методам, которые `_A` `_B`могли бы изменить любой из одновременных векторов или .

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
