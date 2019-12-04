---
title: Ошибка компилятора C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 292f5c6ab9a4e14077f848ff57ff08adefeb09a1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757336"
---
# <a name="compiler-error-c2008"></a>Ошибка компилятора C2008

"символ": не требуется в макроопределении

Символ отображается сразу после имени макроса. Чтобы устранить эту ошибку, после имени макроса должен быть пробел.

Следующий пример приводит к возникновению ошибки C2008:

```cpp
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

Возможное решение

```cpp
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```
