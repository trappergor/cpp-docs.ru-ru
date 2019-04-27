---
title: Предупреждение компилятора (уровень 1 и 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: 8050edbd7a653776d046bc7b4155fd43094d9a5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187526"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>Предупреждение компилятора (уровень 1 и 4) C4949

директивы pragma «managed» и «unmanaged» имеют смысл только в том случае, при компиляции с "/ clr [: option]"

Компилятор игнорирует [управляемых](../../preprocessor/managed-unmanaged.md) и неуправляемые директив pragma, если исходный код не компилируется с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md). Это предупреждение носит информационный характер.

Следующий пример приводит к возникновению ошибки C4949:

```
// C4949.cpp
// compile with: /LD /W1
#pragma managed   // C4949
```

Когда **#pragma неуправляемого** используется без **/CLR**, C4949 является предупреждение уровня 4.

Следующий пример приводит к возникновению ошибки C4949:

```
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```