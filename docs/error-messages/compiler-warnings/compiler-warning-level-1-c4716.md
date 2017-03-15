---
title: "Предупреждение компилятора (уровень 1) C4716 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4716"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4716"
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 1) C4716
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": функция должна возвращать значение  
  
 Данная функция не вернула значение.  
  
 Только функции с возвращаемым типом "void" могут использовать команду возвращения без возвращаемого значения.  
  
 При вызове функции будет возвращено неопределенное значение.  
  
 Данное предупреждение автоматически переходит в разряд ошибки.  Для устранения этого состояния следует использовать предупреждение директивы [\#pragma](../../preprocessor/warning.md).  
  
 Следующий пример приводит к возникновению ошибки C4716:  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```