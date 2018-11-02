---
title: Предупреждение компилятора (уровень 4) C4702
ms.date: 11/04/2016
f1_keywords:
- C4702
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
ms.openlocfilehash: 96ae3a0742db5e3a5006f031ce62beb281c38ccd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607237"
---
# <a name="compiler-warning-level-4-c4702"></a>Предупреждение компилятора (уровень 4) C4702

недостижимый код

Это предупреждение является результатом действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: недостижимый код. Когда компилятор (внутреннюю) обнаруживает недостижимый код, он создает C4702, предупреждение уровня 4.

Для кода, который действителен в версиях Visual C++ для Visual Studio .NET 2003 и Visual Studio .NET удалите недостижимый код или убедиться, что весь исходный код доступен для определенного потока выполнения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4702.

```
// C4702.cpp
// compile with: /W4
#include <stdio.h>

int main() {
   return 1;
   printf_s("I won't print.\n");   // C4702 unreachable
}
```

## <a name="example"></a>Пример

При компиляции с параметром **/GX**, **/EHc**, **/EHsc**, или **/EHac** и используя внешние функции C, код может оказаться недостижимым так как extern C предполагается, что функции не throw, поэтому блок catch недостижим.  Если вы считаете, что это предупреждение не является допустимым, так как функция может создавать, компиляцию с **/EHa** или **/EHs**, в зависимости от исключения.

Дополнительные сведения см. в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md) Дополнительные сведения.

Следующий пример приводит к возникновению ошибки C4702.

```
// C4702b.cpp
// compile with: /W4 /EHsc
#include <iostream>

using namespace std;
extern "C" __declspec(dllexport) void Function2(){}

int main() {
   try {
      Function2();
   }
   catch (...) {
      cout << "Exp: Function2!" << endl;   // C4702
   }
}
```