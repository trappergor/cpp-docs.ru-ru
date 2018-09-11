---
title: Класс piecewise_constant_distribution | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::piecewise_constant_distribution
- random/std::piecewise_constant_distribution::reset
- random/std::piecewise_constant_distribution::intervals
- random/std::piecewise_constant_distribution::densities
- random/std::piecewise_constant_distribution::param
- random/std::piecewise_constant_distribution::min
- random/std::piecewise_constant_distribution::max
- random/std::piecewise_constant_distribution::operator()
- random/std::piecewise_constant_distribution::param_type
- random/std::piecewise_constant_distribution::param_type::intervals
- random/std::piecewise_constant_distribution::param_type::densities
- random/std::piecewise_constant_distribution::param_type::operator==
- random/std::piecewise_constant_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::piecewise_constant_distribution [C++]
- std::piecewise_constant_distribution [C++], reset
- std::piecewise_constant_distribution [C++], intervals
- std::piecewise_constant_distribution [C++], densities
- std::piecewise_constant_distribution [C++], param
- std::piecewise_constant_distribution [C++], min
- std::piecewise_constant_distribution [C++], max
- std::piecewise_constant_distribution [C++], param_type
- std::piecewise_constant_distribution [C++], param_type
ms.assetid: 2c9a21fa-623e-4d63-b827-3f1556b6dedb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c2b4c93604a95b4c2d73c69a834ab6724bd9193
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103949"
---
# <a name="piecewiseconstantdistribution-class"></a>Класс piecewise_constant_distribution

Формирует кусочно-постоянное распределение с меняющимися интервалами ширины и одинаковой вероятностью в каждом интервале.

## <a name="syntax"></a>Синтаксис

```cpp
template<class RealType = double>
class piecewise_constant_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;

   // constructor and reset functions
   piecewise_constant_distribution();
   template <class InputIteratorI, class InputIteratorW>
   piecewise_constant_distribution(
       InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);
   template <class UnaryOperation>
   piecewise_constant_distribution(
      initializer_list<result_type> intervals, UnaryOperation weightfunc);
   template <class UnaryOperation>
   piecewise_constant_distribution(
      size_t count, result_type xmin, result_type xmax, UnaryOperation weightfunc);
   explicit piecewise_constant_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   vector<result_type> intervals() const;
   vector<result_type> densities() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Параметры

*RealType*<br/>
С плавающей запятой тип результата, по умолчанию — **двойные**. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

## <a name="remarks"></a>Примечания

Выборочное распределение использует меняющиеся интервалы ширины с одинаковой вероятностью в каждом интервале. Сведения о других выборочных распределениях см. в разделах [piecewise_linear_distribution](../standard-library/piecewise-linear-distribution-class.md) и [discrete_distribution](../standard-library/discrete-distribution-class.md).

В следующей таблице представлены ссылки на статьи об отдельных членах.

||||
|-|-|-|
|[piecewise_constant_distribution](#piecewise_constant_distribution)|`piecewise_constant_distribution::intervals`|`piecewise_constant_distribution::param`|
|`piecewise_constant_distribution::operator()`|`piecewise_constant_distribution::densities`|[param_type](#param_type)|

Функция свойства `intervals()` возвращает значение типа `vector<result_type>` с набором хранимых интервалов распределения.

Функция свойства `densities()` возвращает значение типа `vector<result_type>` с хранимыми плотностями для каждого набора интервалов, которые вычисляются в соответствии с весами, заданными в параметрах конструктора.

Член свойства `param()` устанавливает или возвращает хранимый пакет параметров распределения `param_type`.

Функции-члены `min()` и `max()` возвращают наименьший и наибольший из возможных результатов соответственно.

Функция-член `reset()` удаляет любые кэшированные значения, чтобы результат следующего вызова `operator()` не зависел от любых значений, полученных от механизма перед вызовом.

Функции-члены `operator()` возвращают следующее значение, созданное механизмом РГСЧ, из текущего или указанного пакета параметров.

Дополнительные сведения о классах распределения и их членах см. в разделе [\<random>](../standard-library/random.md).

## <a name="example"></a>Пример

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

using namespace std;

void test(const int s) {

    // uncomment to use a non-deterministic generator
    // random_device rd;
    // mt19937 gen(rd());
    mt19937 gen(1701);

    // Three intervals, non-uniform: 0 to 1, 1 to 6, and 6 to 15
    vector<double> intervals{ 0, 1, 6, 15 };
    // weights determine the densities used by the distribution
    vector<double> weights{ 1, 5, 10 };

    piecewise_constant_distribution<double> distr(intervals.begin(), intervals.end(), weights.begin());

    cout << endl;
    cout << "min() == " << distr.min() << endl;
    cout << "max() == " << distr.max() << endl;
    cout << "intervals (index: interval):" << endl;
    vector<double> i = distr.intervals();
    int counter = 0;
    for (const auto& n : i) {
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;
        ++counter;
    }
    cout << endl;
    cout << "densities (index: density):" << endl;
    vector<double> d = distr.densities();
    counter = 0;
    for (const auto& n : d) {
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;
        ++counter;
    }
    cout << endl;

    // generate the distribution as a histogram
    map<int, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    cout << "Distribution for " << s << " samples:" << endl;
    for (const auto& elem : histogram) {
        cout << setw(5) << elem.first << '-' << elem.first+1 << ' ' << string(elem.second, ':') << endl;
    }
    cout << endl;
}

int main()
{
    int samples = 100;

    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;
    cout << "Enter an integer value for the sample count: ";
    cin >> samples;

    test(samples);
}

```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for the sample count: 100
min() == 0
max() == 15
intervals (index: interval):
          0:   0.0000000000
          1:   1.0000000000
          2:   6.0000000000
          3:  15.0000000000
