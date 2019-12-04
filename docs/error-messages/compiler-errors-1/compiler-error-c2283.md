---
title: Ошибка компилятора C2283
ms.date: 11/04/2016
f1_keywords:
- C2283
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
ms.openlocfilehash: 7f3568aa5dfee116a225256a4452465c05f72f6f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759156"
---
# <a name="compiler-error-c2283"></a>Ошибка компилятора C2283

"идентификатор": чистый спецификатор или абстрактный спецификатор переопределения не допускаются в безымянной структуре

Функция-член неименованного класса или структуры объявляется с чистым спецификатором, что не допускается.

В следующем примере возникает ошибка C2283:

```cpp
// C2283.cpp
// compile with: /c
struct {
   virtual void func() = 0;   // C2283
};
struct T {
   virtual void func() = 0;   // OK
};
```
