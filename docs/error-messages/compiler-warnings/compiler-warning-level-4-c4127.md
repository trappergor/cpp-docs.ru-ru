---
title: Предупреждение компилятора (уровень 4) C4127
ms.date: 10/16/2019
f1_keywords:
- C4127
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
ms.openlocfilehash: bef825f546573b878c415c385e1a2a2286e08db4
ms.sourcegitcommit: 9aab425662a66825772f091112986952f341f7c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444901"
---
# <a name="compiler-warning-level-4-c4127"></a>Предупреждение компилятора (уровень 4) C4127

> условное выражение является константой

## <a name="remarks"></a>Заметки

Управляющее выражение оператора **If** или цикла **while** вычисляет константу. Из-за общего использования идиоматическим, начиная с Visual Studio 2015 с обновлением 3, тривиальные константы, такие как 1 или **true** , не активируют предупреждение, если только они не являются результатом операции в выражении.

Если управляющее выражение цикла **while** является константой, поскольку цикл завершается в середине, попробуйте заменить цикл **while** на цикл **for** . Можно опустить инициализацию, тест завершения и инкремент цикла цикла **for** , что приводит к бесконечности цикла, как `while(1)`, и можно выйти из цикла из тела оператора **for** .

## <a name="example"></a>Пример

В следующем примере показаны два способа создания C4127 и показано, как использовать цикл for, чтобы избежать предупреждения.

```cpp
// C4127.cpp
// compile with: /W4
#include <stdio.h>
int main() {
   if (true) {}           // OK in VS2015 update 3 and later
   if (1 == 1) {}         // C4127
   while (42) { break; }  // C4127

   // OK
   for ( ; ; ) {
      printf("test\n");
      break;
   }
}
```

Это предупреждение также может быть создано при использовании константы времени компиляции в условном выражении:


```cpp
#include <string>

using namespace std;

template<size_t S, class T>
void MyFunc()
{
   if (sizeof(T) >= S) // C4127. "Consider using 'if constexpr' statement instead"
   {
   }
}

class Foo
{
   int i;
   string s;
};

int main()
{
   Foo f;
   MyFunc<4, Foo>();
}
```