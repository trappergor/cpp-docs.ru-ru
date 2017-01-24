---
title: "Класс back_insert_iterator | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/std::back_insert_iterator"
  - "std::back_insert_iterator"
  - "back_insert_iterator"
  - "std.back_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back_insert_iterator - класс"
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс back_insert_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 Контейнер должен удовлетворять требованиям последовательности вставки в конечную часть, если можно вставить элементы в конец последовательности в постоянном времени с поправкой на амортизацию. Контейнеры последовательности STL, определенные классами [класс deque](../standard-library/deque-class.md), [класс list](../standard-library/list-class.md) и [класс vector](vector%20Class.md) обеспечивают необходимую `push_back` члена функции и удовлетворяют этим требованиям. Эти три контейнера, как и строки, можно адаптировать для использования в сочетании с итераторами `back_insert_iterator`. Итератор `back_insert_iterator` всегда необходимо инициализировать с его контейнером.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[back_insert_iterator](#back_insert_iterator__back_insert_iterator)|Создает итератор `back_insert_iterator`, который добавляет элементы в местоположение за последним элементом в контейнере.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#back_insert_iterator__container_type)|Тип, предоставляющий контейнер для итератора `back_insert_iterator`.|  
|[ссылка](#back_insert_iterator__reference)|Тип, предоставляющий ссылку для итератора `back_insert_iterator`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор *](#back_insert_iterator__operator_star)|Оператор удаления ссылки, используемые для реализации выражения итератора вывода * `i` = `x` Назад вставки.|  
|[Operator ++](#back_insert_iterator__operator_add_add)|Увеличивает `back_insert_iterator` до следующего местоположения, в котором можно сохранить значение.|  
|[оператор =](#back_insert_iterator__operator_eq)|Оператор присваивания, используемый для реализации выражения итератора вывода * `i` = `x` Назад вставки.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок**: \< итератора>  
  
 **Пространство имен:** std  
  
##  <a name="a-namebackinsertiteratorbackinsertiteratora-backinsertiteratorbackinsertiterator"></a><a name="back_insert_iterator__back_insert_iterator"></a>  back_insert_iterator::back_insert_iterator  
 Создает итератор `back_insert_iterator`, который добавляет элементы в местоположение за последним элементом в контейнере.  
  
```  
 
explicit back_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Параметры  
 `_Cont`  
 Контейнер, `back_insert_iterator` вставляет элемент в.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `back_insert_iterator` для параметра контейнера.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namebackinsertiteratorcontainertypea-backinsertiteratorcontainertype"></a><a name="back_insert_iterator__container_type"></a>  back_insert_iterator::container_type  
 Тип, предоставляющий контейнер для итератора `back_insert_iterator`.  
  
```  
 
typedef Container  
container_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **контейнер**.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namebackinsertiteratoroperatorstara-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_star"></a>  back_insert_iterator::operator *  
 Оператор удаления ссылки, используемые для реализации выражения итератора вывода \* *я* = *x*.  
  
```  
back_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка для элемента, вставляемого обратной стороны контейнера.  
  
### <a name="remarks"></a>Примечания  
 Используется для реализации выражения итератора вывода **\*Iter** = **значение**. Если **Iter** является итератором, который затем обращается элемент в последовательности, **\*Iter** = **значение** заменяет значение элемента и не изменяет общее число элементов в последовательности.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namebackinsertiteratoroperatoraddadda-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_add_add"></a>  back_insert_iterator::operator ++  
 Увеличивает `back_insert_iterator` до следующего местоположения, в котором можно сохранить значение.  
  
```  
back_insert_iterator<Container>& operator++();

back_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `back_insert_iterator` адресации следующего местоположения, в котором можно сохранить значение.  
  
### <a name="remarks"></a>Примечания  
 Операторы preincrementation и postincrementation возвращают одинаковый результат.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namebackinsertiteratoroperatoreqa-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_eq"></a>  back_insert_iterator::operator =  
 Добавляет или помещает значение на конец контейнера.  
  
```  
back_insert_iterator<Container>& operator=(typename Container::const_reference val);

    back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Параметры  
 ` val`  
 Значение вставляемого в контейнере.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка для последнего элемента, вставленного на задней контейнера.  
  
### <a name="remarks"></a>Примечания  
 Первый оператор член имеет `Container.push_back( val)`,  
  
 Возвращает `*this`. Второй оператор член имеет  
  
 `container->push_back((typename Container::value_type&&)val)`,  
  
 Возвращает `*this`.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namebackinsertiteratorreferencea-backinsertiteratorreference"></a><a name="back_insert_iterator__reference"></a>  back_insert_iterator::Reference  
 Тип, предоставляющий ссылку для итератора `back_insert_iterator`.  
  
```  
 
typedef typename Container::reference reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип, описывающий ссылку на элемент последовательности под управлением связанного контейнера.  
  
### <a name="example"></a>Пример  
  
```  
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
 [\< итератора>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)

