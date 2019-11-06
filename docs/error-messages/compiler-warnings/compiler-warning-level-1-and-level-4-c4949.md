---
title: Предупреждение компилятора (уровень 1 и уровень 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: f2876813131271ebb2561f8ea7435bb96dc2ce17
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627415"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>Предупреждение компилятора (уровень 1 и уровень 4) C4949

директивы pragma "Managed" и "unmanaged" имеют смысл только при компиляции с параметром "/CLR [: Option]"

Компилятор игнорирует [управляемые](../../preprocessor/managed-unmanaged.md) и неуправляемые прагмы, если исходный код не компилируется с [параметром/CLR](../../build/reference/clr-common-language-runtime-compilation.md). Это предупреждение носит информационный характер.

Следующий пример приводит к возникновению ошибки C4949:

```cpp
// C4949.cpp
// compile with: /LD /W1
#pragma managed   // C4949
```

При использовании **неуправляемого #pragma** без **/CLR**, C4949 представляет собой предупреждение уровня 4.

Следующий пример приводит к возникновению ошибки C4949:

```cpp
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```