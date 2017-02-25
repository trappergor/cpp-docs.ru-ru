---
title: "Предупреждение компилятора (уровень 4) C4701 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4701"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4701"
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Предупреждение компилятора (уровень 4) C4701
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Потенциально использована неинициализированная локальная переменная «имя»  
  
 Локальная переменная *name* может использоваться без необходимости присвоенным значением.  Это может привести к непредсказуемым результатом.  
  
## Пример  
 Следующий код создает C4701 и C4703.  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr) // C4701 and C4703  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
  **C\-: \\src\\test.cpp \(10\). предупреждение C4701: потенциально использована неинициализированная локальная переменная используется «p»**  
 **C\-: \\src\\test.cpp \(10\). предупреждение C4703: потенциально неинициализированных переменных локального указателя «p»,** Чтобы исправить это предупреждение, используйте переменную, как показано в следующем примере:  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p = nullptr;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr)  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
## См. также  
 [Предупреждения, \/sdl и использование неинициализированных переменная обнаружение](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)   
 [Предупреждение компилятора \(уровень 4\) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)