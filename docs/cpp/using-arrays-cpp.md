---
title: "Использование массивов (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++]
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 31402e2f113deb89fce6d2d8b6c3633f06a944be
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="using-arrays-c"></a>Использование массивов (C++)
К отдельным элементам массива можно обращаться при помощи оператора индекса массива (`[ ]`). Если в выражении используется одномерный массив, в котором нет индекса, то вычисление преобразует имя массива в указатель на первый элемент массива.  
  
```  
// using_arrays.cpp  
int main() {  
   char chArray[10];  
   char *pch = chArray;   // Evaluates to a pointer to the first element.  
   char   ch = chArray[0];   // Evaluates to the value of the first element.  
   ch = chArray[3];   // Evaluates to the value of the fourth element.  
}  
```  
  
 Если используются многомерные массивы, в выражениях можно использовать различные сочетания.  
  
```  
// using_arrays_2.cpp  
// compile with: /EHsc /W1  
#include <iostream>  
using namespace std;  
int main() {  
   double multi[4][4][3];   // Declare the array.  
   double (*p2multi)[3];  
   double (*p1multi);  
  
   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.  
   p2multi = multi[3];               // Make p2multi point to  
                                     // fourth "plane" of multi.  
   p1multi = multi[3][2];            // Make p1multi point to  
                                     // fourth plane, third row  
                                     // of multi.  
}  
```  
  
 В предыдущем примере объект `multi` представляет собой трехмерный массив типа `double`. Указатель `p2multi` указывает на массив типа `double` с размером 3. В этом примере массив используется с одним, двумя и тремя индексами. Хотя чаще всего определяют все индексы, в операторе `cout` иногда бывает удобнее выбирать определенное подмножество элементов массива, как показано в операторах, следующих за указанием объекта `cout`.  
  
## <a name="see-also"></a>См. также  
 [Массивы](../cpp/arrays-cpp.md)
