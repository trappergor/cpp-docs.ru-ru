---
title: Ошибка компилятора C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: 85cac4919c048c30a3ed1ff5573a3c14b77da0bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737196"
---
# <a name="compiler-error-c2178"></a>Ошибка компилятора C2178

"*идентификатор*" не может быть объявлен с описателем "*спецификатор*"

В объявлении использовался спецификатор `mutable`, но в данном контексте спецификатор не разрешен.

Описатель `mutable` может применяться только к именам элементов данных класса и не может применяться к именам, объявленным `const` или `static`, и не может применяться к ссылочным элементам.

## <a name="example"></a>Пример

В следующем примере показано, как может произойти C2178, и как устранить эту проблему.

```cpp
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```
