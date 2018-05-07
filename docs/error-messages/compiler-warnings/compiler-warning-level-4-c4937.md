---
title: Ошибка компилятора предупреждение (уровень 4) C4937 | Документы Microsoft
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
ms.openlocfilehash: 6ed7b33889677a304d303873799f36430c38129a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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