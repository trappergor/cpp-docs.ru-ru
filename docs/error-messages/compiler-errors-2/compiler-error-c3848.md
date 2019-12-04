---
title: Ошибка компилятора C3848
ms.date: 11/04/2016
f1_keywords:
- C3848
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
ms.openlocfilehash: 51a5cf6d866a5e5ee914a3d70365761749f79eea
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761950"
---
# <a name="compiler-error-c3848"></a>Ошибка компилятора C3848

выражение HAVING типа "тип" потеряет некоторые квалификаторы const-volatile для вызова "Function"

Переменная с указанным типом const константы может вызывать только функции-члены, определенные с теми же или большими квалификациями const-volatile.

Следующие примеры создают C3848:

```cpp
// C3848.cpp
void glbFunc1()
{
}

typedef void (* pFunc1)();

struct S3
{
   operator pFunc1() // const
   {
      return &glbFunc1;
   }
};

int main()
{
   const S3 s3;
   s3();   // C3848, uncomment const qualifier
}
```
