---
title: Auto (C++)
ms.date: 11/04/2016
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
ms.openlocfilehash: 8af2aceb2964a5ec3adcbb0b0accab0b051ff48c
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303388"
---
# <a name="auto-c"></a>Auto (C++)

Выводит тип объявленной переменной из выражения инициализации.

## <a name="syntax"></a>Синтаксис

```
auto declarator initializer;
```

```
[](auto param1, auto param2) {};
```

## <a name="remarks"></a>Заметки

Ключевое слово **Auto** направляет компилятору использование выражения инициализации объявленной переменной или параметра лямбда-выражения, чтобы вывести его тип.

Рекомендуется использовать ключевое слово **Auto** для большинства ситуаций, если только не требуется преобразование, так как оно предоставляет следующие преимущества:

- **Надежность.** Если тип выражения изменился (в том числе если изменен возвращаемый тип функции), это не влияет на его работу.

- **Эффективность.** Преобразование гарантированно не будет выполнено.

- **Удобство использования:** Не нужно беспокоиться о неправильном написании имени типа и опечатке.

- **Эффективность.** Быстрое написание кода.

Варианты преобразования, в которых может не потребоваться использовать **Auto**:

- Если необходимо получить конкретный тип.

- Вспомогательные типы шаблонов выражений, например `(valarray+valarray)`.

Чтобы использовать ключевое слово **Auto** , используйте его вместо типа для объявления переменной и укажите выражение инициализации. Кроме того, можно изменить ключевое слово **Auto** , используя описатели и деклараторы, такие как **const**, **volatile**, указатель (`*`), Reference (`&`) и ссылку rvalue (`&&`). Компилятор вычисляет выражение инициализации, а затем использует эти сведения, чтобы вывести тип переменной.

Выражением инициализации может быть присваивание (синтаксис равенства-знака), прямая инициализация (синтаксис в стиле функции), выражение [оператора New](new-operator-cpp.md) или выражение инициализации может быть параметром *объявления for-Range* в операторе [на основе диапазона для оператора (C++)](../cpp/range-based-for-statement-cpp.md) . Дополнительные сведения см. в статье [Инициализаторы](../cpp/initializers.md), а также в примерах кода в этом документе.

Ключевое слово **Auto** — это заполнитель для типа, но сам по себе он не является типом. Поэтому ключевое слово **Auto** не может использоваться в приведениях или операторах, таких как [sizeof](../cpp/sizeof-operator.md) и C++(for/CLI) [typeid](../extensions/typeid-cpp-component-extensions.md).

## <a name="usefulness"></a>Удобство

Ключевое слово **Auto** — это простой способ объявления переменной, имеющей сложный тип. Например, можно использовать функцию **Auto** для объявления переменной, в которой выражение инициализации включает шаблоны, указатели на функции или указатели на члены.

Можно также использовать **Auto** для объявления и инициализации переменной в лямбда-выражении. Вы не сможете самостоятельно объявить тип переменной, поскольку тип лямбда-выражения известен только компилятору. Дополнительные сведения см. в статье [Примеры лямбда-выражений](../cpp/examples-of-lambda-expressions.md).

## <a name="trailing-return-types"></a>Отслеживание возвращаемых типов

Для создания библиотек шаблонов можно использовать **Auto**вместе с описателем типа **decltype** . Используйте **auto** и **decltype** для объявления функции-шаблона, тип возвращаемого значения которой зависит от типов ее шаблонных аргументов. Или используйте **Auto** и **decltype** для объявления функции-шаблона, которая создает оболочку для вызова другой функции, а затем возвращает все, что является типом возвращаемого значения этой функции. Дополнительные сведения см. в разделе [decltype](../cpp/decltype-cpp.md).

## <a name="references-and-cv-qualifiers"></a>Ссылки и cv-квалификаторы

Обратите внимание, что при использовании ссылок **Auto** , квалификаторы Const и временные квалификаторы. Рассмотрим следующий пример.

```cpp
// cl.exe /analyze /EHsc /W4
#include <iostream>

using namespace std;

int main( )
{
    int count = 10;
    int& countRef = count;
    auto myAuto = countRef;

    countRef = 11;
    cout << count << " ";

    myAuto = 12;
    cout << count << endl;
}
```

В предыдущем примере Мяуто является типом int, а не ссылкой на int, поэтому выходные данные `11 11`, а не `11 12` как в случае, если квалификатор ссылки не был удален **Auto**.

## <a name="type-deduction-with-braced-initializers-c14"></a>Выведение типа с инициализаторами в фигурных скобках (C++ 14)

В следующем примере кода показано, как инициализировать автоматическую переменную с помощью фигурных скобок. Обратите внимание на разницу между B и C и между A и E.

