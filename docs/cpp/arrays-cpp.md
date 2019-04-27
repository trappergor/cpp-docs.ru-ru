---
title: Массивы (C++)
ms.date: 11/19/2018
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
ms.openlocfilehash: 176e358bd0217ac914eb4ee6079126d3f429b6dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184518"
---
# <a name="arrays-c"></a>Массивы (C++)

Массив — это коллекция похожих объектов. Простейший пример массива — вектор, который может быть объявлен следующей последовательностью:

> *decl-specifier* *identifier* **\[** *constant-expression* **]**<br/>
> *спецификатор decl* *идентификатор*  **\[]**<br/>
> *decl-specifier* *identifer* **\[]\[** *constant-expression* **]** . . .<br/>
> *decl-specifier* *identifier* **\[** *constant-expression* **]** **\[** *constant-expression* **]** . . .

1. Спецификатор объявления:

   - Необязательный спецификатор класса хранения.

   - Необязательный **const** и/или **volatile** спецификаторы.

   - Имя типа элементов массива.

1. Декларатор:

   - Идентификатор.

   - Константное выражение целочисленного типа, заключенное в квадратные скобки,  **\[]**. Если с помощью дополнительных квадратных скобок объявляется несколько измерений, в первом наборе квадратных скобок может быть опущено константное выражение.

   - Необязательные дополнительные квадратные скобки для константных выражений.

1. Необязательный инициализатор. Дополнительные сведения см. в разделе [инициализаторы](../cpp/initializers.md).

Число элементов в массиве задается *константное_выражение*. Первый элемент массива является нулевой элемент, а последний элемент (*n*-1) элемента, где *n* — количество элементов, которые может содержать массив. *Константное_выражение* должен быть целочисленного типа и должно быть больше 0. Массив нулевого размера допустим только в том случае, когда массив является последним полем в **структуры** или **объединение** и при включенных расширениях Майкрософт (/Ze).

В следующем примере показано, как определить массив во время выполнения.

```cpp
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

Массивы являются производными типами и поэтому могут создаваться из любого другого производного или базового типа за исключением функций, ссылок и **void**.

Массивы, созданные из других массивов, являются многомерными. Такие многомерные массивы определяются путем последовательного размещения нескольких константных выражений, заключенных в квадратные скобки. Рассмотрим, например, следующее объявление:

```cpp
int i2[5][7];
```

Он указывает массив объектов типа **int**, по существу размещенный в двумерной матрице, состоящей из пяти строк и семи столбцов, как показано на следующем рисунке:

![Концептуальная раскладка комплексных&#45;одномерным массивом](../cpp/media/vc38rc1.gif "концептуальная раскладка комплексных&#45;одномерным массивом.") <br/>
Концептуальная структура многомерного массива

В объявлениях многомерных массивов, содержащих список инициализаторов (как описано в разделе [инициализаторы](../cpp/initializers.md)), константное выражение, задающее границы первого измерения можно опустить. Пример:

```cpp
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

- [Использование массивов](../cpp/using-arrays-cpp.md)

- [Массивы в выражениях](../cpp/arrays-in-expressions.md)

- [Интерпретация оператора индекса](../cpp/interpretation-of-subscript-operator.md)

- [Косвенное обращение к типам массивов](../cpp/indirection-on-array-types.md)

- [Упорядочение массивов C++](../cpp/ordering-of-cpp-arrays.md)

## <a name="example"></a>Пример

Метод пропуска определения границ первого измерения многомерного массива можно также использовать в объявлениях функций следующим образом.

```cpp
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
