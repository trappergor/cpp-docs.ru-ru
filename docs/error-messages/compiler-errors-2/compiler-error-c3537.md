---
title: Ошибка компилятора C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: cfd2aa6f10b6e43ed10135ea2b6801619176cff5
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508191"
---
# <a name="compiler-error-c3537"></a>Ошибка компилятора C3537

"тип": невозможно привести к типу, содержащему "Auto"

Невозможно привести переменную к указанному типу, так как тип содержит **`auto`** ключевое слово, и действует параметр компилятора [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) по умолчанию.

## <a name="example"></a>Пример

Следующий код выдает C3537, так как переменные приведены к типу, содержащему **`auto`** ключевое слово.

```cpp
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

[Ключевое слово auto](../../cpp/auto-cpp.md)
