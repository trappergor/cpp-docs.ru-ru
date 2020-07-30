---
title: ':::no-loc(constexpr)::: (C++)'
description: 'Пошаговое руководством по :::no-loc(constexpr)::: ключевому слову языка C++.'
ms.date: 01/28/2020
f1_keywords:
- :::no-loc(constexpr):::_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
no-loc:
- ':::no-loc(constexpr):::'
- ':::no-loc(const):::'
- ':::no-loc(inline):::'
- ':::no-loc(goto):::'
- ':::no-loc(try):::'
- ':::no-loc(if):::'
- ':::no-loc(switch):::'
- ':::no-loc(for):::'
- ':::no-loc(while):::'
ms.openlocfilehash: d66dc333b7ac9fba94221dc4efa723c7919ef88f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229029"
---
# <a name="no-locconstexpr-c"></a>:::no-loc(constexpr)::: (C++)

Ключевое слово **`:::no-loc(constexpr):::`** было введено в c++ 11 и улучшено в c++ 14. Это означает * :::no-loc(const)::: Ant выражение*. Например **`:::no-loc(const):::`** , его можно применять к переменным: Ошибка компилятора возникает, когда любой код пытается пересчитать :::no-loc(if)::: значение y. В отличие от **`:::no-loc(const):::`** , **`:::no-loc(constexpr):::`** можно также применять к функциям и классу :::no-loc(const)::: рукторс. **`:::no-loc(constexpr):::`** Указывает, что значение (или возвращаемое значение) является :::no-loc(const)::: Ant и, где возможно, вычислено во время компиляции.

**`:::no-loc(constexpr):::`** Целочисленное значение можно использовать везде, где :::no-loc(const)::: требуется целое число, например в аргументах шаблона и в объявлениях массивов. Если значение вычислено во время компиляции, а не во время выполнения, оно помогает программе работать быстрее и использует меньше памяти.

