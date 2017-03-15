---
title: "Функции &lt;numeric&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4b0449a-c80c-4a1d-8d9f-d7fcd0058f8b
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 88c311b28caa80d4c4292888be501feae797ce27
ms.lasthandoff: 02/24/2017

---
# <a name="ltnumericgt-functions"></a>Функции &lt;numeric&gt;
||||  
|-|-|-|  
|[accumulate](#accumulate)|[adjacent_difference](#adjacent_difference)|[inner_product](#inner_product)|  
|[iota](#iota)|[partial_sum](#partial_sum)|  
  
##  <a name="a-nameaccumulatea--accumulate"></a><a name="accumulate"></a>  accumulate  
 Вычисляет сумму всех элементов в указанном диапазоне, включая некоторое начальное значение, путем вычисления последовательных частичных сумм или вычисляет результат последовательных частичных сумм, аналогичным образом полученных от использования указанной бинарной операции, отличной от суммы.  
  
```  
template <class InputIterator, class Type>  
Type accumulate(InputIterator first, InputIterator last, Type val);

template <class InputIterator, class Type, class BinaryOperation>  
Type accumulate(
    InputIterator first, 
    InputIterator last, 
    Type val, 
    BinaryOperation binary_op);
```  
  
### <a name="parameters"></a>Параметры   
 ` first`  
 Входной итератор, адресующий первый элемент в диапазоне для суммирования или комбинирования в соответствии с указанной бинарной операцией.  
  
 ` last`  
 Входной итератор, адресующий последний элемент в диапазоне для суммирования или комбинирования в соответствии с указанной бинарной операцией, который находится на одну позицию позади конечного элемента, фактически включенного в перебираемое накопление.  
  
 ` val`  
 Начальное значение, к которому каждый элемент по очереди прибавляется или с которым комбинируется в соответствии с указанной бинарной операцией.  
  
 `binary_op`  
 Бинарная операция, которая будет применена к каждому элементу в указанном диапазоне, и результат ее предыдущих применений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сумма ` val` и всех элементов в указанном диапазоне для первой функции-шаблона или, для второй функции-шаблона, результат применения указанной бинарной операции (вместо суммирования) к (*PartialResult, \*Iter*), где *PartialResult* — это результат предыдущего применения операции, а `Iter` — итератор, указывающий на элемент в диапазоне.  
  
### <a name="remarks"></a>Примечания  
 Начальное значение гарантирует, что при пустом диапазоне будет получен хорошо определенный результат. В этом случае возвращается ` val`. Бинарная операция не обязательно должна быть ассоциативной или коммутативной. Результат инициализируется в начальное значение ` val`, а затем *result* = `binary_op` (*result*, **\***`Iter`) вычисляется последовательно по всему диапазону, где `Iter` — итератор, указывающий на следующий элемент в диапазоне. Диапазон должен быть корректным, а сложность должна быть линейной от размера диапазона. Возвращаемый тип бинарного оператора должен поддерживать преобразование в **Type**, чтобы гарантировать закрытие в ходе перебора.  
  
### <a name="example"></a>Пример  
  
```cpp  
// numeric_accum.cpp  
// compile with: /EHsc  
#include <vector>  
#include <numeric>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   vector <int> v1, v2(20);  
   vector <int>::iterator iter1, iter2;  
  
   int i;  
   for (i = 1; i < 21; i++)  
   {  
      v1.push_back(i);  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)  
      cout << *iter1 << " ";  
   cout << ")." << endl;  
  
   // The first member function for the accumulated sum  
   int total;  
   total = accumulate(v1.begin(), v1.end(), 0);  
  
   cout << "The sum of the integers from 1 to 20 is: "  
        << total << "." << endl;  
  
   // Constructing a vector of partial sums  
   int j = 0, partotal;  
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)  
   {  
      partotal = accumulate(v1.begin(), iter1 + 1, 0);  
      v2[j] = partotal;  
      j++;  
   }  
  
   cout << "The vector of partial sums is:\n ( " ;  
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)  
      cout << *iter2 << " ";  
   cout << ")." << endl << endl;  
  
   // The second member function for the accumulated product  
   vector <int> v3, v4(10);  
   vector <int>::iterator iter3, iter4;  
  
   int s;  
   for (s = 1; s < 11; s++)  
   {  
      v3.push_back(s);  
   }  
  
   cout << "The original vector v3 is:\n ( " ;  
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)  
      cout << *iter3 << " ";  
   cout << ")." << endl;  
  
   int ptotal;  
   ptotal = accumulate(v3.begin(), v3.end(), 1, multiplies<int>());  
  
   cout << "The product of the integers from 1 to 10 is: "  
        << ptotal << "." << endl;  
  
   // Constructing a vector of partial products  
   int k = 0, ppartotal;  
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++) {  
      ppartotal = accumulate(v3.begin(), iter3 + 1, 1, multiplies<int>());  
      v4[k] = ppartotal;  
      k++;  
   }  
  
   cout << "The vector of partial products is:\n ( " ;  
   for (iter4 = v4.begin(); iter4 != v4.end(); iter4++)  
      cout << *iter4 << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).  
The sum of the integers from 1 to 20 is: 210.  
The vector of partial sums is:  
 ( 1 3 6 10 15 21 28 36 45 55 66 78 91 105 120 136 153 171 190 210 ).  
  
The original vector v3 is:  
 ( 1 2 3 4 5 6 7 8 9 10 ).  
The product of the integers from 1 to 10 is: 3628800.  
The vector of partial products is:  
 ( 1 2 6 24 120 720 5040 40320 362880 3628800 ).  
```  
  
##  <a name="a-nameadjacentdifferencea--adjacentdifference"></a><a name="adjacent_difference"></a>  adjacent_difference  
 Вычисляет последовательные различия между каждым элементом и его предшественником в диапазоне ввода и выводит результаты в диапазон назначения или вычисляет результат обобщенной процедуры, где операция разности заменена другой определенной бинарной операцией.  
  
```  
template <class InputIterator, class OutIterator>  
OutputIterator adjacent_difference(
    InputIterator first, 
    InputIterator last, 
    OutputIterator result);

template <class InputIterator, class OutIterator, class BinaryOperation>  
OutputIterator adjacent_difference(
    InputIterator first, 
    InputIterator last, 
    OutputIterator result, 
    BinaryOperation binary_op);
```  
  
### <a name="parameters"></a>Параметры  
 ` first`  
 Итератор ввода, обращающийся к первому элементу в диапазоне ввода, элементы которого необходимо отличить от соответствующих им предшественников или где с парой значений должна быть выполнена другая заданная бинарная операция.  
  
 ` last`  
 Итератор ввода, обращающийся к последнему элементу в диапазоне ввода, элементы которого необходимо отличить от соответствующих им предшественников или где с парой значений должна быть выполнена другая заданная бинарная операция.  
  
 `result`  
 Итератор вывода, обращающийся к первому элементу в диапазоне назначения, где необходимо сохранить ряд различий или результаты определенной операции.  
  
 `binary_op`  
 Бинарная операция, которую необходимо применить в обобщенной операции с заменой операции вычитания в процедуре дифференцирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор вывода, адресующий конец целевого диапазона: `result` + (` last` - ` first`).  
  
### <a name="remarks"></a>Примечания  
 Итератор вывода _ *result* может быть тем же самым, что и входной итератор * first.* Таким образом, `adjacent_difference` могут быть вычислены на месте.  
  
 Для последовательности значений *a*1, *a*2, *a*3 во входном диапазоне первая функция-шаблон сохраняет последовательные **partial_difference** *a*1, *a*2 – *a*1, a3 – *a*2 в целевом диапазоне.  
  
 Для последовательности значений *a*1, *a*2, *a*3 во входном диапазоне вторая функция-шаблон сохраняет последовательные **partial_difference** *a*1, *a*2 `binary_op` *a*1, *a*3 `binary_op` *a*2 в целевом диапазоне.  
  
 Бинарная операция `binary_op` не обязательно должна быть либо ассоциативной, либо коммутативной, поскольку применяемый порядок операций полностью определен.  
  
### <a name="example"></a>Пример  
  
```cpp  
// numeric_adj_diff.cpp  
// compile with: /EHsc  
#include <vector>  
#include <list>  
#include <numeric>  
#include <functional>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   vector<int> V1( 10 ), V2( 10 );  
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;  
  
   list <int> L1;  
   list <int>::iterator LIter1, LIterend, LIterend2;  
  
   int t;  
   for ( t = 1 ; t <= 10 ; t++ )  
   {  
      L1.push_back( t * t );  
   }  
  
   cout << "The input list L1 is:\n ( " ;  
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )  
      cout << *LIter1 << " ";  
   cout << ")." << endl;  
  
   // The first member function for the adjacent_differences of  
   // elements in a list output to a vector  
   VIterend = adjacent_difference ( L1.begin ( ) , L1.end ( ) ,   
      V1.begin ( ) );  
  
   cout << "Output vector containing adjacent_differences is:\n ( " ;  
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )  
      cout << *VIter1 << " ";  
   cout << ")." << endl;  
  
   // The second member function used to compute  
   // the adjacent products of the elements in a list  
   VIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,   
      multiplies<int>( ) );  
  
   cout << "The output vector with the adjacent products is:\n ( " ;  
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )  
      cout << *VIter2 << " ";  
   cout << ")." << endl;  
  
   // Computation of adjacent_differences in place  
   LIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );  
   cout << "In place output adjacent_differences in list L1 is:\n ( " ;  
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend2 ; LIter1++ )  
      cout << *LIter1 << " ";  
   cout << ")." << endl;  
}  
```  
  
##  <a name="a-nameinnerproducta--innerproduct"></a><a name="inner_product"></a>  inner_product  
 Вычисляет сумму поэлементного умножения двух диапазонов и добавляет ее к указанному начальному значению либо вычисляет результат обобщенной процедуры, где бинарные операции суммы и умножения заменены на другие указанные бинарные операции.  
  
```  
template <class InputIterator1, class InputIterator2, class Type>  
Type inner_product(
    InputIterator1   first1, 
    InputIterator1   last1, 
    InputIterator2   first2, 
    Type             val);

template <class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>  
Type inner_product(
    InputIterator1   first1, 
    InputIterator1   last1, 
    InputIterator2   first2, 
    Type             val, 
    BinaryOperation1  binary_op1, 
    BinaryOperation2  binary_op2);
```  
  
### <a name="parameters"></a>Параметры  
 ` first1`  
 Входной итератор, адресующий первый элемент в первом диапазоне, для которого нужно вычислить внутреннее произведение или обобщенное внутреннее произведение со вторым диапазоном.  
  
 ` last1`  
 Входной итератор, адресующий последний элемент в первом диапазоне, для которого нужно вычислить внутреннее произведение или обобщенное внутреннее произведение со вторым диапазоном.  
  
 ` first2`  
 Входной итератор, адресующий первый элемент во втором диапазоне, для которого нужно вычислить внутреннее произведение или обобщенное внутреннее произведение с первым диапазоном.  
  
 ` val`  
 Начальное значение, к которому прибавляется внутреннее произведение или обобщенное внутреннее произведение диапазонов.  
  
 *binary_op1*  
 Бинарная операция, которая заменяет операцию внутреннего произведения суммирования, применяемую к поэлементным произведениям в обобщении внутреннего произведения.  
  
 *binary_op2*  
 Бинарная операция, которая заменяет операцию внутреннего поэлементного произведения умножения в обобщении внутреннего произведения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая функция-член возвращает сумму поэлементного произведения и добавляет к ней указанное начальное значение. Таким образом, для диапазонов значений *a*i и *b*i она возвращает:  
  
 ` val` + (*a*1 \* *b*1) + (*a*2 \* *b*2) +  
  
 последовательно заменяя` val` на ` val` + (\* *a*i \* \* *b*i).  
  
 Вторая функция-член возвращает:  
  
 ` val` _ *Binary_op1* (*a*1 \_ *Binary_op2* *b*1) \_ *Binary_op1* (*a*2 \_ *Binary_op2* *b*2) \_ *Binary_op1*  
  
 последовательно заменяя ` val` на ` val` _ *Binary_op1* (\* *a*i \_ *Binary_op2* \* *b*i).  
  
### <a name="remarks"></a>Примечания  
 Начальное значение гарантирует, что при пустом диапазоне будет получен правильно определенный результат. В этом случае возвращается ` val`. Бинарные операции не обязательно должны быть ассоциативными или коммутативными. Диапазон должен быть корректным, а сложность должна быть линейной от размера диапазона. Возвращаемый тип бинарного оператора должен поддерживать преобразование в **Type**, чтобы гарантировать закрытие в ходе перебора.  
  
### <a name="example"></a>Пример  
  
```cpp  
// numeric_inner_prod.cpp  
// compile with: /EHsc  
#include <vector>  
#include <list>  
#include <numeric>  
#include <functional>  
#include <iostream>  
  
int main()  
{  
   using namespace std;  
  
   vector <int> v1, v2(7), v3(7);  
   vector <int>::iterator iter1, iter2, iter3;  
  
   int i;  
   for (i = 1; i <= 7; i++)  
   {  
      v1.push_back(i);  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)  
      cout << *iter1 << " ";  
   cout << ")." << endl;  
  
   list <int> l1, l2(7);  
   list <int>::iterator lIter1, lIter2;  
  
   int t;  
   for (t = 1; t <= 7; t++)  
   {  
      l1.push_back(t);  
   }  
  
   cout << "The original list l1 is:\n ( " ;  
   for (lIter1 = l1.begin(); lIter1 != l1.end(); lIter1++)  
      cout << *lIter1 << " ";  
   cout << ")." << endl;  
  
   // The first member function for the inner product  
   int inprod;  
   inprod = inner_product(v1.begin(), v1.end(), l1.begin(), 0);  
  
   cout << "The inner_product of the vector v1 and the list l1 is: "  
        << inprod << "." << endl;  
  
   // Constructing a vector of partial inner_products between v1 & l1  
   int j = 0, parinprod;  
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++) {  
      parinprod = inner_product(v1.begin(), iter1 + 1, l1.begin(), 0);  
      v2[j] = parinprod;  
      j++;  
   }  
  
   cout << "Vector of partial inner_products between v1 & l1 is:\n ( " ;  
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)  
      cout << *iter2 << " ";  
   cout << ")." << endl << endl;  
  
   // The second member function used to compute  
   // the product of the element-wise sums  
   int inprod2;  
   inprod2 = inner_product (v1.begin(), v1.end(),  
      l1.begin(), 1, multiplies<int>(), plus<int>());  
  
   cout << "The sum of the element-wise products of v1 and l1 is: "  
        << inprod2 << "." << endl;  
  
   // Constructing a vector of partial sums of element-wise products  
   int k = 0, parinprod2;  
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)  
   {  
      parinprod2 =  
         inner_product(v1.begin(), iter1 + 1, l1.begin(), 1,  
         multiplies<int>(), plus<int>());  
      v3[k] = parinprod2;  
      k++;  
   }  
  
   cout << "Vector of partial sums of element-wise products is:\n ( " ;  
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)  
      cout << *iter3 << " ";  
   cout << ")." << endl << endl;  
}  
```  
  
##  <a name="a-nameiotaa--iota"></a><a name="iota"></a>  iota  
 Сохраняет начальное значение, начиная с первого элемента и заполняя последовательными приращениями этого значения (` value++`) в каждом элементе в интервале `[ first,  last)`.  
  
```  
template <class ForwardIterator, class Type>  
void iota(ForwardIterator first, ForwardIterator last, Type value);
```  
  
### <a name="parameters"></a>Параметры  
 ` first`  
 Входной итератор, адресующий первый элемент в диапазоне для заполнения.  
  
 ` last`  
 Входной итератор, адресующий последний элемент в диапазоне для заполнения.  
  
 ` value`  
 Начальное значение для сохранения в первом элементе и для последовательного приращения для последующих элементов.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
  Следующий пример показывает некоторые способы использования функции `iota` заполнением [списка](../standard-library/list.md) целых чисел, а затем заполнением [вектора](../standard-library/vector.md) `list`, так что можно будет использовать функцию [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle).  
  
```cpp  
// compile by using: cl /EHsc /nologo /W4 /MTd  
#include <algorithm>  
#include <numeric>  
#include <list>  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main(void)  
{  
    list <int> intList(10);  
    vector <list<int>::iterator> intVec(intList.size());  
  
    // Fill the list  
    iota(intList.begin(), intList.end(), 0);  
  
    // Fill the vector with the list so we can shuffle it  
    iota(intVec.begin(), intVec.end(), intList.begin());  
  
    random_shuffle(intVec.begin(), intVec.end());  
  
    // Output results  
    cout << "Contents of the integer list: " << endl;  
    for (auto i: intList) {  
        cout << i << ' ';  
    }  
    cout << endl << endl;  
  
    cout << "Contents of the integer list, shuffled by using a vector: " << endl;  
    for (auto i: intVec) {  
        cout << *i << ' ';  
    }  
    cout << endl;  
}  
```  
  
##  <a name="a-namepartialsuma--partialsum"></a><a name="partial_sum"></a>  partial_sum  
 Вычисляет ряд сумм во входном диапазоне от первого до *i*-го элемента и сохраняет результат каждого суммирования в *i*-м элементе диапазона назначения либо вычисляет результат обобщенной процедуры, где операция суммирования заменяется на другую указанную бинарную операцию.  
  
```  
template <class InputIterator, class OutIt>  
OutputIterator partial_sum(
    InputIterator first, 
    InputIterator last, 
    OutputIterator result);

template <class InputIterator, class OutIt, class Fn2>  
OutputIterator partial_sum(
    InputIterator first, 
    InputIterator last, 
    OutputIterator result, 
    BinaryOperation binary_op);
```  
  
### <a name="parameters"></a>Параметры  
 ` first`  
 Итератор ввода, обращающийся к первому элементу в диапазоне, который необходимо частично суммировать или объединить в соответствии с заданной бинарной операцией.  
  
 ` last`  
 Итератор ввода, обращающийся к последнему элементу в диапазоне, который необходимо частично суммировать или объединить в соответствии с указанной бинарной операцией, который расположен на одну позицию далее за последним элементом, фактически включенным в совокупности, в которой проводятся итерации.  
  
 `result`  
 Итератор вывода, обращающийся к первому элементу в диапазоне назначения, где необходимо сохранить ряд частичных сумм или результаты определенной операции.  
  
 `binary_op`  
 Бинарная операция, которую необходимо применить в обобщенной операции с заменой операции суммирования в процедуре частичного суммирования.    
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор вывода, адресующий конец диапазона назначения: `result` + (` last` - ` first`),  
  
### <a name="remarks"></a>Примечания  
 Итератором вывода `result` может быть тот же итератор, что и итератор ввода ` first`, чтобы частичные суммы можно было вычислить на месте.  
  
 Для последовательности значений *a*1, *a*2, *a*3 во входном диапазоне первая функция-шаблон сохраняет последовательные частичные суммы в диапазоне назначения, где *i*-й элемент определяется (((*a*1 + *a*2) + *a*3) *a*i).  
  
 Для последовательности значений *a*1, *a*2, *a*3 во входном диапазоне вторая функция-шаблон сохраняет последовательные частичные суммы в диапазоне назначения, где i-й элемент определяется (((*a*1`binary_op` *a*2) `binary_op` *a*3) *a*i).  
  
 Бинарная операция `binary_op` не обязательно должна быть либо ассоциативной, либо коммутативной, поскольку применяемый порядок операций полностью определен.  
  
### <a name="example"></a>Пример  
  
```cpp  
// numeric_partial_sum.cpp  
// compile with: /EHsc  
#include <vector>  
#include <list>  
#include <numeric>  
#include <functional>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;     
   vector<int> V1( 10 ), V2( 10 );  
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;  
  
   list <int> L1;  
   list <int>::iterator LIter1, LIterend;  
  
   int t;  
   for ( t = 1 ; t <= 10 ; t++ )  
   {  
      L1.push_back( t );  
   }  
  
   cout << "The input list L1 is:\n ( " ;  
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )  
      cout << *LIter1 << " ";  
   cout << ")." << endl;  
  
   // The first member function for the partial sums of  
   // elements in a list output to a vector  
   VIterend = partial_sum ( L1.begin ( ) , L1.end ( ) ,   
      V1.begin ( ) );  
  
   cout << "The output vector containing the partial sums is:\n ( " ;  
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )  
      cout << *VIter1 << " ";  
   cout << ")." << endl;  
  
   // The second member function used to compute  
   // the partial product of the elements in a list  
   VIterend2 = partial_sum ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,   
      multiplies<int>( ) );  
  
   cout << "The output vector with the partial products is:\n ( " ;  
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )  
      cout << *VIter2 << " ";  
   cout << ")." << endl;  
  
   // Computation of partial sums in place  
   LIterend = partial_sum ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );  
   cout << "The in place output partial_sum list L1 is:\n ( " ;  
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend ; LIter1++ )  
      cout << *LIter1 << " ";  
   cout << ")." << endl;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [\<numeric>](../standard-library/numeric.md)


