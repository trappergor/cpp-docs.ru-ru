---
title: "Ошибка компилятора C3899 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3899"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3899"
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Ошибка компилятора C3899
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var" : левостороннее использование элемента данных initonly не разрешается напрямую в параллельной области в классе "class"  
  
 Элемент данных [initonly](../../dotnet/initonly-cpp-cli.md) нельзя инициализировать внутри этой части конструктора, которая расположена в области [parallel](../../parallel/openmp/reference/parallel.md).  Это происходит потому что компилятор осуществляет внутреннее перемещение этого кода, из условия что этот код больше не является частью конструктора.  
  
 Чтобы устранить это, инициализируйте элемент данных initonly в конструкторе, но вне параллельной области.  
  
## Пример  
 В следующем примере возникает сообщение об ошибке С3899.  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```