---
title: "Разрешение перегрузки вызовов шаблонов функций | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "разрешение перезагрузки шаблонов функций"
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Разрешение перегрузки вызовов шаблонов функций
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблон функции может перегрузить нешаблонные функции с одинаковым именем.  В этом сценарии вызовы функций разрешаются с помощью вычета аргумента шаблона для создания экземпляра шаблона функции с уникальной специализацией.  Если вычет аргумента шаблона завершается с ошибкой, считается, что другие перезагрузки функций разрешат вызов.  Эти другие перезагрузки, также известные как набор кандидатов, включают нешаблонные функции и другие экземпляры шаблонов функций.  Если вычет аргумента шаблона завершается успешно, то созданная функция сравнивается с другими функциями для определения оптимального совпадения с учетом правил разрешения перегрузок.  Дополнительные сведения см. в разделах [Перегрузка](../misc/overloading-cpp.md) и [Сопоставление аргументов](../Topic/Argument%20Matching.md).  
  
## Пример  
 Если нешаблонная функция хорошо соответствует функции шаблона, используется нешаблонная функция \(если аргументы шаблона не заданы явно\), как в вызове `f(1, 1)` в следующем примере.  
  
```  
// template_name_resolution9.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
void f(char, char) { cout << "f(char, char)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   f(1, 1);   // Equally good match; choose the nontemplate function.  
   f('a', 1); // Chooses the template function.  
   f<int, int>(2, 2);  // Template arguments explicitly specified.  
}  
```  
  
  **f\(int, int\)**  
**void f\(T1, T2\)**  
**void f\(T1, T2\)**   
## Пример  
 В следующем примере показано, что точное соответствие функции шаблона предпочтительнее, если требуется преобразование нешаблонной функции.  
  
```  
// template_name_resolution10.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   long l = 0;  
   int i = 0;  
   // Call the template function f(long, int) because f(int, int)  
   // would require a conversion from long to int.  
   f(l, i);  
}  
```  
  
  **void f\(T1, T2\)**   
## См. также  
 [Разрешение имен](../cpp/templates-and-name-resolution.md)   
 [typename](../Topic/typename.md)   
 [Выведение аргументов шаблонов](../Topic/Template%20Argument%20Deduction.md)