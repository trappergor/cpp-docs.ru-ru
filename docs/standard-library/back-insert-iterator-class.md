---
title: "Класс back_insert_iterator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::back_insert_iterator
- back_insert_iterator
- iterator/std::back_insert_iterator::container_type
- iterator/std::back_insert_iterator::reference
dev_langs:
- C++
helpviewer_keywords:
- back_insert_iterator class
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
caps.latest.revision: 21
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 3ef742cc4715c419b113e9235bbcc257ba8f1944
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="backinsertiterator-class"></a>Класс back_insert_iterator
Описывает адаптер итератора, удовлетворяющий требованиям итератора вывода. Вставляет, а не перезаписывает элементы в конечную часть последовательности, тем самым предоставляя семантику, отличную от семантики перезаписи, предоставляемой итераторами контейнеров последовательности C++. Класс `back_insert_iterator` шаблонизируется в типе контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Container>  
class back_insert_iterator;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Container`  
 Тип контейнера, в конец которого итератор `back_insert_iterator` вставит элементы.  
  
## <a name="remarks"></a>Примечания  
 Контейнер должен удовлетворять требованиям последовательности вставки в конечную часть, если можно вставить элементы в конец последовательности в постоянном времени с поправкой на амортизацию. Контейнеры последовательности стандартной библиотеки C++, определенные классами [deque](../standard-library/deque-class.md), [list](../standard-library/list-class.md) и [vector](../standard-library/vector-class.md), предоставляют необходимую функцию-член `push_back` и удовлетворяют данным требованиям. Эти три контейнера, как и строки, можно адаптировать для использования в сочетании с итераторами `back_insert_iterator`. Итератор `back_insert_iterator` всегда необходимо инициализировать с его контейнером.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[back_insert_iterator](#back_insert_iterator)|Создает итератор `back_insert_iterator`, который добавляет элементы в местоположение за последним элементом в контейнере.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#container_type)|Тип, предоставляющий контейнер для итератора `back_insert_iterator`.|  
|[reference](#reference)|Тип, предоставляющий ссылку для итератора `back_insert_iterator`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор*](#op_star)|Оператор удаления ссылки, используемый для реализации выражения итератора вывода * `i` = `x` для вставки в конечную часть.|  
|[оператор++](#op_add_add)|Увеличивает `back_insert_iterator` до следующего местоположения, в котором можно сохранить значение.|  
|[оператор=](#op_eq)|Оператор присваивания, используемый для применения выражения итератора вывода * `i` = `x` для вставки в конечную часть.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<iterator>  
  
 **Пространство имен:** std  
  
##  <a name="back_insert_iterator"></a>  back_insert_iterator::back_insert_iterator  
 Создает итератор `back_insert_iterator`, который добавляет элементы в местоположение за последним элементом в контейнере.  
  
```   
explicit back_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Параметры  
 `_Cont`  
 Контейнер, в который `back_insert_iterator` вставляет элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `back_insert_iterator` для параметра Container.  
  
### <a name="example"></a>Пример  
  
```cpp  
// back_insert_iterator_back_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The initial vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   // Insertions with member function  
   back_inserter ( vec ) = 40;  
   back_inserter ( vec ) = 50;  
  
   // Alternatively, insertions can be done with template function  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 600;  
   backiter++;  
 *backiter = 700;  
  
   cout << "After the insertions, the vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The initial vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec is: ( 1 2 3 40 50 600 700 ).  
```  
  
##  <a name="container_type"></a>  back_insert_iterator::container_type  
 Тип, предоставляющий контейнер для итератора `back_insert_iterator`.  
  
```   
typedef Container  
container_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра-шаблона **Container**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// back_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back (  i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The original vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::container_type vec1 = vec;  
   back_inserter ( vec1 ) = 40;  
  
   cout << "After the insertion, the vector is: ( ";  
   for ( vIter = vec1.begin ( ) ; vIter != vec1.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector vec is: ( 1 2 3 ).  
After the insertion, the vector is: ( 1 2 3 40 ).  
```  
  
##  <a name="op_star"></a>  back_insert_iterator::operator*  
 Оператор удаления ссылки, используемый для реализации выражения итератора вывода \* *i* = *x*.  
  
```  
back_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент, вставленный в конец контейнера.  
  
### <a name="remarks"></a>Примечания  
 Используется для применения выражения итератора вывода **\*Iter** = **value**. Если **Iter** является итератором, который адресует элемент в последовательности, то  **\*Iter** = **value** заменяет этот элемент значением и не изменяет общее число элементов в последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// back_insert_iterator_back_insert.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec becomes: ( 1 2 3 10 20 ).  
```  
  
##  <a name="op_add_add"></a>  back_insert_iterator::operator++  
 Увеличивает `back_insert_iterator` до следующего местоположения, в котором можно сохранить значение.  
  
```  
back_insert_iterator<Container>& operator++();
back_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `back_insert_iterator`, адресующий следующее местоположение, в котором можно сохранить значение.  
  
### <a name="remarks"></a>Примечания  
 Операторы preincrementation и postincrementation возвращают одинаковый результат.  
  
### <a name="example"></a>Пример  
  
```cpp  
// back_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 3 ; ++i )    
   {  
      vec.push_back ( 10 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 30;  
   backiter++;      // Increment to the next element  
 *backiter = 40;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 10 20 ).  
After the insertions, the vector vec becomes: ( 10 20 30 40 ).  
```  
  
##  <a name="op_eq"></a>  back_insert_iterator::operator=  
 Добавляет или вставляет значение в конец контейнера.  
  
```  
back_insert_iterator<Container>& operator=(typename Container::const_reference val);
back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Параметры  
 `val`  
 Значение для вставки в контейнер.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на последний элемент, вставленный в конец контейнера.  
  
### <a name="remarks"></a>Примечания  
 Первый оператор-член вычисляет `Container.push_back( val)`,  
  
 затем возвращает `*this`. Второй оператор-член вычисляет  
  
 `container->push_back((typename Container::value_type&&)val)`,  
  
 затем возвращает `*this`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// back_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
##  <a name="reference"></a>  back_insert_iterator::reference  
 Тип, предоставляющий ссылку для итератора `back_insert_iterator`.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип, который описывает ссылку на элемент последовательности под управлением связанного контейнера.  
  
### <a name="example"></a>Пример  
  
```cpp  
// back_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::reference   
        RefLast = *(vec.end ( ) - 1 );  
   cout << "The last element in the vector vec is: "   
        << RefLast << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
The last element in the vector vec is: 3.  
```  
  
## <a name="see-also"></a>См. также  
 [\<iterator>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)


