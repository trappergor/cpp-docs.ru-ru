---
title: Ошибка компилятора C2283
ms.date: 11/04/2016
f1_keywords:
- C2283
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
ms.openlocfilehash: 1113236680241a80c462e382c8c9c7de342b5463
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630000"
---
# <a name="compiler-error-c2283"></a>Ошибка компилятора C2283

"идентификатор": чистый спецификатор или абстрактный спецификатор переопределения не допускаются в безымянной структуре

Функция-член неименованного класса или структуры объявляется с чистым спецификатором, что не допускается.

В следующем примере возникает ошибка C2283:

```
// C2283.cpp
// compile with: /c
struct {
   virtual void func() = 0;   // C2283
};
struct T {
   virtual void func() = 0;   // OK
};
```