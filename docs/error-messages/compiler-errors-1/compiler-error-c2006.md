---
title: Ошибка компилятора C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: c23f17483925f25468214165fb459db577e576fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209014"
---
# <a name="compiler-error-c2006"></a>Ошибка компилятора C2006

«Директива» требуется имя файла, найден «токен»

Директивы, такие как [#include](../../preprocessor/hash-include-directive-c-cpp.md) или [#import](../../preprocessor/hash-import-directive-cpp.md) должно использоваться имя файла. Чтобы устранить эту ошибку, убедитесь, что *маркера* является допустимым именем файла. Кроме того поместите имя файла в двойных кавычках или угловых скобках.

Следующий пример приводит к возникновению ошибки C2006:

```
// C2006.cpp
#include stdio.h   // C2006
```

Возможное решение

```
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```