---
title: Предупреждение компилятора (уровень 1 и уровень 4) C4949 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f806912188ada3a4f97f0b1500e811d1271f40fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077312"
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