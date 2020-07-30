---
title: Ошибка компилятора C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: a67d4d859e3a9dd2241f14a476492df0fd3e6b8d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223425"
---
# <a name="compiler-error-c3495"></a>Ошибка компилятора C3495

var : передаваемый параметр лямбда-выражения должен иметь длительность автоматического хранения

Невозможно записать переменную, не имеющую автоматического времени хранения, например переменную, которая помечена как **`static`** или **`extern`** .

### <a name="to-correct-this-error"></a>Исправление ошибки

- Не передавайте **`static`** **`extern`** переменную или в список записи лямбда-выражения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3495, так как **`static`** переменная `n` появляется в списке записи лямбда-выражения:

```cpp
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>См. также статью

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
