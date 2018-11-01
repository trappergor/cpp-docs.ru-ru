---
title: /Zc:rvalueCast (принудительное применение правил преобразования типов)
ms.date: 03/06/2018
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
ms.openlocfilehash: 8e4be80d09ebf7f48795e01669610a0dc4f736d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648205"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (принудительное применение правил преобразования типов)

Когда **/Zc: rvaluecast** параметр указан, компилятор правильно определяет ссылочный тип rvalue в результате операции приведения в соответствии со стандартом C ++ 11. Если этот параметр не задан, поведение компилятора является таким же, как в Visual Studio 2012.

## <a name="syntax"></a>Синтаксис

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>Примечания

Если **/Zc: rvaluecast** указан, компилятор следует разделу 5.4 стандартом C ++ 11 и рассматривает только выражения приведения, дающие привести типы и выражения, которые приводят к ссылки rvalue на типы, функции, не являющейся приведения как типы rvalue. По умолчанию или если **/Zc:rvalueCast-** указан, компилятор не обеспечивает соответствие стандарту и рассматривает все выражения приведения, которые приводят к ссылки rvalue, как значения rvalue. Для соответствия требованиям, а также во избежание ошибок при использовании приведений, мы рекомендуем использовать **/Zc: rvaluecast**.

По умолчанию **/Zc: rvaluecast** отключен (**/Zc:rvalueCast-**). [/ Permissive-](permissive-standards-conformance.md) параметр компилятора неявно задает этот параметр, но его можно переопределить с помощью **/Zc:rvalueCast-**.

Используйте **/Zc: rvaluecast** при передаче выражения приведения в качестве аргумента в функцию, которая принимает ссылочный тип rvalue. Поведение по умолчанию приводит к ошибке компилятора [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) когда компилятор неправильно определяет тип выражения приведения. В этом примере показано ошибку компилятора в правильный код при **/Zc: rvaluecast** не указан:

```cpp
// Test of /Zc:rvalueCast
// compile by using:
// cl /c /Zc:rvalueCast- make_thing.cpp
// cl /c /Zc:rvalueCast make_thing.cpp

#include <utility>

template <typename T>
struct Thing {
   // Construct a Thing by using two rvalue reference parameters
   Thing(T&& t1, T&& t2)
      : thing1(t1), thing2(t2) {}

   T& thing1;
   T& thing2;
};

// Create a Thing, using move semantics if possible
template <typename T>
Thing<T> make_thing(T&& t1, T&& t2)
{
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));
}

struct Test1 {
   long a;
   long b;

   Thing<long> test() {
      // Use identity casts to create rvalues as arguments
      return make_thing(static_cast<long>(a), static_cast<long>(b));
   }
};
```

По умолчанию компилятор может не сообщать об ошибке C2102, когда это необходимо. В этом примере компилятор не сообщает об ошибке, если берется адрес rvalue, созданного путем приведения идентификатора, когда **/Zc: rvaluecast** не указан:

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Zc: rvaluecast** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
