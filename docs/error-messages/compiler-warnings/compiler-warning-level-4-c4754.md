---
title: Предупреждение (уровень 4) C4754 компилятора | Документы Microsoft
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
ms.openlocfilehash: c7f4e42d2e44a55c98abdcd5c3e723e2a9269a1e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302858"
---
# <a name="compiler-warning-level-4-c4754"></a>Предупреждение компилятора (уровень 4) C4754
Правила преобразования арифметических операций в сравнении означает, что одна ветвь не может быть выполнена.  
  
 C4754 предупреждение выдается в том случае, так как результат сравнения не изменяется. Это означает, что одной из ветвей условие не выполняется, скорее всего из-за неправильной связанного целочисленное выражение. Этот дефект кода часто возникает в проверки переполнения для целочисленных неверные на 64-разрядных архитектур.  
  
 Правила преобразования целочисленное сложны и существует множество слабая ловушек. В качестве альтернативы для исправления каждой C4754 предупреждение, можно обновить код для использования [библиотека SafeInt](../../windows/safeint-library.md).  
  
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
  
 Добавление `a + b` может привести к арифметическое переполнение, прежде чем результат приведения с повышением 64-разрядное значение и присваивается переменной 64-разрядных `x`. Это означает, что проверка на `x` является избыточным и никогда не catch переполнение. В этом случае компилятор выдает это предупреждение:  
  
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
  
 `sizeof()` Оператор возвращает `size_t`, размер которого зависит от архитектуры. В примере кода работает на 32-разрядных архитектур где `size_t` является 32-разрядным типом. Тем не менее, на 64-разрядных архитектур `size_t` является 64-разрядным типом. Правила преобразования целых чисел означает, что `a` — для 64-разрядное значение в выражении приведения с повышением `a + b < a` как если бы он был оформлен `(size_t)a + (size_t)b < (size_t)a`. Когда `a` и `b` являются 32-разрядных целых чисел, операция сложения 64-разрядных никогда не может выйти за пределы и ограничения никогда не содержит. В результате код никогда не обнаруживает условие переполнения целое число со знаком на 64-разрядных архитектур. В этом примере указывает компилятору на необходимость создания этого предупреждения:  
  
```Output  
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754b.cpp (7) mean that one branch cannot be executed. Cast '4' to 'ULONG' (or similar type of 4 bytes).  
```  
  
 Обратите внимание, что предупреждение явно перечисляются постоянное значение 4 вместо исходной строки источника, к моменту анализа предупреждение встречает фрагменты кода `sizeof(unsigned long)` уже был преобразован в константу. Таким образом может потребоваться отслеживать работу какое именно выражение в источнике связан код с константным значением в предупреждающем сообщении. Наиболее распространенными источниками кода сопоставляется констант в C4754 предупреждающих сообщений являются выражениями, такие как `sizeof(TYPE)` и `strlen(szConstantString)`.  
  
 В этом случае Исправленный код будет выглядеть так:  
  
```cpp  
// Casting the result of sizeof() to unsigned long ensures  
// that all the addition operands are 32-bit, so any overflow   
// is detected by the check.  
if (a + (unsigned long)sizeof(unsigned long) < a)  
  
```  
  
 **Примечание** номер строки, который ссылается предупреждения компилятора является последней строке оператора. В предупреждающем сообщении о сложных условных инструкций, которые распределены на нескольких строках строку, которая содержит дефект кода может быть несколько строк, перед строкой, которая передается. Пример:  
  
```cpp  
unsigned long a;  
  
if (a + sizeof(unsigned long) < a || // incorrect check  
    condition1() ||   
    a == 0) {    // C4754 warning reported on this line  
         // never executes!  
         return INVALID_PARAMETER;  
}  
```