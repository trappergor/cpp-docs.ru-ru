---
title: Ошибка компилятора C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: 2d93902ee0008a54da1b2ecf165e0a829362511f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389038"
---
# <a name="compiler-error-c2351"></a>Ошибка компилятора C2351

устаревший синтаксис инициализации конструктора C++

В списке инициализации нового стиля для конструктора необходимо явно задать имена каждой прямой базовый класс, даже если это только базовый класс.

В следующем примере возникает в C2351:

```
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```