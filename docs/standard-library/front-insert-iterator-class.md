---
title: "Класс front_insert_iterator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::front_insert_iterator
- std::front_insert_iterator
- std.front_insert_iterator
- front_insert_iterator
dev_langs:
- C++
helpviewer_keywords:
- front_insert_iterator class
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 6468f372324cb6f62b5b09524cfbf5386b1502c6
ms.lasthandoff: 02/24/2017

---
# <a name="frontinsertiterator-class"></a>Класс front_insert_iterator
Описывает адаптер итератора, удовлетворяющий требованиям итератора вывода. Вставляет, а не перезаписывает элементы в переднюю часть последовательности, тем самым предоставляя семантику, отличную от семантики перезаписи, предоставляемой итераторами контейнеров последовательности C++. Класс `front_insert_iterator` шаблонизируется в типе контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Container>  
class front_insert_iterator;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Container`  
 Тип контейнера, в переднюю часть которого итератор `front_insert_iterator` вставит элементы.  
  
## <a name="remarks"></a>Примечания  
 Контейнер должен удовлетворять требованиям последовательности вставки в переднюю часть, если можно вставить элементы в начало последовательности в постоянном времени с поправкой на амортизацию. Контейнеры последовательности стандартной библиотеки C++, определенные классами [deque](../standard-library/deque-class.md) и [list](../standard-library/list-class.md), обеспечивают необходимую функцию-член `push_front` и удовлетворяют этим требованиям. Напротив, контейнеры последовательности, заданные классом [vector](../standard-library/vector-class.md), не удовлетворяют данным требованиям и не могут быть адаптированы для использования в сочетании с итераторами `front_insert_iterator`. Итератор `front_insert_iterator` всегда необходимо инициализировать с его контейнером.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[front_insert_iterator](#front_insert_iterator__front_insert_iterator)|Создает итератор, может вставлять элементы с передней стороны указанного объекта контейнера.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#front_insert_iterator__container_type)|Тип, представляющий контейнер, в переднюю часть которого будет осуществляться вставка.|  
|[reference](#front_insert_iterator__reference)|Тип, который предоставляет ссылку на элемент последовательности под управлением связанного контейнера.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор*](#front_insert_iterator__operator_star)|Оператор удаления ссылки, используемый для применения выражения итератора вывода * `i` = `x` для вставки в переднюю часть.|  
|[оператор++](#front_insert_iterator__operator_add_add)|Увеличивает `front_insert_iterator` до следующего местоположения, в котором можно сохранить значение.|  
|[оператор=](#front_insert_iterator__operator_eq)|Оператор присваивания, используемый для применения выражения итератора вывода * `i` = `x` для вставки в переднюю часть.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<iterator>  
  
 **Пространство имен:** std  
  
##  <a name="a-namefrontinsertiteratorcontainertypea--frontinsertiteratorcontainertype"></a><a name="front_insert_iterator__container_type"></a>  front_insert_iterator::container_type  
 Тип, представляющий контейнер, в переднюю часть которого будет осуществляться вставка.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра-шаблона **Container**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// front_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> >::container_type L2 = L1;  
   front_inserter ( L2 ) = 20;  
   front_inserter ( L2 ) = 10;  
   front_inserter ( L2 ) = 40;  
  
   list <int>::iterator vIter;  
   cout << "The list L2 is: ( ";  
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L2 is: ( 40 10 20 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorfrontinsertiteratora--frontinsertiteratorfrontinsertiterator"></a><a name="front_insert_iterator__front_insert_iterator"></a>  front_insert_iterator::front_insert_iterator  
 Создает итератор, может вставлять элементы с передней стороны указанного объекта контейнера.  
  
```  
explicit front_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Параметры  
 `_Cont`  
 Объект контейнера, в который `front_insert_iterator` вставляет элементы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `front_insert_iterator` для объекта контейнера параметра.  
  
### <a name="example"></a>Пример  
  
```cpp  
// front_insert_iterator_front_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = -1 ; i < 9 ; ++i )    
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   // Using the member function to insert an element  
   front_inserter ( L ) = 20;  
  
   // Alternatively, one may use the template function  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatorstara--frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_star"></a>  front_insert_iterator::operator*  
 Разыменовывает итератор вставки и возвращает адресованный элемент.  
  
```  
front_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член возвращает значение адресованного элемента.  
  
### <a name="remarks"></a>Примечания  
 Используется для применения выражения итератора вывода **\*Iter** = **value**. Если **Iter** является итератором, который адресует элемент в последовательности, то ** \*Iter** = **value** заменяет этот элемент значением и не изменяет общее число элементов в последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// front_insert_iterator_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for ( i = -1 ; i < 9 ; ++i )   
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 20;  
  
   // Alternatively, you may use  
   front_inserter ( L ) = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoraddadda--frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_add_add"></a>  front_insert_iterator::operator++  
 Увеличивает `back_insert_iterator` до следующего местоположения, в котором можно сохранить значение.  
  
```  
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `front_insert_iterator`, адресующий следующее местоположение, в котором можно сохранить значение.  
  
### <a name="remarks"></a>Примечания  
 Операторы preincrementation и postincrementation возвращают одинаковый результат.  
  
### <a name="example"></a>Пример  
  
```cpp  
// front_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoreqa--frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_eq"></a>  front_insert_iterator::operator=  
 Добавляет (заносит) значение в переднюю часть контейнера.  
  
```  
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Параметры  
 ` val`  
 Значение, которое должно быть присвоено контейнеру.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на последний элемент, вставленный в начале контейнера.  
  
### <a name="remarks"></a>Примечания  
 Первый оператор-член вычисляет `container.push_front( val)`, затем возвращает `*this`.  
  
 Второй оператор-член вычисляет  
  
 `container->push_front((typename Container::value_type&&) val)`,  
  
 затем возвращает `*this`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// front_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorreferencea--frontinsertiteratorreference"></a><a name="front_insert_iterator__reference"></a>  front_insert_iterator::reference  
 Тип, который предоставляет ссылку на элемент последовательности под управлением связанного контейнера.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="example"></a>Пример  
  
```cpp  
// front_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L;  
   front_insert_iterator<list<int> > fiivIter( L );  
 *fiivIter = 10;  
 *fiivIter = 20;  
 *fiivIter = 30;  
  
   list<int>::iterator LIter;  
   cout << "The list L is: ( ";  
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++)  
      cout << *LIter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator<list<int> >::reference   
        RefFirst = *(L.begin ( ));  
   cout << "The first element in the list L is: "   
        << RefFirst << "." << endl;  
}  
\* Output:   
The list L is: ( 30 20 10 ).  
The first element in the list L is: 30.  
*\  
```  
  
## <a name="see-also"></a>См. также  
 [\<iterator>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)


