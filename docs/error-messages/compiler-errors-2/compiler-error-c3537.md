---
title: Ошибка компилятора C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 22387470019b0118d06b4cacd82a1df5c3e505fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576128"
---
# <a name="compiler-error-c3537"></a>Ошибка компилятора C3537

«Тип»: не может быть приведен к типу, содержащему «auto»

Нельзя привести переменную к указанному типу, так как содержит тип `auto` ключевое слово и значение по умолчанию [/Zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) параметр компилятора.

## <a name="example"></a>Пример

Следующий код вызывает ошибку C3537, поскольку переменные приводятся к типу, содержащему `auto` ключевое слово.

```
// C3537.cpp
// Compile with /Zc:auto
int main()
{
   int value = 123;
   auto(value);                        // C3537
   (auto)value;                        // C3537
   auto x1 = auto(value);              // C3537
   auto x2 = (auto)value;              // C3537
   auto x3 = static_cast<auto>(value); // C3537
   return 0;
}
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)