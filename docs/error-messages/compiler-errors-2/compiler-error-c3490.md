---
title: Ошибка компилятора C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: 55580533d6a1a6b80f79b017ba78a08fb44df744
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478160"
---
# <a name="compiler-error-c3490"></a>Ошибка компилятора C3490

"переменная" не может быть изменен, поскольку доступ к нему осуществляется через константный объект

Лямбда-выражение, объявленное в методе `const` , не может изменять данные недоступного для изменения члена.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите модификатор `const` из объявления метода.

## <a name="example"></a>Пример

Приведенный ниже пример вызывает ошибку C3490, так как переменная-член `_i` изменяется в методе `const` .

```
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

В приведенном ниже примере ошибка C3490 устраняется путем удаления модификатора `const` из объявления метода.

```
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

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)