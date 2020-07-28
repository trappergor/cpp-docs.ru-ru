---
title: Ошибка компилятора C2800
ms.date: 11/04/2016
f1_keywords:
- C2800
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
ms.openlocfilehash: 8bab5cd015bd28228b9829cb59cb3b6fdf2f3717
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214611"
---
# <a name="compiler-error-c2800"></a>Ошибка компилятора C2800

"operator оператор" не может быть перегружен

Следующие операторы не могут быть перегружены: доступ к членам класса ( `.` ), указатель на член ( `.*` ), разрешение области ( `::` ), условное выражение ( `? :` ) и **`sizeof`** .

Следующий пример приводит к возникновению ошибки C2800:

```cpp
// C2800.cpp
// compile with: /c
class C {
   operator:: ();   // C2800
};
```
