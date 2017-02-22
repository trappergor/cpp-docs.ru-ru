---
title: "Двоичные выходные файлы | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "двоичные данные, двоичные выходные файлы"
  - "файлы [C++], двоичные выходные файлы"
  - "ввод-вывод [C++], двоичные выходные файлы"
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Двоичные выходные файлы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Изначально потоки предназначены для текста, поэтому режим вывода по умолчанию текст.  В режиме текста, символ новой строки \(шестнадцатеричной системе счисления 10\) развернуть на RETURN\- переводу строки экипажа разрядному только \(16\).  Расширение может вызвать проблемы, как показано ниже:  
  
```  
// binary_output_files.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
int main( )  
{  
    ofstream os( "test.dat" );  
    os.write( (char *) iarray, sizeof( iarray ) );  
}  
```  
  
 Можно предположить программа для вывода последовательность байтов {99, 0, 10, 0}; вместо этого она выводит {99, 0, 13, 10, 0}, которая вызывает проблемы программы, ожидающую бинарный входных данных.  Если требуется значение true двоичный выход, в котором символы записываются непреобразованный, можно определить двоичный выход с помощью аргумента режима конструктора [ofstream](../Topic/ofstream.md):  
  
```  
// binary_output_files2.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
  
int main()  
{  
   ofstream ofs ( "test.dat", ios_base::binary );  
  
   // Exactly 8 bytes written  
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );   
}  
```  
  
## См. также  
 [Потоки вывода](../standard-library/output-streams.md)