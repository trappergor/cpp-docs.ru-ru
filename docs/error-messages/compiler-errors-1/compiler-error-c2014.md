---
title: Ошибка компилятора C2014
ms.date: 11/04/2016
f1_keywords:
- C2014
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
ms.openlocfilehash: 58cf9867a9e36b304ab9da79084bc01dff453892
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350706"
---
# <a name="compiler-error-c2014"></a>Ошибка компилятора C2014

команда препроцессора не должна начинаться с пробела

`#` Знак директивы препроцессора, должен быть первый символ в строке, которая не является пробелом.

Следующий пример приводит к возникновению ошибки C2014:

```
// C2014.cpp
int k; #include <stdio.h>   // C2014
```

Возможное решение

```
// C2014b.cpp
// compile with: /c
int k;
#include <stdio.h>
```