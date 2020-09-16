---
title: constexpr (C++)
description: Пошаговое руководством по constexpr ключевому слову языка C++.
ms.date: 01/28/2020
f1_keywords:
- constexpr_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
no-loc:
- constexpr
- const
- inline
- goto
- try
- if
- switch
- for
- while
ms.openlocfilehash: 57ebf4bf69c768bfcd2e4d26a5c3334ca788b08f
ms.sourcegitcommit: a6b97f5d78299ad93675de2fe0f0561f528d26c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90569562"
---
# <a name="no-locconstexpr-c"></a>constexpr (C++)

Ключевое слово **`constexpr`** было введено в c++ 11 и улучшено в c++ 14. Это означает * const Ant выражение*. Например **`const`** , его можно применять к переменным: Ошибка компилятора возникает, когда любой код пытается пересчитать if значение y. В отличие от **`const`** , **`constexpr`** можно также применять к функциям и классу const рукторс. **`constexpr`** Указывает, что значение (или возвращаемое значение) является const Ant и, где возможно, вычислено во время компиляции.

**`constexpr`** Целочисленное значение можно использовать везде, где const требуется целое число, например в аргументах шаблона и в объявлениях массивов. Если значение вычислено во время компиляции, а не во время выполнения, оно помогает программе работать быстрее и использует меньше памяти.

Для ограничения сложности const вычислений Ant времени компиляции и их возможного влияния на время компиляции стандарт c++ 14 требует, чтобы типы в const выражениях Ant были [литеральными типами](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="syntax"></a>Синтаксис

> **`constexpr`***тип литерала* *Ident if Иер* **=** * const Ant-Expression* **;**\
> **`constexpr`***тип литерала* *Ident if Иер* **{** * const Ant-Expression* **}** **;**\
> **`constexpr`***тип литерала* *Ident if Иер* **(** *params* **)** **;**\
> **`constexpr`***ctor* **(** *params* **)** **;**

## <a name="parameters"></a>Параметры

*params*\
Один или несколько параметров, каждый из которых должен быть типом литерала и сам должен быть const выражением Ant.

## <a name="return-value"></a>Возвращаемое значение

**`constexpr`** Переменная или функция должна возвращать [литеральный тип](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="no-locconstexpr-variables"></a>Переменные constexpr

Основной d if -вывод между **`const`** **`constexpr`** переменными и заключается в том, что инициализация **`const`** переменной может быть отложена до времени выполнения. **`constexpr`** Переменная должна быть инициализирована во время компиляции.  Все **`constexpr`** переменные имеют значения **`const`** .

- Переменная может быть объявлена с **`constexpr`** , если она имеет литеральный тип и инициализирована. Если инициализация задается для for MED с помощью const руктор, const руктор должен быть объявлен как **`constexpr`** .

- Ссылка может быть объявлена как **`constexpr`** при выполнении обоих этих условий: объект, на который указывает ссылка, инициализируется const выражением Ant, а любые неявные преобразования, вызванные во время инициализации, также const Ant выражениями.

- Все объявления **`constexpr`** переменной или функции должны иметь **`constexpr`** спецификацию if Иер.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="no-locconstexpr-functions"></a>Функции <a name="constexpr_functions"></a> constexpr

**`constexpr`** Функция — это одна из функций, возвращаемое значение которой вычисляемым во время компиляции, если это требуется для использования кода. Для использования кода требуется возвращаемое значение во время компиляции для инициализации **`constexpr`** переменной или для предоставления аргумента шаблона, не являющегося типом. Если его аргументы являются **`constexpr`** значениями, **`constexpr`** функция создает Ant времени компиляции const . При вызове с **`constexpr`** аргументами, отличными от аргументов, или когда его значение не требуется во время компиляции, оно создает значение во время выполнения, например обычную функцию. (Это двойное поведение избавляет от необходимости писать **`constexpr`** и не использовать **`constexpr`** версии одной и той же функции.)

**`constexpr`** Функция или const руктор являются неявными **`inline`** .

К функциям применяются следующие правила constexpr .

- **`constexpr`** Функция должна принимать и возвращать только [типы литералов](trivial-standard-layout-and-pod-types.md#literal_types).

- **`constexpr`** Функция может быть рекурсивной.

- Он не может быть [виртуальным](../cpp/virtual-cpp.md). constРуктор не может быть определен, как **`constexpr`** Если включающий класс имеет какие-либо виртуальные базовые классы.

- Тело может быть определено как `= default` или `= delete`.

- Текст не может содержать **`goto`** операторы или **`try`** блоки.

- Явная специализация не **`constexpr`** шаблона может быть объявлена следующим образом **`constexpr`** :

- Явная специализация **`constexpr`** шаблона также не должна быть такой **`constexpr`** :

К **`constexpr`** функциям в Visual Studio 2017 и более поздних версий применяются следующие правила.

- Он может содержать **`if`** **`switch`** инструкции и, а также все операторы цикла, включая **`for`** , основанные на диапазонах **`for`** , **`while`** и **Do- while **.

- Он может содержать объявления локальных переменных, но переменная должна быть инициализирована. Он должен быть типом литерала и не может быть **`static`** или локальным потоком. Локально объявленная переменная не обязательно должна быть **`const`** и может изменяться.

- Функция, не относящаяся **`constexpr`** **`static`** к члену, не обязательно должна быть неявно **`const`** .

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
}
```

> [!TIP]
> В отладчике Visual Studio при отладке неоптимизированной отладочной сборки можно определить, **`constexpr`** вычисляется ли функция во время компиляции, поместив в нее точку останова. Попадание в точку останова означает, что функция была вызвана во время выполнения.  Если попадания в точку останова не происходит, это означает, что функция была вызвана во время компиляции.

## <a name="extern-no-locconstexpr"></a>Название constexpr

Параметр компилятора [/Zc: externConstexpr](../build/reference/zc-externconstexpr.md) заставляет компилятор применить [внешнюю компоновку](../c-language/external-linkage.md) к переменным, объявленным с **помощью constexpr модификатора extern **. В более ранних версиях Visual Studio либо по умолчанию, либо при использовании параметра **/Zc: externConstexpr-** Spec if Иед, Visual Studio применяет внутреннюю компоновку к **`constexpr`** переменным, даже если **`extern`** используется ключевое слово. Параметр **/Zc: externConstexpr** доступен начиная с Visual Studio 2017 с обновлением 15,6 и по умолчанию отключен. Параметр [/permissive-](../build/reference/permissive-standards-conformance.md) не включает **/Zc: externConstexpr**.

## <a name="example"></a>Пример

В следующем примере показаны **`constexpr`** переменные, функции и определяемый пользователем тип. В последней инструкции в `main()` **`constexpr`** функция `GetValue()` -член является вызовом во время выполнения, поскольку значение не обязательно должно быть известно во время компиляции.

```cpp
// constexpr.cpp
// Compile with: cl /EHsc /W4 constexpr.cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
}

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
}

// Compile-time computation of array length
template<typename T, int N>
constexpr int length(const T(&)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue() const
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>Требования

Visual Studio 2015 или более поздней версии.

## <a name="see-also"></a>См. также

[Объявления и определения](../cpp/declarations-and-definitions-cpp.md)\
[const](../cpp/const-cpp.md)
