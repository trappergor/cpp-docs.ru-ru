---
title: Ошибка компилятора C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: 3f32307e519394433927d49aa92333fdff7b70f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378873"
---
# <a name="compiler-error-c2883"></a>Ошибка компилятора C2883

«name»: объявление функции вступает в конфликт с «идентификатор», представленное в объявление using

Предпринята попытка определить функцию более одного раза. Первое определение был сделан из пространства имен с `using` объявления. Вторая была локальное определение.

Следующий пример приводит к возникновению ошибки C2883:

```
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```