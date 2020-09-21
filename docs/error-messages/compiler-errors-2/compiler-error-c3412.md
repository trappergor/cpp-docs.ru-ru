---
title: Ошибка компилятора C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: 6918e3be0a0288bab50d63a188bc33df87fe7754
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742896"
---
# <a name="compiler-error-c3412"></a>Ошибка компилятора C3412

"шаблон": не удается заспециализациь шаблона в текущей области

Шаблон не может быть специализированным в области видимости класса, только в области глобальных или пространств имен.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C3412.

```cpp
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

В следующем примере показано возможное решение.

```cpp
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```
