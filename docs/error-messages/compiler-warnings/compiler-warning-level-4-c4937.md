---
title: "Предупреждение компилятора (уровень 4) C4937 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4937"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4937"
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4937
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"текст1" и "текст2" неразличимы в качестве аргументов для директивы "директива"  
  
 Из\-за способа обработки компилятором аргументов директив имена, которые имеют смысл для компилятора, такие как ключевые слова с несколькими текстовыми представлениями \(формы с одинарным и двойным подчеркиванием\), неразличимы.  
  
 Примеры таких строк: \_\_cdecl и \_\_forceinline.  Обратите внимание: при использовании параметра \/Za разрешены только формы с двойным подчеркиванием.  
  
 В следующем примере возникает ошибка C4937:  
  
```  
// C4937.cpp // compile with: /openmp /W4 #include "omp.h" int main() { #pragma omp critical ( __leave )   // C4937 ; // OK #pragma omp critical ( leave ) ; }  
```