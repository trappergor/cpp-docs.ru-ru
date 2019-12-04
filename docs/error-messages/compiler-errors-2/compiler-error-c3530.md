---
title: Ошибка компилятора C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 3766eaa83457ba6cffaf8b1599983a065772911c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750147"
---
# <a name="compiler-error-c3530"></a>Ошибка компилятора C3530

"Auto" не может использоваться вместе с любым другим описателем типа

Описатель типа используется с ключевым словом `auto`.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не используйте спецификатор типа в объявлении переменной, который использует ключевое слово `auto`.

## <a name="example"></a>Пример

В следующем примере создается C3530, так как переменная `x` объявляется как с ключевым словом `auto`, так и с типом `int`, а также из-за того, что пример компилируется с параметром **/Zc: Auto**.

```cpp
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>См. также:

[Ключевое слово auto](../../cpp/auto-keyword.md)
