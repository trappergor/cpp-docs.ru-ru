---
title: Разрешение перегрузки вызовов шаблонов функций | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function templates overload resolution
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d4a0e2867c5057eb5808c4d39687961eabba6dd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420032"
---
# <a name="overload-resolution-of-function-template-calls"></a>Разрешение перегрузки вызовов шаблонов функций
Шаблон функции может перегрузить нешаблонные функции с одинаковым именем. В этом сценарии вызовы функций разрешаются с помощью вычета аргумента шаблона для создания экземпляра шаблона функции с уникальной специализацией. Если вычет аргумента шаблона завершается с ошибкой, считается, что другие перезагрузки функций разрешат вызов. Эти другие перезагрузки, также известные как набор кандидатов, включают нешаблонные функции и другие экземпляры шаблонов функций. Если вычет аргумента шаблона завершается успешно, то созданная функция сравнивается с другими функциями для определения оптимального совпадения с учетом правил разрешения перегрузок. Дополнительные сведения см. в разделе [перегрузка функций](function-overloading.md).  
  
## <a name="example"></a>Пример

 Если нешаблонная функция хорошо соответствует функции шаблона, используется нешаблонная функция (если аргументы шаблона не заданы явно), как в вызове `f(1, 1)` в следующем примере.  
  
```cpp
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
  
```Output  
f(int, int)  
void f(T1, T2)  
void f(T1, T2)  
```  
  
## <a name="example"></a>Пример

 В следующем примере показано, что точное соответствие функции шаблона предпочтительнее, если требуется преобразование нешаблонной функции.  
  
```cpp
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
  
```Output  
void f(T1, T2)  
```  
  
## <a name="see-also"></a>См. также

 [Разрешение имен](../cpp/templates-and-name-resolution.md)   
 [typename](../cpp/typename.md)   
 
