---
title: "Класс priority_queue | Microsoft Docs"
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
  - "std.priority_queue"
  - "priority_queue"
  - "std::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "priority_queue - класс"
ms.assetid: 69fca9cc-a449-4be4-97b7-02ca5db9cbb2
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс priority_queue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс адаптера контейнера шаблона, предоставляющий ограничение функциональности ограничения доступа к верхнему элементу некоторые базовый тип контейнера, который всегда является наибольшим или с наивысшим приоритетом. Новые элементы добавляются в priority_queue и верхний элемент priority_queue можно просмотреть или удалить.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Type, class Container= vector <Type>, class Compare= less <typename Container ::value_type>>  
class priority_queue  
```  
  
#### <a name="parameters"></a>Параметры  
 *Тип*  
 Тип данных элемента для сохранения в priority_queue.  
  
 `Container`  
 Тип базового контейнера, используемый для реализации priority_queue.  
  
 *Сравнение*  
 Тип, предоставляющий объект функции, который может сравнить два значения элемента как ключи сортировки для определения их относительного порядка в priority_queue. Этот аргумент является необязательным и бинарный предикат **меньше***\<***typename** *контейнер***:: value_type***>* значение по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 Элементы класса **тип** оговорено в шаблоне первый параметр объекта очереди являются синонимами [value_type](#priority_queue__value_type) и должно соответствовать типу элемента в базовый класс контейнера **контейнер** оговорено в качестве второго параметра шаблона.  **Тип** должно быть присваиваемым, так что возможно копирование объектов этого типа и для присвоения значений переменных этого типа.  
  
 Priority_queue упорядочивает последовательности, он управляет, путем обращения к сохраненному объекту функции класса **признаков**. В целом, упорядочиваемые элементы должны лишь подлежать сравнению "меньше чем" для установления такого порядка, чтобы, имея любые два элемента, можно было определить, что они равны (ни один не меньше другого) или что один меньше другого. Это приводит к упорядочению неравнозначных элементов. С более технической точки зрения, функция сравнения является бинарным предикатом, который вызывает строгого слабое упорядочение в стандартном математически смысле.  
  
 Включить подходящие базовые классы контейнеров для priority_queue [класс deque](../standard-library/deque-class.md) и значение по умолчанию [класс vector](vector%20Class.md) или другой контейнер последовательности, которая поддерживает операции `front`, `push_back`, и `pop_back` и итератор произвольного доступа. Класс базового контейнера инкапсулирован в адаптер контейнера, который предоставляет только ограниченный набор функций-членов контейнера последовательностей в виде открытого интерфейса.  
  
 Элементы для добавления и удаления элементов из `priority_queue` имеют логарифмической сложности. Доступ к элементам в `priority_queue` имеет постоянную сложность.  
  
 Существует три типа адаптеров контейнера определяется STL: стека, очереди и priority_queue. Каждый ограничивает функциональность некоторых базового класса контейнера для выполнения точно управляемый интерфейс к структуре стандартных данных.  
  
-    [Класс stack](../standard-library/stack-class.md) поддерживает структуру данных последним поступил — первым обслужен (LIFO). Хороший аналог такого подхода — стопка тарелок. Элементы (тарелки) можно вставлять, проверять или удалять только из верхней части стека, которая является последним элементом в конце базового контейнера. Ограничение на доступ только к верхнему элементу является причиной использования класса стека.  
  
-    [Класс queue](../standard-library/queue-class.md) поддерживает структуру данных первым пришел, first-out (FIFO). Хороший аналог такого подхода — очередь из людей к банковскому служащему. Элементы (люди) можно добавлять в конец очереди и удалять из начала очереди. Проверять можно как начало, так и конец очереди. Ограничение на доступ к только Передняя и задняя элементы таким образом — причина с помощью класса очереди.  
  
-   Класс priority_queue упорядочивает элементы таким образом самого большого элемента всегда в верхней части. Он поддерживает вставку элемента, а также проверку и удаление верхнего элемента. Хороший аналог такого подхода — очередь из людей, упорядоченная по возрасту, росту или любому другому критерию.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[priority_queue](#priority_queue__priority_queue)|Создает `priority_queue` пуста или которая является копию диапазона объекта базового контейнера или других `priority_queue`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#priority_queue__container_type)|Тип, предоставляющий базовый контейнер для принятия `priority_queue`.|  
|[size_type](#priority_queue__size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `priority_queue`.|  
|[value_type](#priority_queue__value_type)|Тип, представляющий тип объекта, который хранится в виде элемента в `priority_queue`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[пустой](#priority_queue__empty)|Проверяет, является ли `priority_queue` пустым.|  
|[POP](#priority_queue__pop)|Удаляет наибольший элемент из `priority_queue` с верхней строчки.|  
|[Push](#priority_queue__push)|Добавляет элемент в очередь приоритета на основе приоритета элемента из оператора <.|  
|[размер](#priority_queue__size)|Возвращает количество элементов в контейнере `priority_queue`.|  
|[Вверх](#priority_queue__top)|Возвращает константную ссылку самого большого элемента в верхней части `priority_queue`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< очереди>  
  
 **Пространство имен:** std  
  
##  <a name="a-namepriorityqueuecontainertypea-priorityqueuecontainertype"></a><a name="priority_queue__container_type"></a>  priority_queue::container_type  
 Тип, предоставляющий необходимо адаптировать базового контейнера.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Container`. Deque класса контейнера последовательности STL и вектор класса по умолчанию требованиям для использования в качестве базового контейнера для объекта priority_queue. Может также использоваться определяемые пользователем типы, удовлетворяющие требованиям.  
  
 Дополнительные сведения о `Container`, в разделе «Примечания» [класс priority_queue](../standard-library/priority-queue-class.md) раздела.  
  