Для ограничения сложности :::no-loc(const)::: вычислений Ant времени компиляции и их возможного влияния на время компиляции стандарт c++ 14 требует, чтобы типы в :::no-loc(const)::: выражениях Ant были [литеральными типами](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="syntax"></a>Синтаксис

> **`:::no-loc(constexpr):::`***тип литерала* *Ident :::no-loc(if)::: Иер* **=** * :::no-loc(const)::: Ant-Expression* **;**\
> **`:::no-loc(constexpr):::`***тип литерала* *Ident :::no-loc(if)::: Иер* **{** * :::no-loc(const)::: Ant-Expression* **}** **;**\
> **`:::no-loc(constexpr):::`***тип литерала* *Ident :::no-loc(if)::: Иер* **(** *params* **)** **;**\
> **`:::no-loc(constexpr):::`***ctor* **(** *params* **)** **;**

## <a name="parameters"></a>Параметры

*params*\
Один или несколько параметров, каждый из которых должен быть типом литерала и сам должен быть :::no-loc(const)::: выражением Ant.

## <a name="return-value"></a>Возвращаемое значение

**`:::no-loc(constexpr):::`** Переменная или функция должна возвращать [литеральный тип](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="no-locconstexpr-variables"></a>Переменные :::no-loc(constexpr):::

Основной d :::no-loc(if)::: -вывод между **`:::no-loc(const):::`** **`:::no-loc(constexpr):::`** переменными и заключается в том, что инициализация **`:::no-loc(const):::`** переменной может быть отложена до времени выполнения. **`:::no-loc(constexpr):::`** Переменная должна быть инициализирована во время компиляции.  Все **`:::no-loc(constexpr):::`** переменные имеют значения **`:::no-loc(const):::`** .

- Переменная может быть объявлена с **`:::no-loc(constexpr):::`** , если она имеет литеральный тип и инициализирована. Если инициализация задается для :::no-loc(for)::: MED с помощью :::no-loc(const)::: руктор, :::no-loc(const)::: руктор должен быть объявлен как **`:::no-loc(constexpr):::`** .

- Ссылка может быть объявлена как **`:::no-loc(constexpr):::`** при выполнении обоих этих условий: объект, на который указывает ссылка, инициализируется :::no-loc(const)::: выражением Ant, а любые неявные преобразования, вызванные во время инициализации, также :::no-loc(const)::: Ant выражениями.

- Все объявления **`:::no-loc(constexpr):::`** переменной или функции должны иметь **`:::no-loc(constexpr):::`** спецификацию :::no-loc(if)::: Иер.

```cpp
:::no-loc(constexpr)::: float x = 42.0;
:::no-loc(constexpr)::: float y{108};
:::no-loc(constexpr)::: float z = exp(5, 3);
:::no-loc(constexpr)::: int i; // Error! Not initialized
int j = 0;
:::no-loc(constexpr)::: int k = j + 1; //Error! j not a :::no-loc(const):::ant expression
```

## <a name="no-locconstexpr-functions"></a><a name=":::no-loc(constexpr):::_functions"></a>:::no-loc(constexpr):::функции

**`:::no-loc(constexpr):::`** Функция — это одна из функций, возвращаемое значение которой вычисляемым во время компиляции, если это требуется для использования кода. Для использования кода требуется возвращаемое значение во время компиляции для инициализации **`:::no-loc(constexpr):::`** переменной или для предоставления аргумента шаблона, не являющегося типом. Если его аргументы являются **`:::no-loc(constexpr):::`** значениями, **`:::no-loc(constexpr):::`** функция создает Ant времени компиляции :::no-loc(const)::: . При вызове с **`:::no-loc(constexpr):::`** аргументами, отличными от аргументов, или когда его значение не требуется во время компиляции, оно создает значение во время выполнения, например обычную функцию. (Это двойное поведение избавляет от необходимости писать **`:::no-loc(constexpr):::`** и не использовать **`:::no-loc(constexpr):::`** версии одной и той же функции.)

**`:::no-loc(constexpr):::`** Функция или :::no-loc(const)::: руктор являются неявными **`:::no-loc(inline):::`** .

К функциям применяются следующие правила :::no-loc(constexpr)::: .

- **`:::no-loc(constexpr):::`** Функция должна принимать и возвращать только [типы литералов](trivial-standard-layout-and-pod-types.md#literal_types).

- **`:::no-loc(constexpr):::`** Функция может быть рекурсивной.

- Он не может быть [виртуальным](../cpp/virtual-cpp.md). :::no-loc(const):::Руктор не может быть определен, как **`:::no-loc(constexpr):::`** Если включающий класс имеет какие-либо виртуальные базовые классы.

- Тело может быть определено как `= default` или `= delete`.

- Текст не может содержать **`:::no-loc(goto):::`** операторы или **`:::no-loc(try):::`** блоки.

- Явная специализация не **`:::no-loc(constexpr):::`** шаблона может быть объявлена следующим образом **`:::no-loc(constexpr):::`** :

- Явная специализация **`:::no-loc(constexpr):::`** шаблона также не должна быть такой **`:::no-loc(constexpr):::`** :

К **`:::no-loc(constexpr):::`** функциям в Visual Studio 2017 и более поздних версий применяются следующие правила.

- Он может содержать **`:::no-loc(if):::`** **`:::no-loc(switch):::`** инструкции и, а также все операторы цикла, включая **`:::no-loc(for):::`** , основанные на диапазонах **`:::no-loc(for):::`** , **`:::no-loc(while):::`** и **Do- :::no-loc(while)::: **.

- Он может содержать объявления локальных переменных, но переменная должна быть инициализирована. Он должен быть типом литерала и не может быть **`static`** или локальным потоком. Локально объявленная переменная не обязательно должна быть **`:::no-loc(const):::`** и может изменяться.

- Функция, не относящаяся **`:::no-loc(constexpr):::`** **`static`** к члену, не обязательно должна быть неявно **`:::no-loc(const):::`** .

```cpp
:::no-loc(constexpr)::: float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> В отладчике Visual Studio при отладке неоптимизированной отладочной сборки можно определить, **`:::no-loc(constexpr):::`** вычисляется ли функция во время компиляции, поместив в нее точку останова. Попадание в точку останова означает, что функция была вызвана во время выполнения.  Если попадания в точку останова не происходит, это означает, что функция была вызвана во время компиляции.

## <a name="extern-no-locconstexpr"></a>Название:::no-loc(constexpr):::

Параметр компилятора [/Zc: externConstexpr](../build/reference/zc-extern:::no-loc(constexpr):::.md) заставляет компилятор применить [внешнюю компоновку](../c-language/external-linkage.md) к переменным, объявленным с **помощью :::no-loc(constexpr)::: модификатора extern **. В более ранних версиях Visual Studio либо по умолчанию, либо при использовании параметра **/Zc: externConstexpr-** Spec :::no-loc(if)::: Иед, Visual Studio применяет внутреннюю компоновку к **`:::no-loc(constexpr):::`** переменным, даже если **`extern`** используется ключевое слово. Параметр **/Zc: externConstexpr** доступен начиная с Visual Studio 2017 с обновлением 15,6 и по умолчанию отключен. Параметр [/permissive-](../build/reference/permissive-standards-con:::no-loc(for):::mance.md) не включает **/Zc: externConstexpr**.

## <a name="example"></a>Пример

В следующем примере показаны **`:::no-loc(constexpr):::`** переменные, функции и определяемый пользователем тип. В последней инструкции в `main()` **`:::no-loc(constexpr):::`** функция `GetValue()` -член является вызовом во время выполнения, поскольку значение не обязательно должно быть известно во время компиляции.

```cpp
// :::no-loc(constexpr):::.cpp
// Compile with: cl /EHsc /W4 :::no-loc(constexpr):::.cpp
#include <iostream>

using namespace std;

// Pass by value
:::no-loc(constexpr)::: float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
:::no-loc(constexpr)::: float exp2(:::no-loc(const)::: float& x, :::no-loc(const)::: int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile-time computation of array length
template<typename T, int N>
:::no-loc(constexpr)::: int length(:::no-loc(const)::: T(&)[N])
{
    return N;
}

// Recursive :::no-loc(constexpr)::: function
:::no-loc(constexpr)::: int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    :::no-loc(constexpr)::: explicit Foo(int i) : _i(i) {}
    :::no-loc(constexpr)::: int GetValue() :::no-loc(const):::
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is :::no-loc(const)::::
    :::no-loc(constexpr)::: Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    :::no-loc(constexpr)::: float x = exp(5, 3);
    :::no-loc(constexpr)::: float y { exp(2, 5) };
    :::no-loc(constexpr)::: int val = foo.GetValue();
    :::no-loc(constexpr)::: int f5 = fac(5);
    :::no-loc(const)::: int nums[] { 1, 2, 3, 4 };
    :::no-loc(const)::: int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>Требования

Visual Studio 2015 или более поздней версии.

## <a name="see-also"></a>См. также статью

[Объявления и определения](../cpp/declarations-and-definitions-cpp.md)\
[:::no-loc(const):::](../cpp/:::no-loc(const):::-cpp.md)
