---
title: constexpr (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- constexpr_cpp
dev_langs:
- C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b9479957fdfb4d6b92ec531941808940765a9e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116728"
---
# <a name="constexpr-c"></a>constexpr (C++)

Ключевое слово **constexpr** была представлена в C ++ 11 и было усовершенствовано в C ++ 14. Это означает *константное выражение*. Как и **const**, он может применяться к переменным таким образом, если любой код пытается изменить значение формируется ошибка компилятора. В отличие от **const**, **constexpr** могут также применяться к функциям и конструкторам классов. **constexpr** указывает, что значение, то возвращаемое значение является константой и, если это возможно, будет вычисляться во время компиляции.

Объект **constexpr** целочисленное значение может использоваться везде, где const integer является обязательным, например в аргументах шаблонов и объявлениях массивов. И, если значение может быть вычислено во время компиляции, а не время выполнения, он может позволить программе работать быстрее и использовать меньше памяти.

Чтобы ограничить сложность вычислений константы времени компиляции и их последствиях времени компиляции, стандартом C ++ 14 требует, чтобы типы, применяемые в константных выражениях был ограничен [типы литералов](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="syntax"></a>Синтаксис

```
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);
```

## <a name="parameters"></a>Параметры

*params*<br/>
Один или несколько параметров, которые должны относиться к типу литерала, а сами должны быть константным выражением.

## <a name="return-value"></a>Возвращаемое значение

Переменная или функция constexpr должна возвращать [типа литерала](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="constexpr-variables"></a>переменные constexpr

Основное различие между переменными const и constexpr заключается в том, что инициализация переменной const может быть отложена до времени выполнения, тогда как переменная constexpr должна быть инициализирована во время компиляции.  Все переменные constexpr относятся к типу const.

- Переменная может быть объявлен с **constexpr**, если он имеет тип литерала и инициализирована. Если инициализация выполняется конструктором, конструктор должен объявляться как **constexpr**.

- Ссылка может быть объявлена как constexpr, если объект, на который она ссылается, был инициализирован с помощью константного выражения, а любые неявные преобразования, вызываемые во время инициализации, также являются константными выражениями.

- Все объявления **constexpr** переменной или функции должен иметь **constexpr** спецификатор.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a> функции constexpr

Объект **constexpr** функция является одним, возвращаемое значение может быть вычислено во компиляции, когда оно требуется коду-потребителю.  Если ее аргументы являются **constexpr** значения и кода-потребителя требуется возвращаемое значение во время компиляции, например для инициализации **constexpr** переменной или предоставления аргумента шаблона, не являющийся типом, он Создает константу времени компиляции. При вызове с отличным от**constexpr** аргументов, или если его значение не требуется во время компиляции, она формирует значение во время выполнения как обычную функцию.  (Такое двойственное поведение избавляет вас от необходимости писать **constexpr** и не-**constexpr** версии той же функции.)

Объект **constexpr** функция или конструктор является неявно **встроенного**.

В функциях constexpr применяются следующие правила:

- Объект **constexpr** функция должна принимать и возвращать только [типы литералов](trivial-standard-layout-and-pod-types.md#literal_types).

- Объект **constexpr** функции могут быть рекурсивными.

- Он не может быть [виртуального](../cpp/virtual-cpp.md). Объект конструктор не может быть определен как constexpr, если включающий класс содержит все виртуальные базовые классы.

- Тело может быть определено как `= default` или `= delete`.

- Текст может содержать нет **goto** операторов или блоков try.

- Явная специализация шаблона, не являющийся constexpr могут быть объявлены как **constexpr**:

- Явная специализация **constexpr** шаблона не обязательно также должна быть **constexpr**:

Следующие правила применяются к **constexpr** функций в Visual Studio 2017 и более поздних версий:

- Он может содержать **Если** и **переключения** инструкций и все операторы выполнения цикла включая **для**, основанных на диапазоне, **хотя**и **сделать-хотя**.

- Он может содержать объявления локальных переменных, но переменная должна быть инициализирована, должны относиться к типу литерала и не может быть статическим или локального потока. Локально объявленные переменной не обязана быть константой и может изменяется.

- Функция-член constexpr не требуется была явной константой.


```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Примечание: В отладчике Visual Studio при отладке не оптимизированы отладочное построение, видно ли **constexpr** функция будет вычисляться во время компиляции, поместив в нем точку останова. Попадание в точку останова означает, что функция была вызвана во время выполнения.  Если попадания в точку останова не происходит, это означает, что функция была вызвана во время компиляции.

## <a name="extern-constexpr"></a>extern constexpr

[/Zc: externconstexpr](../build/reference/zc-externconstexpr.md) компилятора предписывает компилятору для применения [внешнюю компоновку]() к переменным, объявленным с помощью **extern constexpr**. В более ранних версиях Visual Studio и по умолчанию или если **/Zc:externConstexpr-** указан, Visual Studio применяет внутреннюю компоновку для **constexpr** переменные, даже если **extern** используется ключевое слово. **/Zc: externconstexpr** параметр доступен, начиная с Visual Studio 2017 15.6 обновления. и по умолчанию отключены. / Zc: externconstexpr /permissive-option не включается.

## <a name="example"></a>Пример

В следующем примере показан **constexpr** переменные, функции и определяемого пользователем типа. Обратите внимание, что в последнем операторе в main() **constexpr** функция-член GetValue() является вызовом времени выполнения, поскольку значение не должен быть известен во время компиляции.

```cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile time computation of array length
template<typename T, int N>
constexpr int length(const T(&ary)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n*fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue()
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    //foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    //Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    //Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;

}
```

## <a name="requirements"></a>Требования

Visual Studio 2015

## <a name="see-also"></a>См. также

[Объявления и определения](../cpp/declarations-and-definitions-cpp.md)<br/>
[const](../cpp/const-cpp.md)
