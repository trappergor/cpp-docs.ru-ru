---
title: Ошибка компилятора C2850
ms.date: 11/04/2016
f1_keywords:
- C2850
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
ms.openlocfilehash: 0a87767bb9194a0a9858dd1734abbe516ffcfac0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758506"
---
# <a name="compiler-error-c2850"></a>Ошибка компилятора C2850

"конструкция": допускается только в области видимости файла; не может находиться во вложенной конструкции

Конструкции, такие как некоторые директивы pragma, могут присутствовать только в глобальной области видимости.

Следующий пример приводит к возникновению ошибки C2850:

```cpp
// C2850.cpp
// compile with: /c /Yc
// try the following line instead
// #pragma hdrstop
namespace X {
   #pragma hdrstop   // C2850
};
```
