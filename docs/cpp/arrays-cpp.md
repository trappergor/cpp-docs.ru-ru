---
title: "Массивы (C++) | Документы Microsoft"
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
- declaring arrays, about declaring arrays
- multidimensional arrays
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
caps.latest.revision: 12
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
ms.openlocfilehash: efd124254ece8f863afee13e132eea7945525a0e
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="arrays-c"></a>Массивы (C++)
Массив — это коллекция похожих объектов. Простейший пример массива — вектор, который может быть объявлен следующей последовательностью:  
  
```  
  
      decl-specifier identifier [ constant-expression ]  
decl-specifier identifier []  
decl-specifier identifer [][ constant-expression] . . .  
decl-specifier identifier [ constant-expression ]  
[ constant-expression ] . . .  
```  
  
 1. Спецификатор объявления:  
  
-   Необязательный спецификатор класса хранения.  
  
-   Необязательный **const** и/или `volatile` спецификаторы.  
  
-   Имя типа элементов массива.  
  
 2. Декларатор:  
  
-   Идентификатор.  
  
-   Константное выражение целого типа, заключенных в скобки, **[].** Если с помощью дополнительных квадратных скобок объявляется несколько измерений, константное выражение может быть опущено в первом наборе квадратных скобок.  
  
-   Необязательные дополнительные квадратные скобки для константных выражений.  
  
 3. Необязательный инициализатор.  В разделе [инициализаторы](../cpp/initializers.md).  
  
 Количество элементов в массиве задается константным выражением. Первый элемент массива является нулевой элемент, а последний элемент — (*n*-1) элемента, где * n * — количество элементов, которые может содержать массив. *Константное выражение* должен быть целочисленного типа и должно быть больше 0. Массив нулевого размера допустим только в том случае, если массив является последним полем в `struct` или **объединение** и при включенных расширениях Microsoft (/Ze).  
  
 В следующем примере показано, как определить массив во время выполнения.  
  
```  
// arrays.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main() {  
   using namespace std;  
   int size = 3, i = 0;  
  
   int* myarr = new int[size];  
  
   for (i = 0 ; i < size ; i++)  
      myarr[i] = 10;  
  
   for (i = 0 ; i < size ; i++)  
      printf_s("myarr[%d] = %d\n", i, myarr[i]);  
  
   delete [] myarr;  
}  
```  
  
 Массивы — это производные типы, поэтому они могут создаваться из любого другого производного или базового типа, кроме функций, ссылок и типа `void`.  
  
 Массивы, созданные из других массивов, являются многомерными. Такие многомерные массивы определяются путем последовательного размещения нескольких константных выражений, заключенных в квадратные скобки. Рассмотрим, например, следующее объявление:  
  
```  
int i2[5][7];  
```  
  
 Оно определяет массив типа `int`, по существу размещенный в двумерной матрице, состоящей из пяти строк и семи столбцов, как показано на следующем рисунке.  
  
 ![Концептуальная раскладка нескольких &#45; двумерный массив](../cpp/media/vc38rc1.gif "vc38RC1")  
Концептуальная раскладка многомерного массива  
  
 В объявлениях многомерных массивов, содержащих список инициализаторов (как описано в [инициализаторы](../cpp/initializers.md)), константное выражение, определяющее границы первого измерения может быть опущено. Пример:  
  
```  
// arrays2.cpp  
// compile with: /c  
const int cMarkets = 4;  
// Declare a float that represents the transportation costs.  
double TransportCosts[][cMarkets] = {   
   { 32.19, 47.29, 31.99, 19.11 },  
   { 11.29, 22.49, 33.47, 17.29 },  
   { 41.97, 22.09,  9.76, 22.55 }  
};  
```  
  
 В показанном выше объявлении определяется массив, состоящий из трех строк и четырех столбцов. Строки представляют фабрики, а столбцы — рынки, на которые фабрики поставляют свою продукцию. Значения — это стоимости транспортировки с фабрик на рынки. Первое измерение массива опущено, но компилятор заполняет его, проверяя инициализатор.  
  
 Подразделы в этом разделе:  
  
-   [Использование массивов](../cpp/using-arrays-cpp.md)  
  
-   [Массивы в выражениях](../cpp/arrays-in-expressions.md)  
  
-   [Интерпретация оператора индекса](../cpp/interpretation-of-subscript-operator.md)  
  
-   [Косвенное обращение к типам массивов](../cpp/indirection-on-array-types.md)  
  
-   [Упорядочение массивов C++](../cpp/ordering-of-cpp-arrays.md)  
  
## <a name="example"></a>Пример  
 Метод пропуска определения границ первого измерения многомерного массива можно также использовать в объявлениях функций следующим образом.  
  
```  
// multidimensional_arrays.cpp  
// compile with: /EHsc  
// arguments: 3  
#include <limits>   // Includes DBL_MAX  
#include <iostream>  
  
const int cMkts = 4, cFacts = 2;  
  
// Declare a float that represents the transportation costs  
double TransportCosts[][cMkts] = {   
   { 32.19, 47.29, 31.99, 19.11 },  
   { 11.29, 22.49, 33.47, 17.29 },  
   { 41.97, 22.09,  9.76, 22.55 }    
};  
  
// Calculate size of unspecified dimension  
const int cFactories = sizeof TransportCosts /  
                  sizeof( double[cMkts] );  
  
double FindMinToMkt( int Mkt, double myTransportCosts[][cMkts], int mycFacts);  
  
using namespace std;  
  
int main( int argc, char *argv[] ) {  
   double MinCost;  
  
   if (argv[1] == 0) {  
      cout << "You must specify the number of markets." << endl;  
      exit(0);  
   }  
   MinCost = FindMinToMkt( *argv[1] - '0', TransportCosts, cFacts);  
   cout << "The minimum cost to Market " << argv[1] << " is: "  
       << MinCost << "\n";  
}  
  
double FindMinToMkt(int Mkt, double myTransportCosts[][cMkts], int mycFacts) {  
   double MinCost = DBL_MAX;  
  
   for( int i = 0; i < cFacts; ++i )  
      MinCost = (MinCost < TransportCosts[i][Mkt]) ?  
         MinCost : TransportCosts[i][Mkt];  
  
   return MinCost;  
}  
```  
  
```Output  
The minimum cost to Market 3 is: 17.29  
```  
  
## <a name="comments"></a>Комментарии  
 Функция `FindMinToMkt` создана таким образом, что для добавления новых фабрик не требуется никаких изменений в коде, необходима только перекомпиляция.  
  
## <a name="see-also"></a>См. также  
 
