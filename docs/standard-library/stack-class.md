---
title: "Класс stack | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- stack/std::stack::container_type
- stack/std::stack::size_type
- stack/std::stack::value_type
- stack/std::stack::empty
- stack/std::stack::pop
- stack/std::stack::push
- stack/std::stack::size
- stack/std::stack::top
dev_langs:
- C++
helpviewer_keywords:
- std::stack [C++], container_type
- std::stack [C++], size_type
- std::stack [C++], value_type
- std::stack [C++], empty
- std::stack [C++], pop
- std::stack [C++], push
- std::stack [C++], size
- std::stack [C++], top
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 876b4614438e92b3f90482a91f13f33b78e8266a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="stack-class"></a>Класс stack
Класс адаптера контейнера шаблона, который предоставляет ограничение функциональности, ограничивая доступ к элементу, который был последним добавлен в некоторый тип базового контейнера. Класс стека используется в том случае, когда важно пояснить, что в контейнере выполняются только операции стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Type, class Container= deque <Type>>  
class stack  
```  
  
#### <a name="parameters"></a>Параметры  
 *Тип*  
 Тип данных элемента для сохранения в стеке.  
  
 `Container`  
 Тип базового контейнера, используемый для реализации стека. Значение по умолчанию — класс `deque`*\<Type>*.  
  
## <a name="remarks"></a>Примечания  
 Элементы класса **Type**, заданного в первом параметре шаблона объекта стека, являются синонимами [value_type](#value_type) и должны соответствовать типу элемента в классе базового контейнера **Container**, заданного вторым параметром шаблона. Класс **Type** должен быть назначаемым, чтобы можно было скопировать объекты этого типа и присвоить значения переменным этого типа.  
  
 К подходящим классам базового контейнера для стека относятся [deque](../standard-library/deque-class.md), [list](../standard-library/list-class.md) и [vector](../standard-library/vector-class.md), а также любой другой контейнер последовательностей, поддерживающий операции **back**, `push_back` и `pop_back`. Класс базового контейнера инкапсулирован в адаптер контейнера, который предоставляет только ограниченный набор функций-членов контейнера последовательностей в виде открытого интерфейса.  
  
 Объекты стека можно сравнивать по равенству тогда и только тогда, когда элементы класса **Type** сравнимы по равенству, и сравнивать по оператору "меньше чем" тогда и только тогда, когда элементы класса **Type** сравнимы по оператору "меньше чем".  
  
-   Класс стека поддерживает структуру данных «последним поступил — первым обслужен» (LIFO). Хороший аналог такого подхода — стопка тарелок. Элементы (тарелки) можно вставлять, проверять или удалять только из верхней части стека, которая является последним элементом в конце базового контейнера. Ограничение на доступ только к верхнему элементу является причиной использования класса стека.  
  
-   [Класс queue](../standard-library/queue-class.md) поддерживает структуру данных "первым поступил — первым обслужен" (FIFO). Хороший аналог такого подхода — очередь из людей к банковскому служащему. Элементы (люди) можно добавлять в конец очереди и удалять из начала очереди. Проверять можно как начало, так и конец очереди. Ограничение на доступ только к переднему и заднему элементам в таком подходе является причиной использования класса очереди.  
  
-   [Класс priority_queue](../standard-library/priority-queue-class.md) упорядочивает элементы, чтобы наибольший элемент всегда находился сверху. Он поддерживает вставку элемента, а также проверку и удаление верхнего элемента. Хороший аналог такого подхода — очередь из людей, упорядоченная по возрасту, росту или любому другому критерию.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[stack](#stack)|Создает `stack`, который является пустым или копией объекта базового контейнера.|  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[container_type](#container_type)|Тип, предоставляющий базовый контейнер для принятия `stack`.|  
|[size_type](#size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `stack`.|  
|[value_type](#value_type)|Тип, представляющий тип объекта, который хранится в виде элемента в `stack`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[empty](#empty)|Проверяет, является ли `stack` пустым.|  
|[pop](#pop)|Удаляет элемент из верхней части `stack`.|  
|[push](#push)|Добавляет элемент в верхнюю часть `stack`.|  
|[size](#size)|Возвращает количество элементов в контейнере `stack`.|  
|[top](#top)|Возвращает ссылку на элемент в верхней части `stack`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<stack>  
  
 **Пространство имен:** std  
  
##  <a name="container_type"></a> stack::container_type  
 Тип, предоставляющий базовый контейнер для изменения.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Container`. Все три класса контейнеров последовательности стандартной библиотеки C++ (класс vector, класс list и класс по умолчанию deque) соответствуют требованиям для использования в качестве базового контейнера для объекта стека. Также можно использовать пользовательские типы, удовлетворяющие таким требованиям.  
  
 Дополнительные сведения о `Container` см. в подразделе "Примечания" раздела [Класс stack](../standard-library/stack-class.md).  
  
