---
title: Написание функций во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
ms.openlocfilehash: 7848a8f071f50f8d809a999a96a9c0f8193c480e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445192"
---
# <a name="writing-functions-with-inline-assembly"></a>Написание функций во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Если при создании функции используется встроенный код ассемблера, можно легко передать аргументы в функцию и вернуть из нее значение. В следующих примерах сравнивается функция, написанная для отдельного сборщика, и функция, перезаписанная для встроенного кода на языке ассемблера. Функция `power2` получает два параметра путем умножения первого параметра на 2 в степени второго параметра. Если функция написана для отдельного сборщика, она может выглядеть следующим образом.

```asm
; POWER.ASM
; Compute the power of an integer
;
       PUBLIC _power2
_TEXT SEGMENT WORD PUBLIC 'CODE'
_power2 PROC

        push ebp        ; Save EBP
        mov ebp, esp    ; Move ESP into EBP so we can refer
                        ;   to arguments on the stack
        mov eax, [ebp+4] ; Get first argument
        mov ecx, [ebp+6] ; Get second argument
        shl eax, cl     ; EAX = EAX * ( 2 ^ CL )
        pop ebp         ; Restore EBP
        ret             ; Return with sum in EAX

_power2 ENDP
_TEXT   ENDS
        END
```

Поскольку функция написана для отдельного сборщика, для нее требуется отдельной исходный файл и шаги по сборке и компоновке. Аргументы функций C и C++ обычно передаются в стек, поэтому эта версия функции `power2` обращается к аргументам по их позициям в стеке. (Обратите внимание, что **МОДЕЛИ** директивы, доступная в MASM и некоторых других сборщиках, также позволяет получить доступ к аргументам стека и локальным переменным стека по имени.)

## <a name="example"></a>Пример

В следующей программе функция `power2` написана со встроенным кодом на языке ассемблера.

```cpp
// Power2_inline_asm.c
// compile with: /EHsc
// processor: x86

#include <stdio.h>

int power2( int num, int power );

int main( void )
{
    printf_s( "3 times 2 to the power of 5 is %d\n", \
              power2( 3, 5) );
}
int power2( int num, int power )
{
   __asm
   {
      mov eax, num    ; Get first argument
      mov ecx, power  ; Get second argument
      shl eax, cl     ; EAX = EAX * ( 2 to the power of CL )
   }
   // Return with result in EAX
}
```

Встроенная версия функции `power2` ссылается на аргументы по имени и отображается в том же исходном файле, что и остальные части программы. Кроме того, для этой версии требуется меньше инструкций сборки.

Поскольку встроенная версия функции `power2` не выполняет оператор `return` С, при компилировании на уровне предупреждений 2 или выше отображается безвредное предупреждение. Функция возвращает значение, но компилятор не может определить его при отсутствии оператора `return`. Можно использовать [#pragma warning](../../preprocessor/warning.md) можно отключить создание этого предупреждения.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>