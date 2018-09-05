---
title: Функции вызова C во встроенной сборке | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a080c05aee58a2e6ffae17d14e99c66922aa1f17
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686691"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Вызов функций C во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Блок `__asm` может вызывать функции языка C, включая библиотечные процедуры языка C. В следующем примере вызывается библиотечная процедура `printf`.

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

[Встроенный сборщик](../../assembler/inline/inline-assembler.md)<br/>