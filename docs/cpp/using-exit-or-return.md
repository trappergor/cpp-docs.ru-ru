---
title: С помощью выхода или возвращать | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- return keyword [C++], using for program termination
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47fb8ff09fc50557283a0f4e8ef0e159bc900e86
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460949"
---
# <a name="using-exit-or-return"></a>Использование операторов exit и return
При вызове **выйти из** или выполнить **возвращают** инструкции от `main`, статические объекты удаляются в порядке, обратном их инициализации. В следующем примере показано выполнение такого процесса инициализации и удаления.  
  
## <a name="example"></a>Пример  
  
```cpp 
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
  
 В предыдущем примере статические объекты `sd1` и `sd2` созданы и инициализированы перед переходом в `main`. После завершения этой программы с помощью **возвращают** инструкции, в первом `sd2` уничтожается и затем `sd1`. Деструктор класса `ShowData` закрывает файлы, связанные с этими статическими объектами.   
  
 Другой способ записать этот код — объявить объекты `ShowData` с областью видимости блока, в результате чего они будут удаляться при выходе из области.  
  
```cpp 
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Дополнительные сведения о завершении](../cpp/additional-termination-considerations.md)