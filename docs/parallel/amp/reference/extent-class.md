---
title: Класс (C++ AMP) Extent | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
dev_langs:
- C++
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71a02b89e7b2098f8a125d1477cff2a0d1cda30a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429972"
---
# <a name="extent-class-c-amp"></a>Касс extent (C++ AMP)

Представляет вектор из *N* целочисленных значений, которые определяют границы *N*-мерного пространства с началом координат в 0. Значения в векторе упорядочены от наиболее важных до наименее важных.

### <a name="syntax"></a>Синтаксис

```
template <int _Rank>
class extent;
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг `extent` объекта.

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[область конструктора](#ctor)|Инициализирует новый экземпляр класса `extent`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Содержит](#contains)|Проверяет, что указанный `extent` объект с указанным рангом.|
|[size](#size)|Возвращает полный линейный размер области памяти (в единицах элементов).|
|[Плитка](#tile)|Создает `tiled_extent` объект с размерами плитки указанными с помощью измерений.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator-](#operator_min)|Возвращает новый `extent` объект, созданный путем вычитания `index` элементы из соответствующих `extent` элементов.|
|[оператор--](#operator_min_min)|Уменьшает каждый элемент `extent` объекта.|
|[оператор%=](#operator_mod_eq)|Вычисляет модуль (остаток от деления) каждого элемента в `extent` объекта при делении этого элемента на число.|
|[оператор*=](#operator_star_eq)|Умножает каждый элемент объекта `extent` на число.|
|[оператор/=](#operator_min_eq)|Делит каждый элемент объекта `extent` на число.|
|[extent::operator\[\]](#operator_at)|Возвращает элемент, находящийся по указанному индексу.|
|[operator+](#operator_add)|Возвращает новый `extent` объект, созданный путем добавления соответствующих `index` и `extent` элементы.|
|[оператор++](#operator_add_add)|Увеличивает на единицу каждый элемент из `extent` объекта.|
|[оператор+=](#operator_add_eq)|Добавляет указанное число к каждому элементу `extent` объекта.|
|[оператор=](#operator_eq)|Копирует содержимое другого объекта `extent` в данный объект.|
|[оператор-=](#operator_min_eq)|Вычитает указанное число из каждого элемента объекта `extent` объекта.|

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[Ранг константа](#rank)|Получает ранг объекта `extent` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`extent`

## <a name="contains"></a> Содержит

Указывает ли указанный [индекс](index-class.md) значение содержится в объекте «область».

### <a name="syntax"></a>Синтаксис

```
bool contains(const index<rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
`index` Значение для проверки.

### <a name="return-value"></a>Возвращаемое значение

`true` Если указанный `index` значение содержится в `extent` объекта; в противном случае `false`.

##  <a name="ctor"></a> экстент

Инициализирует новый экземпляр класса «область».

### <a name="syntax"></a>Синтаксис

```
extent() restrict(amp,cpu);
extent(const extent<_Rank>& _Other) restrict(amp,cpu);
explicit extent(int _I) restrict(amp,cpu);
extent(int _I0,  int _I1) restrict(amp,cpu);
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);
explicit extent(const int _Array[_Rank])restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Array*<br/>
Массив `_Rank` целых чисел, который используется для создания нового `extent` объекта.

*_I*<br/>
Размер области памяти.

*_I0*<br/>
Длина самого значительного измерения.

*_I1*<br/>
Длина следующего к наиболее значительное измерение.

*_I2*<br/>
Длина наименее значительного измерения.

*_Другое*<br/>
`extent` Объект, для которого новый `extent` основан объект.

## <a name="remarks"></a>Примечания

Этот конструктор инициализирует `extent` объект, имеющий ранг равный трем.

Если массив используется для создания `extent` объект, длина массива должна соответствовать рангу объекта `extent` объекта.

##  <a name="operator_mod_eq"></a> оператор % =

Вычисляет модуль (остаток от деления) каждого элемента в области «», при делении этого элемента на число.

### <a name="syntax"></a>Синтаксис

```
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Номер, чтобы найти модуль.

### <a name="return-value"></a>Возвращаемое значение

Объект `extent`.

##  <a name="operator_star_eq"></a> оператор * =

Умножает каждый элемент в объекте «область» на заданную величину.

### <a name="syntax"></a>Синтаксис

```
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число для перемножения.

### <a name="return-value"></a>Возвращаемое значение

Объект `extent`.

## <a name="operator_add"></a> оператор +

Возвращает новый `extent` объект, созданный путем добавления соответствующих `index` и `extent` элементы.

### <a name="syntax"></a>Синтаксис

```
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
`index` , Содержащий добавляемые элементы.

### <a name="return-value"></a>Возвращаемое значение

Новый объект `extent`.

##  <a name="operator_add_add"></a> Operator ++

Увеличивает на единицу каждый элемент объекта «область».

### <a name="syntax"></a>Синтаксис

```
extent<_Rank>& operator++() restrict(amp,cpu);
extent<_Rank> operator++(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Для префиксной формы оператора `extent` объекта (`*this`). Для суффиксной формы оператора новый `extent` объекта.

##  <a name="operator_add_eq"></a> оператор +=

Добавляет указанное число к каждому элементу «границы».

### <a name="syntax"></a>Синтаксис

```
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Номер, индекс или экстент для добавления.

### <a name="return-value"></a>Возвращаемое значение

Результирующий объект `extent`.

##  <a name="operator_min"></a> оператор-

Создает новый `extent` объекта путем вычитания каждого элемента в указанном `index` объект из соответствующего элемента в этом `extent` объекта.

### <a name="syntax"></a>Синтаксис

```
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
`index` , Содержащий элементы для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Новый объект `extent`.

##  <a name="operator_min_min"></a> оператор--

Уменьшает каждый элемент в объекте «область».

### <a name="syntax"></a>Синтаксис

```
extent<_Rank>& operator--() restrict(amp,cpu);
extent<_Rank> operator--(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Для префиксной формы оператора `extent` объекта (`*this`). Для суффиксной формы оператора новый `extent` объекта.

##  <a name="operator_div_eq"></a> оператор / =

Делит каждый элемент в объекте «область» на заданную величину.

### <a name="syntax"></a>Синтаксис

```
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число-знаменатель.

### <a name="return-value"></a>Возвращаемое значение

Объект `extent`.

##  <a name="operator_min_eq"></a> оператор-=

Вычитает указанное число из каждого элемента объекта «область».

### <a name="syntax"></a>Синтаксис

```
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Результирующий объект `extent`.

##  <a name="operator_eq"></a> оператор =

Копирует содержимое другого объекта «область» в другой.

### <a name="syntax"></a>Синтаксис

```
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`extent` Для копирования.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `extent` объекта.

##  <a name="operator_at"></a> Extent::operator \[\]

Возвращает элемент, находящийся по указанному индексу.

### <a name="syntax"></a>Синтаксис

```
int operator[](unsigned int _Index) const restrict(amp,cpu);
int& operator[](unsigned int _Index) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Целое число от 0 до ранга минус 1.

### <a name="return-value"></a>Возвращаемое значение

Элемент, находящийся по указанному индексу.

##  <a name="rank_constant"></a> Ранг

Хранит ранг объекта «область».

### <a name="syntax"></a>Синтаксис

```
static const int rank = _Rank;
```

##  <a name="size"></a> Размер

Возвращает полный линейный размер `extent` объекта (в единицах элементов).

### <a name="syntax"></a>Синтаксис

```
unsigned int size() const restrict(amp,cpu);
```

## <a name="tile"></a> Плитка

Создает объект tiled_extent с заданными размерами плитки.

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```
### <a name="parameters"></a>Параметры

*_Dim0*<br/>
Наиболее значимый компонент замощенной области памяти.
*_Dim1*<br/>
Далее к наиболее значимый компонент замощенной области памяти.
*_Dim2*<br/>
Наименее значимый компонент замощенной области памяти.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
