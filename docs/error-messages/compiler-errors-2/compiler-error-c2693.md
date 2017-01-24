---
title: "Ошибка компилятора C2693 | Microsoft Docs"
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
  - "C2693"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2693"
ms.assetid: b7364ca8-b6be-48c0-97d6-6029787fb171
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2693
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

operator: недопустимое сравнение для ссылок на управляемый массив или массив WinRT  
  
 Невозможно проверить управляемый массив или массив WinRT на любые типы неравенства.  Например, можно проверить, равны ли управляемые массивы, но нельзя проверить, больше ли один массив другого или меньше.  
  
 **Управляемые расширения для C\+\+**  
  
 Невозможно проверить массив [\_\_gc](../Topic/__gc.md) на любые типы неравенства.  Например, можно проверить, равны ли управляемые массивы, но нельзя проверить, больше ли один массив другого или меньше.  
  
 Следующий пример приводит к возникновению ошибки C2693:  
  
```  
// C2693b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
int func3(int a __gc[], int b __gc[]) {  
   return a < b;    // C2693  
}  
int func1(int a __gc[], int b __gc[]) {  
   return a != b;   // OK  
}  
  
int func2(int a __gc[], int b __gc[]) {  
   return a == b;   // OK  
}  
```