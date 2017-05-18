---
title: "Манипуляторы потока вывода с одним аргументом (int или long) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 84cbc5d016f6796a1cab208a1d77b51ea2ac6ecb
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Манипуляторы потока вывода с одним аргументом (int или long)
Библиотека классов iostream предоставляет набор макросов для создания параметризованных манипуляторов. Манипуляторы с одним аргументом `int` или `long` представляют собой особый случай. Для создания манипулятора потока вывода, принимающего один аргумент `int` или `long` (как `setw`), необходимо использовать макрос _Smanip, который определен в \<iomanip>. В этом примере определяется манипулятор `fillblank`, который вставляет в поток заданное число пробелов.  
  
## <a name="example"></a>Пример  
  
```cpp  
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
  
## <a name="see-also"></a>См. также  
 [Пользовательские манипуляторы с аргументами](../standard-library/custom-manipulators-with-arguments.md)


