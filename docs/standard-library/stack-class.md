---
title: "Класс stack | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::stack"
  - "std.stack"
  - "stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "стек stack-класс"
  - "stack - класс"
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс stack
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 Тип базового контейнера, используемый для реализации стека. Значение по умолчанию является класс `deque`*\< тип>*.  
  
## <a name="remarks"></a>Примечания  
 Элементы класса **тип** оговорено в шаблоне первого параметра объект стека являются синонимами [value_type](#stack__value_type) и должно соответствовать типу элемента в базовый класс контейнера **контейнер** оговорено в качестве второго параметра шаблона.  **Тип** должно быть присваиваемым, так что возможно копирование объектов этого типа и для присвоения значений переменных этого типа.  
  
 Включить подходящие базовые классы контейнеров для стека [deque](../standard-library/deque-class.md), [класс list](../standard-library/list-class.md), и [класс vector](vector%20Class.md), или другой контейнер последовательности, которая поддерживает операции **обратно**, `push_back`, и `pop_back`. Класс базового контейнера инкапсулирован в адаптер контейнера, который предоставляет только ограниченный набор функций-членов контейнера последовательностей в виде открытого интерфейса.  
  
 Стека объекты сравним равенства, только если элементы класса **тип** сравнимы равенства и меньше,-чем сравнимых, только если элементы класса **тип** меньше-чем сравним.  
  
-   Класс стека поддерживает структуру данных «последним поступил — первым обслужен» (LIFO). Хороший аналог такого подхода — стопка тарелок. Элементы (тарелки) можно вставлять, проверять или удалять только из верхней части стека, которая является последним элементом в конце базового контейнера. Ограничение на доступ только к верхнему элементу является причиной использования класса стека.  
  
-    [Класс queue](../standard-library/queue-class.md) поддерживает структуру данных первым пришел, first-out (FIFO). Хороший аналог такого подхода — очередь из людей к банковскому служащему. Элементы (люди) можно добавлять в конец очереди и удалять из начала очереди. Проверять можно как начало, так и конец очереди. Ограничение на доступ только к переднему и заднему элементам в таком подходе является причиной использования класса очереди.  
  
-    [Класс priority_queue](../standard-library/priority-queue-class.md) упорядочивает элементы, чтобы самого большого элемента всегда в верхней части. Он поддерживает вставку элемента, а также проверку и удаление верхнего элемента. Хороший аналог такого подхода — очередь из людей, упорядоченная по возрасту, росту или любому другому критерию.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[стек](#stack__stack)|Создает `stack`, который является пустым или копией объекта базового контейнера.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#stack__container_type)|Тип, предоставляющий базовый контейнер для принятия `stack`.|  
|[size_type](#stack__size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `stack`.|  
|[value_type](#stack__value_type)|Тип, представляющий тип объекта, который хранится в виде элемента в `stack`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[пустой](#stack__empty)|Проверяет, является ли `stack` пустым.|  
|[POP](#stack__pop)|Удаляет элемент из верхней части `stack`.|  
|[Push](#stack__push)|Добавляет элемент в верхнюю часть `stack`.|  
|[размер](#stack__size)|Возвращает количество элементов в контейнере `stack`.|  
|[Вверх](#stack__top)|Возвращает ссылку на элемент в верхней части `stack`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< стека>  
  
 **Пространство имен:** std  
  
##  <a name="a-namestackcontainertypea-stackcontainertype"></a><a name="stack__container_type"></a>  STACK::container_type  
 Тип, предоставляющий необходимо адаптировать базового контейнера.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Container`. Все три класса контейнера последовательности STL, класс vector, класс списка и deque класса по умолчанию — требованиям для использования в качестве базового контейнера для объекта стека. Может также использоваться определяемые пользователем типы, удовлетворяющие этим требованиям.  
  
 Дополнительные сведения о `Container`, в разделе «Примечания» [класс stack](../standard-library/stack-class.md) раздела.  
  
### <a name="example"></a>Пример  
  В примере показано [stack::stack](#stack__stack) пример того, как объявить и использовать `container_type`.  
  
##  <a name="a-namestackemptya-stackempty"></a><a name="stack__empty"></a>  STACK::Empty  
 Проверяет, если стек пуст.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если стек пуст; **false** Если стека не является пустой.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namestackpopa-stackpop"></a><a name="stack__pop"></a>  STACK::POP  
 Удаляет элемент из верхней части стека.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Примечания  
 Стек должно быть пустым, чтобы применить функцию-член. Вверху стека — это положение, занимаемая элементом, недавно добавленных и является последним элементом в конце контейнера.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namestackpusha-stackpush"></a><a name="stack__push"></a>  STACK::Push  
 Добавляет элемент в верхнем конце стека.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Параметры  
 ` val`  
 Элемент, добавляемый в верхней части стека.  
  
### <a name="remarks"></a>Примечания  
 Вверху стека — это положение, занимаемая элементом, недавно добавленных и является последним элементом в конце контейнера.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namestacksizea-stacksize"></a><a name="stack__size"></a>  STACK::size  
 Возвращает количество элементов в стеке.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина стека.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namestacksizetypea-stacksizetype"></a><a name="stack__size_type"></a>  STACK::size_type  
 Беззнаковый целочисленный тип, который может представлять число элементов в стеке.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `size_type` адаптировать стеком базового контейнера.  
  
### <a name="example"></a>Пример  
  В примере показано [размер](#stack__size) пример того, как объявить и использовать `size_type`.  
  
##  <a name="a-namestackstacka-stackstack"></a><a name="stack__stack"></a>  STACK::Stack  
 Создает стека, который является пустым или копией класса базового контейнера.  
  
```  
stack();

explicit stack(const container_type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Контейнер, сконструированный стек которого является копией.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namestacktopa-stacktop"></a><a name="stack__top"></a>  STACK::Top  
 Возвращает ссылку на элемент в верхней части стека.  
  
```  
reference top();

const_reference top() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на последний элемент в контейнере в верхней части стека.  
  
### <a name="remarks"></a>Примечания  
 Стек должно быть пустым, чтобы применить функцию-член. Вверху стека — это положение, занимаемая элементом, недавно добавленных и является последним элементом в конце контейнера.  
  
 Если возвращаемое значение **Начало** назначается `const_reference`, объект стека невозможно изменить. Если возвращаемое значение **Начало** назначается **ссылки**, объект стека можно изменить.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namestackvaluetypea-stackvaluetype"></a><a name="stack__value_type"></a>  STACK::value_type  
 Тип, представляющий тип объекта, сохраненный как элемент в стеке.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `value_type` адаптировать стеком базового контейнера.  
  
### <a name="example"></a>Пример  
  
```  
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
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)

