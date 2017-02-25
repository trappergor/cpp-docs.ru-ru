---
title: "Класс queue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.queue"
  - "std::queue"
  - "queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue - класс"
ms.assetid: 28c20ab0-3a72-4185-9e0f-5a44eea0e204
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс queue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс адаптера контейнера шаблона, предоставляющий ограничения функциональных возможностей для некоторых базовый тип контейнера, ограничивая доступ к элементам передней и задней. Элементы могут добавляться на задней панели или удалены из начала и элементы, которые можно проверить на любом конце очереди.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Type, class Container = deque <Type>>  
class queue  
```  
  
#### <a name="parameters"></a>Параметры  
 *Тип*  
 Тип данных элемента должны храниться в очереди  
  
 `Container`  
 Тип базового контейнера, используемый для реализации очереди.  
  
## <a name="remarks"></a>Примечания  
 Элементы класса **тип** оговорено в шаблоне первый параметр объекта очереди являются синонимами [value_type](#queue__value_type) и должно соответствовать типу элемента в базовый класс контейнера **контейнер** оговорено в качестве второго параметра шаблона.  **Тип** должно быть присваиваемым, так что возможно копирование объектов этого типа и для присвоения значений переменных этого типа.  
  
 Включить подходящие базовые классы контейнеров для очереди [deque](../standard-library/deque-class.md) и [список](../standard-library/list-class.md), или другой контейнер последовательности, которая поддерживает операции `front`, **обратно**, `push_back`, и `pop_front`. Класс базового контейнера инкапсулирован в адаптер контейнера, который предоставляет только ограниченный набор функций-членов контейнера последовательностей в виде открытого интерфейса.  
  
 Очередь объекты сравним равенства, только если элементы класса **тип** сравнимы равенства и меньше,-чем сравнимых, только если элементы класса **тип** меньше-чем сравним.  
  
 Существует три типа адаптеров контейнера определяется STL: стека, очереди и priority_queue. Каждый ограничивает функциональность некоторых базового класса контейнера для выполнения точно управляемый интерфейс к структуре стандартных данных.  
  
-    [Класс stack](../standard-library/stack-class.md) поддерживает структуру данных последним поступил — первым обслужен (LIFO). Хороший аналог такого подхода — стопка тарелок. Элементы (тарелки) можно вставлять, проверять или удалять только из верхней части стека, которая является последним элементом в конце базового контейнера. Ограничение на доступ только к верхнему элементу является причиной использования класса стека.  
  
-   Класс очереди поддерживает первым в структуру данных first-out (FIFO). Хороший аналог такого подхода — очередь из людей к банковскому служащему. Элементы (люди) можно добавлять в конец очереди и удалять из начала очереди. Проверять можно как начало, так и конец очереди. Ограничение на доступ к только Передняя и задняя элементы таким образом — причина с помощью класса очереди.  
  
-    [Класс priority_queue](../standard-library/priority-queue-class.md) упорядочивает элементы, чтобы самого большого элемента всегда в верхней части. Он поддерживает вставку элемента, а также проверку и удаление верхнего элемента. Хороший аналог такого подхода — очередь из людей, упорядоченная по возрасту, росту или любому другому критерию.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[очереди](#queue__queue)|Создает `queue`, который является пустым или копией объекта базового контейнера.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#queue__container_type)|Тип, предоставляющий базовый контейнер адаптировать по `queue`.|  
|[size_type](#queue__size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `queue`.|  
|[value_type](#queue__value_type)|Тип, представляющий тип объекта, который хранится в виде элемента в `queue`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[Назад](#queue__back)|Добавлена ссылка на последнюю и наиболее часто элемент на резервное из возвращает `queue`.|  
|[пустой](#queue__empty)|Проверяет, является ли `queue` пустым.|  
|[передний план](#queue__front)|Возвращает ссылку на первый элемент в передней части `queue`.|  
|[POP](#queue__pop)|Удаляет элемент из начала `queue`.|  
|[Push](#queue__push)|Добавляет элемент в конец `queue`.|  
|[размер](#queue__size)|Возвращает количество элементов в контейнере `queue`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< очереди>  
  
 **Пространство имен:** std  
  
##  <a name="a-namequeuebacka-queueback"></a><a name="queue__back"></a>  Queue::Back  
 Возвращает ссылку на последнюю и наиболее часто добавлением элемент обратной стороны очереди.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последний элемент из очереди. Если очередь пуста, возвращаемое значение не определено.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение **обратно** назначается `const_reference`, объект очереди нельзя изменить. Если возвращаемое значение **обратно** назначается **ссылки**, объект очереди может быть изменен.  
  
 При компиляции с параметром _SECURE_SCL 1 возникнет ошибка времени выполнения, при попытке доступа к элементу в пустую очередь.  Дополнительные сведения см. в разделе [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Пример  
  
```  
// queue_back.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 11 );  
  
   int& i = q1.back( );  
   const int& ii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << i   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << ii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuecontainertypea-queuecontainertype"></a><a name="queue__container_type"></a>  Queue::container_type  
 Тип, предоставляющий необходимо адаптировать базового контейнера.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Container`. Два класса контейнера последовательности STL — класса list и deque-класс по умолчанию — требованиям для использования в качестве базового контейнера для объекта очереди. Может также использоваться определяемые пользователем типы, удовлетворяющие требованиям.  
  
 Дополнительные сведения о `Container`, в разделе «Примечания» [класс queue](../standard-library/queue-class.md) раздела.  
  
### <a name="example"></a>Пример  
  В примере показано [очереди](#queue__queue) пример того, как объявить и использовать `container_type`.  
  
##  <a name="a-namequeueemptya-queueempty"></a><a name="queue__empty"></a>  Queue::Empty  
 Проверяет, пуста ли очередь.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если очередь пуста; **false** Если очередь не пуста.  
  
### <a name="example"></a>Пример  
  
```  
// queue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue <int> q1, q2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The queue q1 is empty." << endl;  
   else  
      cout << "The queue q1 is not empty." << endl;  
  
   if ( q2.empty( ) )  
      cout << "The queue q2 is empty." << endl;  
   else  
      cout << "The queue q2 is not empty." << endl;  
}  
```  
  
```Output  
The queue q1 is not empty.  
The queue q2 is empty.  
```  
  
##  <a name="a-namequeuefronta-queuefront"></a><a name="queue__front"></a>  Queue::Front  
 Возвращает ссылку на первый элемент в начале очереди.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый элемент из очереди. Если очередь пуста, возвращаемое значение не определено.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `front` назначается `const_reference`, объект очереди нельзя изменить. Если возвращаемое значение `front` назначается **ссылки**, объект очереди может быть изменен.  
  
 Функция-член возвращает **ссылки** первый элемент управляемой последовательности, которой не должно быть пустым.  
  
 При компиляции с параметром _SECURE_SCL 1 возникнет ошибка времени выполнения, при попытке доступа к элементу в пустую очередь.  Дополнительные сведения см. в разделе [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Пример  
  
```  
// queue_front.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   int& ii = q1.back( );  
   int& iii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << ii   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << iii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuepopa-queuepop"></a><a name="queue__pop"></a>  Queue::POP  
 Удаляет элемент из начала очереди.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Примечания  
 Очереди должно быть пустым, чтобы применить функцию-член. Начало очереди — это положение, занимаемая элементом, недавно добавленных и является последним элементом в конце контейнера.  
  
