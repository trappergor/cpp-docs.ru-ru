---
title: Ошибка компилятора C3496 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3496
dev_langs:
- C++
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ec4602e6a0061f5eb750ab29587209a6c97985d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062297"
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