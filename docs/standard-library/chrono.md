---
title: '&lt;chrono&gt;'
ms.date: 05/07/2019
f1_keywords:
- chrono/std::chrono::nanoseconds
- chrono/std::chrono::minutes
- chrono/std::chrono::seconds
- <chrono>
- chrono/std::chrono::hours
- chrono/std::chrono::milliseconds
- chrono/std::chrono::microseconds
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
ms.openlocfilehash: 72d16b068f337fe935d07e1eb2d0e2b74de6268f
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244866"
---
# <a name="ltchronogt"></a>&lt;chrono&gt;

Включите стандартный заголовок \<chrono> для определения классов и функций, которые представляют интервалы и моменты времени и работают с ними.

Начиная с Visual Studio 2015, реализация `steady_clock` был изменен в соответствии с требованиями равномерности и монотонности стандарта C++. `steady_clock` теперь основан на функции QueryPerformanceCounter(), а `high_resolution_clock` теперь является определением типа для `steady_clock`. Таким образом, в Microsoft C++ компилятора `steady_clock::time_point` теперь является typedef для `chrono::time_point<steady_clock>`, однако это правило не обязательно в случае других реализаций.

## <a name="requirements"></a>Требования

**Заголовок:** \<chrono >

**Пространство имен:** std

## <a name="members"></a>Участники

### <a name="classes"></a>Классы

|||
|-|-|
|[Класс duration](../standard-library/duration-class.md)|Описывает тип, содержащий интервал времени.|
|[Класс time_point](../standard-library/time-point-class.md)|Описывает тип, представляющий момент времени.|

### <a name="structs"></a>Структуры

|||
|-|-|
|[Структура common_type](../standard-library/common-type-structure.md)|Описывает специализации класса шаблона [common_type](../standard-library/common-type-class.md) для создания экземпляров `duration` и `time_point`.|
|[Структура duration_values](../standard-library/duration-values-structure.md)|Предоставляет конкретные значения для параметра `Rep` шаблона `duration`.|
|[high_resolution_clock структуры](../standard-library/high-resolution-clock-struct.md)||
|[Структура steady_clock](../standard-library/steady-clock-struct.md)|Представляет часы `steady`.|
|[Структура system_clock](../standard-library/system-clock-structure.md)|Представляет *тип clock*, использующий данные системных часов в реальном времени.|
|[Структура treat_as_floating_point](../standard-library/treat-as-floating-point-structure.md)|Указывает, может ли тип рассматриваться как тип с плавающей запятой.|

### <a name="functions"></a>Функции

|||
|-|-|
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|Приводит объект `duration` к указанному типу.|
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|Приводит объект `time_point` к указанному типу.|

### <a name="operators"></a>Операторы

|||
|-|-|
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

### <a name="typedefs-predefined-duration-types"></a>Определения типов (предопределенные типы длительности)

Дополнительные сведения о типах отношения, используемых в следующих определениях типов, см. в разделе [\<ratio>](../standard-library/ratio.md).

||| ||| | `typedef duration<long long, nano> nanoseconds;`| Синоним для `duration` типа, имеющего с тактовым периодом равным 1 наносекунды. | |`typedef duration<long long, micro> microseconds;`| Синоним для `duration` типа, имеющего с тактовым периодом равным 1 микросекунды. | |`typedef duration<long long, milli> milliseconds;`| Синоним для `duration` типа, имеющего с тактовым периодом равным 1 миллисекунде. | |`typedef duration<long long> seconds;`| Синоним для `duration` типа, имеющего с тактовым периодом равным 1 секунде. | |`typedef duration<int, ratio<60> > minutes;`| Синоним для `duration` тип, с тактовым периодом равным 1 минуте. | |`typedef duration<int, ratio<3600> > hours;`| Синоним для `duration` типа, имеющего с тактовым периодом равным 1 час. |

### <a name="literals"></a>Литералы

**(C ++ 11)**  \<Chrono > заголовок определяет следующие [определенные пользователем литералы](../cpp/user-defined-literals-cpp.md) можно использовать для более удобства, типобезопасности и обслуживаемости кода. Такие литералы определяются во встроенном пространстве имен `literals::chrono_literals` и находятся в области действия, когда std::chrono находится в области действия.

|||
|-|-|
|часы оператор «» h (unsigned long long Val)|Указывает часы как целочисленное значение.|
|длительность\<двойным, соотношением\<3600 >> оператор «» h (long double Val)|Указывает часы как значение с плавающей запятой.|
|минут (оператор «» min) (unsigned long long Val)|Указывает минуты как целочисленное значение.|
|длительность\<двойным, соотношением\<60 >> (оператор «» min) (long двойной Val)|Указывает минуты как значение с плавающей запятой.|
|оператор секунд «» s (unsigned long long Val)|Указывает минуты как целочисленное значение.|
|длительность\<double > оператор «» s (long double Val)|Указывает секунды как значение с плавающей запятой.|
|оператор миллисекунд «» мс (unsigned long long Val)|Указывает миллисекунды как целочисленное значение.|
|длительность\<double передачи > оператор «» мс (long double Val)|Указывает миллисекунды как значение с плавающей запятой.|
|оператор микросекундах» «США (unsigned long long Val)|Указывает микросекунды как целочисленное значение.|
|длительность\<double, micro > оператор «» нам (long double Val)|Указывает микросекунды как значение с плавающей запятой.|
|оператор наносекунд «» ns (unsigned long long Val)|Указывает наносекунды как целочисленное значение.|
|длительность\<double nano > оператор «» ns (long double Val)|Указывает наносекунды как значение с плавающей запятой.|

В следующем примере демонстрируется использование литералов chrono.

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
