---
title: Ошибка компилятора C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 0463f6de51e324bd02c8b766fd39909ee2803ecd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212583"
---
# <a name="compiler-error-c3482"></a>Ошибка компилятора C3482

"this" может быть использован в качестве передаваемого параметра в лямбда-выражении только с нестатической функцией-членом

Нельзя передать в **`this`** список записи лямбда-выражения, объявленного в статическом методе или глобальной функции.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Преобразуйте включающую функцию в нестатический метод или

- Удалите **`this`** указатель из списка записи лямбда-выражения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C3482:

```cpp
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

## <a name="see-also"></a>См. также раздел

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
