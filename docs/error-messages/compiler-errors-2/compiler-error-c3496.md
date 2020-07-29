---
title: Ошибка компилятора C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: 993d391f28a59afc8926748f2e6f34ab441657dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228860"
---
# <a name="compiler-error-c3496"></a>Ошибка компилятора C3496

"this" всегда передается по значению: знак "&" проигнорирован

Невозможно захватить **`this`** указатель по ссылке.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Зафиксируйте **`this`** указатель по значению.

## <a name="example"></a>Пример

В следующем примере создается C3496, так как ссылка на **`this`** указатель появляется в списке записи лямбда-выражения:

```cpp
// C3496.cpp
// compile with: /c

class C
{
   void f()
   {
      [&this] {}(); // C3496
   }
};
```

## <a name="see-also"></a>См. также статью

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
