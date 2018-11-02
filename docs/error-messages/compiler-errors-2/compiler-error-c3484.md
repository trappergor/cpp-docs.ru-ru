---
title: Ошибка компилятора C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: fd8909b664f739afa1ab1208be0984b8f410154d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468644"
---
# <a name="compiler-error-c3484"></a>Ошибка компилятора C3484

требуется "->" перед типом возврата

Необходимо указать `->` перед типом возврата лямбда-выражения.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Укажите `->` перед типом возврата.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3484:

```
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

## <a name="example"></a>Пример

В следующем примере устраняется ошибка C3484 путем предоставления `->` перед типом возврата лямбда-выражения:

```
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)