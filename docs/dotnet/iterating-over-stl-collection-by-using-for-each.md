---
title: "Перебор элементов коллекции STL с использованием цикла for each | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "коллекции DTL, итерация через"
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Перебор элементов коллекции STL с использованием цикла for each
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `for each` можно использовать для итерации по коллекции стандартной библиотеки C\+\+ C \(STL\).  
  
## Все платформы  
 **Примечания**  
  
 Коллекция STL также контейнером.  Для получения дополнительной информации см. [Контейнеры STL](../standard-library/stl-containers.md).  
  
## Примеры  
 **Пример**  
  
 В следующем примере кода используется `for each` для итерации [\< map \>](../Topic/%3Cmap%3E.md).  
  
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
  
 **Output**  
  
  **С днями месяца 30 \= 4** **Пример**  
  
 В следующем примере кода используется ссылка const \(`const&`\) для переменной итерации с контейнерами STL.  Можно использовать ссылку \(`&`\) как переменная итерации на любой коллекции типов, могут быть объявлены как *T*`&`.  
  
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
  
 **Output**  
  
  **retval: 60**   
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Примечания**  
  
 Отсутствуют замечания платформы об этой функции.  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Примечания**  
  
 Отсутствуют замечания платформы об этой функции.  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
## См. также  
 [for each, in](../dotnet/for-each-in.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)