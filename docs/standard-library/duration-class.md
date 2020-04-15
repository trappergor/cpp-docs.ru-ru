---
title: Класс duration
ms.date: 03/27/2016
f1_keywords:
- chrono/std::chrono::duration
- chrono/std::chrono::duration::duration
- chrono/std::chrono::duration::count
- chrono/std::chrono::duration::max
- chrono/std::chrono::duration::min
- chrono/std::chrono::duration::zero
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
helpviewer_keywords:
- std::chrono [C++], duration
ms.openlocfilehash: 3669935bf094f476ca24a8170a0388dff29e0a0c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368756"
---
# <a name="duration-class"></a>Класс duration

Описывает тип, содержащий *интервал времени*, представляющий собой затраченное время между двумя точками времени.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Rep, class Period = ratio<1>>
class duration;
template <class Rep, class Period>
class duration;
template <class Rep, class Period1, class Period2>
class duration <duration<Rep, Period1>, Period2>;
```

## <a name="remarks"></a>Remarks

Аргумент шаблона `Rep` описывает тип, используемый для удержания числа тактов в интервале. Аргумент шаблона `Period` — экземпляр [отношения](../standard-library/ratio.md), описывающий размер интервала, который представляет каждый такт.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|duration::period Typedef|Синоним для параметра-шаблона `Period`.|
|duration::rep Typedef|Синоним для параметра-шаблона `Rep`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Длительность](#duration)|Формирует объект `duration`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[count](#count)|Возвращает количество тактов в интервале времени.|
|[Макс](#max)|Статический. Возвращает максимальное допустимое значение параметра-шаблона `Ref`.|
|[Мин](#min)|Статический. Возвращает минимально допустимое значение параметра-шаблона `Ref`.|
|[Нуля](#zero)|Статический. Фактически возвращает `Rep` (0).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[продолжительность::оператор-](#operator-)|Возвращает копию объекта `duration` вместе с отрицательным счетчиком тактов.|
|[продолжительность:оператор--](#operator--)|Уменьшает на единицу накопленный счетчик тактов.|
|[продолжительность::оператор](#op_eq)|Уменьшает накопленный счетчик тактов по модулю на указанное значение.|
|[duration::operator*=](#op_star_eq)|Умножает накопленный счетчик тактов на указанное значение.|
|[продолжительность:оператор/з.](#op_div_eq)|Делит накопленный счетчик тактов на счетчик тактов указанного объекта `duration`.|
|[продолжительность::оператор](#op_add)|Возвращает `*this`.|
|[продолжительность:оператор](#op_add_add)|Увеличивает на единицу накопленный счетчик тактов.|
|[продолжительность::оператор](#op_add_eq)|Добавляет счетчик тактов указанного объекта `duration` к накопленному счетчику тактов.|
|[продолжительность:оператор-я](#operator-_eq)|Вычитает счетчик тактов указанного объекта `duration` из накопленного счетчика тактов.|

## <a name="requirements"></a>Требования

**Заголовок:** \<хроно>

**Пространство имен:** std::chrono

## <a name="durationcount"></a><a name="count"></a>продолжительность::счет

Получает количество тактов в интервале времени.

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тактов в интервале времени.

## <a name="durationduration-constructor"></a><a name="duration"></a>продолжительность::dконструктор

Формирует объект `duration`.

```cpp
constexpr duration() = default;

template <class Rep2>
constexpr explicit duration(const Rep2& R);

