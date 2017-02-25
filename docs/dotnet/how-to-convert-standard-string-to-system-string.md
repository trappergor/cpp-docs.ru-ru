---
title: "Практическое руководство. Преобразование стандартной строки к типу System::String | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Стандартная библиотека C++, конвертирование строк в System::String"
  - "преобразование строк [C++], Стандартная библиотека строк C++"
  - "строки [C++], преобразование"
ms.assetid: 1fde79a0-9d0b-44e5-981b-e8f2676c199d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Практическое руководство. Преобразование стандартной строки к типу System::String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В данном разделе показаны способы преобразования стандартной строки библиотеки C\+\+ \([\<string\>](../standard-library/string.md)\) к типу <xref:System.String>.  
  
## Пример  
  
```  
// convert_standard_string_to_system_string.cpp  
// compile with: /clr  
#include <string>  
#include <iostream>  
using namespace System;  
using namespace std;  
  
int main() {  
   string str = "test";  
   cout << str << endl;  
   String^ str2 = gcnew String(str.c_str());  
   Console::WriteLine(str2);  
  
   // alternatively  
   String^ str3 = gcnew String(str.c_str());  
   Console::WriteLine(str3);  
}  
```  
  
  **тест**  
**тест**  
**тест**   
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)