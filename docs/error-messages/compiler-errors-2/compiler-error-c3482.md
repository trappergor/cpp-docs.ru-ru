---
title: Ошибка компилятора C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 6ff269d719dd354932ef79946ae99a9b60490199
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173228"
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