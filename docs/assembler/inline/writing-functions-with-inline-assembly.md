---
title: Написание функций во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
ms.openlocfilehash: 3ce42147693f0c4c180076c627ef88c182745186
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191005"
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

Поскольку функция написана для отдельного сборщика, для нее требуется отдельной исходный файл и шаги по сборке и компоновке. Аргументы функций C и C++ обычно передаются в стек, поэтому эта версия функции `power2` обращается к аргументам по их позициям в стеке. (Обратите внимание, что директива **model** , доступная в MASM и другие сборки, также позволяет обращаться к аргументам стека и локальным переменным стека по имени.)

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

Поскольку Встроенная версия `power2` не выполняет **`return`** инструкцию C, она вызывает безобидное предупреждение при компиляции на уровне предупреждения 2 или выше. Функция возвращает значение, но компилятор не может определить, что в отсутствие **`return`** оператора. Чтобы отключить создание этого предупреждения, можно использовать [#pragma предупреждение](../../preprocessor/warning.md) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
