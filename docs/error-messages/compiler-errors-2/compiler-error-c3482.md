---
title: Ошибка компилятора C3482 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3482
dev_langs:
- C++
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9921c25575888ab2db1c092f9325002d1becb921
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053379"
---
# <a name="compiler-error-c3482"></a>Ошибка компилятора C3482

"this" может быть использован в качестве передаваемого параметра в лямбда-выражении только с нестатической функцией-членом

Нельзя передавать `this` в список передаваемых параметров лямбда-выражения, объявленного в статическом методе или в глобальной функции.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Преобразуйте включающую функцию в нестатический метод или

- удалите указатель `this` из списка передаваемых параметров лямбда-выражения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C3482:

```
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)