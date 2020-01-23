---
title: Ошибка компилятора C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: 91f2bac38166a8972193a7aaa7e84913b941c799
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518326"
---
# <a name="compiler-error-c2346"></a>Ошибка компилятора C2346

"функция" не может быть скомпилирована как собственная: причина

Компилятору не удалось скомпилировать функцию в MSIL.

Дополнительные сведения см. в разделе [управляемые, неуправляемые](../../preprocessor/managed-unmanaged.md) и [/CLR (компиляция общеязыковой среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Удалите код в функции, которая не может быть скомпилирована в MSIL.

1. Либо не компилируйте модуль с помощью **параметра/clr**, либо пометьте функцию как неуправляемую с помощью неуправляемой директивы pragma.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2346.

```cpp
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

int main()
{
   S s;
}
```
