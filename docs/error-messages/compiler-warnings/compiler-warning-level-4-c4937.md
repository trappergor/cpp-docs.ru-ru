---
title: Предупреждение компилятора (уровень 4) C4937 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4937
dev_langs:
- C++
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7bc6232458b357f41e859c58d4b6b77f78ef2a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118301"
---
# <a name="compiler-warning-level-4-c4937"></a>Предупреждение компилятора (уровень 4) C4937

"текст1" и "текст2" неразличимы в качестве аргументов для директивы "директива"

Из-за способа обработки компилятором аргументов директив имена, которые имеют смысл для компилятора, такие как ключевые слова с несколькими текстовыми представлениями (формы с одинарным и двойным подчеркиванием), неразличимы.

Примеры таких строк: __cdecl и \__forceinline.  Обратите внимание: при использовании параметра /Za разрешены только формы с двойным подчеркиванием.

В следующем примере возникает ошибка C4937:

```
// C4937.cpp
// compile with: /openmp /W4
#include "omp.h"
int main() {
   #pragma omp critical ( __leave )   // C4937
   ;

   // OK
   #pragma omp critical ( leave )
   ;
}
```