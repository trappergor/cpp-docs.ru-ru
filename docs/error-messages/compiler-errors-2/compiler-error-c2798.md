---
title: Ошибка компилятора C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: f3e8f0ac260e49866d1c654f89d34bf57a8ffbc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463064"
---
# <a name="compiler-error-c2798"></a>Ошибка компилятора C2798

«super::member» является неоднозначным

Несколько унаследованных структур содержат член, на который существует ссылка [super](../../cpp/super.md). Может исправить ошибку, либо:

- Удаление B1 и B2 из списка наследования г.

- Изменение имени члена данных в B1 и B2.

Следующий пример приводит к возникновению ошибки C2798:

```
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```