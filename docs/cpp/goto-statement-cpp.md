---
title: "Оператор goto (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "goto_cpp"
  - "goto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "goto - ключевое слово [C++]"
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор goto (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор `goto` осуществляет безусловную передачу управления оператору, метка которого задана идентификатором.  
  
## Синтаксис  
  
```  
goto identifier;  
```  
  
## Заметки  
 Оператор, метка которого задана в параметре `identifier`, должен находиться в текущей функции.  Все имена, заданные в параметре `identifier`, являются членами внутреннего пространства имен и, следовательно, не пересекаются с другими идентификаторами.  
  
 Метка оператора имеет значение только для оператора `goto`; в остальных случаях метки операторов игнорируются.  Повторное объявление меток невозможно.  
  
 Вместо `break` во всех случаях, когда это возможно, рекомендуется использовать операторы `continue`, `return` и `goto`.  Однако, поскольку оператор `break` выполняет выход только из одного уровня цикла, возможны ситуации, когда для выхода из глубоко вложенного цикла может потребоваться использовать оператор `goto`.  
  
 Дополнительные сведения о метках и операторе `goto` см. в разделах [Операторы с метками](../cpp/labeled-statements.md) и [Использование меток с оператором goto](http://msdn.microsoft.com/ru-ru/6cd7c31a-9822-4241-8566-f79f51be48fe).  
  
## Пример  
 В этом примере оператор `goto` передает управление в точку с меткой `stop`, когда значение переменной `i` равно 3.  
  
```  
// goto_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 2; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 3 )  
                goto stop;  
        }  
    }  
  
    // This message does not print:   
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop:   
    printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
  **Outer loop executing.  i \= 0**  
 **Inner loop executing.  j \= 0**  
 **Inner loop executing.  j \= 1**  
**Outer loop executing.  i \= 1**  
 **Inner loop executing.  j \= 0**  
 **Inner loop executing.  j \= 1**  
**Outer loop executing.  i \= 2**  
 **Inner loop executing.  j \= 0**  
 **Inner loop executing.  j \= 1**  
**Outer loop executing.  i \= 3**  
 **Inner loop executing.  j \= 0**  
**Jumped to stop.  i \= 3**    
## См. также  
 [Операторы перехода](../cpp/jump-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)