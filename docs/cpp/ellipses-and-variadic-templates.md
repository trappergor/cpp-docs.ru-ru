---
title: Эллипсис и вариадские шаблоны
ms.date: 11/04/2016
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
ms.openlocfilehash: 8326a6b9e75db6adc37a68aa5d5741b004d27d30
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031528"
---
# <a name="ellipsis-and-variadic-templates"></a>Эллипсис и вариадские шаблоны

В этой статье показано, как использовать многоточие (`...`) в шаблонах C++ с переменным числом аргументов. Многоточие активно использовалось в C и C++. Они вводят переменные списки аргументов для функций. Одним из наиболее известных примеров является функция `printf()` из библиотеки времени выполнения C .

*Валиадический шаблон* — это шаблон класса или функции, который поддерживает произвольное количество аргументов. Этот механизм особенно удобен для разработчиков библиотек C++, поскольку его можно применить к как к шаблонам классов, так и к шаблонам функций. Таким образом, он предоставляет широкий спектр широкий спектр типобезопасных и нетривиальных функций и гибких возможностей.

## <a name="syntax"></a>Синтаксис

В шаблонах шаблонами с переменным числом аргументов многоточие используется двумя способами. Слева от имени параметра, он означает *пакет параметров,* а справа от имени параметра, он расширяет параметр пакеты в отдельные имена.

Вот основной пример синтаксиса определения *класса вазиады шаблонов:*

```cpp
template<typename... Arguments> class classname;
```

В обоих случаях (как при введении пакета параметров, так и при его развертывании) вокруг многоточия можно оставить пробельные символы, как показано в этом примере:

```cpp
template<typename ...Arguments> class classname;
```

или

```cpp
template<typename ... Arguments> class classname;
```

Обратите внимание, что в этой статье используется соглашение, показанное в первом примере (многоточие примыкает к имени типа — `typename`).

В предыдущих *примерах Аргументы* — это пакет параметров. Класс `classname` может принимать переменное число аргументов, как показано в следующих примерах:

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
vtclass<long, std::vector<int>, std::string> vtinstance4;
```

Кроме того, определение шаблонного класса с переменным числом аргументов может устанавливать требование о том, что должен быть передан по меньшей мере один параметр:

```cpp
template <typename First, typename... Rest> class classname;
```

Вот основной пример синтаксиса *функции вазиады шаблона:*

```cpp
template <typename... Arguments> returntype functionname(Arguments... args);
```

Пакет *параметров Аргументы* затем расширяется для использования, как показано в следующем разделе, **Понимание вазиадных шаблонов.**

Возможны и другие формы синтаксиса шаблонной функции с переменным количеством аргументов возможны. Некоторые примеры приведены ниже.

```cpp
template <typename... Arguments> returntype functionname(Arguments&... args);
template <typename... Arguments> returntype functionname(Arguments&&... args);
template <typename... Arguments> returntype functionname(Arguments*... args);
```

Специфика, как **const** также допускается:

```cpp
template <typename... Arguments> returntype functionname(const Arguments&... args);
```

Шаблонные функции с переменным числом аргументов (как и аналогичные шаблонные классы) также могут устанавливать требование о том, что должен быть передан по меньшей мере один параметр.

```cpp
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);
```

В шаблонах с переменным числом аргументов используется оператор `sizeof...()` (он не имеет отношения к старому оператору `sizeof()`).

```cpp
template<typename... Arguments>
void tfunc(const Arguments&... args)
{
    constexpr auto numargs{ sizeof...(Arguments) };

    X xobj[numargs]; // array of some previously defined type X

    helper_func(xobj, args...);
}
```

## <a name="more-about-ellipsis-placement"></a>Дополнительные сведения о положении многоточия

Выше в этой статье говорилось, что если многоточие определяет пакеты параметров и их развертывание, то "Слева от имени параметра оно означает пакет параметров, а справа от имени параметра оно служит для развертывания пакетов параметров в отдельные имена". Технически это верно, но может порождать неоднозначности при трансляции в код. Попробуйте следующее:

- В шаблон-параметр-список `typename...` ( ,`template <parameter-list>`вводит пакет параметров шаблона.

- В параметр-декларации-клаузу (),`func(parameter-list)`"верхний уровень" эллипс вводит пакет параметров функции, и позиционирование эллипсиса имеет важное значение:

    ```cpp
    // v1 is NOT a function parameter pack:
    template <typename... Types> void func1(std::vector<Types...> v1);

    // v2 IS a function parameter pack:
    template <typename... Types> void func2(std::vector<Types>... v2);
    ```

- Там, где многоточие стоит непосредственно за именем параметра, оно используется для развертывания пакета параметров.

## <a name="example"></a>Пример

Механизм действия шаблонных функций с переменным числом аргументов можно проиллюстрировать на показательном примере — переписать с ее использованием какую-либо функциональность `printf`:

```cpp
#include <iostream>

using namespace std;

void print() {
    cout << endl;
}

template <typename T> void print(const T& t) {
    cout << t << endl;
}

template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {
    cout << first << ", ";
    print(rest...); // recursive call using pack expansion syntax
}

int main()
{
    print(); // calls first overload, outputting only a newline
    print(1); // calls second overload

    // these call the third overload, the variadic template,
    // which uses recursion as needed.
    print(10, 20);
    print(100, 200, 300);
    print("first", 2, "third", 3.14159);
}
```

## <a name="output"></a>Выходные данные

```Output
1
10, 20
100, 200, 300
first, 2, third, 3.14159
```

> [!NOTE]
> Большинство реализаций, которые включают вариативные функции шаблона, используют рекурсию той или иной формы, но она немного отличается от традиционной рекурсии.  Традиционная рекурсия включает в себя функцию, вызывая себя с помощью той же подписи. (Она может быть перегружена или шаблонизирована, но каждый раз выбирается один и тот же выбор.) Вариадная рекурсия включает в себя вызов шаблона вазиадической функции, используя различные (почти всегда уменьшающиеся) числа аргументов, и тем самым каждый раз искореняя другую подпись. "Базовый случай" по-прежнему является обязательным, но природа рекурсии отличается.
