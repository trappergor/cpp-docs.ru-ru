---
title: Ошибка компилятора C3492
ms.date: 11/04/2016
f1_keywords:
- C3492
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
ms.openlocfilehash: 53dd22368aee5e0de9eca1349eb4d7dd3ed1c570
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485011"
---
# <a name="compiler-error-c3492"></a>Ошибка компилятора C3492

var: нельзя передавать член анонимного объединения

Вы не можете передавать член анонимного объединения

### <a name="to-correct-this-error"></a>Исправление ошибки

- Присвойте объединению имя и передайте полную структуру объединения в список передаваемых параметров лямбда-выражения.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3492, поскольку в нем передается член анонимного объединения:

```
// C3492a.cpp

int main()
{
   union
   {
      char ch;
      int x;
   };

   ch = 'y';
   [&x](char ch) { x = ch; }(ch); // C3492
}
```

## <a name="example"></a>Пример

В следующем примере устраняется ошибка C3492 путем предоставления объединению имени и передачи полной структуры объединения в список передаваемых параметров лямбда-выражения:

```
// C3492b.cpp

int main()
{
   union
   {
      char ch;
      int x;
   } u;

   u.ch = 'y';
   [&u](char ch) { u.x = ch; }(u.ch);
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)