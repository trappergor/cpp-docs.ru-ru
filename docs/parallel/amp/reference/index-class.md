---
title: Класс index
ms.date: 03/27/2019
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
ms.openlocfilehash: 06a5fa9a2d7e645c46b90ace957d31251baed81c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127807"
---
# <a name="index-class"></a>Класс index

Определяет вектор *N*-мерных индексов.

## <a name="syntax"></a>Синтаксис

```cpp
template <int _Rank>
class index;
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг или количество измерений.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Конструктор индекса](#index_ctor)|Инициализирует новый экземпляр класса `index`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[оператор--](#operator--)|Уменьшает каждый элемент объекта `index`.|
|[оператор%=](#operator_mod_eq)|Вычисляет остаток от деления каждого элемента в объекте `index`, если этот элемент делится на число.|
|[оператор*=](#operator_star_eq)|Умножает каждый элемент объекта `index` на число.|
|[оператор/=](#operator_div_eq)|Делит каждый элемент объекта `index` на число.|
|[\]\[оператора index::](#operator_at)|Возвращает элемент, расположенный по указанному индексу.|
|[оператор++](#operator_add_add)|Увеличивает каждый элемент `index` объекта.|
|[оператор+=](#operator_add_eq)|Добавляет указанный номер в каждый элемент объекта `index`.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `index` в этот объект.|
|[оператор-=](#operator_-_eq)|Вычитает указанное число из каждого элемента объекта `index`.|

### <a name="public-constants"></a>Открытые константы

|Имя|Description|
|----------|-----------------|
|[Константа Rank](#rank)|Хранит ранг объекта `index`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`index`

## <a name="remarks"></a>Remarks

Структура `index` представляет вектор координат *n* целых чисел, указывающий уникальную положение в *n*-мерном пространстве. Значения в векторе упорядочиваются от наиболее значимых к минимально значимым. Значения компонентов можно получить с помощью [оператора operator =](#operator_eq).

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="index_ctor"></a>Конструктор индекса

Инициализирует новый экземпляр класса index.

```cpp
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Array*<br/>
Одномерный массив со значениями ранга.

*_I*<br/>
Расположение индекса в одномерном индексе.

*_I0*<br/>
Длина наиболее значимого измерения.

*_I1*<br/>
Длина измерения "следующий к значимости".

*_I2*<br/>
Длина наименее значимого измерения.

*_Other*<br/>
Объект индекса, на котором основан новый объект индекса.

## <a name="operator--"></a>Оператор--

Уменьшает каждый элемент объекта index.

```cpp
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```

### <a name="return-values"></a>Возвращаемые значения

Для оператора префикса объект индекса (* this). Для оператора суффикса — новый объект index.

## <a name="operator_mod_eq"></a>Оператор% =

Вычисляет остаток от деления каждого элемента в объекте индекса, если этот элемент делится на указанное число.

```cpp
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число, на которое производится деление, для поиска модуля.

## <a name="return-value"></a>Возвращаемое значение

Объект index.

## <a name="operator_star_eq"></a>operator * =

Умножает каждый элемент в объекте индекса на указанное число.

```cpp
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число для умножения.

## <a name="operator_div_eq"></a>Оператор/=

Делит каждый элемент в объекте индекса на указанное число.

```cpp
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число, на которое производится деление.

## <a name="operator_at"></a>  operator\[\]

Возвращает компонент индекса в указанном расположении.

```cpp
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Целое число от 0 до ранга минус 1.

### <a name="return-value"></a>Возвращаемое значение

Элемент, расположенный по указанному индексу.

### <a name="remarks"></a>Remarks

В следующем примере выводятся значения компонентов индекса.

```cpp
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>operator + +

Увеличивает каждый элемент объекта index.

```cpp
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Для оператора префикса объект индекса (* this). Для оператора суффикса — новый объект index.

## <a name="operator_add_eq"></a>operator + =

Добавляет указанный номер в каждый элемент объекта index.

```cpp
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Добавляемое число.

### <a name="return-value"></a>Возвращаемое значение

Объект index.

## <a name="operator_eq"></a>  оператор=

Копирует содержимое указанного объекта индекса в этот объект.

```cpp
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект index, из которого необходимо выполнить копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект индекса.

## <a name="operator_-_eq"></a>Оператор-=

Вычитает указанное число из каждого элемента объекта индекса.

```cpp
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Вычитаемое число.

### <a name="return-value"></a>Возвращаемое значение

Объект index.

## <a name="rank"></a>Рейтинг

Возвращает ранг объекта индекса.

```cpp
static const int rank = _Rank;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
