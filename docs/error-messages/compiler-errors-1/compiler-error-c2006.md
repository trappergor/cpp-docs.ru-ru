---
title: Ошибка компилятора C2006 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9468be17584a54047563bace2b35f5cb4888b41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031214"
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