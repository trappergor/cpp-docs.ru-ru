---
title: Ошибка компилятора C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: cd153bb5b331872bfe35b046d41612998bd0eff7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386009"
---
# <a name="compiler-error-c2178"></a>Ошибка компилятора C2178

"*идентификатор*«не может объявляться с»*описатель*" описатель

Объект `mutable` используется спецификатор в объявлении, но описатель не допускается в данном контексте.

`mutable` Описатель могут применяться только к именам членов класса данных и не могут быть назначены имена, объявленные `const` или `static`и не могут применяться к элементам ссылки.

## <a name="example"></a>Пример

В следующем примере показано, как может возникнуть C2178 и способы ее устранения.

```
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```
