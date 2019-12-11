---
title: Предупреждение компилятора (уровень 4) C4937
ms.date: 11/04/2016
f1_keywords:
- C4937
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
ms.openlocfilehash: dd7a7f9ac3d0ce0798a88f753cb0ccb4addbd5bc
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988755"
---
# <a name="compiler-warning-level-4-c4937"></a>Предупреждение компилятора (уровень 4) C4937

"текст1" и "текст2" неразличимы в качестве аргументов для директивы "директива"

Из-за способа обработки компилятором аргументов директив имена, которые имеют смысл для компилятора, такие как ключевые слова с несколькими текстовыми представлениями (формы с одинарным и двойным подчеркиванием), неразличимы.

Примерами таких строк являются __cdecl и \__forceinline.  Обратите внимание: при использовании параметра /Za разрешены только формы с двойным подчеркиванием.

В следующем примере возникает ошибка C4937:

```cpp
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
