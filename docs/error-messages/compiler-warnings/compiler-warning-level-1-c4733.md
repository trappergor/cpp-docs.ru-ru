---
title: Предупреждение компилятора (уровень 1) C4733
ms.date: 11/04/2016
f1_keywords:
- C4733
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
ms.openlocfilehash: 39674c32deb506725aa5f7c1f5f875e771519938
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185676"
---
# <a name="compiler-warning-level-1-c4733"></a>Предупреждение компилятора (уровень 1) C4733

Назначение встроенного ассемблерного кода для "FS: 0": обработчик не зарегистрирован как надежный обработчик

Функция, изменяющая значение в FS: 0 чтобы добавить новый обработчик исключений, может не работать с бездействующими исключениями, так как обработчик может не быть зарегистрирован как допустимый обработчик исключений (см. параметр [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)).

Чтобы устранить это предупреждение, удалите FS: 0 определение или отключение этого предупреждения и использование [. SAFESEH](../../assembler/masm/dot-safeseh.md) для указания безнадежных обработчиков исключений.

Следующий пример приводит к возникновению ошибки C4733:

```cpp
// C4733.cpp
// compile with: /W1 /c
// processor: x86
#include "stdlib.h"
#include "stdio.h"
void my_handler()
{
   printf("Hello from my_handler\n");
   exit(1);
}

int main()
{
   _asm {
      push    my_handler
      mov     eax, DWORD PTR fs:0
      push    eax
      mov     DWORD PTR fs:0, esp   // C4733
   }

   *(int*)0 = 0;
}
```
