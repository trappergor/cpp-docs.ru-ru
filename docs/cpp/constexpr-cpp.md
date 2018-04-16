---
title: constexpr (C++) | Документы Microsoft
ms.custom: ''
ms.date: 04/06/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- constexpr_cpp
dev_langs:
- C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
caps.latest.revision: 3
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fdf0a4794dd32208b08791d921f6d638873545a1
ms.sourcegitcommit: d9ee6f777974d031570f4260c9581ea2c81ad875
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2018
---
# <a name="constexpr-c"></a>constexpr (C++)

Ключевое слово **constexpr** была введена в C ++ 11 и было усовершенствовано в C ++ 14. Это означает *константное выражение*. Как **const**, он может применяться к переменным, если код пытается изменить значение формируется ошибка компилятора. В отличие от **const**, **constexpr** также может применяться к функциям и конструкторам классов. **constexpr** указывает, что значение или возвращаемое значение является константой и, если это возможно, будет вычислено во время компиляции.

Объект **constexpr** целочисленное значение, которое можно использовать везде, где требуется const integer, например в аргументах шаблонов и объявлениях массивов. И, если значение может быть вычислено во время компиляции, а не во время выполнения, он может позволить программе работать быстрее и использовать меньше памяти.

Для ограничения сложности вычислительных константы времени компиляции и их влияния на время компиляции, стандартом C ++ 14 требует, чтобы типы, применяемые в константных выражениях был ограничен [типы литералов](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="syntax"></a>Синтаксис

```
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);
```

## <a name="parameters"></a>Параметры

 *params*  
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

## <a name="constexpr-functions"></a>функции constexpr

Объект **constexpr** функцией называется функция, возвращаемое значение может быть вычислено во время компиляции, когда код необходимо.  Если ее аргументы являются **constexpr** значения и кода-потребителя требуется возвращаемое значение во время компиляции, например для инициализации **constexpr** переменной или предоставления аргумента шаблона, не являющегося типом, он Создает константу времени компиляции. При вызове отличным от**constexpr** аргументов, или если его значение не требуется во время компиляции, она создает значение во время выполнения, как и обычные функции.  (Такое двойственное поведение избавляет от необходимости писать **constexpr** и не-**constexpr** версий одной функции.)

Объект **constexpr** функция или конструктор является неявно **встроенного**.

В функции constexpr применяются следующие правила:

- Объект **constexpr** функция должна принимать и возвращать только [типы литералов](trivial-standard-layout-and-pod-types.md#literal_types).

- Объект **constexpr** функции могут быть рекурсивными.

- Он не может быть [виртуальный](../cpp/virtual-cpp.md). Объект конструктора не может быть определен как constexpr, если включающий класс содержит все виртуальные базовые классы.

- Текст может быть определена как **= значение по умолчанию** или **= удаление**.

- Текст может содержать нет **goto** инструкций или блоков try.

- Явная специализация шаблона, не являющийся constexpr могут быть объявлены как **constexpr**:

- Явная специализация **constexpr** шаблона не должен также быть **constexpr**:

Следующие правила применяются к **constexpr** функций в Visual Studio 2017 г. и более поздних версий:

- Он может содержать **Если** и **переключения** инструкций и все операторы цикла включая **для**, на основе диапазонов, **пока**и **сделать-пока**.
 
- Он может содержать объявления локальных переменных, но переменной должны инициализироваться, должны относиться к типу литерала и не может быть статическими или локальными для потока. Локально объявленные переменной не обязательно const и может изменить.

- Функция-член constexpr не обязательно неявно const.


```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Примечание: В отладчике Visual Studio при отладке не оптимизированы отладочное построение, можно определить, является ли **constexpr** функция вычисляется во время компиляции, поместив в нем точку останова. Попадание в точку останова означает, что функция была вызвана во время выполнения.  Если попадания в точку останова не происходит, это означает, что функция была вызвана во время компиляции.

## <a name="extern-constexpr"></a>extern constexpr

[/Zc:externConstexpr](../build/reference/zc-externconstexpr.md) параметр компилятора указывает компилятору на необходимость применения [внешней компоновки]() к переменным, объявленным с помощью **extern constexpr**. В более ранних версиях Visual Studio и по умолчанию или если **/Zc:externConstexpr-** указан, Visual Studio применяет внутренней компоновки для **constexpr** переменных, даже если **extern** используется ключевое слово. **/Zc:externConstexpr** параметр доступен, начиная с Visual Studio 2017 г. обновление 15,6. и по умолчанию отключена. /Permissive-option не включает /Zc:externConstexpr.

## <a name="example"></a>Пример

 В следующем примере показан **constexpr** переменных, функций и определяемых пользователем типов. Обратите внимание, что в последнем операторе в main() **constexpr** функции-члена GetValue() является вызовом времени выполнения, так как значение не требуется быть известно во время компиляции.

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

- [Объявления и определения](../cpp/declarations-and-definitions-cpp.md)
- [const](../cpp/const-cpp.md)
