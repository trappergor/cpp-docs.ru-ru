---
title: "Использование массивов (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++]"
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование массивов (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

К отдельным элементам массива можно обращаться при помощи оператора индекса массива \(`[ ]`\).  Если в выражении используется одномерный массив, в котором нет индекса, то вычисление преобразует имя массива в указатель на первый элемент массива.  
  
```  
// using_arrays.cpp  
int main() {  
   char chArray[10];  
   char *pch = chArray;   // Evaluates to a pointer to the first element.  
   char   ch = chArray[0];   // Evaluates to the value of the first element.  
   ch = chArray[3];   // Evaluates to the value of the fourth element.  
}  
```  
  
 Если используются многомерные массивы, в выражениях можно использовать различные сочетания.  
  
```  
// using_arrays_2.cpp  
// compile with: /EHsc /W1  
#include <iostream>  
using namespace std;  
int main() {  
   double multi[4][4][3];   // Declare the array.  
   double (*p2multi)[3];  
   double (*p1multi);  
  
   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.  
   p2multi = multi[3];               // Make p2multi point to  
                                     // fourth "plane" of multi.  
   p1multi = multi[3][2];            // Make p1multi point to  
                                     // fourth plane, third row  
                                     // of multi.  
}  
```  
  
 В предыдущем примере объект `multi` представляет собой трехмерный массив типа `double`.  Указатель `p2multi` указывает на массив типа `double` с размером 3.  В этом примере массив используется с одним, двумя и тремя индексами.  Хотя чаще всего определяют все индексы, в операторе `cout` иногда бывает удобнее выбирать определенное подмножество элементов массива, как показано в операторах, следующих за указанием объекта `cout`.  
  
## См. также  
 [Массивы](../Topic/Arrays%20\(C++\).md)