---
title: Ошибка компилятора C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: 1e6c3c502290e88feec89877de7ad791084401cf
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023260"
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