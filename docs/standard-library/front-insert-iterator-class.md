---
title: "Класс front_insert_iterator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/std::front_insert_iterator"
  - "std::front_insert_iterator"
  - "std.front_insert_iterator"
  - "front_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "front_insert_iterator - класс"
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс front_insert_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 Контейнер должен удовлетворять требованиям последовательности вставки в переднюю часть, если можно вставить элементы в начало последовательности в постоянном времени с поправкой на амортизацию. Контейнеры последовательности библиотеки стандартных шаблонов, определенные классами [класс deque](../standard-library/deque-class.md) и [класс list](../standard-library/list-class.md) обеспечивают необходимую `push_front` члена функции и удовлетворяют этим требованиям. Напротив, контейнеры последовательности, заданные по [класс vector](vector%20Class.md) не удовлетворяют этим требованиям и не может быть адаптирован для использования с `front_insert_iterator`s. Итератор `front_insert_iterator` всегда необходимо инициализировать с его контейнером.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[front_insert_iterator](#front_insert_iterator__front_insert_iterator)|Создает итератор, может вставлять элементы с передней стороны указанного объекта контейнера.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#front_insert_iterator__container_type)|Тип, представляющий контейнер, в переднюю часть которого будет осуществляться вставка.|  
|[ссылка](#front_insert_iterator__reference)|Тип, который предоставляет ссылку на элемент последовательности под управлением связанного контейнера.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор *](#front_insert_iterator__operator_star)|Оператор удаления ссылки, используемые для реализации выражения итератора вывода * `i` = `x` для вставки в переднюю часть.|  
|[Operator ++](#front_insert_iterator__operator_add_add)|Увеличивает `front_insert_iterator` до следующего местоположения, в котором можно сохранить значение.|  
|[оператор =](#front_insert_iterator__operator_eq)|Оператор присваивания, используемый для реализации выражения итератора вывода * `i` = `x` для вставки в переднюю часть.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок**: \< итератора>  
  
 **Пространство имен:** std  
  
##  <a name="a-namefrontinsertiteratorcontainertypea-frontinsertiteratorcontainertype"></a><a name="front_insert_iterator__container_type"></a>  front_insert_iterator::container_type  
 Тип, представляющий контейнер, в переднюю часть которого будет осуществляться вставка.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **контейнера**.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namefrontinsertiteratorfrontinsertiteratora-frontinsertiteratorfrontinsertiterator"></a><a name="front_insert_iterator__front_insert_iterator"></a>  front_insert_iterator::front_insert_iterator  
 Создает итератор, может вставлять элементы с передней стороны указанного объекта контейнера.  
  
```  
explicit front_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Параметры  
 `_Cont`  
 Объект контейнера, в который `front_insert_iterator` — для вставки элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `front_insert_iterator` для контейнера объекта параметра.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namefrontinsertiteratoroperatorstara-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_star"></a>  front_insert_iterator::operator *  
 Разыменовывает вставки итератор возвращает элемент, к которому он относится.  
  
```  
front_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член возвращает значение элемента обращаться.  
  
### <a name="remarks"></a>Примечания  
 Используется для реализации выражения итератора вывода **\*Iter** = **значение**. Если **Iter** является итератором, который затем обращается элемент в последовательности, **\*Iter** = **значение** заменяет значение элемента и не изменяет общее число элементов в последовательности.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namefrontinsertiteratoroperatoraddadda-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_add_add"></a>  front_insert_iterator::operator ++  
 Увеличивает `back_insert_iterator` до следующего местоположения, в котором можно сохранить значение.  
  
```  
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `front_insert_iterator` адресации следующего местоположения, в котором можно сохранить значение.  
  
### <a name="remarks"></a>Примечания  
 Операторы preincrementation и postincrementation возвращают одинаковый результат.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namefrontinsertiteratoroperatoreqa-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_eq"></a>  front_insert_iterator::operator =  
 Добавляет (отправок) значение в передней части контейнера.  
  
```  
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Параметры  
 ` val`  
 Значение, присваиваемое контейнера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка для последнего элемента, вставленного в начале контейнера.  
  
### <a name="remarks"></a>Примечания  
 Первый оператор член имеет `container.push_front( val)`, возвращается `*this`.  
  
 Второй оператор член имеет  
  
 `container->push_front((typename Container::value_type&&) val)`,  
  
 Возвращает `*this`.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namefrontinsertiteratorreferencea-frontinsertiteratorreference"></a><a name="front_insert_iterator__reference"></a>  front_insert_iterator::Reference  
 Тип, который предоставляет ссылку на элемент последовательности под управлением связанного контейнера.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="example"></a>Пример  
  
```  
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
 [\< итератора>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)

