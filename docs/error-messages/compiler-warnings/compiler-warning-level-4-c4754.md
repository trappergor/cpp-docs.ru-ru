---
title: Предупреждение компилятора (уровень 4) C4754 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4754
dev_langs:
- C++
helpviewer_keywords:
- C4754
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7681f78812ef33dce5bd6d7792f8158a8f35ce3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118665"
---
# <a name="compiler-warning-level-4-c4754"></a>Предупреждение компилятора (уровень 4) C4754

Правила преобразования арифметических операций в сравнении означает, что одна ветвь не может быть выполнена.

C4754 предупреждение в том случае, так как результат сравнения всегда одинаков. Это означает, что одно из ответвлений условие никогда не выполняется, скорее всего из-за неправильной связанные целочисленное выражение. Этот дефект кода часто происходит в проверки переполнения для целочисленных неверные на 64-разрядных архитектур.

Правила преобразования целого числа являются сложными и существует множество ловушек незначительные. В качестве альтернативы для исправлений C4754, можно обновить код, чтобы использовать [библиотека SafeInt](../../windows/safeint-library.md).

## <a name="example"></a>Пример

Этот пример приводит к возникновению ошибки C4754:

```cpp
// C4754a.cpp
// Compile with: /W4 /c
#include "errno.h"

int sum_overflow(unsigned long a, unsigned long b)
{
   unsigned long long x = a + b; // C4754

   if (x > 0xFFFFFFFF)
   {
      // never executes!
      return EOVERFLOW;
   }
   return 0;
}
```

Добавление `a + b` может привести к арифметическое переполнение, прежде чем результат приведен с повышением к 64-разрядное значение и присваивается переменной 64-разрядных `x`. Это означает, что проверка на `x` является избыточным и никогда не catch переполнение. В этом случае компилятор выдает это предупреждение:

```Output
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754a.cpp (7) mean that one branch cannot be executed. Cast '(a + ...)' to 'ULONG64' (or similar type of 8 bytes).
```

Чтобы устранить предупреждение, можно изменить оператор присваивания для приведения операндов для 8-байтовых значений:

```cpp
// Casting one operand is sufficient to force all the operands in
// the addition be upcast according to C/C++ conversion rules, but
// casting both is clearer.
unsigned long long x =
   (unsigned long long)a + (unsigned long long)b;
```

## <a name="example"></a>Пример

Следующий пример также приводит к возникновению ошибки C4754.

```cpp
// C4754b.cpp
// Compile with: /W4 /c
#include "errno.h"

int wrap_overflow(unsigned long a)
{
   if (a + sizeof(unsigned long) < a) // C4754
   {
      // never executes!
      return EOVERFLOW;
   }
   return 0;
}
```

`sizeof()` Оператор возвращает `size_t`, размер которого зависит от архитектуры. В примере кода работает на 32-разрядных архитектур где `size_t` является 32-разрядный тип. Тем не менее, на 64-разрядных архитектур `size_t` является 64-разрядного типа. Правила преобразования целых чисел означает, что `a` является восходящее приведение типа для 64-разрядное значение в выражении `a + b < a` так, как если бы он был оформлен `(size_t)a + (size_t)b < (size_t)a`. Когда `a` и `b` являются 32-разрядных целых чисел, никогда не случаются операции сложения 64-разрядных и никогда не содержит ограничение. В результате код никогда не обнаруживает условие переполнения целое число, на 64-разрядных архитектур. Этот пример вызывает компилятору выдавать это предупреждение.

```Output
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754b.cpp (7) mean that one branch cannot be executed. Cast '4' to 'ULONG' (or similar type of 4 bytes).
```

Обратите внимание на то, что предупреждающее сообщение явным образом перечислены постоянное значение 4 вместо исходной строки источника, к моменту анализа предупреждение обнаруживает фрагменты кода, `sizeof(unsigned long)` уже преобразовано в константу. Таким образом необходимо отслеживать работу вычисление какого выражения в источнике кода, связанного с постоянное значение в предупреждающем сообщении. Наиболее распространенными источниками кода разрешен к константам, определенным в C4754 предупреждающие сообщения являются выражениями, такие как `sizeof(TYPE)` и `strlen(szConstantString)`.

В этом случае Исправленный код будет выглядеть так:

```cpp
// Casting the result of sizeof() to unsigned long ensures
// that all the addition operands are 32-bit, so any overflow
// is detected by the check.
if (a + (unsigned long)sizeof(unsigned long) < a)

```

**Примечание** номер строки, который ссылается предупреждения компилятора находится в последней строке оператора. В сообщении с предупреждением о сложных условный оператор, который распространяется на несколько строк строки с установленной дефект кода может быть несколько строк перед строкой, которая передается. Пример:

```cpp
unsigned long a;

if (a + sizeof(unsigned long) < a || // incorrect check
    condition1() ||
    a == 0) {    // C4754 warning reported on this line
         // never executes!
         return INVALID_PARAMETER;
}
```