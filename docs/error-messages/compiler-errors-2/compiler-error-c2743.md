---
title: Ошибка компилятора C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: 03cd7c13e093be5073b3df7e7cf29dda870bc47a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228934"
---
# <a name="compiler-error-c2743"></a>Ошибка компилятора C2743

«Тип»: невозможно перехватить собственный тип с деструктором __clrcall или конструктором копий

Модуль компиляции с **/CLR** предпринята попытка перехвата исключения собственного типа, где тип деструктор или конструктор копии используют `__clrcall` соглашение о вызовах.

При компиляции с **/CLR**, обработка исключений ожидает, что функции-члены в собственный тип быть [__cdecl](../../cpp/cdecl.md) и не [__clrcall](../../cpp/clrcall.md). Собственные типы с помощью функции-члены `__clrcall` соглашение о вызовах, не может быть перехвачено в модуле, скомпилированном с **/CLR**.

Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2743.

```
// C2743.cpp
// compile with: /clr
public struct S {
   __clrcall ~S() {}
};

public struct T {
   ~T() {}
};

int main() {
   try {}
   catch(S) {}   // C2743
   // try the following line instead
   // catch(T) {}

   try {}
   catch(S*) {}   // OK
}
```