densities (index: density):
          0:   0.0625000000
          1:   0.0625000000
          2:   0.0694444444
Distribution for 100 samples:
    0-1 :::::::
    1-2 ::::::
    2-3 :::::
    3-4 ::::::
    4-5 :::::::
    5-6 ::::::
    6-7 :::
    7-8 ::::::::::
    8-9 ::::::
    9-10 ::::::::::::
    10-11 :::::
    11-12 ::::::
    12-13 :::::::::
    13-14 ::::
    14-15 ::::::::
```

## <a name="requirements"></a>Требования

**Заголовок:** \<random>

**Пространство имен:** std

## <a name="piecewise_constant_distribution"></a>  piecewise_constant_distribution::piecewise_constant_distribution

Формирует распределение.

```cpp
// default constructor
piecewise_constant_distribution();

// constructs using a range of intervals, [firstI, lastI), with
// matching weights starting at firstW
template <class InputIteratorI, class InputIteratorW>
piecewise_constant_distribution(InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);

// constructs using an initializer list for range of intervals,
// with weights generated by function weightfunc
template <class UnaryOperation>
piecewise_constant_distribution(initializer_list<RealType>
intervals, UnaryOperation weightfunc);

// constructs using an initializer list for range of count intervals,
// distributed uniformly over [xmin,xmax] with weights generated by function weightfunc
template <class UnaryOperation>
piecewise_constant_distribution(size_t count, RealType xmin, RealType xmax, UnaryOperation weightfunc);

// constructs from an existing param_type structure
explicit piecewise_constant_distribution(const param_type& parm);
```

### <a name="parameters"></a>Параметры

*firstI*<br/>
Итератор ввода первого элемента в диапазоне распределения.

*lastI*<br/>
Итератор ввода последнего элемента в диапазоне распределения.

*firstW*<br/>
Итератор ввода первого элемента в диапазоне весов.

*intervals*<br/>
Объект [initializer_list](../cpp/initializers.md) с интервалами распределения.

*count*<br/>
Количество элементов в диапазоне распределения.

*xmin*<br/>
Минимальное значение в диапазоне распределения.

*xmax*<br/>
Максимальное значение в диапазоне распределения. Должно быть больше, чем *xmin*.

*weightfunc*<br/>
Объект, представляющий функцию вероятности распределения. Параметр и возвращаемое значение должно быть преобразуемым в **двойные**.

*parm*<br/>
Структура параметров, используемая для формирования распределения.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию задает хранимые параметры таким образом, чтобы существовал один интервал от 0 до 1 с плотностью вероятности 1.

Конструктор диапазона итератора
```cpp
template <class InputIteratorI, class InputIteratorW>
piecewise_constant_distribution(InputIteratorI firstI, InputIteratorI lastI,
    InputIteratorW firstW);
```

создает объект распределения с интервалами от итераторов в последовательности [`firstI`, `lastI`) и соответствующей последовательности весов начиная с `firstW`.

Конструктор списка инициализаторов
```cpp
template <class UnaryOperation>
piecewise_constant_distribution(initializer_list<result_type>
intervals,
    UnaryOperation weightfunc);
```

Создает объект распределения с интервалами из списка инициализаторов *интервалы* и весами из функции *weightfunc*.

Конструктор, определенный как
```cpp
template <class UnaryOperation>
piecewise_constant_distribution(size_t count, result_type xmin, result_type xmax,
    UnaryOperation weightfunc);
```

Создает объект распределения с *число* интервалов, равномерно распределенных по [ `xmin,xmax`], вес каждого интервала в соответствии с функцией *weightfunc*, и  *weightfunc* должна принимать один параметр и должны иметь возвращаемого значения, которые могут быть преобразованы `double`. **Предусловие:** `xmin < xmax`

Конструктор, определенный как
```cpp
explicit piecewise_constant_distribution(const param_type& parm);
```

Создает объект распределения, используя *parm* как сохраненную структуру параметров.

## <a name="param_type"></a>  piecewise_constant_distribution::param_type

Сохраняет все параметры распределения.

```cpp
struct param_type {
   typedef piecewise_constant_distribution<result_type> distribution_type;
   param_type();
   template <class IterI, class IterW>
   param_type(IterI firstI, IterI lastI, IterW firstW);
   template <class UnaryOperation>
   param_type(size_t count, result_type xmin, result_type xmax, UnaryOperation weightfunc);
   std::vector<result_type> densities() const;
   std::vector<result_type> intervals() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Параметры

Параметры конструктора см. в разделе [piecewise_constant_distribution](#piecewise_constant_distribution).

### <a name="remarks"></a>Примечания

**Предусловие:** `xmin < xmax`

Эту структуру можно передать конструктору класса распределения во время создания экземпляра, функции-члену `param()` для установки хранимых параметров существующего распределения и `operator()` для использования вместо хранимых параметров.

## <a name="see-also"></a>См. также

[\<random>](../standard-library/random.md)<br/>
[piecewise_linear_distribution](../standard-library/piecewise-linear-distribution-class.md)<br/>
