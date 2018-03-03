---
title: "Ошибка компилятора предупреждение (уровень 4) C4937 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4937
dev_langs:
- C++
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c054051db1b7c765dd2b144b8bd3426593896a91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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