### <a name="example"></a>Пример  
  См. пример объявления и использования `container_type` в разделе [stack::stack](#stack).  
  
##  <a name="empty"></a> stack::empty  
 Проверяет, пуст ли стек.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если стек пуст; значение **false**, если стек не пуст.  
  
### <a name="example"></a>Пример  
  
```cpp  
// stack_empty.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack <int> s1, s2;  
  
   s1.push( 1 );  
  
   if ( s1.empty( ) )  
      cout << "The stack s1 is empty." << endl;  
   else  
      cout << "The stack s1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The stack s2 is empty." << endl;  
   else  
      cout << "The stack s2 is not empty." << endl;  
}  
```  
  
```Output  
The stack s1 is not empty.  
The stack s2 is empty.  
```  
  
##  <a name="pop"></a> stack::pop  
 Удаляет элемент из верхней части стека.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Примечания  
 Для применения функции-члена стек должен быть непустым. Начало (верх) стека — это положение, занимаемое последним добавленным элементом, которое является последним элементом в конце контейнера.  
  
### <a name="example"></a>Пример  
  
```cpp  
// stack_pop.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
  
   s1.pop( );  
  
   i = s1.size( );  
   cout << "After a pop, the stack length is "   
        << i << "." << endl;  
  
   i = s1.top( );  
   cout << "After a pop, the element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
After a pop, the stack length is 2.  
After a pop, the element at the top of the stack is 20.  
```  
  
##  <a name="push"></a> stack::push  
 Добавляет элемент в начало (верх) стека.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Параметры  
 `val`  
 Элемент, добавленный в верх стека.  
  
### <a name="remarks"></a>Примечания  
 Начало (верх) стека — это положение, занимаемое последним добавленным элементом, которое является последним элементом в конце контейнера.  
  
### <a name="example"></a>Пример  
  
```cpp  
// stack_push.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
```  
  
##  <a name="size"></a> stack::size  
 Возвращает количество элементов в стеке.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина стека.  
  
### <a name="example"></a>Пример  
  
```cpp  
// stack_size.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
   stack <int>::size_type i;  
  
   s1.push( 1 );  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   s1.push( 2 );  
   i = s1.size( );  
   cout << "The stack length is now " << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 1.  
The stack length is now 2.  
```  
  
##  <a name="size_type"></a> stack::size_type  
 Целочисленный тип без знака, который может представлять количество элементов в стеке.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для `size_type` базового контейнера, адаптированного стеком.  
  
### <a name="example"></a>Пример  
  См. пример объявления и использования `size_type` в разделе [size](#size).  
  
##  <a name="stack"></a> stack::stack  
 Создает стек, который является пустым или представляет собой копию класса базового контейнера.  
  
```  
stack();

explicit stack(const container_type& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Контейнер, копией которого должен стать создаваемый стек.  
  
### <a name="example"></a>Пример  
  
```cpp  
// stack_stack.cpp  
// compile with: /EHsc  
#include <stack>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares stack with default deque base container  
   stack <char> dsc1;  
  
   //Explicitly declares a stack with deque base container  
   stack <char, deque<char> > dsc2;  
  
   // Declares a stack with vector base containers  
   stack <int, vector<int> > vsi1;  
  
   // Declares a stack with list base container  
   stack <int, list<int> > lsi;  
  
   // The second member function copies elements from a container  
   vector<int> v1;  
   v1.push_back( 1 );  
   stack <int, vector<int> > vsi2( v1 );  
   cout << "The element at the top of stack vsi2 is "  
        << vsi2.top( ) << "." << endl;  
}  
```  
  
```Output  
The element at the top of stack vsi2 is 1.  
```  
  
##  <a name="top"></a> stack::top  
 Возвращает ссылку на элемент вверху стека.  
  
```  
reference top();

const_reference top() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на последний элемент в контейнере, вставленный вверху стека.  
  
### <a name="remarks"></a>Примечания  
 Для применения функции-члена стек должен быть непустым. Начало (верх) стека — это положение, занимаемое последним добавленным элементом, которое является последним элементом в конце контейнера.  
  
 Если возвращаемое значение **top** присваивается `const_reference`, изменить объект стека невозможно. Если возвращаемое значение **top** присваивается **reference**, объект стека можно изменить.  
  
### <a name="example"></a>Пример  
  
```cpp  
// stack_top.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 1 );  
   s1.push( 2 );  
  
   int& i = s1.top( );  
   const int& ii = s1.top( );  
  
   cout << "The top integer of the stack s1 is "  
        << i << "." << endl;  
   i--;  
   cout << "The next integer down is "<< ii << "." << endl;  
}  
```  
  
```Output  
The top integer of the stack s1 is 2.  
The next integer down is 1.  
```  
  
##  <a name="value_type"></a> stack::value_type  
 Тип, представляющий тип объекта, который хранится в стеке в виде элемента.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для `value_type` базового контейнера, адаптированного стеком.  
  
### <a name="example"></a>Пример  
  
```cpp  
// stack_value_type.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   stack<int> s1;  
   s1.push( AnInt );  
   cout << "The element at the top of the stack is "  
        << s1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the stack is 69.  
```  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)