### <a name="example"></a>Пример  
  В примере показано [priority_queue](#priority_queue__priority_queue) пример того, как объявить и использовать `container_type`.  
  
##  <a name="a-namepriorityqueueemptya-priorityqueueempty"></a><a name="priority_queue__empty"></a>  priority_queue::Empty  
 Проверяет priority_queue пуст.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если priority_queue пуст; **false** Если priority_queue не является пустой.  
  
### <a name="example"></a>Пример  
  
```  
// pqueue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue <int> q1, s2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The priority_queue q1 is empty." << endl;  
   else  
      cout << "The priority_queue q1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The priority_queue s2 is empty." << endl;  
   else  
      cout << "The priority_queue s2 is not empty." << endl;  
}  
```  
  
```Output  
The priority_queue q1 is not empty.  
The priority_queue s2 is empty.  
```  
  
##  <a name="a-namepriorityqueuepopa-priorityqueuepop"></a><a name="priority_queue__pop"></a>  priority_queue::POP  
 Удаляет наибольший элемент priority_queue с верхней строчки.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Примечания  
 Для применения функции-члена класс priority_queue не должен быть пустым. Вверху priority_queue всегда занятую наибольшего элемента в контейнере.  
  
### <a name="example"></a>Пример  
  
```  
// pqueue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   priority_queue <int>::size_type i, iii;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
  
   q1.pop( );  
  
   iii = q1.size( );  
   cout << "After a pop, the priority_queue length is "   
        << iii << "." << endl;  
  
   const int& iv = q1.top( );  
   cout << "After a pop, the element at the top of the "  
        << "priority_queue is " << iv << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
After a pop, the priority_queue length is 2.  
After a pop, the element at the top of the priority_queue is 20.  
```  
  
##  <a name="a-namepriorityqueuepriorityqueuea-priorityqueuepriorityqueue"></a><a name="priority_queue__priority_queue"></a>  priority_queue::priority_queue  
 Создает priority_queue, который является пустым или копией объекта базового контейнера или другой priority_queue диапазона.  
  
```  
priority_queue();

explicit priority_queue(const Traits&_comp);

priority_queue(const Traits&_comp, const container_type& _Cont);

priority_queue(const priority_queue& right);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp, const container_type& _Cont);
```  
  
### <a name="parameters"></a>Параметры  
 *Макет _*  
 Функция сравнения типа **constTraits** для упорядочивания элементов в priority_queue, по умолчанию используется для сравнения функции базового контейнера.  
  
 `_Cont`  
 Базовый контейнер сконструированный priority_queue которого является копией.  
  
 ` right`  
 Priority_queue, сконструированный набор которого является копией.  
  
 ` first`  
 Положение первого элемента в диапазоне копируемых элементов.  
  
 ` last`  
 Положение первого элемента после диапазона копируемых элементов.  
  
### <a name="remarks"></a>Примечания  
 Каждый из первых трех конструкторов задает пустой начальный priority_queue, во-вторых указания типа функции сравнения ( ` comp`) для использования при установлении порядок элементов и третий явного указания `container_type` ( `_Cont`) для использования. Ключевое слово **явных** подавляет некоторые виды автоматическое преобразование типов.  
  
 Четвертый конструктор задает копию priority_queue ` right`.  
  
 Последние три конструктора копируют диапазон [ * Фамилия*) некоторые контейнера и использовать значения, чтобы инициализировать priority_queue с увеличением explicitness при указании типа функции сравнения класса **признаков** и `container_type`.  
  
### <a name="example"></a>Пример  
  
```  
// pqueue_ctor.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <deque>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function declares priority_queue  
   // with a default vector base container  
   priority_queue <int> q1;  
   cout << "q1 = ( ";  
   while ( !q1.empty( ) )  
   {  
      cout << q1.top( ) << " ";  
      q1.pop( );  
   }  
   cout << ")" << endl;  
  
   // Explicitly declares a priority_queue with nondefault  
   // deque base container  
   priority_queue <int, deque <int> > q2;  
   q2.push( 5 );  
   q2.push( 15 );  
   q2.push( 10 );  
   cout << "q2 = ( ";  
   while ( !q2.empty( ) )  
   {  
      cout << q2.top( ) << " ";  
      q2.pop( );  
   }  
   cout << ")" << endl;  
  
   // This method of printing out the elements of a priority_queue  
   // removes the elements from the priority queue, leaving it empty  
   cout << "After printing, q2 has " << q2.size( ) << " elements." << endl;  
  
   // The third member function declares a priority_queue   
   // with a vector base container and specifies that the comparison   
   // function greater is to be used for ordering elements  
   priority_queue <int, vector<int>, greater<int> > q3;  
   q3.push( 2 );  
   q3.push( 1 );  
   q3.push( 3 );  
   cout << "q3 = ( ";  
   while ( !q3.empty( ) )  
   {  
      cout << q3.top( ) << " ";  
      q3.pop( );  
   }  
   cout << ")" << endl;  
  
   // The fourth member function declares a priority_queue and  
   // initializes it with elements copied from another container:  
   // first, inserting elements into q1, then copying q1 elements into q4  
   q1.push( 100 );  
   q1.push( 200 );  
   priority_queue <int> q4( q1 );  
   cout << "q4 = ( ";     
   while ( !q4.empty( ) )  
   {  
      cout << q4.top( ) << " ";  
      q4.pop( );  
   }  
   cout << ")" << endl;  
  
   // Creates an auxiliary vector object v5 to be used to initialize q5  
   vector <int> v5;  
   vector <int>::iterator v5_Iter;  
   v5.push_back( 10 );  
   v5.push_back( 30 );  
   v5.push_back( 20 );  
   cout << "v5 = ( " ;  
   for ( v5_Iter = v5.begin( ) ; v5_Iter != v5.end( ) ; v5_Iter++ )  
      cout << *v5_Iter << " ";  
   cout << ")" << endl;  
  
   // The fifth member function declares and  
   // initializes a priority_queue q5 by copying the  
   // range v5[ first,  last) from vector v5  
   priority_queue <int> q5( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q5 = ( ";  
   while ( !q5.empty( ) )  
   {  
      cout << q5.top( ) << " ";  
      q5.pop( );  
   }  
   cout << ")" << endl;  
  
   // The sixth member function declares a priority_queue q6  
   // with a comparison function greater and initializes q6  
   // by copying the range v5[ first,  last) from vector v5  
   priority_queue <int, vector<int>, greater<int> >   
      q6( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q6 = ( ";  
   while ( !q6.empty( ) )  
   {  
      cout << q6.top( ) << " ";  
      q6.pop( );  
   }  
   cout << ")" << endl;  
}  
```  
  
##  <a name="a-namepriorityqueuepusha-priorityqueuepush"></a><a name="priority_queue__push"></a>  priority_queue::Push  
 Добавляет элемент в очередь приоритета на основе приоритета элемента из оператора <.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Параметры  
 ` val`  
 Элемент, добавляемый в верхней части priority_queue.  
  
### <a name="remarks"></a>Примечания  
 Вверху priority_queue — это положение, занимаемое наибольшего элемента в контейнере.  
  
### <a name="example"></a>Пример  
  
```  
// pqueue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuesizea-priorityqueuesize"></a><a name="priority_queue__size"></a>  priority_queue::size  
 Возвращает число элементов в priority_queue.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина priority_queue.  
  
### <a name="example"></a>Пример  
  
```  
// pqueue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, q2;  
   priority_queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The priority_queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 1.  
The priority_queue length is now 2.  
```  
  
##  <a name="a-namepriorityqueuesizetypea-priorityqueuesizetype"></a><a name="priority_queue__size_type"></a>  priority_queue::size_type  
 Беззнаковый целочисленный тип, который может представлять число элементов в priority_queue.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `size_type` адаптировать путем priority_queue базового контейнера.  
  
### <a name="example"></a>Пример  
  В примере показано [размер](#priority_queue__size) пример того, как объявить и использовать `size_type`.  
  
##  <a name="a-namepriorityqueuetopa-priorityqueuetop"></a><a name="priority_queue__top"></a>  priority_queue::Top  
 Возвращает константную ссылку на наибольший элемент в верхней части priority_queue.  
  
```  
const_reference top() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на самого большого элемента определяется **признаков** функцию, объект priority_queue.  
  
### <a name="remarks"></a>Примечания  
 Для применения функции-члена класс priority_queue не должен быть пустым.  
  
### <a name="example"></a>Пример  
  
```  
// pqueue_top.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuevaluetypea-priorityqueuevaluetype"></a><a name="priority_queue__value_type"></a>  priority_queue::value_type  
 Тип, представляющий тип объекта, сохраненный как элемент в priority_queue.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `value_type` адаптировать путем priority_queue базового контейнера.  
  
### <a name="example"></a>Пример  
  
```  
// pqueue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   priority_queue<int> q1;  
   q1.push( AnInt );  
   cout << "The element at the top of the priority_queue is "  
        << q1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the priority_queue is 69.  
```  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)

