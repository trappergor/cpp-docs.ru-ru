---
title: "Манипуляторы потока вывода с одним аргументом (int или long) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "потоки вывода, манипуляторы аргументов int или long"
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Манипуляторы потока вывода с одним аргументом (int или long)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотека классов iostream предлагает набор макросов для создания параметризованной манипуляторов.  Манипуляторов с отдельными `int` или аргументом `long` особый случай.  Для создания манипулятор потока вывода, который принимает одно `int` или аргумент `long` \(например, `setw`\), необходимо использовать макрос \_Smanip, который определен в \<iomanip\>.  В этом примере определяется манипулятора `fillblank`, который вставляет заданное количество пробелов в поток.  
  
## Пример  
  
```  
// output_stream_manip.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <iomanip>  
using namespace std;  
  
void fb( ios_base& os, int l )  
{  
   ostream *pos = dynamic_cast<ostream*>(&os);  
   if (pos)  
   {  
      for( int i=0; i < l; i++ )  
      (*pos) << ' ';  
   };  
}  
  
_Smanip<int>  
   __cdecl fillblank(int no)  
   {     
   return (_Smanip<int>(&fb, no));  
   }  
  
int main( )  
{  
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";  
}  
```  
  
## См. также  
 [Пользовательские манипуляторы с аргументами](../standard-library/custom-manipulators-with-arguments.md)