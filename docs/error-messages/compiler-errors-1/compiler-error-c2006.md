---
title: Ошибка компилятора C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: 64f81929916cd3a4adf38a302ea34d46d9a5c070
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756556"
---
# <a name="compiler-error-c2006"></a>Ошибка компилятора C2006

для "директивы" требуется имя файла, найдено "token"

Для директив, таких как [#include](../../preprocessor/hash-include-directive-c-cpp.md) или [#import](../../preprocessor/hash-import-directive-cpp.md) , требуется имя файла. Чтобы устранить эту ошибку, убедитесь, что *токен* является допустимым именем файла. Кроме того, заключите имя файла в двойные кавычки или угловые скобки.

Следующий пример приводит к возникновению ошибки C2006:

```cpp
// C2006.cpp
#include stdio.h   // C2006
```

Возможное решение

```cpp
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```
