---
title: Ошибка компилятора C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: 025498f3fe244916cd0a06e36feee6fdb532acc6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026705"
---
# <a name="compiler-error-c3496"></a>Ошибка компилятора C3496

"this" всегда передается по значению: знак "&" проигнорирован

Нельзя передать указатель `this` по ссылке.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Передайте указатель `this` по значению.

## <a name="example"></a>Пример

Представленный ниже пример приводит к возникновению ошибки C3496, так как ссылка на указатель `this` присутствует в списке передачи лямбда-выражения.

```
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

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)