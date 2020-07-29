---
title: Ошибка компилятора C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: ea7341b9c587a764c7366fa7b7c89e4fc67bc7d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230861"
---
# <a name="compiler-error-c3490"></a>Ошибка компилятора C3490

"переменная" не может быть изменен, поскольку доступ к нему осуществляется через константный объект

Лямбда-выражение, объявленное в **`const`** методе, не может изменять неизменяемые данные элемента.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите **`const`** модификатор из объявления метода.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3490, так как изменяет переменную-член `_i` в **`const`** методе:

```cpp
// C3490a.cpp
// compile with: /c

class C
{
   void f() const
   {
      auto x = [=]() { _i = 20; }; // C3490
   }

   int _i;
};
```

## <a name="example"></a>Пример

В следующем примере разрешается C3490 путем удаления **`const`** модификатора из объявления метода:

```cpp
// C3490b.cpp
// compile with: /c

class C
{
   void f()
   {
      auto x = [=]() { _i = 20; };
   }

   int _i;
};
```

## <a name="see-also"></a>См. также статью

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
