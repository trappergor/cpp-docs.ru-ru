---
title: Ошибка компилятора C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 152157824cb270f32b1233f39225abab7741eda5
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507057"
---
# <a name="compiler-error-c3530"></a>Ошибка компилятора C3530

"Auto" не может использоваться вместе с любым другим описателем типа

Описатель типа используется с **`auto`** ключевым словом.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не используйте спецификатор типа в объявлении переменной, использующем **`auto`** ключевое слово.

## <a name="example"></a>Пример

В следующем примере создается C3530, так как переменная `x` объявлена как с ключевым словом, так и с **`auto`** типом **`int`** , а так как пример компилируется с параметром **/Zc: Auto**.

```cpp
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-cpp.md)
