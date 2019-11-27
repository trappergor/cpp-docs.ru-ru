---
title: Предупреждение компилятора (уровень 3) C4823
ms.date: 11/04/2016
f1_keywords:
- C4823
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
ms.openlocfilehash: a96877252b0b7699f5e4033f8e695f4d9016a6c9
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541268"
---
# <a name="compiler-warning-level-3-c4823"></a>Предупреждение компилятора (уровень 3) C4823

"функция": использует закрепленные указатели, но семантика очистки не включена. Рекомендуется использовать/EHa

Чтобы открепить объект в управляемой куче, на которую указывает закрепленный указатель, объявленный в области видимости блока, компилятор имитирует поведение деструкторов локальных классов, "предмечая" указатель закрепляющий имеет деструктор, сводят указатель. Чтобы включить вызов деструктора после создания исключения, необходимо включить параметр "Очистка объекта", который можно сделать с помощью [/EHsc](../../build/reference/eh-exception-handling-model.md).

Можно также вручную открепить объект и проигнорировать предупреждение.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4823.

```cpp
// C4823.cpp
// compile with: /clr /W3 /EHa-
using namespace System;

ref struct G {
   int m;
};

void f(G ^ pG) {
   try {
      pin_ptr<int> p = &pG->m;
      // manually unpin, ignore warning
      // p = nullptr;
      throw gcnew Exception;
   }
   catch(Exception ^) {}
}   // C4823 warning

int main() {
   f( gcnew G );
}
```