template <class Rep2, class Period2>
constexpr duration(const duration<Rep2, Period2>& Dur);
```

### <a name="parameters"></a>Параметры

*Rep2*\
Арифметический тип для представления числа тактов.

*Период2*\
Специализация шаблона `std::ratio` для представления тактового периода в секундах.

*R*\
Количество тактов в периоде по умолчанию.

*Dur*\
Количество тиков периода, указанного *Period2*.

### <a name="remarks"></a>Remarks

Конструктор по умолчанию создает объект, который не инициализирован. Инициализация значения с помощью пустых фигурных скобок инициализирует объект, представляющий интервал времени нулевых тактов.

Второй, один шаблон аргумент конструктор строит объект, который *R* представляет собой временной интервал `std::ratio<1>`R часы тикает с помощью периода по умолчанию . Чтобы избежать округления подсчетов тиков, ошибкой является построение объекта продолжительности из типа представления *Rep2,* который можно рассматривать как тип плавающей точки, когда `duration::rep` его нельзя рассматривать как тип плавающей точки.

Третий, два шаблона аргумент конструктор строит объект, который представляет собой временной интервал, длина которого является временной интервал, который указан *Dur*. Чтобы избежать усечения значений счетчика тактов, считается ошибкой создание объекта длительности из другого объекта длительности, тип которого *несоизмерим* с целевым типом.

Тип длительности `D1`*несоизмерим* с другим типом длительности `D2`, если `D2` не может рассматриваться как тип с плавающей запятой, а [ratio_divide\<D1::period, D2::period>::type::den](../standard-library/ratio.md) не равен 1.

Если *Rep2* неявно кабриолет `rep` и либо `treat_as_floating_point<rep>`имеет *право* или `treat_as_floating_point<Rep2>`содержит *ложные*, второй конструктор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

Если второй конструктор не участвует в разрешении перегрузки и `treat_as_floating_point<rep>`*не содержит значение true* или оба `ratio_divide<Period2, period>::den` не равны 1 и `treat_as_floating_point<Rep2>`*не содержит значение false*, третий конструктор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="durationmax"></a><a name="max"></a>продолжительность::max

Статический метод, который возвращает верхнюю границу значений типа параметра-шаблона `Ref`.

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `duration(duration_values<rep>::max())`.

## <a name="durationmin"></a><a name="min"></a>продолжительность:мин

Статический метод, который возвращает нижнюю границу значений типа параметра-шаблона `Ref`.

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `duration(duration_values<rep>::min())`.

## <a name="durationoperator-"></a><a name="operator-"></a>продолжительность::оператор-

Возвращает копию объекта `duration` вместе с отрицательным счетчиком тактов.

```cpp
constexpr duration operator-() const;
```

## <a name="durationoperator--"></a><a name="operator--"></a>продолжительность:оператор--

Уменьшает на единицу накопленный счетчик тактов.

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый метод возвращает `*this`.

Второй метод возвращает копию `*this`, сделанную до уменьшения значения.

## <a name="durationoperator"></a><a name="op_eq"></a>продолжительность::оператор

Уменьшает накопленный счетчик тактов по модулю на указанное значение.

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Параметры

*Div*\
Для первого метода *Div* представляет количество тиков. Для второго *Div* метода `duration` Div — это объект, содержащий количество тиков.

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после выполнения операции по модулю.

## <a name="durationoperator"></a><a name="op_star_eq"></a>продолжительность::оператор

Умножает накопленный счетчик тактов на указанное значение.

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>Параметры

*Мульт*\
Значение типа, которое задается параметром `duration::rep`.

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после выполнения умножения.

## <a name="durationoperator"></a><a name="op_div_eq"></a>продолжительность:оператор/з.

Делит накопленный счетчик тактов на указанное значение.

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>Параметры

*Div*\
Значение типа, которое задается параметром `duration::rep`.

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после выполнения деления.

## <a name="durationoperator"></a><a name="op_add"></a>продолжительность::оператор

Возвращает `*this`.

```cpp
constexpr duration operator+() const;
```

## <a name="durationoperator"></a><a name="op_add_add"></a>продолжительность:оператор

Увеличивает на единицу накопленный счетчик тактов.

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый метод возвращает `*this`.

Второй метод возвращает копию `*this`, сделанную до увеличения значения.

## <a name="durationoperator"></a><a name="op_add_eq"></a>продолжительность::оператор

Добавляет счетчик тактов указанного объекта `duration` к накопленному счетчику тактов.

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Параметры

*Dur*\
Объект `duration` .

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после добавления.

## <a name="durationoperator-"></a><a name="operator-_eq"></a>продолжительность:оператор-я

Вычитает счетчик тактов указанного объекта `duration` из накопленного счетчика тактов.

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Параметры

*Dur*\
Объект `duration` .

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после вычитания.

## <a name="durationzero"></a><a name="zero"></a>продолжительность::ноль

Возвращает `duration(duration_values<rep>::zero())`.

```cpp
static constexpr duration zero();
```

## <a name="durationoperator-mod"></a><a name="op_mod_eq"></a>продолжительность::оператор мод

Уменьшает накопленный счетчик тактов по модулю на Div или Div.count().

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Параметры

*Div*\
Делитель, который является либо объектом длительности, либо значением, представляющим значение счетчика тактов.

### <a name="remarks"></a>Remarks

Первая функция-член уменьшает накопленный счетчик тактов по модулю на Div и возвращает *this. Вторая функция-член уменьшает накопленный счетчик тактов по модулю на Div.count() и возвращает \*this.

## <a name="see-also"></a>См. также раздел

[Справка по файлам заголовка](../standard-library/cpp-standard-library-header-files.md)\
[\<хроно>](../standard-library/chrono.md)\
[Структура duration_values](../standard-library/duration-values-structure.md)
