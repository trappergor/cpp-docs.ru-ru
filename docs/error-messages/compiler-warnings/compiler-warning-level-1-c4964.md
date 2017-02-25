---
title: "Предупреждение компилятора (уровень 1) C4964 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4964"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4964"
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 1) C4964
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметры оптимизации не указаны; сведения о профиле не будут собраны  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) и [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) были указаны, но никаких оптимизаций не потребовалось, так что никаких PGC\-файлов не было создано и, следовательно, профильные оптимизации невозможны.  
  
 Если нужно, чтобы PGC\-файлы были созданы при выполнении вашего приложения, укажите один из параметров компилятора [\/O](../../build/reference/o-options-optimize-code.md).  
  
 Следующий пример приводит к возникновению ошибки C4964:  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```