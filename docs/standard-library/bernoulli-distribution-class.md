---
title: Класс bernoulli_distribution
ms.date: 11/04/2016
f1_keywords:
- random/std::bernoulli_distribution
- random/std::bernoulli_distribution::reset
- random/std::bernoulli_distribution::p
- random/std::bernoulli_distribution::param
- random/std::bernoulli_distribution::min
- random/std::bernoulli_distribution::max
- random/std::bernoulli_distribution::operator()
- random/std::bernoulli_distribution::param_type
- random/std::bernoulli_distribution::param_type::p
- random/std::bernoulli_distribution::param_type::operator==
- random/std::bernoulli_distribution::param_type::operator!=
helpviewer_keywords:
- std::bernoulli_distribution [C++]
- std::bernoulli_distribution [C++], reset
- std::bernoulli_distribution [C++], p
- std::bernoulli_distribution [C++], param
- std::bernoulli_distribution [C++], min
- std::bernoulli_distribution [C++], max
- std::bernoulli_distribution [C++], param_type
- std::bernoulli_distribution [C++], param_type
ms.assetid: 586bcde1-95ca-411a-bf17-4aaf19482f34
ms.openlocfilehash: 6a53707d823ced7316604f75691194dc6e05545e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364859"
---
# <a name="bernoulli_distribution-class"></a>Класс bernoulli_distribution

Формирует распределение Бернулли.

## <a name="syntax"></a>Синтаксис

```cpp
class bernoulli_distribution
   {
public:
   // types
   typedef bool result_type;
   struct param_type;

   // constructors and reset functions
   explicit bernoulli_distribution(double p = 0.5);
   explicit bernoulli_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   double p() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Параметры

*Ргсч*\
Единый генератор случайных чисел. Для возможных типов см [ \<>. ](../standard-library/random.md)

## <a name="remarks"></a>Remarks

Класс описывает распределение, которое производит значения типа **bool**, распределенные в соответствии с функцией дискретной вероятности распределения Bernoulli. В следующей таблице представлены ссылки на статьи об отдельных членах.

||||
|-|-|-|
|[bernoulli_distribution](#bernoulli_distribution)|`bernoulli_distribution::p`|`bernoulli_distribution::param`|
|`bernoulli_distribution::operator()`||[param_type](#param_type)|

Член свойства `p()` возвращает текущее значение хранимого параметра распределения `p`.

Член свойства `param()` устанавливает или возвращает хранимый пакет параметров распределения `param_type`.

Функции-члены `min()` и `max()` возвращают наименьший и наибольший из возможных результатов соответственно.

Функция-член `reset()` удаляет любые кэшированные значения, чтобы результат следующего вызова `operator()` не зависел от любых значений, полученных от механизма перед вызовом.

Функции-члены `operator()` возвращают следующее значение, созданное механизмом РГСЧ, из текущего или указанного пакета параметров.

Для получения дополнительной информации о классах распределения и их членах [ \<>](../standard-library/random.md)см.

Дополнительные сведения о дискретной функции вероятности распределения Бернулли см. в статье [Распределение Бернулли](https://go.microsoft.com/fwlink/p/?linkid=398467).

## <a name="example"></a>Пример

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double p, const int s) {

    // uncomment to use a non-deterministic seed
    //    std::random_device rd;
    //    std::mt19937 gen(rd());
    std::mt19937 gen(1729);

    std::bernoulli_distribution distr(p);

    std::cout << "p == " << distr.p() << std::endl;

    // generate the distribution as a histogram
    std::map<bool, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Histogram for " << s << " samples:" << std::endl;
    for (const auto& elem : histogram) {
        std::cout << std::boolalpha << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    double p_dist = 0.5;
    int samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a double value for p distribution (where 0.0 <= p <= 1.0): ";
    std::cin >> p_dist;
    std::cout << "Enter an integer value for a sample count: ";
    std::cin >> samples;

    test(p_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .45
Enter an integer value for a sample count: 100
p == 0.45
Histogram for 100 samples:
false :::::::::::::::::::::::::::::::::::::::::::::::::::::::::::
true :::::::::::::::::::::::::::::::::::::::::
```

## <a name="requirements"></a>Требования

**Заголовок:** \<random>

**Пространство имен:** std

## <a name="bernoulli_distributionbernoulli_distribution"></a><a name="bernoulli_distribution"></a>bernoulli_distribution::bernoulli_distribution

Формирует распределение.

```cpp
explicit bernoulli_distribution(double p = 0.5);
explicit bernoulli_distribution(const param_type& parm);
```

### <a name="parameters"></a>Параметры

*P*\
Хранимый параметр распределения `p`.

*парм*\
Структура `param_type`, используемая для формирования распределения.

### <a name="remarks"></a>Remarks

**Предварительное условие:**`0.0 ≤ p ≤ 1.0`

Первый конструктор создает объект, хранимое значение `p` которого содержит значение *p*.

Второй конструктор создает объект, хранимые параметры которого инициализируются из *parm*. Вы можете получить и задать текущие параметры существующего распределения, вызвав функцию-член `param()`.

## <a name="bernoulli_distributionparam_type"></a><a name="param_type"></a>bernoulli_distribution::pараматип

Содержит параметры распределения.

структурировать param_type - typedef bernoulli_distribution distribution_type; param_type (двойной р 0,5); двойной р() конст;

   bool operator==(const param_type& right) const; bool operator!=(const param_type& right) const; };

### <a name="parameters"></a>Параметры

*P*\
Хранимый параметр распределения `p`.

### <a name="remarks"></a>Remarks

**Предварительное условие:**`0.0 ≤ p ≤ 1.0`

Эту структуру можно передать конструктору класса распределения во время создания экземпляра, функции-члену `param()` для установки хранимых параметров существующего распределения и `operator()` для использования вместо хранимых параметров.

## <a name="see-also"></a>См. также раздел

[\<случайные>](../standard-library/random.md)