### <a name="example"></a>Пример  
  
```  
// queue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
  
   q1.pop( );  
  
   i = q1.size( );  
   cout << "After a pop the queue length is "   
        << i << "." << endl;  
  
   i = q1. front ( );  
   cout << "After a pop, the element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
After a pop the queue length is 2.  
After a pop, the element at the front of the queue is 20.  
```  
  
##  <a name="a-namequeuepusha-queuepush"></a><a name="queue__push"></a>  Queue::Push  
 Добавляет элемент в конец очереди.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Параметры  
 `val`  
 Элемент, добавляемый в конец очереди.  
  
### <a name="remarks"></a>Примечания  
 В конец очереди — это положение, занимаемая элементом, недавно добавленных и является последним элементом в конце контейнера.  
  
### <a name="example"></a>Пример  
  
```  
// queue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
```  
  
##  <a name="a-namequeuequeuea-queuequeue"></a><a name="queue__queue"></a>  Queue::Queue  
 Создает очередь, который является пустым или копией объекта базового контейнера.  
  
```  
queue();

explicit queue(const container_type& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
  **Const** контейнера сконструированный очереди которого является копией.  
  
### <a name="remarks"></a>Примечания  
 Базовый контейнер по умолчанию для очереди является deque. Список также можно указать в качестве базового контейнера, но нельзя указать вектор, так как у него нет необходимых `pop_front` функции-члена.  
  
### <a name="example"></a>Пример  
  
```  
// queue_queue.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queue with default deque base container  
   queue <char> q1;  
  
   // Explicitly declares a queue with deque base container  
   queue <char, deque<char> > q2;  
  
   // These lines don't cause an error, even though they  
   // declares a queue with a vector base container  
   queue <int, vector<int> > q3;  
   q3.push( 10 );  
   // but the following would cause an error because vector has   
   // no pop_front member function  
   // q3.pop( );  
  
   // Declares a queue with list base container  
   queue <int, list<int> > q4;  
  
   // The second member function copies elements from a container  
   list<int> li1;  
   li1.push_back( 1 );  
   li1.push_back( 2 );  
   queue <int, list<int> > q5( li1 );  
   cout << "The element at the front of queue q5 is "  
        << q5.front( ) << "." << endl;  
   cout << "The element at the back of queue q5 is "  
        << q5.back( ) << "." << endl;  
}  
```  
  
```Output  
The element at the front of queue q5 is 1.  
The element at the back of queue q5 is 2.  
```  
  
##  <a name="a-namequeuesizea-queuesize"></a><a name="queue__size"></a>  Queue::size  
 Возвращает количество элементов в очереди.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина очереди.  
  
### <a name="example"></a>Пример  
  
```  
// queue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2;  
   queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 1.  
The queue length is now 2.  
```  
  
##  <a name="a-namequeuesizetypea-queuesizetype"></a><a name="queue__size_type"></a>  Queue::size_type  
 Беззнаковый целочисленный тип, который может представлять число элементов в очереди.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `size_type` базового контейнера адаптировать по очереди.  
  
### <a name="example"></a>Пример  
  В примере показано [queue::front](#queue__front) пример того, как объявить и использовать `size_type`.  
  
##  <a name="a-namequeuevaluetypea-queuevaluetype"></a><a name="queue__value_type"></a>  Queue::value_type  
 Тип, представляющий тип объекта, сохраненный как элемент в очереди.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `value_type` базового контейнера адаптировать по очереди.  
  
### <a name="example"></a>Пример  
  
```  
// queue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   queue<int> q1;  
   q1.push(AnInt);  
   cout << "The element at the front of the queue is "  
        << q1.front( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the front of the queue is 69.  
```  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)

