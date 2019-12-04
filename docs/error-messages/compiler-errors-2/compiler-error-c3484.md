---
title: Ошибка компилятора C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: c9895a3e5a8ae7e941fccde2da85fedfb3d2c6dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743124"
---
# <a name="compiler-error-c3484"></a>Ошибка компилятора C3484

требуется "->" перед типом возврата

Необходимо указать `->` перед типом возврата лямбда-выражения.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Укажите `->` перед типом возврата.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3484:

```cpp
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

## <a name="example"></a>Пример

В следующем примере устраняется ошибка C3484 путем предоставления `->` перед типом возврата лямбда-выражения:

```cpp
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>См. также:

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
