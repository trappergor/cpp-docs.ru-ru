---
title: Ошибка компилятора C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: 0d6c1467575e7fae7d5e4862f36e733a68210f8e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743098"
---
# <a name="compiler-error-c3483"></a>Ошибка компилятора C3483

var уже является частью списка передаваемых параметров лямбда-выражения

Вы несколько раз передали одну и ту же переменную в список передаваемых параметров лямбда-выражения.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите все дополнительные экземпляры переменной из списка передаваемых параметров.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3483, так как в списке передаваемых параметров лямбда-выражения переменная `n` присутствует несколько раз.

```cpp
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>См. также:

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
