---
title: Ошибка компилятора C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: acbe89b5183d0991fb8d4a571a9595d6f6bafc6c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026127"
---
# <a name="compiler-error-c3483"></a>Ошибка компилятора C3483

var уже является частью списка передаваемых параметров лямбда-выражения

Вы несколько раз передали одну и ту же переменную в список передаваемых параметров лямбда-выражения.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите все дополнительные экземпляры переменной из списка передаваемых параметров.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3483, так как в списке передаваемых параметров лямбда-выражения переменная `n` присутствует несколько раз.

```
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)