---
title: Предупреждение компилятора (уровень 4) C4702
ms.date: 11/04/2016
f1_keywords:
- C4702
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
ms.openlocfilehash: 5e46bfef925f999ed7f04b5bbe7c88800209ed14
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990644"
---
# <a name="compiler-warning-level-4-c4702"></a>Предупреждение компилятора (уровень 4) C4702

недостижимый код

Это предупреждение является результатом действий по согласованности компилятора, выполненных для Visual Studio .NET 2003: недостижимый код. Когда компилятор (серверная система) обнаруживает недостижимый код, он создает C4702, предупреждение уровня 4.

Для кода, который является допустимым в версиях Visual Studio .NET 2003 и Visual Studio .NET C++, удалите недостижимый код или убедитесь, что весь исходный код доступен для потока выполнения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4702.

```cpp
// C4702.cpp
// compile with: /W4
#include <stdio.h>

int main() {
   return 1;
   printf_s("I won't print.\n");   // C4702 unreachable
}
```

## <a name="example"></a>Пример

При компиляции с параметром **/GX**, **/EHC**, **/EHsc**или **/ехак** и использованием внешних функций c код может стать недостижимым, так как предполагается, что внешние функции c не вызывают исключение, поэтому блок catch недоступен.  Если вы считаете, что это предупреждение является недопустимым, так как функция может вызывать, компилировать с **/EHa** или **/EHs**в зависимости от вызываемого исключения.

Дополнительные сведения см. в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md) .

Следующий пример приводит к возникновению ошибки C4702.

```cpp
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
