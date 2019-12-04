---
title: Ошибка компилятора C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: 6eed1f1aad0783f9e1d5f4126847b54f6b7278e0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739211"
---
# <a name="compiler-error-c2798"></a>Ошибка компилятора C2798

"Super:: member" является неоднозначным

Несколько унаследованных структур содержат член, на который имеется ссылка [Super](../../cpp/super.md). Эту ошибку можно исправить одним из следующих:

- Удаление B1 или B2 из списка наследования D.

- Изменение имени элемента данных в B1 или B2.

Следующий пример приводит к возникновению ошибки C2798:

```cpp
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
