---
title: '&lt;chrono&gt;'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::nanoseconds
- chrono/std::chrono::minutes
- chrono/std::chrono::seconds
- <chrono>
- chrono/std::chrono::hours
- chrono/std::chrono::milliseconds
- chrono/std::chrono::microseconds
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
ms.openlocfilehash: 1fcf87d84b2c99b89217b7f2e0fc7fecd55fff02
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331481"
---
# <a name="ltchronogt"></a>&lt;chrono&gt;

Включите стандартный заголовок \<chrono> для определения классов и функций, которые представляют интервалы и моменты времени и работают с ними.

Начиная с Visual Studio 2015, реализация `steady_clock` был изменен в соответствии с требованиями равномерности и монотонности стандарта C++. `steady_clock` теперь основан на функции QueryPerformanceCounter(), а `high_resolution_clock` теперь является определением типа для `steady_clock`. В результате в Visual C++ `steady_clock::time_point` теперь является определением типа для `chrono::time_point<steady_clock>`, однако в других реализациях это может быть не так.

## <a name="syntax"></a>Синтаксис

```cpp
#include <chrono>
```

### <a name="classes"></a>Классы

|Имя|Описание|
|----------|-----------------|
|[Класс duration](../standard-library/duration-class.md)|Описывает тип, содержащий интервал времени.|
|[Класс time_point](../standard-library/time-point-class.md)|Описывает тип, представляющий момент времени.|

### <a name="structs"></a>структурам;

|name|Описание|
|----------|-----------------|
|[Структура common_type](../standard-library/common-type-structure.md)|Описывает специализации класса шаблона [common_type](../standard-library/common-type-class.md) для создания экземпляров `duration` и `time_point`.|
|[Структура duration_values](../standard-library/duration-values-structure.md)|Предоставляет конкретные значения для параметра `Rep` шаблона `duration`.|
|[Структура steady_clock](../standard-library/steady-clock-struct.md)|Представляет часы `steady`.|
|[Структура system_clock](../standard-library/system-clock-structure.md)|Представляет *тип clock*, использующий данные системных часов в реальном времени.|
|[Структура treat_as_floating_point](../standard-library/treat-as-floating-point-structure.md)|Указывает, может ли тип рассматриваться как тип с плавающей запятой.|

### <a name="functions"></a>Функции

|Имя|Описание|
|----------|-----------------|
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|Приводит объект `duration` к указанному типу.|
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|Приводит объект `time_point` к указанному типу.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|----------|-----------------|
|[operator-](../standard-library/chrono-operators.md#operator-)|Оператор вычитания или отрицания объектов `duration` и `time_point`.|
|[operator!=](../standard-library/chrono-operators.md#op_neq)|Оператор неравенства, используемый с объектами `duration` или `time_point`.|
|[operator modulo](../standard-library/chrono-operators.md#op_modulo)|Оператор для операций вычисления остатка от деления над объектами `duration`.|
|[operator*](../standard-library/chrono-operators.md#op_star)|Оператор умножения для объектов `duration`.|
|[оператор/](../standard-library/chrono-operators.md#op_div)|Оператор деления для объектов `duration`.|
|[operator+](../standard-library/chrono-operators.md#op_add)|Складывает объекты `duration` и `time_point`.|
|[operator&lt;](../standard-library/chrono-operators.md#op_lt)|Определяет, справедливо ли, что один из объектов `duration` или `time_point` меньше, чем другой объект `duration` или `time_point`.|
|[operator&lt;=](../standard-library/chrono-operators.md#op_lt_eq)|Определяет, справедливо ли, что один из объектов `duration` или `time_point` меньше или равен другому объекту `duration` или `time_point`.|
|[operator==](../standard-library/chrono-operators.md#op_eq_eq)|Определяет, справедливо ли, что два объекта `duration` представляют интервалы времени, имеющие одинаковую длину, или, что два объекта `time_point` представляют один и тот же момент времени.|
|[оператор&gt;](../standard-library/chrono-operators.md#op_gt)|Определяет, справедливо ли, что один из объектов `duration` или `time_point` больше, чем другой объект `duration` или `time_point`.|
|[operator&gt;=](../standard-library/chrono-operators.md#op_gt_eq)|Определяет, справедливо ли, что один из объектов `duration` или `time_point` больше или равен другому объекту `duration` или `time_point`.|

### <a name="predefined-duration-types"></a>Предопределенные типы длительности

Дополнительные сведения о типах отношения, используемых в следующих определениях типов, см. в разделе [\<ratio>](../standard-library/ratio.md).

|Typedef|Описание|
|-------------|-----------------|
|`typedef duration<long long, nano> nanoseconds;`|Синоним для типа `duration` с тактовым периодом равным 1 наносекунде.|
|`typedef duration<long long, micro> microseconds;`|Синоним для типа `duration` с тактовым периодом равным 1 микросекунде.|
|`typedef duration<long long, milli> milliseconds;`|Синоним для типа `duration` с тактовым периодом равным 1 миллисекунде.|
|`typedef duration<long long> seconds;`|Синоним для типа `duration` с тактовым периодом равным 1 секунде.|
|`typedef duration<int, ratio<60> > minutes;`|Синоним для типа `duration` с тактовым периодом равным 1 минуте.|
|`typedef duration<int, ratio<3600> > hours;`|Синоним для типа `duration` с тактовым периодом равным 1 часу.|

### <a name="literals"></a>Литералы

**(C ++ 11)**  \<Chrono > заголовок определяет следующие [определенные пользователем литералы](../cpp/user-defined-literals-cpp.md) можно использовать для удобства, типобезопасности и обслуживаемости кода. Такие литералы определяются во встроенном пространстве имен `literals::chrono_literals` и находятся в области действия, когда std::chrono находится в области действия.

|Литерал|Описание|
|-------------|-----------------|
|chrono::hours operator "" h(unsigned long long Val)|Указывает часы как целочисленное значение.|
|chrono::Duration\<двойным, соотношением\<3600 >> оператор «» h (long double Val)|Указывает часы как значение с плавающей запятой.|
|chrono::minutes (operator "" min)(unsigned long long Val)|Указывает минуты как целочисленное значение.|
|chrono::Duration\<двойным, соотношением\<60 >> (оператор «» min) (long двойной Val)|Указывает минуты как значение с плавающей запятой.|
|chrono::seconds operator "" s(unsigned long long Val)|Указывает минуты как целочисленное значение.|
|chrono::duration\<double> operator "" s(long double Val)|Указывает секунды как значение с плавающей запятой.|
|chrono::milliseconds operator "" ms(unsigned long long Val)|Указывает миллисекунды как целочисленное значение.|
|chrono::duration\<double, milli> operator "" ms(long double Val)|Указывает миллисекунды как значение с плавающей запятой.|
|chrono::microseconds operator "" us(unsigned long long Val)|Указывает микросекунды как целочисленное значение.|
|chrono::duration\<double, micro> operator "" us(long double Val)|Указывает микросекунды как значение с плавающей запятой.|
|chrono::nanoseconds operator "" ns(unsigned long long Val)|Указывает наносекунды как целочисленное значение.|
|chrono::duration\<double, nano> operator "" ns(long double Val)|Указывает наносекунды как значение с плавающей запятой.|
|||

В следующем примере демонстрируется использование литералов chrono.

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```

## <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
