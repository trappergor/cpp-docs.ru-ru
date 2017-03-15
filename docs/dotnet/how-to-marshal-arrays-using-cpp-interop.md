---
title: "Практическое руководство. Упаковка и передача массивов с помощью взаимодействия C++ | Microsoft Docs"
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
  - "массивы [C++], маршалинг"
  - "взаимодействие C++, массивы"
  - "маршалинг данных [C++], массивы"
  - "взаимодействие [C++], массивы"
  - "маршалинг [C++], массивы"
ms.assetid: c2b37ab1-8acf-4855-ad3c-7d2864826b14
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Упаковка и передача массивов с помощью взаимодействия C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе продемонстрирован еще один аспект возможностей взаимодействия Visual C\+\+.  Для получения дополнительной информации см. [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 В следующем примере кода используются директивы \#pragma [managed, unmanaged](../preprocessor/managed-unmanaged.md), которые встраивают управляемые и неуправляемые функции в один файл. Эти функции также взаимодействуют и в случае их распределения в отдельные файлы.  Файлы, содержащие только неуправляемые функции, не требуется компилировать с использованием параметра [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
 В следующем примере кода показано, как передать управляемый массив неуправляемой функции.  Управляемая функция использует [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md) для подавления сборки мусора для массива перед вызовом неуправляемой функции.  Путем предоставления неуправляемой функции закрепленного указателя на кучу сборщика мусора можно избежать дополнительных действий, связанных с созданием копии массива.  Чтобы показать, что неуправляемая функция получает доступ к куче сборщика мусора, содержимое массива изменяется с ее помощью, и эти изменения отражаются, когда управление возвращается управляемой функции.  
  
```  
// PassArray1.cpp  
// compile with: /clr  
#ifndef _CRT_RAND_S  
#define _CRT_RAND_S  
#endif  
  
#include <iostream>  
#include <stdlib.h>  
using namespace std;  
  
using namespace System;  
  
#pragma unmanaged  
  
void TakesAnArray(int* a, int c) {  
   cout << "(unmanaged) array received:\n";  
   for (int i=0; i<c; i++)  
      cout << "a[" << i << "] = " << a[i] << "\n";  
  
   unsigned int number;  
   errno_t err;  
  
   cout << "(unmanaged) modifying array contents...\n";  
   for (int i=0; i<c; i++) {  
      err = rand_s( &number );  
      if ( err == 0 )  
         a[i] = number % 100;  
   }  
}  
  
#pragma managed  
  
int main() {  
   array<int>^ nums = gcnew array<int>(5);  
  
   nums[0] = 0;  
   nums[1] = 1;  
   nums[2] = 2;  
   nums[3] = 3;  
   nums[4] = 4;  
  
   Console::WriteLine("(managed) array created:");  
   for (int i=0; i<5; i++)  
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);  
  
   pin_ptr<int> pp = &nums[0];  
   TakesAnArray(pp, 5);  
  
   Console::WriteLine("(managed) contents:");  
   for (int i=0; i<5; i++)  
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);  
}  
```  
  
## Пример  
 В следующем примере кода демонстрируется передача неуправляемого массива управляемой функции.  Управляемая функция обращается к памяти массива напрямую \(вместо того чтобы создавать управляемый массив и копировать содержимое массива\), благодаря чему изменения, произведенные управляемой функцией, могут отражаться в неуправляемой функции, когда к ней возвращается управление.  
  
```  
// PassArray2.cpp  
// compile with: /clr   
#include <iostream>  
using namespace std;  
  
using namespace System;  
  
#pragma managed  
  
void ManagedTakesAnArray(int* a, int c) {  
   Console::WriteLine("(managed) array received:");  
   for (int i=0; i<c; i++)  
      Console::WriteLine("a[{0}] = {1}", i, a[i]);  
  
   cout << "(managed) modifying array contents...\n";  
   Random^ r = gcnew Random(DateTime::Now.Second);  
   for (int i=0; i<c; i++)  
      a[i] = r->Next(100);  
}  
  
#pragma unmanaged  
  
void NativeFunc() {  
   int nums[5] = { 0, 1, 2, 3, 4 };  
  
   printf_s("(unmanaged) array created:\n");  
   for (int i=0; i<5; i++)  
      printf_s("a[%d] = %d\n", i, nums[i]);  
  
   ManagedTakesAnArray(nums, 5);  
  
   printf_s("(ummanaged) contents:\n");  
   for (int i=0; i<5; i++)  
      printf_s("a[%d] = %d\n", i, nums[i]);  
}  
  
#pragma managed  
  
int main() {  
   NativeFunc();  
}  
```  
  
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)