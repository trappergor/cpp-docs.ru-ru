---
title: Операторы пространства имен concurrency
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: 6cef9304be17dd39e0f0b020133abd08f07fba7c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87194385"
---
# <a name="concurrency-namespace-operators"></a>Операторы пространства имен concurrency

||||
|-|-|-|
|[operator! =](#operator_neq)|[оператор&amp;&amp;](#operator_amp_amp)|[оператор&gt;](#operator_gt)|
|[оператор&gt;=](#operator_gt_eq)|[оператор&lt;](#operator_lt)|[оператор&lt;=](#operator_lt_eq)|
|[Оператор = =](#operator_eq_eq)|[оператор||](#operator_lor)| |

## <a name="operator124124-operator"></a><a name="operator_lor"></a>Оператор&#124;&#124; оператора

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

*ReturnType*<br/>
Тип возвращаемой задачи.

*LHS*<br/>
Первая задача для объединения в результирующую задачу.

*rhs*<br/>
Вторая задача для объединения в результирующую задачу.

### <a name="return-value"></a>Возвращаемое значение

Задача, которая завершается успешно при успешном завершении любой из входных задач. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>`. Если входные задачи относятся к типу, **`void`** задача вывода также будет иметь тип `task<void>` .

### <a name="remarks"></a>Remarks

Если обе задачи отменяются или создают исключения, возвращенная задача завершится в отмененном состоянии, и одно из исключений, если таковое встречено, возникнет при вызове `get()` или `wait()` для этой задачи.

## <a name="operatorampamp-operator"></a><a name="operator_amp_amp"></a>Оператор &amp; operator &amp;

Создает задачу, которая будет успешно выполнена при успешном завершении обеих задач в качестве аргументов.

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

*ReturnType*<br/>
Тип возвращаемой задачи.

*LHS*<br/>
Первая задача для объединения в результирующую задачу.

*rhs*<br/>
Вторая задача для объединения в результирующую задачу.

### <a name="return-value"></a>Возвращаемое значение

Задача, которая завершается успешно, если обе входные задачи завершены успешно. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>>`. Если входные задачи относятся к типу, **`void`** задача вывода также будет иметь тип `task<void>` .

### <a name="remarks"></a>Remarks

Если одна из задач отменена или вызывает исключение, возвращаемая задача будет завершена на раннем этапе, в состоянии Canceled, а исключение, если оно произошло, будет вызываться при вызове метода `get()` или `wait()` для этой задачи.

## <a name="operator-operator"></a><a name="operator_eq_eq"></a>оператор operator = =

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
Тип распределителя первого `concurrent_vector` объекта.

*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.

*_A*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если параллельный вектор слева от оператора равен параллельному вектору в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

Два одновременных вектора равны, если они имеют одинаковое число элементов и их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

Этот метод не является типобезопасным по отношению к другим методам, которые могут изменять любой из параллельных векторов `_A` или `_B` .

## <a name="operator-operator"></a><a name="operator_neq"></a>оператор operator! =

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
Тип распределителя первого `concurrent_vector` объекта.

*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.

*_A*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если одновременные векторы не равны; **`false`** значение, если одновременные векторы равны.

### <a name="remarks"></a>Remarks

Два одновременных вектора равны, если они имеют одинаковое число элементов и их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

Этот метод не является типобезопасным по отношению к другим методам, которые могут изменять любой из параллельных векторов `_A` или `_B` .

## <a name="operatorlt-operator"></a><a name="operator_lt"></a>Оператор &lt; operator

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
Тип распределителя первого `concurrent_vector` объекта.

*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.

*_A*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если параллельный вектор слева от оператора меньше параллельного вектора в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

Поведение этого оператора идентично эквивалентному оператору для `vector` класса в `std` пространстве имен.

Этот метод не является типобезопасным по отношению к другим методам, которые могут изменять любой из параллельных векторов `_A` или `_B` .

## <a name="operatorlt-operator"></a><a name="operator_lt_eq"></a>operator &lt; =, оператор

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
Тип распределителя первого `concurrent_vector` объекта.

*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.

*_A*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если параллельный вектор слева от оператора меньше или равен параллельному вектору в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

Поведение этого оператора идентично эквивалентному оператору для `vector` класса в `std` пространстве имен.

Этот метод не является типобезопасным по отношению к другим методам, которые могут изменять любой из параллельных векторов `_A` или `_B` .

## <a name="operatorgt-operator"></a><a name="operator_gt"></a>Оператор &gt; operator

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
Тип распределителя первого `concurrent_vector` объекта.

*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.

*_A*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если параллельный вектор слева от оператора больше параллельного вектора в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

Поведение этого оператора идентично эквивалентному оператору для `vector` класса в `std` пространстве имен.

Этот метод не является типобезопасным по отношению к другим методам, которые могут изменять любой из параллельных векторов `_A` или `_B` .

## <a name="operatorgt-operator"></a><a name="operator_gt_eq"></a>operator &gt; =, оператор

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
Тип распределителя первого `concurrent_vector` объекта.

*A2*<br/>
Тип распределителя второго `concurrent_vector` объекта.

*_A*<br/>
Объект типа `concurrent_vector`.

*_B*<br/>
Объект типа `concurrent_vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если параллельный вектор слева от оператора больше или равен параллельному вектору в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

Поведение этого оператора идентично эквивалентному оператору для `vector` класса в `std` пространстве имен.

Этот метод не является типобезопасным по отношению к другим методам, которые могут изменять любой из параллельных векторов `_A` или `_B` .

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)
