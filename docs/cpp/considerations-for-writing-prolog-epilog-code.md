---
title: Особенности написания кода пролога эпилога | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bd87d4af4c797d324e6f882cc5c2e139a784543
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414774"
---
# <a name="considerations-for-writing-prologepilog-code"></a>Особенности написания кода пролога и эпилога
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Перед написанием собственных последовательностей кодов пролога и эпилога важно понимать, как размещается кадр стека. Полезно также знать, как использовать **__LOCAL_SIZE** символов.  
  
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
 Компилятор предоставляет символ, **__LOCAL_SIZE**, для использования во встроенном ассемблерном блоке кода пролога функции. Этот символ служит для выделения пространства локальным переменным в кадре стека пользовательского кода пролога.  
  
 Значение константы **__LOCAL_SIZE** определяется компилятором. Это значение представляет общее количество байтов всех определяемых пользователем локальных переменных и временных переменных, создаваемых компилятором. Константу **__LOCAL_SIZE** можно использовать только в качестве непосредственного операнда, но не в выражениях. Значение этого символа не следует изменять и переопределять. Пример:  
  
```  
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov        eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 В следующем примере функции с атрибутом naked содержащей пользовательского кода пролога и эпилога последовательности использует **__LOCAL_SIZE** символа в последовательности пролога:  
  
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