---
title: Перебор коллекции библиотеки C++ Standard с использованием для каждого | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DTL collections, iterating over
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 963c8a4213da756f03e95924940dc179bd305f60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131346"
---
# <a name="iterating-over-c-standard-library-collection-by-using-for-each"></a>Перебор элементов коллекции библиотеки C++ Standard с использованием цикла for each
`for each` Ключевое слово может использоваться для итерации по коллекции стандартной библиотеки C++.  
  
## <a name="all-platforms"></a>Все платформы  
 **Заметки**  
  
 Коллекция стандартной библиотеки C++, также называемая *контейнер*. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).  
  
## <a name="examples"></a>Примеры  
 **Пример**  
  
 Следующий пример кода использует `for each` для прохода по [ \<карты >](../standard-library/map.md).  
  
```  
// for_each_stl.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
#include <string>  
using namespace std;  
  
int main() {  
   int retval  = 0;  
   map<string, int> months;  
  
   months["january"] = 31;  
   months["february"] = 28;  
   months["march"] = 31;  
   months["april"] = 30;  
   months["may"] = 31;  
   months["june"] = 30;  
   months["july"] = 31;  
   months["august"] = 31;  
   months["september"] = 30;  
   months["october"] = 31;  
   months["november"] = 30;  
   months["december"] = 31;  
  
   map<string, int> months_30;  
  
   for each( pair<string, int> c in months )  
      if ( c.second == 30 )  
         months_30[c.first] = c.second;  
  
   for each( pair<string, int> c in months_30 )  
      retval++;  
  
   cout << "Months with 30 days = " << retval << endl;  
}  
```  
  
 **Вывод**  
  
```Output  
Months with 30 days = 4  
```  
  
 **Пример**  
  
 В следующем примере кода используется ссылка const (`const&`) для переменной итерации с контейнерами стандартной библиотеки C++. Можно использовать ссылку на (`&`) как переменная итерации, на какой-либо коллекции типа, который может быть объявлен как *T*`&`.  
  
```  
// for_each_stl_2.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
using namespace std;  
  
int main() {  
   int retval = 0;  
  
   vector<int> col(3);  
   col[0] = 10;  
   col[1] = 20;  
   col[2] = 30;  
  
   for each( const int& c in col )  
      retval += c;  
  
   cout << "retval: " << retval << endl;  
}  
```  
  
 **Вывод**  
  
```Output  
retval: 60  
```  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 **Заметки**  
  
 Отсутствуют платформой комментарии об этой функции.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Заметки**  
  
 Отсутствуют платформой комментарии об этой функции.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
## <a name="see-also"></a>См. также  
 [для каждой из них в](../dotnet/for-each-in.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)