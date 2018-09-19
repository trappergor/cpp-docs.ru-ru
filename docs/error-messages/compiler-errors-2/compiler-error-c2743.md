---
title: Ошибка компилятора C2743 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4217a1e7a8475362c654ac34b6a345846341ec35
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056497"
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