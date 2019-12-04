---
title: Ошибка компилятора C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: a7d20a7658a75a492e19b9e81acaa3b6fce5cae7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743943"
---
# <a name="compiler-error-c2460"></a>Ошибка компилятора C2460

"идентификатор1": использует "идентификатор2", который определяется

Класс или структура (`identifier2`) объявляется как член самого себя (`identifier1`). Рекурсивные определения классов и структур не допускаются.

Следующий пример приводит к возникновению ошибки C2460:

```cpp
// C2460.cpp
class C {
   C aC;    // C2460
};
```

Вместо этого используйте ссылку на указатель в классе.

```cpp
// C2460.cpp
class C {
   C * aC;    // OK
};
```
