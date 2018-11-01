---
title: Ошибка компилятора C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: 7c16ffa37f4d7192956afae26c825b63add1bfdd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540257"
---
# <a name="compiler-error-c3412"></a>Ошибка компилятора C3412

«шаблон»: невозможно настроить шаблон в текущей области

Шаблон не может быть настроен в только в глобальной области видимости класса или области видимости пространства имен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3412.

```
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

## <a name="example"></a>Пример

В следующем примере показано возможное решение.

```
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```