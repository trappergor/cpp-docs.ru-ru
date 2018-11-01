---
title: Ошибка компилятора C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: ec6725472d31b0b2ade0cd73da4440036239fde3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598566"
---
# <a name="compiler-error-c3849"></a>Ошибка компилятора C3849

вызов в стиле функции выражения типа «тип» будут потеряны квалификаторы const и volatile для всех доступных перегрузок операторов

Переменная с указанным типом const или volatile может вызывать только член функции, определенные с помощью одной или более поздней версии const и volatile.

Чтобы устранить эту ошибку, укажите соответствующую функцию-член. Невозможно выполнить преобразование в const или volatile уточненный объект, если преобразование приводит к потере квалификации. Вы получаете квалификаторы, но не может потерять при преобразовании.

Следующий пример приводит к возникновению ошибки C3849:

```
// C3849.cpp
void glbFunc3(int i, char c)
{
   i;
}
typedef void (* pFunc3)(int, char);

void glbFunc2(int i)
{
   i;
}

typedef void (* pFunc2)(int);

void glbFunc1()
{
}
typedef void (* pFunc1)();

struct S4
{
   operator ()(int i)
   {
      i;
   }

   operator pFunc1() const
   {
      return &glbFunc1;
   }

   operator pFunc2() volatile
   {
      return &glbFunc2;
   }

   operator pFunc3()
   {
      return &glbFunc3;
   }

   // operator pFunc1() const volatile
   // {
   //    return &glbFunc1;
   // }
};

int main()
{
   // Cannot call any of the 4 overloads of "operator ()(.....)" and
   // "operator pFunc()" because none is declared as "const volatile"
   const volatile S4 s4;  // can only call cv member functions of S4
   s4();   // C3849 to resolve, uncomment member function
}
```