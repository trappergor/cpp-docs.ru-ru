---
title: "Оператор continue (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "continue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "continue - ключевое слово [C]"
  - "циклические структуры, continue - ключевое слово"
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Оператор continue (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор `continue` передает элемент управления в следующую итерацию ближайшего внешнего оператора `do`, `for` или `while`, в которой она отображается, минуя все оставшиеся операторы в теле оператора `do`, `for` или `while`.  
  
## Синтаксис  
 `jump-statement`:  
 `continue;`  
  
 Следующая итерация оператора `do`, `for` или `while` определяется следующим образом.  
  
-   В операторе `do` или `while` следующая итерация начинается с повторного вычисления выражения оператора `do` или `while`.  
  
-   Оператор `continue` в операторе `for` приводит к вычислению выражения цикла оператора `for`.  Затем компилятор повторно вычисляет условное выражение и в зависимости от результата либо завершает, либо выполняет итерацию тела оператора.  Дополнительные сведения об операторе `for` и его нетерминальных символах см. в разделе [Оператор for](../c-language/for-statement-c.md).  
  
 Ниже приводится пример оператора `continue`.  
  
```  
while ( i-- > 0 )   
{  
    x = f( i );  
    if ( x == 1 )  
        continue;  
    y += x * x;  
}  
```  
  
 В этом примере тело оператора выполняется при `i` больше 0.  Для первой переменной `f(i)` присваивается значение `x`; затем, если `x` равно 1, выполняется оператор `continue`.  Остальные операторы в теле игнорируются, и выполнение возобновляется в начале цикла с вычисления теста цикла.  
  
## См. также  
 [Оператор continue](../cpp/continue-statement-cpp.md)