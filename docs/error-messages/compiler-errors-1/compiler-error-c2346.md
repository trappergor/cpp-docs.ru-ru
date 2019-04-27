---
title: Ошибка компилятора C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: a6d75ca671e22203cb40ca18de21606834eeefa8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188095"
---
# <a name="compiler-error-c2346"></a>Ошибка компилятора C2346

«функция» не может компилироваться как машинный код: причина

Компилятору не удалось скомпилировать функцию в код MSIL.

Дополнительные сведения см. в разделе [управляемые, неуправляемые](../../preprocessor/managed-unmanaged.md) и [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Удалите код в функции, которая не может компилироваться в MSIL.

1. Либо не компилируйте модуль с помощью **/CLR**, или пометьте ее как неуправляемые и неуправляемая прагма.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2346.

```
// C2346.cpp
// processor: x86
// compile with: /clr
// C2346 expected
struct S
{
   S()
   {
      { __asm { nop } }
   }
   virtual __clrcall ~S() { }
};

void main()
{
   S s;
}
```