---
title: "Ошибка компилятора C2381 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2381"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2381"
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2381
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция" : повторное определение; модификаторы \_\_declspec\(noreturn\) различаются  
  
 Функция была объявлена и затем определена, но в определении использовался модификатор `__declspec` [noreturn](../../cpp/noreturn.md).  Использование модификатора `noreturn` представляет собой переопределение функции; объявление и определение необходимо согласовать по использованию модификатора `noreturn`.  
  
 Следующий пример приводит к возникновению ошибки C2381:  
  
```  
// C2381.cpp  
// compile with: /c  
void f1();  
void __declspec(noreturn) f1() {}   // C2381  
void __declspec(noreturn) f2() {}   // OK  
```