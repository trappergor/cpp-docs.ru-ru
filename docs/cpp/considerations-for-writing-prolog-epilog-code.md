---
title: Рассмотрение для написания Пролог-Эпилог код
ms.date: 11/04/2016
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
ms.openlocfilehash: cda6a6c82efcf30a916aced121024095d7ce8138
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337100"
---
# <a name="considerations-for-writing-prologepilog-code"></a>Особенности написания кода пролога и эпилога

**Microsoft Специфический**

Прежде чем писать собственные последовательности пролога и эпилог-кода, важно понять, как выкладывается рамка стека. Также полезно знать, как использовать `__LOCAL_SIZE` символ.

## <a name="stack-frame-layout"></a><a name="_pluslang_c.2b2b_.stack_frame_layout"></a>Укладка макета кадров

В данном примере показан стандартный код пролога, который может присутствовать в 32-разрядной функции.

```
push        ebp                ; Save ebp
mov         ebp, esp           ; Set stack frame pointer
sub         esp, localbytes    ; Allocate space for locals
push        <registers>        ; Save registers
```

Переменная `localbytes` представляет число байтов, которые требуются в стеке для локальных переменных, а переменная `<registers>` — это заполнитель, представляющий список сохраняемых в стеке регистров. После проталкивания регистров можно разместить в стеке все другие необходимые данные. Ниже приведен соответствующий код эпилога.

```
pop         <registers>   ; Restore registers
mov         esp, ebp      ; Restore stack pointer
pop         ebp           ; Restore ebp
ret                       ; Return from function
```

Стек всегда расширяется в направлении вниз (от старших адресов памяти к младшим). Указатель базы (`ebp`) указывает на помещенное в стек значение `ebp`. Область локальных переменных начинается с адреса `ebp-4`. Для доступа к локальным переменным необходимо вычислить смещение от `ebp` путем вычитания соответствующего значения из `ebp`.

## <a name="__local_size"></a><a name="_pluslang___local_size"></a>__LOCAL_SIZE

Компилятор предоставляет `__LOCAL_SIZE`символ, для использования в водном блоке сборки функции prolog code. Этот символ служит для выделения пространства локальным переменным в кадре стека пользовательского кода пролога.

Компилятор определяет `__LOCAL_SIZE`значение. Это значение представляет общее количество байтов всех определяемых пользователем локальных переменных и временных переменных, создаваемых компилятором. `__LOCAL_SIZE`может быть использован только в качестве немедленного оперативного; он не может быть использован в выражении. Значение этого символа не следует изменять и переопределять. Пример:

```
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov        eax, [ebp - __LOCAL_SIZE]   ;Error
```

Следующий пример голой функции, содержащей пользовательские `__LOCAL_SIZE` пролог и эпилог последовательности использует символ в последовательности prolog:

```cpp
// the__local_size_symbol.cpp
// processor: x86
__declspec ( naked ) int main() {
   int i;
   int j;

   __asm {      /* prolog */
      push   ebp
      mov      ebp, esp
      sub      esp, __LOCAL_SIZE
      }

   /* Function body */
   __asm {   /* epilog */
      mov      esp, ebp
      pop      ebp
      ret
      }
}
```

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[Голые вызовы функции](../cpp/naked-function-calls.md)
