---
title: "Использование операторов exit и return | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit - функция"
  - "return - ключевое слово [C++], используется для завершения программы"
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование операторов exit и return
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При вызове **exit** или выполнении оператора `return` из **main** статические объекты удаляются в порядке, обратном их инициализации.  В следующем примере показано выполнение такого процесса инициализации и удаления.  
  
## Пример  
  
```  
// using_exit_or_return1.cpp  
#include <stdio.h>  
class ShowData {  
public:  
   // Constructor opens a file.  
   ShowData( const char *szDev ) {  
   errno_t err;  
      err = fopen_s(&OutputDev, szDev, "w" );  
   }  
  
   // Destructor closes the file.  
   ~ShowData() { fclose( OutputDev ); }  
  
   // Disp function shows a string on the output device.  
   void Disp( char *szData ) {   
      fputs( szData, OutputDev );  
   }  
private:  
   FILE *OutputDev;  
};  
  
//  Define a static object of type ShowData. The output device  
//   selected is "CON" -- the standard output device.  
ShowData sd1 = "CON";  
  
//  Define another static object of type ShowData. The output  
//   is directed to a file called "HELLO.DAT"  
ShowData sd2 = "hello.dat";  
  
int main() {  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
 В предыдущем примере статические объекты `sd1` и `sd2` созданы и инициализированы перед переходом в `main`.  После завершения выполнения данной программы с помощью оператора `return` сначала удаляется `sd2`, а затем — `sd1`.  Деструктор класса `ShowData` закрывает файлы, связанные с этими статическими объектами. \(Дополнительные сведения об инициализации, конструкторах и деструкторах см. в разделе [Специальные функции\-члены](../misc/special-member-functions-cpp.md).\)  
  
 Другой способ записать этот код — объявить объекты `ShowData` с областью видимости блока, в результате чего они будут удаляться при выходе из области.  
  
```  
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## См. также  
 [Дополнительные сведения о завершении](../cpp/additional-termination-considerations.md)