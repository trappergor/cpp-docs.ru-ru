---
title: Особенности написания кода пролога и эпилога
ms.date: 11/04/2016
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
ms.openlocfilehash: a70c444af9e1622b3f46837fcfa2d5e8856abf30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399139"
---
# <a name="considerations-for-writing-prologepilog-code"></a>Особенности написания кода пролога и эпилога

**Блок, относящийся только к системам Microsoft**

Перед написанием собственных последовательностей кодов пролога и эпилога важно понимать, как размещается кадр стека. Это также полезно знать, как использовать `__LOCAL_SIZE` символов.

##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a> Макет кадра стека

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

##  <a name="_pluslang___local_size"></a> __LOCAL_SIZE

Компилятор предоставляет символ `__LOCAL_SIZE`, для использования в встроенном ассемблерном блоке кода пролога функции. Этот символ служит для выделения пространства локальным переменным в кадре стека пользовательского кода пролога.

Компилятор определяет значение `__LOCAL_SIZE`. Это значение представляет общее количество байтов всех определяемых пользователем локальных переменных и временных переменных, создаваемых компилятором. `__LOCAL_SIZE` может использоваться только в качестве непосредственного операнда; он не может использоваться в выражении. Значение этого символа не следует изменять и переопределять. Пример:

```
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov        eax, [ebp - __LOCAL_SIZE]   ;Error
```

В следующем примере функции с атрибутом naked, содержащей пользовательский пролога и эпилога последовательности `__LOCAL_SIZE` символа в последовательности пролога:

```
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

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Вызовы функций с атрибутом naked](../cpp/naked-function-calls.md)