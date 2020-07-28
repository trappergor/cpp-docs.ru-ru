---
title: Вызов функций C во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
ms.openlocfilehash: 73be1142747dc608d683e6bd847639b9df718a13
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192630"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Вызов функций C во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

**`__asm`** Блок может вызывать функции C, включая подпрограммы библиотеки C. В следующем примере вызывается библиотечная процедура `printf`.

```cpp
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp
// processor: x86
#include <stdio.h>

char format[] = "%s %s\n";
char hello[] = "Hello";
char world[] = "world";
int main( void )
{
   __asm
   {
      mov  eax, offset world
      push eax
      mov  eax, offset hello
      push eax
      mov  eax, offset format
      push eax
      call printf
      //clean up the stack so that main can exit cleanly
      //use the unused register ebx to do the cleanup
      pop  ebx
      pop  ebx
      pop  ebx
   }
}
```

Так как аргументы функции передается в стеке, перед вызовом функции просто поместите в стек требуемые аргументы (в предыдущем примере это указатели строк). Аргументы помещаются в стек в обратном порядке, поэтому они извлекаются из стека в требуемом порядке. Эмуляция оператора C

```cpp
printf( format, hello, world );
```

В этом примере в стек помещаются указатели на строки `world`, `hello` и `format` (в этом порядке), затем вызывается процедура `printf`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенный ассемблер](../../assembler/inline/inline-assembler.md)<br/>