```cpp
#include <initializer_list>

int main()
{
    // std::initializer_list<int>
    auto A = { 1, 2 };

    // std::initializer_list<int>
    auto B = { 3 };

    // int
    auto C{ 4 };

    // C3535: cannot deduce type for 'auto' from initializer list'
    auto D = { 5, 6.7 };

    // C3518 in a direct-list-initialization context the type for 'auto'
    // can only be deduced from a single initializer expression
    auto E{ 8, 9 };

    return 0;
}
```

## <a name="restrictions-and-error-messages"></a>Ограничения и сообщения об ошибках

В следующей таблице перечислены ограничения на использование ключевого слова **Auto** и соответствующее сообщение об ошибке диагностики, выдаваемое компилятором.

|Номер ошибки|Описание|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|Ключевое слово **Auto** не может использоваться вместе с любым другим описателем типа.|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|Символ, объявленный с ключевым словом **Auto** , должен иметь инициализатор.|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|Неправильно использовалось ключевое слово **Auto** для объявления типа. Например, был объявлен тип возвращаемого значения метода или массив.|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Параметр или аргумент шаблона не может быть объявлен с ключевым словом **Auto** .|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Невозможно объявить метод или параметр шаблона с ключевым словом **Auto** .|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Символ не может быть использован до инициализации. Практически это означает, что переменную нельзя использовать для инициализации самой себя.|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|Нельзя привести к типу, объявленному с ключевым словом **Auto** .|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|Все символы в списке деклараторов, объявленном с ключевым словом **Auto** , должны разрешаться в один и тот же тип. Дополнительные сведения см. в разделе [объявления и определения](declarations-and-definitions-cpp.md).|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|Операторы [sizeof](../cpp/sizeof-operator.md) и [typeid](../extensions/typeid-cpp-component-extensions.md) нельзя применять к символам, объявленным с помощью ключевого слова **Auto** .|

## <a name="examples"></a>Примеры

Эти фрагменты кода иллюстрируют некоторые способы использования ключевого слова **Auto** .

Следующие объявления эквивалентны. В первой инструкции переменная `j` объявлена как тип **int**. Во второй инструкции переменная `k` выведена как тип **int** , поскольку выражение инициализации (0) является целым числом.

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

Следующие объявления эквивалентны, но второе объявление проще первого. Одной из наиболее интересных причин использования ключевого слова **Auto** является простота.

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

В следующем фрагменте кода объявляется тип переменных `iter` и `elem` при запуске циклов **for** и Range **for** .

```cpp
// cl /EHsc /nologo /W4
#include <deque>
using namespace std;

int main()
{
    deque<double> dqDoubleData(10, 0.1);

    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)
    { /* ... */ }

    // prefer range-for loops with the following information in mind
    // (this applies to any range-for with auto, not just deque)

    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples
    { /* ... */ }

    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE
    { /* ... */ }

    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE
    { /* ... */ }
}
```

В следующем фрагменте кода для объявления указателей используется **Новый** оператор и объявление указателя.

```cpp
double x = 12.34;
auto *y = new auto(x), **z = new auto(&x);
```

В следующем примере кода объявлено несколько символов в каждом операторе объявления. Обратите внимание, что все символы во всех операторах разрешаются к одному и тому же типу.

```cpp
auto x = 1, *y = &x, **z = &y; // Resolves to int.
auto a(2.01), *b (&a);         // Resolves to double.
auto c = 'a', *d(&c);          // Resolves to char.
auto m = 1, &n = m;            // Resolves to int.
```

В этом примере кода используется условный оператор (`?:`). Переменная `x` здесь объявляется как целочисленная переменная со значением 200.

```cpp
int v1 = 100, v2 = 200;
auto x = v1 > v2 ? v1 : v2;
```

Следующий фрагмент кода инициализирует переменную `x` для типа **int**, Variable `y` в ссылку на тип **const int**, а переменная `fp` указатель на функцию, возвращающую тип **int**.

```cpp
int f(int x) { return x; }
int main()
{
    auto x = f(0);
    const auto& y = f(1);
    int (*p)(int x);
    p = f;
    auto fp = p;
    //...
}
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../cpp/auto-keyword.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[/Zc:auto (выведение типа переменной)](../build/reference/zc-auto-deduce-variable-type.md)<br/>
[Оператор sizeof](../cpp/sizeof-operator.md)<br/>
[typeid](../extensions/typeid-cpp-component-extensions.md)<br/>
[оператор new](new-operator-cpp.md)<br/>
[Объявления и определения](declarations-and-definitions-cpp.md)<br/>
[Примеры лямбда-выражений](../cpp/examples-of-lambda-expressions.md)<br/>
[Инициализаторы](../cpp/initializers.md)<br/>
[decltype](../cpp/decltype-cpp.md)
