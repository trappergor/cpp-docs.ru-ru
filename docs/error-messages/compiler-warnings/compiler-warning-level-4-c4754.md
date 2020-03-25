---
title: Предупреждение компилятора (уровень 4) C4754
ms.date: 11/04/2016
f1_keywords:
- C4754
helpviewer_keywords:
- C4754
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
ms.openlocfilehash: f55d40044fef58275ad0e1fbd281b5f1af43c243
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198137"
---
# <a name="compiler-warning-level-4-c4754"></a>Предупреждение компилятора (уровень 4) C4754

Правила преобразования для арифметических операций в сравнении означают, что одна ветвь не может быть выполнена.

Выдается предупреждение C4754, так как результат сравнения всегда один и тот же. Это указывает на то, что одна из ветвей условия никогда не выполняется, скорее всего, из-за неверного выражения с соответствующим целочисленным значением. Этот дефект кода часто возникает при неправильной проверке переполнения целочисленных значений в 64-разрядных архитектурах.

Правила целочисленного преобразования являются сложными, и существует множество неявных ловушек. В качестве альтернативы исправлению каждого предупреждения C4754 можно обновить код для использования [библиотеки SafeInt](../../safeint/safeint-library.md).

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

Добавление `a + b` может привести к арифметическому переполнению до того, как результат будет приведен к 64-разрядному значению и назначен в 64-разрядную переменную `x`. Это означает, что проверка `x` является избыточной и никогда не перехватывает переполнение. В этом случае компилятор выдает это предупреждение:

```Output
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754a.cpp (7) mean that one branch cannot be executed. Cast '(a + ...)' to 'ULONG64' (or similar type of 8 bytes).
```

Чтобы устранить это предупреждение, можно изменить инструкцию присваивания, чтобы привести операнды к 8-байтным значениям:

```cpp
// Casting one operand is sufficient to force all the operands in
// the addition be upcast according to C/C++ conversion rules, but
// casting both is clearer.
unsigned long long x =
   (unsigned long long)a + (unsigned long long)b;
```

## <a name="example"></a>Пример

В следующем примере также создается C4754.

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

Оператор `sizeof()` возвращает `size_t`, размер которого зависит от архитектуры. Пример кода работает на 32-разрядных архитектурах, где `size_t` является 32-битным типом. Однако в 64-разрядных архитектурах `size_t` является 64-битным типом. Правила преобразования для целых чисел означают, что `a` выполняется приведение к 64-разрядному значению в выражении `a + b < a` как если бы оно было написано `(size_t)a + (size_t)b < (size_t)a`. Если `a` и `b` являются 32-разрядными целыми числами, то операция сложения 64 не может быть переполнена, а ограничение никогда не будет храниться. В результате код никогда не обнаруживает условие переполнения целого числа в 64-разрядных архитектурах. Этот пример приводит к тому, что компилятор выдает это предупреждение:

```Output
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754b.cpp (7) mean that one branch cannot be executed. Cast '4' to 'ULONG' (or similar type of 4 bytes).
```

Обратите внимание, что предупреждение явным образом перечисляет постоянное значение 4 вместо исходной исходной строки — по моменту, когда анализ предупреждений обнаруживает код, вызвавший ошибку, `sizeof(unsigned long)` уже преобразован в константу. Поэтому, возможно, придется отчислить, какое выражение в исходном коде связано с постоянным значением в сообщении с предупреждением. Наиболее распространенные источники кода, разрешенные в константы в C4754 предупреждения, — это выражения, такие как `sizeof(TYPE)` и `strlen(szConstantString)`.

В этом случае фиксированный код будет выглядеть следующим образом:

```cpp
// Casting the result of sizeof() to unsigned long ensures
// that all the addition operands are 32-bit, so any overflow
// is detected by the check.
if (a + (unsigned long)sizeof(unsigned long) < a)
```

**Примечание** . Номер строки, на который ссылается предупреждение компилятора, является последней строкой инструкции. В сообщении с предупреждением о сложном условном операторе, распределенном по нескольким строкам, строка с кодом дефекта может быть выведена на несколько строк перед строкой. Пример:

```cpp
unsigned long a;

if (a + sizeof(unsigned long) < a || // incorrect check
    condition1() ||
    a == 0) {    // C4754 warning reported on this line
         // never executes!
         return INVALID_PARAMETER;
}
```
