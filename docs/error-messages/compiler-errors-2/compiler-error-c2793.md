---
title: Ошибка компилятора C2793
ms.date: 11/04/2016
f1_keywords:
- C2793
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
ms.openlocfilehash: faf87334f1a98661078341a4d7dc11280802a376
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220214"
---
# <a name="compiler-error-c2793"></a>Ошибка компилятора C2793

"токен": непредвиденная лексема после "::", требуется идентификатор или ключевое слово "operator"

Единственными токенами, которые могут следовать, `__super::` являются идентификатор или ключевое слово **`operator`** .

Следующий пример приводит к возникновению ошибки C2793

```cpp
// C2793.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::(); // C2793
   }
};
```
