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
ms.openlocfilehash: 49c68b1650ced36ebcf949ae2594508480e15136
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413805"
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

## <a name="remarks"></a>Примечания

Аргумент шаблона `Rep` описывает тип, используемый для удержания числа тактов в интервале. Аргумент шаблона `Period` — экземпляр [отношения](../standard-library/ratio.md), описывающий размер интервала, который представляет каждый такт.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|duration::period Typedef|Синоним для параметра-шаблона `Period`.|
|duration::rep Typedef|Синоним для параметра-шаблона `Rep`.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Длительность](#duration)|Создает объект `duration`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[count](#count)|Возвращает количество тактов в интервале времени.|
|[max](#max)|Статический. Возвращает максимальное допустимое значение параметра-шаблона `Ref`.|
|[min](#min)|Статический. Возвращает минимально допустимое значение параметра-шаблона `Ref`.|
|[ноль](#zero)|Статический. Фактически возвращает `Rep` (0).|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[duration::operator-](#operator-)|Возвращает копию объекта `duration` вместе с отрицательным счетчиком тактов.|
|[duration::operator--](#operator--)|Уменьшает на единицу накопленный счетчик тактов.|
|[duration::operator=](#op_eq)|Уменьшает накопленный счетчик тактов по модулю на указанное значение.|
|[duration::operator*=](#op_star_eq)|Умножает накопленный счетчик тактов на указанное значение.|
|[duration::operator/=](#op_div_eq)|Делит накопленный счетчик тактов на счетчик тактов указанного объекта `duration`.|
|[duration::operator+](#op_add)|Возвращает `*this`.|
|[duration::operator++](#op_add_add)|Увеличивает на единицу накопленный счетчик тактов.|
|[duration::operator+=](#op_add_eq)|Добавляет счетчик тактов указанного объекта `duration` к накопленному счетчику тактов.|
|[duration::operator-=](#operator-_eq)|Вычитает счетчик тактов указанного объекта `duration` из накопленного счетчика тактов.|

## <a name="requirements"></a>Требования

**Заголовок:** \<chrono >

**Пространство имен:** std::chrono

## <a name="count"></a>  duration::count

Получает количество тактов в интервале времени.

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тактов в интервале времени.

## <a name="duration"></a> Конструктор duration::duration

Создает объект `duration`.

```cpp
constexpr duration() = default;

template <class Rep2>
constexpr explicit duration(const Rep2& R);

template <class Rep2, class Period2>
constexpr duration(const duration<Rep2, Period2>& Dur);
```

### <a name="parameters"></a>Параметры

*Rep2*<br/>
Арифметический тип для представления числа тактов.

*Period2*<br/>
Специализация шаблона `std::ratio` для представления тактового периода в секундах.

*R*<br/>
Количество тактов в периоде по умолчанию.

*Длительность*<br/>
Количество тактов в течение указанного периода *Period2*.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию создает объект, который не инициализирован. Инициализация значения с помощью пустых фигурных скобок инициализирует объект, представляющий интервал времени нулевых тактов.

Во-вторых, аргументов шаблона 1, конструктор создает объект, представляющий интервал времени *R* тактов, используя период по умолчанию `std::ratio<1>`. Чтобы избежать округления значений счетчика тактов, считается ошибкой создание объекта длительности из типа представления *Rep2* , могут рассматриваться как с плавающей запятой типу при `duration::rep` не может рассматриваться как тип с плавающей запятой.

Третий, два шаблона аргумента конструктор создает объект, представляющий интервал времени, длина которого совпадает с интервала времени, который задается параметром *Dur*. Чтобы избежать усечения значений счетчика тактов, считается ошибкой создание объекта длительности из другого объекта длительности, тип которого *несоизмерим* с целевым типом.

Тип длительности `D1` *несоизмерим* с другим типом длительности `D2`, если `D2` не может рассматриваться как тип с плавающей запятой, а [ratio_divide\<D1::period, D2::period>::type::den](../standard-library/ratio.md) не равен 1.

Если не *Rep2* неявно преобразуется к типу `rep` и либо `treat_as_floating_point<rep>` *справедливо* или `treat_as_floating_point<Rep2>` *содержит значение false*, второй конструктор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

Если второй конструктор не участвует в разрешении перегрузки и `treat_as_floating_point<rep>`*не содержит значение true* или оба `ratio_divide<Period2, period>::den` не равны 1 и `treat_as_floating_point<Rep2>`*не содержит значение false*, третий конструктор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="max"></a>  duration::max

Статический метод, который возвращает верхнюю границу значений типа параметра-шаблона `Ref`.

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `duration(duration_values<rep>::max())`.

## <a name="min"></a>  duration::min

Статический метод, который возвращает нижнюю границу значений типа параметра-шаблона `Ref`.

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `duration(duration_values<rep>::min())`.

## <a name="operator-"></a>  duration::operator-

Возвращает копию объекта `duration` вместе с отрицательным счетчиком тактов.

```cpp
constexpr duration operator-() const;
```

## <a name="operator--"></a>  duration::operator--

Уменьшает на единицу накопленный счетчик тактов.

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый метод возвращает `*this`.

Второй метод возвращает копию `*this`, сделанную до уменьшения значения.

## <a name="op_eq"></a>  duration::operator=

Уменьшает накопленный счетчик тактов по модулю на указанное значение.

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Параметры

*ДИВ*<br/>
Для первого метода *Div* представляет счетчик тактов. Для второго метода *Div* является `duration` объект, который содержит счетчик тактов.

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после выполнения операции по модулю.

## <a name="op_star_eq"></a>  duration::operator*=

Умножает накопленный счетчик тактов на указанное значение.

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>Параметры

*Mult*<br/>
Значение типа, которое задается параметром `duration::rep`.

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после выполнения умножения.

## <a name="op_div_eq"></a>  duration::operator/=

Делит накопленный счетчик тактов на указанное значение.

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>Параметры

*ДИВ*<br/>
Значение типа, которое задается параметром `duration::rep`.

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после выполнения деления.

## <a name="op_add"></a>  duration::operator+

Возвращает `*this`.

```cpp
constexpr duration operator+() const;
```

## <a name="op_add_add"></a>  duration::operator++

Увеличивает на единицу накопленный счетчик тактов.

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый метод возвращает `*this`.

Второй метод возвращает копию `*this`, сделанную до увеличения значения.

## <a name="op_add_eq"></a>  duration::operator+=

Добавляет счетчик тактов указанного объекта `duration` к накопленному счетчику тактов.

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после выполнения сложения.

## <a name="operator-_eq"></a>  duration::operator-=

Вычитает счетчик тактов указанного объекта `duration` из накопленного счетчика тактов.

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` после выполнения вычитания.

## <a name="zero"></a>  duration::zero

Возвращает `duration(duration_values<rep>::zero())`.

```cpp
static constexpr duration zero();
```

## <a name="op_mod_eq"></a>  duration::operator mod=

Уменьшает накопленный счетчик тактов по модулю на Div или Div.count().

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Параметры

*ДИВ*<br/>
Делитель, который является либо объектом длительности, либо значением, представляющим значение счетчика тактов.

### <a name="remarks"></a>Примечания

Первая функция-член уменьшает накопленный счетчик тактов по модулю на Div и возвращает *this. Вторая функция-член уменьшает накопленный счетчик тактов по модулю на Div.count() и возвращает \*this.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
[Структура duration_values](../standard-library/duration-values-structure.md)<br/>
