---
title: "/ Zc: rvaluecast (принудительное применение правил преобразования типов) | Документы Microsoft"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9e2223176082a2252dd410af4012ace31c14267
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (принудительное применение правил преобразования типов)

Когда **/Zc: rvaluecast** параметр указан, компилятор правильно определяет ссылочный тип rvalue как результат операции приведения в соответствии с C ++ 11 standard. Если этот параметр не задан, поведение компилятора является таким же, как в Visual Studio 2012.

## <a name="syntax"></a>Синтаксис

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>Примечания

Если **/Zc: rvaluecast** указан, компилятор следует разделу 5.4 стандарте C ++ 11 и рассматривает только выражения приведения, привести не ссылочными типами и выражения приведения, дающие ссылки rvalue на типы, не являющихся функциями как типы rvalue. По умолчанию или если **/Zc:rvalueCast-** указан, компилятор не соответствует стандарту и рассматривает все выражения приведения, дающие ссылки rvalue, как значения rvalue. Для соответствия, а также во избежание ошибок при использовании приведений, рекомендуется использовать **/Zc: rvaluecast**.

По умолчанию **/Zc: rvaluecast** отключено (**/Zc:rvalueCast-**). [/ Разрешительным-](permissive-standards-conformance.md) параметр компилятора неявно устанавливает этот параметр, но его можно переопределить с помощью **/Zc:rvalueCast-**.

Используйте **/Zc: rvaluecast** при передаче выражения приведения в качестве аргумента функции, которая принимает ссылочный тип rvalue. Поведение по умолчанию вызывает ошибку компилятора [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) Если компилятор неправильно определяет тип выражения приведения. В этом примере показана ошибка компилятора в правильный код при **/Zc: rvaluecast** не указан:

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

По умолчанию компилятор может не сообщать об ошибке C2102, когда это необходимо. В этом примере компилятор не сообщает об ошибке, если принимается адрес rvalue, созданного путем приведения идентификатора, если **/Zc: rvaluecast** не указан:

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

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** включив **/Zc: rvaluecast** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
