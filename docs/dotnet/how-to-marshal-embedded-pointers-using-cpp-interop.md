---
title: "Практическое руководство. Упаковка встроенных указателей посредством взаимодействия C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "взаимодействие C++, встроенные указатели"
  - "маршалинг данных [C++], встроенные указатели"
  - "взаимодействие [C++], встроенные указатели"
  - "маршалинг [C++], встроенные указатели"
  - "указатели [C++], маршалинг"
  - "структуры [C++], маршалинг встроенных указателей"
ms.assetid: 05fb8858-97f2-47aa-86b2-2c0ad713bdb2
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Упаковка встроенных указателей посредством взаимодействия C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода используются директивы \#pragma [managed, unmanaged](../preprocessor/managed-unmanaged.md), которые встраивают управляемые и неуправляемые функции в один файл. Эти функции также взаимодействуют и в случае их распределения в отдельные файлы.  Файлы, содержащие только неуправляемые функции, не требуется компилировать с использованием параметра [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
 В следующем примере показан порядок вызова неуправляемой функции, которая принимает содержащую указатели структуру, из управляемой функции.  С помощью управляемой функции создается экземпляр структуры и инициализируется встроенный указатель с использованием ключевого слова new \(вместо ключевого слова [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)\).  Поскольку при этом осуществляется выделение памяти в собственной куче, не требуется закреплять массив, чтобы запретить сборку мусора.  Однако чтобы предотвратить утечку памяти, необходимо явно освободить память.  
  
```  
// marshal_embedded_pointer.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// unmanaged struct  
struct ListStruct {  
   int count;  
   double* item;  
};  
  
#pragma unmanaged  
  
void UnmanagedTakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
  
#pragma managed  
  
int main() {  
   ListStruct list;  
   list.count = 10;  
   list.item = new double[list.count];  
  
   Console::WriteLine("[managed] count = {0}", list.count);  
   Random^ r = gcnew Random(0);  
   for (int i=0; i<list.count; i++) {  
      list.item[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, list.item[i]);  
   }  
  
   UnmanagedTakesListStruct( list );  
   delete list.item;  
}  
```  
  
  **\[управляемая\] количество \= 10**  
**массив \[0\] \= 72,624326996796**  
**массив \[1\] \= 81,7325359590969**  
**массив \[2\] \= 76,8022689394663**  
**массив \[3\] \= 55,8161191436537**  
**массив \[4\] \= 20,6033154021033**  
**массив \[5\] \= 55,8884794618415**  
**массив \[6\] \= 90,6027066011926**  
**массив \[7\] \= 44,2177873310716**  
**массив \[8\] \= 97,754975314138**  
**массив \[9\] \= 27,370445768987**  
**\[неуправляемая\] количество \= 10**  
**массив \[0\] \= 72,624327**  
**массив \[1\] \= 81,732536**  
**массив \[2\] \= 76,802269**  
**массив \[3\] \= 55,816119**  
**массив \[4\] \= 20,603315**  
**массив \[5\] \= 55,888479**  
**массив \[6\] \= 90,602707**  
**массив \[7\] \= 44,217787**  
**массив \[8\] \= 97,754975**  
**массив \[9\] \= 27,370446**   
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)