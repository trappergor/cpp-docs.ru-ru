---
title: Класс index
ms.date: 11/04/2016
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
ms.openlocfilehash: 921d87de72c13e1971d9b40474bf3d91033c0580
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529315"
---
# <a name="index-class"></a>Класс index

Определяет *N*-мерный индекс pographics-cpp-amp.md.

## <a name="syntax"></a>Синтаксис

```
template <int _Rank>
class index;
```

#### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг или число измерений.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Индекс конструктора](#ctor)|Инициализирует новый экземпляр класса `index`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор--](#operator--)|Уменьшает каждый элемент `index` объекта.|
|[Operator(MOD) =](#operator_mod_eq)|Вычисляет модуль (остаток от деления) каждого элемента в `index` объекта при делении этого элемента на число.|
|[оператор*=](#operator_star_eq)|Умножает каждый элемент объекта `index` на число.|
|[оператор/=](#operator_div_eq)|Делит каждый элемент объекта `index` на число.|
|[index::operator\[\]](#operator_at)|Возвращает элемент, находящийся по указанному индексу.|
|[оператор++](#operator_add_add)|Увеличивает на единицу каждый элемент из `index` объекта.|
|[оператор+=](#operator_add_eq)|Добавляет указанное число к каждому элементу `index` объекта.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `index` в данный объект.|
|[оператор-=](#operator_-_eq)|Вычитает указанное число из каждого элемента объекта `index` объекта.|

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[Ранг константа](#rank)|Хранит ранг объекта `index` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`index`

## <a name="remarks"></a>Примечания

`index` Структура представляет координатный вектор из *N* целых чисел, указывающий уникальный позицию в *N*-мерном пространстве. Значения в векторе упорядочены от наиболее важных до наименее важных. Можно получить значения компонентов с помощью [оператор =](#operator_eq).

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="index_ctor"></a> Индекс конструктора

Инициализирует новый экземпляр класса индекса.

```
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
Расположение индекса в одномерный индекс.

*_I0*<br/>
Длина самого значительного измерения.

*_I1*<br/>
Длина следующего к наиболее значительное измерение.

*_I2*<br/>
Длина наименее значительного измерения.

*_Другое*<br/>
Объект индекса, на котором основан новый объект индекса.

## <a name="operator--"></a>  оператор--

Уменьшает каждый элемент объекта индекса.
```
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```

### <a name="return-values"></a>Возвращаемые значения

Для префиксной формы оператора объект индекса (* это). Для суффиксной формы оператора, новый объект индекса.

## <a name="operator_mod_eq"></a>  Operator(MOD) =

Вычисляет модуль (остаток от деления) каждого элемента в объект индекса, при делении этого элемента на заданную величину.

```
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число, которое делится по, чтобы найти остаток.

## <a name="return-value"></a>Возвращаемое значение
Объект индекса.

## <a name="operator_star_eq"></a>  оператор * =

Умножает каждый элемент в объекте index на заданную величину.
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число для перемножения.

## <a name="operator_div_eq"></a>  оператор / =

Делит каждый элемент в объекте index на заданную величину.

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число-знаменатель.

## <a name="operator_at"></a> operator\[\]

Возвращает компонент индекса в указанном расположении.

```
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

Элемент, находящийся по указанному индексу.

### <a name="remarks"></a>Примечания

В следующем примере отображаются значения компонентов индекса.
```
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>  Operator ++

Увеличивает на единицу каждый элемент объекта индекса.
```
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Для префиксной формы оператора объект индекса (* это). Для суффиксной формы оператора, новый объект индекса.

## <a name="operator_add_eq"></a>  оператор +=

Добавляет указанное число к каждому элементу объекта индекса.
```
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число для сложения.

### <a name="return-value"></a>Возвращаемое значение

Объект индекса.

## <a name="operator_eq"></a>  оператор=

Копирует содержимое объекта указанного индекса в другой.
```
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
Объект для копирования из индекса.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект индекса.

## <a name="operator_-_eq"></a>  оператор-=

Вычитает указанное число из каждого элемента объекта индекса.
```
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Объект индекса.

## <a name="rank"></a>  Ранг
  Возвращает ранг объекта индекса.
```
static const int rank = _Rank;
```

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
