---
title: "Практическое руководство. Преобразование типа System::String к wchar_t* или char* | Microsoft Docs"
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
  - "char - тип данных, конвертирование System::String в"
  - "PtrToStringChars - метод"
  - "System::String"
  - "System::String, конвертирование в char или wchar_t"
  - "wchart - тип, конвертирование System::String"
ms.assetid: 385da01b-5649-4543-8076-e3e251243ff0
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Преобразование типа System::String к wchar_t* или char*
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представленная в файле Vcclr.h функция `PtrToStringChars` используется для преобразования типа <xref:System.String> к типу `wchar_t *` или `char *` машинного кода.  Эта функция всегда возвращает указатель на двухбайтную строку в формате Юникод, который является внутренним форматом строк CLR.  Затем можно выполнить преобразование из двухбайтного формата, как показано в следующем примере.  
  
## Пример  
  
```  
// convert_string_to_wchar.cpp  
// compile with: /clr  
#include < stdio.h >  
#include < stdlib.h >  
#include < vcclr.h >  
  
using namespace System;  
  
int main() {  
   String ^str = "Hello";  
  
   // Pin memory so GC can't move it while native function is called  
   pin_ptr<const wchar_t> wch = PtrToStringChars(str);  
   printf_s("%S\n", wch);  
  
   // Conversion to char* :  
   // Can just convert wchar_t* to char* using one of the   
   // conversion functions such as:   
   // WideCharToMultiByte()  
   // wcstombs_s()  
   // ... etc  
   size_t convertedChars = 0;  
   size_t  sizeInBytes = ((str->Length + 1) * 2);  
   errno_t err = 0;  
   char    *ch = (char *)malloc(sizeInBytes);  
  
   err = wcstombs_s(&convertedChars,   
                    ch, sizeInBytes,  
                    wch, sizeInBytes);  
   if (err != 0)  
      printf_s("wcstombs_s  failed!\n");  
  
    printf_s("%s\n", ch);  
}  
```  
  
  **Hello**  
**Hello**   
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)