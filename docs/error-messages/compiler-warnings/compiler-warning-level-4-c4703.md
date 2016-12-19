---
title: "Предупреждение компилятора (уровень 4) C4703 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4703"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4703"
ms.assetid: 5dad454e-69e3-4931-9168-050a861c05f8
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4703
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Потенциально неинициализированных переменных локального указателя «имя»  
  
 Переменная указателя локального *name* может использоваться без необходимости присвоенным значением.  Это может привести к непредсказуемым результатом.  
  
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
 [Предупреждение компилятора \(уровень 4\) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)