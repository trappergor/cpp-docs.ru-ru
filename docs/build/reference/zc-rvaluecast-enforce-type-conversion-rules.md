---
title: /Zc:rvalueCast (принудительное применение правил преобразования типов)
ms.date: 02/18/2020
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
ms.openlocfilehash: ac74192cad8a62e4c82b480038e727b114362cdd
ms.sourcegitcommit: b9aaaebe6e7dc5a18fe26f73cc7cf5fce09262c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504576"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (принудительное применение правил преобразования типов)

Если указан параметр **`/Zc:rvalueCast`** , компилятор правильно определяет ссылочный тип rvalue в результате операции приведения. Его поведение соответствует стандарту C++ 11. Если параметр не указан, поведение компилятора будет таким же, как в Visual Studio 2012.

## <a name="syntax"></a>Синтаксис

> **`/Zc:rvalueCast`**\
> **`/Zc:rvalueCast-`**

## <a name="remarks"></a>Примечания

Если указан параметр **`/Zc:rvalueCast`** , компилятор следует за разделом 5,4 стандарта c++ 11 и обрабатывает только выражения приведения, которые приводят к нессылочным типам и выражениям приведения, результатом которых являются ссылки rvalue на типы, не являющиеся функциями, в качестве типов rvalue. По умолчанию или, если указан **`/Zc:rvalueCast-`** , компилятор не выполняет согласование и обрабатывает все выражения приведения, результатом которых являются ссылки rvalue, как rvalues. Для соответствия и исключения ошибок при использовании приведений рекомендуется использовать **`/Zc:rvalueCast`** .

По умолчанию **`/Zc:rvalueCast`** отключена ( **`/Zc:rvalueCast-`** ). Параметр компилятора [/permissive-](permissive-standards-conformance.md) неявно задает этот параметр, но его можно переопределить с помощью **`/Zc:rvalueCast-`** .

Используйте **`/Zc:rvalueCast`** , если передается выражение приведения в качестве аргумента функции, принимающей ссылочный тип rvalue. Поведение по умолчанию приводит к ошибке компилятора [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) , когда компилятор неправильно определяет тип выражения приведения. В этом примере показана ошибка компилятора в правильном коде, если **`/Zc:rvalueCast`** не указано:

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

По умолчанию компилятор может не сообщать об ошибке C2102, когда это необходимо. В этом примере компилятор не сообщает об ошибке, если указан адрес rvalue, созданный приведением удостоверения, если **`/Zc:rvalueCast`** не указано.

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

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **Свойства конфигурации** > странице свойств **язык** **CC++ /**  > .

1. Задайте для свойства **Применить правила преобразования типов** значение **`/Zc:rvalueCast`** или **`/Zc:rvalueCast-`** . Нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

## <a name="see-also"></a>См. также:

[/Zc (соответствие)](zc-conformance.md)
