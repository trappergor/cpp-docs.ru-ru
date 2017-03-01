---
title: "Класс deque | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.deque
- deque
- std::deque
- deque/std::deque
dev_langs:
- C++
helpviewer_keywords:
- deque class, about deque class
- deque class
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
caps.latest.revision: 22
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 804c10035a7c304a631c3afc30a0ca32c02f90c2
ms.lasthandoff: 02/24/2017

---
# <a name="deque-class"></a>Класс deque
Упорядочивает элементы заданного типа в линейном порядке и, подобно векторам, обеспечивает быстрый произвольный доступ к любому элементу и эффективную вставку и удаление в конце контейнера. Однако в отличие от объекта vector класс `deque` также поддерживает эффективную вставку и удаление в передней части контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```unstlib  
template <class Type, class Allocator =allocator<Type>>  
class deque  
```  
  
#### <a name="parameters"></a>Параметры  
 `Type`  
 Тип данных элементов, сохраняемых в объекте deque.  
  
 `Allocator`  
 Тип, представляющий сохраненный объект распределителя, содержащий сведения о распределении и отмене распределения памяти для deque. Этот аргумент является необязательным. Значение по умолчанию — **allocator\<Type>***.*  
  
## <a name="remarks"></a>Примечания  
 Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. [Векторы](../standard-library/vector-class.md) должны быть предпочитаемыми контейнерами для управления последовательностями, когда важен произвольный доступ к любому элементу, а вставка и удаление элементов требуется лишь в конце последовательности. Производительность контейнера list выше, если эффективные вставки и удаления (в константном времени) в любом расположении в последовательности имеют больший приоритет. Таким операциям в середине последовательности требуются копии элементов и присвоения, пропорциональные количеству элементов в последовательности (линейное время).  
  
 Перераспределение объекта deque происходит, когда функция-член должна вставить или удалить элементы последовательности:  
  
-   Если элемент вставляется в пустую последовательность или элемент удаляется, чтобы оставить после себя пустую последовательность, то итераторы, ранее возвращенные [begin](#deque__begin) и [end](#deque__end), становятся недействительными.  
  
-   Если элемент вставляется в первую позицию deque, то все итераторы, но не ссылки, которые определяют существующие элементы, становятся недействительными.  
  
-   Если элемент вставляется в последнюю позицию очереди, то [end](#deque__end) и все итераторы, но не ссылки, которые определяют существующие элементы, становятся недействительными.  
  
-   Если элемент удаляется в передней части объекта deque, только этот итератор и ссылки на удаленный элемент становятся недействительными.  
  
-   Если последний элемент удаляется из конца объекта deque, только этот итератор последнего элемента и ссылки на удаленный элемент становятся недействительными.  
  
 В противном случае вставка или удаление элемента делает недействительными все итераторы и ссылки.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[deque](#deque__deque)|Создает `deque.`. Предоставляются несколько конструкторов, позволяющих настроить содержимое нового объекта `deque` различными способами: он может быть пустым, содержать указанное число пустых элементов, переместить или скопировать содержимое из другого объекта `deque`, скопировать или переместить содержимое с помощью итератора или скопировать один элемент в `deque`` count` раз. Некоторые конструкторы позволяют использовать настраиваемый `allocator` для создания элементов.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#deque__allocator_type)|Тип, представляющий класс `allocator` для объекта `deque`.|  
|[const_iterator](#deque__const_iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать элементы в `deque` как `const` и обращаться к ним.|  
|[const_pointer](#deque__const_pointer)|Тип, предоставляющий указатель на элемент в `deque` как `const.`.|  
|[const_reference](#deque__const_reference)|Тип, предоставляющий ссылку на элемент в `deque` для считывания и выполнения других операций в качестве `const.`.|  
|[const_reverse_iterator](#deque__const_reverse_iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать элементы в `deque` как `const` и обращаться к ним. Объект deque просматривается в обратном порядке. Дополнительные сведения см. в статье [Класс reverse_iterator](../standard-library/reverse-iterator-class.md).|  
|[difference_type](#deque__difference_type)|Тип, предоставляющий разницу между двумя итераторами произвольного доступа, ссылающимися на элементы в одном и том же `deque`.|  
|[iterator](#deque__iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать или изменять любой элемент в `deque`.|  
|[pointer](#deque__pointer)|Тип, предоставляющий указатель на элемент в `deque`.|  
|[reference](#deque__reference)|Тип, предоставляющий ссылку на элемент, хранящийся в контейнере `deque`.|  
|[reverse_iterator](#deque__reverse_iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать или изменять элемент в `deque`. Объект deque просматривается в обратном порядке.|  
|[size_type](#deque__size_type)|Тип, считающий количество элементов в `deque`.|  
|[value_type](#deque__value_type)|Тип, который представляет тип данных, хранящийся в контейнере `deque`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[assign](#deque__assign)|Удаляет элементы из `deque` и копирует новую последовательность элементов в целевой объект `deque`.|  
|[at](#deque__at)|Возвращает ссылку на элемент в заданном положении в `deque`.|  
|[back](#deque__back)|Возвращает ссылку на последний элемент в `deque`.|  
|[begin](#deque__begin)|Возвращает итератор произвольного доступа, указывающий на первый элемент в `deque`.|  
|[cbegin](#deque__cbegin)|Возвращает константный итератор, который указывает на первый элемент в `deque`.|  
|[cend](#deque__cend)|Возвращает итератор `const` произвольного доступа, который указывает на позицию, следующую за концом `deque`.|  
|[clear](#deque__clear)|Стирает все элементы в `deque`.|  
|[crbegin](#deque__crbegin)|Возвращает константный итератор произвольного доступа, указывающий на первый элемент в `deque`, просматриваемый в обратном порядке.|  
|[crend](#deque__crend)|Возвращает константный итератор произвольного доступа, указывающий на первый элемент в `deque`, просматриваемый в обратном порядке.|  
|[emplace](#deque__emplace)|Вставляет элемент, созданный на месте, в указанное положение в `deque`.|  
|[emplace_back](#deque__emplace_back)|Добавляет элемент, созданный на месте, в конец `deque`.|  
|[emplace_front](#deque__emplace_front)|Добавляет элемент, созданный на месте, в начало `deque`.|  
|[empty](#deque__empty)|Возвращает `true`, если `deque` не содержит элементов, и `false`, если он содержит один или несколько элементов.|  
|[end](#deque__end)|Возвращает итератор произвольного доступа, который указывает на позицию, следующую за концом `deque`.|  
|[erase](#deque__erase)|Удаляет элемент или диапазон элементов с указанных позиций в `deque`.|  
|[front](#deque__front)|Возвращает ссылку на первый элемент в `deque`.|  
|[get_allocator](#deque__get_allocator)|Возвращает копию объекта `allocator`, который используется для создания `deque`.|  
|[insert](#deque__insert)|Вставляет элемент, несколько элементов или диапазон элементов в `deque` в заданной позиции.|  
|[max_size](#deque__max_size)|Возвращает максимально возможную длину `deque`.|  
|[pop_back](#deque__pop_back)|Удаляет элемент в конце `deque`.|  
|[pop_front](#deque__pop_front)|Удаляет элемент в начале `deque`.|  
|[push_back](#deque__push_back)|Добавляет элемент в конец `deque`.|  
|[push_front](#deque__push_front)|Добавляет элемент в начало `deque`.|  
|[rbegin](#deque__rbegin)|Возвращает итератор произвольного доступа, указывающий на первый элемент в обратном `deque`.|  
|[rend](#deque__rend)|Возвращает итератор произвольного доступа, указывающий на расположение после последнего элемента в обратном `deque`.|  
|[resize](#deque__resize)|Указывает новый размер `deque`.|  
|[shrink_to_fit](#deque__shrink_to_fit)|Удаляет лишнюю емкость.|  
|[size](#deque__size)|Возвращает количество элементов в контейнере `deque`.|  
|[swap](#deque__swap)|Выполняет обмен элементами между двумя объектами `deque`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор&#91;&#93;](#deque__operator_at)|Возвращает ссылку на элемент `deque` в указанной позиции.|  
|[оператор=](#deque__operator_eq)|Заменяет элементы `deque` копией другого `deque`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<deque>  
  
##  <a name="a-namedequeallocatortypea--dequeallocatortype"></a><a name="deque__allocator_type"></a>  deque::allocator_type  
 Тип, представляющий класс allocator для объекта deque.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Примечания  
 **allocator_type** — синоним параметра шаблона **Allocator**.  
  
### <a name="example"></a>Пример  
  См. пример для [get_allocator](#deque__get_allocator).  
  
##  <a name="a-namedequeassigna--dequeassign"></a><a name="deque__assign"></a>  deque::assign  
 Удаляет элементы из очереди и копирует новый набор элементов в целевую очередь.  
  
```  
template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);

void assign(
    size_type Count,  
    const Type& Val);

void assign(initializer_list<Type> IList);
```  
  
### <a name="parameters"></a>Параметры  
 `First`  
 Положение первого элемента в диапазоне элементов, копируемых из очереди аргументов.  
  
 `Last`  
 Положение первого элемента за пределами диапазона элементов, копируемых из очереди аргументов.  
  
 `Count`  
 Количество копий элемента, вставляемых в очередь.  
  
 `Val`  
 Значение элемента, вставляемого в очередь.  
  
 `IList`  
 Объект initializer_list, вставляемый в очередь.  
  
### <a name="remarks"></a>Примечания  
 После удаления любых существующих элементов в целевой очереди `assign` либо вставляет указанный диапазон элементов из исходной очереди или какой-либо другой очереди в целевую очередь, либо вставляет копии нового элемента указанного значения в целевую очередь.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_assign.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <initializer_list>  
  
int main()  
{  
    using namespace std;  
    deque <int> c1, c2;  
    deque <int>::const_iterator cIter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    deque<int> d1{ 1, 2, 3, 4 };  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    d1.assign(iList);  
  
    cout << "d1 = ";  
    for (int i : d1)  
        cout << i;  
    cout << endl;  
  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(++c2.begin(), c2.end());  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(7, 4);  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
}  
  
```  
  
```Output  
d1 = 5678c1 =102030c1 =5060c1 =4444444  
```  
  
##  <a name="a-namedequeata--dequeat"></a><a name="deque__at"></a>  deque::at  
 Возвращает ссылку на элемент в заданном положении в очереди.  
  
```  
reference at(size_type pos);

const_reference at(size_type pos) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Нижний индекс (или номер позиции) элемента, на который включается ссылка в очереди.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `pos` больше размера очереди, **at** вызывает исключение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение **at** присвоено `const_reference`, то объект очереди нельзя изменить. Если возвращаемое значение **at** присвоено объекту **reference**, то объект очереди можно изменить.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_at.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int& i = c1.at( 0 );  
   int& j = c1.at( 1 );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequebacka--dequeback"></a><a name="deque__back"></a>  deque::back  
 Возвращает ссылку на последний элемент очереди.  
  
```  
reference back();
const_reference back() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последний элемент очереди. Если очередь пуста, возвращаемое значение не определено.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение **back** назначается `const_reference`, то объект очереди невозможно изменить. Если возвращаемое значение **back** назначается объекту **reference**, то объект очереди можно изменить.  
  
 При компиляции с помощью [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), для которого задано значение 1 или 2, возникнет ошибка времени выполнения при попытке доступа к элементу в пустой очереди.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.back( );  
   const int& ii = c1.front( );  
  
   cout << "The last integer of c1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The last integer of c1 is 11  
The next-to-last integer of c1 is 10  
```  
  
##  <a name="a-namedequebegina--dequebegin"></a><a name="deque__begin"></a>  deque::begin  
 Возвращает итератор, адресующий первый элемент в очереди.  
  
```  
const_iterator begin() const;
iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор произвольного доступа, адресующий первый элемент в очереди или расположение после пустой очереди.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение **begin** назначается `const_iterator`, то объект очереди невозможно изменить. Если возвращаемое значение **begin** назначается объекту **iterator**, то объект очереди можно изменить.  
  
### <a name="example"></a>Пример  
  
```cpp  
// deque_begin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::const_iterator c1_cIter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is " << *c1_Iter << endl;  
  
 *c1_Iter = 20;  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is now " << *c1_Iter << endl;  
  
   // The following line would be an error because iterator is const  
   // *c1_cIter = 200;  
}  
```  
  
```Output  
The first element of c1 is 1  
The first element of c1 is now 20  
```  
  
##  <a name="a-namedequecbegina--dequecbegin"></a><a name="deque__cbegin"></a>  deque::cbegin  
 Возвращает итератор `const`, направленный на первый элемент в диапазоне.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор случайного доступа `const`, который указывает на первый элемент диапазона или расположение прямо за концом пустого диапазона (`cbegin() == cend()` для пустого диапазона).  
  
### <a name="remarks"></a>Примечания  
 Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.  
  
 Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере предположим, что `Container` является изменяемым контейнером (не `const`) любого типа, который поддерживает `begin()` и `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namedequecenda--dequecend"></a><a name="deque__cend"></a>  deque::cend  
 Возвращает итератор `const`, который обращается к месту, следующему сразу за последним элементом в диапазоне.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор произвольного доступа, который указывает на место сразу после конца диапазона.  
  
### <a name="remarks"></a>Примечания  
 `cend` используется для проверки того, прошел ли итератор конец диапазона.  
  
 Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере предположим, что `Container` является изменяемым контейнером (не `const`) любого типа, который поддерживает `end()` и `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.  
  
##  <a name="a-namedequecleara--dequeclear"></a><a name="deque__clear"></a>  deque::clear  
 Стирает все элементы в очереди.  
  
```  
void clear();
```  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_clear.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "The size of the deque is initially " << c1.size( ) << endl;  
   c1.clear( );  
   cout << "The size of the deque after clearing is " << c1.size( ) << endl;  
}  
```  
  
```Output  
The size of the deque is initially 3  
The size of the deque after clearing is 0  
```  
  
##  <a name="a-namedequeconstiteratora--dequeconstiterator"></a><a name="deque__const_iterator"></a>  deque::const_iterator  
 Тип, предоставляющий итератор произвольного доступа, который может читать элемент **const** в очереди.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_iterator`нельзя использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  См. пример для [back](#deque__back).  
  
##  <a name="a-namedequeconstpointera--dequeconstpointer"></a><a name="deque__const_pointer"></a>  deque::const_pointer  
 Предоставляет указатель на элемент `const` в очереди.  
  
```
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_pointer`нельзя использовать для изменения значения элемента. Для доступа к элементу очереди чаще используется [iterator](#deque__iterator).  
  
##  <a name="a-namedequeconstreferencea--dequeconstreference"></a><a name="deque__const_reference"></a>  deque::const_reference  
 Тип, предоставляющий ссылку на элемент **const**, хранящийся в очереди, для чтения и выполнения операций **const**.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_reference`нельзя использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  
```cpp  
// deque_const_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const deque <int> c2 = c1;  
   const int &i = c2.front( );  
   const int &j = c2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error as c2 is const  
   // c2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequeconstreverseiteratora--dequeconstreverseiterator"></a><a name="deque__const_reverse_iterator"></a>  deque::const_reverse_iterator  
 Тип, предоставляющий итератор произвольного доступа, который может читать любой элемент **const** в очереди.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_reverse_iterator` не может изменять значение элемента и используется для последовательного прохождения через очередь в обратную сторону.  
  
### <a name="example"></a>Пример  
  См. пример объявления и использования итератора в разделе [rbegin](#deque__rbegin).  
  
##  <a name="a-namedequecrbegina--dequecrbegin"></a><a name="deque__crbegin"></a>  deque::crbegin  
 Возвращает константный итератор первому элементу в очереди в обратную сторону.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный обратный итератор произвольного доступа, указывающий на первый элемент в обращенном объекте [deque](../standard-library/deque-class.md) или на элемент, который был последним в `deque` до обращения.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `crbegin`, то объект `deque` невозможно изменить.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_crbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator v1_Iter;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of deque is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed deque is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of deque is 1.  
The first element of the reversed deque is 2.  
```  
  
##  <a name="a-namedequecrenda--dequecrend"></a><a name="deque__crend"></a>  deque::crend  
 Возвращает константный итератор, который указывает на расположение после последнего элемента в очереди в обратную сторону.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный обратный итератор произвольного доступа, адресующий расположение после последнего элемента в обращенном объекте [deque](../standard-library/deque-class.md) (расположение перед первым элементом в необращенной очереди).  
  
### <a name="remarks"></a>Примечания  
 `crend` используется с обращенной `deque` точно так же, как [array::cend](../standard-library/array-class-stl.md#array__cend) используется с `deque`.  
  
 Если возвращается значение `crend` (соответственно уменьшенное), объект `deque` изменить нельзя.  
  
 `crend` можно использовать, чтобы проверить, достиг ли обратный итератор конца очереди.  
  
 Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_crend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="a-namedequedequea--dequedeque"></a><a name="deque__deque"></a>  deque::deque  
 Создает очередь определенного размера или с элементами определенного значения, или с определенным распределителем, или в качестве копии какой-либо другой очереди или ее части.  
  
```  
deque();

explicit deque(const Allocator& Al);
explicit deque(size_type Count);
deque(size_type Count, const Type& Val);

deque(
    size_type Count,  
    const Type& Val,  
    const Allocator& Al);

deque(const deque& Right);

template <class InputIterator>  
deque(InputIterator First,  InputIterator Last);

template <class InputIterator>  
deque(
   InputIterator First,  
   InputIterator Last,  
   const Allocator& Al);

deque(initializer_list<value_type> IList, const Allocator& Al);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Al`|Класс распределителя для использования с данным объектом.|  
|`Count`|Количество элементов в создаваемой очереди.|  
|`Val`|Значение элементов в создаваемой очереди.|  
|`Right`|Очередь, для которой создаваемая очередь станет копией.|  
|`First`|Положение первого элемента в диапазоне копируемых элементов.|  
|`Last`|Положение первого элемента за пределами диапазона копируемых элементов.|  
|`IList`|Копируемый initializer_list.|  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы хранят объект распределителя (`Al`) и инициализируют очередь.  
  
 Первые два конструктора указывают пустую начальную очередь, второй указывает тип распределителя (`_Al`), который следует использовать.  
  
 Третий конструктор задает повторение указанного числа (` count`) элементов со значением по умолчанию для класса `Type`.  
  
 Четвертый и пятый конструкторы указывают повторение (`Count`) элементов со значением ` val`.  
  
 Шестой конструктор задает копию очереди `Right`.  
  
 Седьмой и восьмой конструкторы копируют диапазон `[First, Last)` очереди.  
  
 Седьмой конструктор перемещает очередь `Right`.  
  
 Восьмой конструктор копирует содержимое initializer_list.  
  
 Ни один из конструкторов не выполняет промежуточные перераспределения.  
  
### <a name="example"></a>Пример  
  
```cpp 
/ compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <forward_list>  
  
int main()  
{  
    using namespace std;  
  
    forward_list<int> f1{ 1, 2, 3, 4 };  
  
    f1.insert_after(f1.begin(), { 5, 6, 7, 8 });  
  
    deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1(3);  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2(5, 2);  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3(3, 1, c2.get_allocator());  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4(c2);  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5(c4.begin(), c4_Iter);  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c6(c4.begin(), c4_Iter, c2.get_allocator());  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for (int i : c1)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for (int i : c2)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for (int i : c3)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for (int i : c4)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for (int i : c5)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for (int i : c6)  
        cout << i << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7(move(c6));  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =";  
    for (int i : c7)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    for (int i : c9)  
        cout << i << " ";  
    cout << endl;  
  
    int x = 3;  
}  
// deque_deque.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
    using namespace std;  
   deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1( 3 );  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2( 5, 2 );  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3( 3, 1, c2.get_allocator( ) );  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4( c2 );  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin( );  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5( c4.begin( ), c4_Iter );  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin( );  
   c4_Iter++;  
   c4_Iter++;  
   c4_Iter++;  
   deque <int> c6( c4.begin( ), c4_Iter, c2.get_allocator( ) );  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
        initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
        cout << *c1_Iter << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
        cout << *c2_Iter << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
        cout << *c3_Iter << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for ( c4_Iter = c4.begin( ); c4_Iter != c4.end( ); c4_Iter++ )  
        cout << *c4_Iter << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for ( c5_Iter = c5.begin( ); c5_Iter != c5.end( ); c5_Iter++ )  
        cout << *c5_Iter << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for ( c6_Iter = c6.begin( ); c6_Iter != c6.end( ); c6_Iter++ )  
        cout << *c6_Iter << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7( move(c6) );  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =" ;  
    for ( c7_Iter = c7.begin( ) ; c7_Iter != c7.end( ) ; c7_Iter++ )  
        cout << " " << *c7_Iter;  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    or (int i : c9)  
        cout << i << " ";  
    cout << endl;  
}  
```  
  
##  <a name="a-namedequedifferencetypea--dequedifferencetype"></a><a name="deque__difference_type"></a>  deque::difference_type  
 Тип, предоставляющий разницу между двумя итераторами, ссылающимися на элементы в одной и той же очереди.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `difference_type` также можно описать как число элементов между двумя указателями.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <deque>  
#include <algorithm>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
   deque <int>::difference_type df_typ1, df_typ2, df_typ3;  
  
   df_typ1 = count( c1_Iter, c2_Iter, 10 );  
   df_typ2 = count( c1_Iter, c2_Iter, 20 );  
   df_typ3 = count( c1_Iter, c2_Iter, 30 );  
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";  
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";  
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";  
}  
```  
  
```Output  
The number '10' is in c1 collection 1 times.  
The number '20' is in c1 collection 2 times.  
The number '30' is in c1 collection 3 times.  
```  
  
##  <a name="a-namedequeemplacea--dequeemplace"></a><a name="deque__emplace"></a>  deque::emplace  
 Вставляет элемент, созданный на месте, в указанное положение в очереди.  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`_Where`|Позиция в объекте [deque](../standard-library/deque-class.md), куда вставляется первый элемент.|  
|` val`|Значение элемента, вставляемого в `deque`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция возвращает итератор, указывающий на положение вставки нового элемента в очередь.  
  
### <a name="remarks"></a>Примечания  
 Любая операция вставки может быть ресурсоемкой. Факторы производительности при работе с объектом `deque` рассматриваются в разделе `deque`.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_emplace.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
vv1[0] = 10 20 30  
```  
  
##  <a name="a-namedequeemplacebacka--dequeemplaceback"></a><a name="deque__emplace_back"></a>  deque::emplace_back  
 Добавляет элемент, созданный на месте, в конец очереди.  
  
```  
void emplace_back(Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` val`|Элемент, добавляемый в конец объекта [deque](../standard-library/deque-class.md).|  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_emplace_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_back( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemplacefronta--dequeemplacefront"></a><a name="deque__emplace_front"></a>  deque::emplace_front  
 Добавляет элемент, созданный на месте, в конец очереди.  
  
```  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` val`|Элемент, добавляемый в начало объекта [deque](../standard-library/deque-class.md).|  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_emplace_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_front( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemptya--dequeempty"></a><a name="deque__empty"></a>  deque::empty  
 Проверяет, пуста ли очередь.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если очередь пуста; **false**, если очередь не пуста.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_empty.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   if ( c1.empty( ) )  
      cout << "The deque is empty." << endl;  
   else  
      cout << "The deque is not empty." << endl;  
}  
```  
  
```Output  
The deque is not empty.  
```  
  
##  <a name="a-namedequeenda--dequeend"></a><a name="deque__end"></a>  deque::end  
 Возвращает итератор, адресующий расположение за последним элементом в очереди.  
  
```  
const_iterator end() const;

iterator end();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает итератор произвольного доступа, адресующий расположение за последним элементом в очереди. Если очередь пуста, то deque::end == deque::begin.  
  
### <a name="remarks"></a>Примечания  
 **end** используется, чтобы проверить, достиг ли итератор конца очереди.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_end.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_Iter = c1.end( );  
   c1_Iter--;  
   cout << "The last integer of c1 is " << *c1_Iter << endl;  
  
   c1_Iter--;  
 *c1_Iter = 400;  
   cout << "The new next-to-last integer of c1 is " << *c1_Iter << endl;  
  
   // If a const iterator had been declared instead with the line:  
   // deque <int>::const_iterator c1_Iter;  
   // an error would have resulted when inserting the 400  
  
   cout << "The deque is now:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
}  
```  
  
```Output  
The last integer of c1 is 30  
The new next-to-last integer of c1 is 400  
The deque is now: 10 400 30  
```  
  
##  <a name="a-namedequeerasea--dequeerase"></a><a name="deque__erase"></a>  deque::erase  
 Удаляет элемент или диапазон элементов с указанных позиций в очереди.  
  
```  
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```  
  
### <a name="parameters"></a>Параметры  
 `_Where`  
 Положение элемента, удаляемого из очереди.  
  
 ` first`  
 Положение первого элемента, удаленного из очереди.  
  
 ` last`  
 Положение после последнего элемента, удаленного из очереди.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор произвольного доступа, указывающий на первый элемент, оставшийся после удаленных элементов, или на указатель конца очереди, если такого элемента не существует.  
  
### <a name="remarks"></a>Примечания  
 **erase** никогда не создает исключений.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_erase.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 40 );  
   c1.push_back( 50 );  
   cout << "The initial deque is: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   c1.erase( c1.begin( ) );  
   cout << "After erasing the first element, the deque becomes:  ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   Iter = c1.begin( );  
   Iter++;  
   c1.erase( Iter, c1.end( ) );  
   cout << "After erasing all elements but the first, deque becomes: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The initial deque is: 10 20 30 40 50   
After erasing the first element, the deque becomes:  20 30 40 50   
After erasing all elements but the first, deque becomes: 20   
```  
  
##  <a name="a-namedequefronta--dequefront"></a><a name="deque__front"></a>  deque::front  
 Возвращает ссылку на первый элемент в очереди.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если очередь пуста, возвращаемое значение не определено.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `front` присвоено `const_reference`, то объект очереди нельзя изменить. Если возвращаемое значение `front` присвоено объекту **reference**, то объект очереди можно изменить.  
  
 При компиляции с помощью [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), для которого задано значение 1 или 2, возникнет ошибка времени выполнения при попытке доступа к элементу в пустой очереди.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.front( );  
   const int& ii = c1.front( );  
  
   cout << "The first integer of c1 is " << i << endl;  
   i++;  
   cout << "The second integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 11  
```  
  
##  <a name="a-namedequegetallocatora--dequegetallocator"></a><a name="deque__get_allocator"></a>  deque::get_allocator  
 Возвращает копию объекта распределителя, использованного для создания очереди.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Распределитель, используемый очередью.  
  
### <a name="remarks"></a>Примечания  
 Распределители для класса очереди определяют, как этот класс управляет хранилищем. Распределителей по умолчанию в классах контейнеров стандартной библиотеки C++ достаточно для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_get_allocator.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects that use the default allocator.  
   deque <int> c1;  
   deque <int, allocator<int> > c2 = deque <int, allocator<int> >( allocator<int>( ) );  
  
   // c3 will use the same allocator class as c1  
   deque <int> c3( c1.get_allocator( ) );  
  
   deque <int>::allocator_type xlst = c1.get_allocator( );  
   // You can now call functions on the allocator class used by c1  
}  
```  
  
##  <a name="a-namedequeinserta--dequeinsert"></a><a name="deque__insert"></a>  deque::insert  
 Вставляет один элемент, несколько элементов или диапазон элементов в указанное положение в очереди.  
  
```  
iterator insert(
    const_iterator Where,  
    const Type& Val);

iterator insert(
    const_iterator Where,  
    Type&& Val);

void insert(
    iterator Where,  
    size_type Count,  
    const Type& Val);

template <class InputIterator>  
void insert(
    iterator Where,  
    InputIterator First,  
    InputIterator Last);

iterator insert(
    iterator Where,initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Where`|Положение в целевой очереди, куда вставляется первый элемент.|  
|`Val`|Значение элемента, вставляемого в очередь.|  
|`Count`|Количество элементов, вставляемых в очередь.|  
|`First`|Положение первого элемента в диапазоне элементов в копируемой очереди аргументов.|  
|`Last`|Положение первого элемента за пределами диапазона элементов в копируемой очереди аргументов.|  
|`IList`|Объект initializer_list, содержащий вставляемые элементы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Две первые функции вставки возвращают итератор, указывающий на положение вставки нового элемента в очередь.  
  
### <a name="remarks"></a>Примечания  
 Любая операция вставки может быть ресурсоемкой.  
  
##  <a name="a-namedequeiteratora--dequeiterator"></a><a name="deque__iterator"></a>  deque::iterator  
 Тип, предоставляющий итератор произвольного доступа, который может читать или изменять любой элемент в очереди.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип **iterator** можно использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  См. пример для [begin](#deque__begin).  
  
##  <a name="a-namedequemaxsizea--dequemaxsize"></a><a name="deque__max_size"></a>  deque::max_size  
 Возвращает максимальную длину очереди.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимально возможная длина очереди.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_max_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   i = c1.max_size( );  
   cout << "The maximum possible length of the deque is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namedequeoperatorata--dequeoperator"></a><a name="deque__operator_at"></a>  deque::operator[]  
 Возвращает ссылку на элемент очереди в указанной позиции.  
  
```  
reference operator[](size_type pos);

const_reference operator[](size_type pos) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Положение элемента очереди, на который должна быть ссылка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент, позиция которого указана в аргументе. Если заданная позиция больше размера очереди, результат не определен.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `operator[]` присвоено `const_reference`, то объект очереди нельзя изменить. Если возвращаемое значение `operator[]` присвоено объекту **reference**, то объект очереди можно изменить.  
  
 При компиляции с помощью [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), для которого задано значение 1 или 2, возникнет ошибка времени выполнения при попытке доступа к элементу за пределами очереди.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_op_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   cout << "The first integer of c1 is " << c1[0] << endl;  
   int& i = c1[1];  
   cout << "The second integer of c1 is " << i << endl;  
  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 20  
```  
  
##  <a name="a-namedequeoperatoreqa--dequeoperator"></a><a name="deque__operator_eq"></a>  deque::operator=  
 Заменяет элементы этой очереди с помощью элементов из другой очереди.  
  
```  
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` right`|Очередь, предоставляющая новое содержимое.|  
  
### <a name="remarks"></a>Примечания  
 Первое переопределение копирует элементы в эту очередь из ` right`, которое является источником назначения. Второе переопределение перемещает элементы в эту очередь из ` right`.  
  
 Элементы, содержащиеся в этой очереди перед выполнением оператора, удаляются.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_operator_as.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
using namespace std;  
  
typedef deque<int> MyDeque;  
  
template<typename MyDeque> struct S;  
  
template<typename MyDeque> struct S<MyDeque&> {  
  static void show( MyDeque& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
    cout << endl;  
  }  
};  
  
template<typename MyDeque> struct S<MyDeque&&> {  
  static void show( MyDeque&& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
cout << " via unnamed rvalue reference " << endl;  
  }  
};  
  
int main( )  
{  
   MyDeque d1, d2;  
  
   d1.push_back(10);  
   d1.push_back(20);  
   d1.push_back(30);  
   d1.push_back(40);  
   d1.push_back(50);  
  
   cout << "d1 = " ;  
   S<MyDeque&>::show( d1 );  
  
   d2 = d1;  
   cout << "d2 = ";  
   S<MyDeque&>::show( d2 );  
  
   cout << "     ";  
   S<MyDeque&&>::show ( move< MyDeque& > (d1) );  
 }  
```  
  
##  <a name="a-namedequepointera--dequepointer"></a><a name="deque__pointer"></a>  deque::pointer  
 Предоставляет указатель на элемент в объекте [deque](../standard-library/deque-class.md).  
  
```unstlib  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип **pointer** можно использовать для изменения значения элемента. Для доступа к элементу очереди чаще используется [iterator](#deque__iterator).  
  
##  <a name="a-namedequepopbacka--dequepopback"></a><a name="deque__pop_back"></a>  deque::pop_back  
 Удаляет элемент в конце очереди.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>Примечания  
 Последний элемент не должен быть пустым. `pop_back` никогда не создает исключений.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_pop_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The last element is: " << c1.back( ) << endl;  
  
   c1.pop_back( );  
   cout << "After deleting the element at the end of the deque, the "  
      "last element is: " << c1.back( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The last element is: 2  
After deleting the element at the end of the deque, the last element is: 1  
```  
  
##  <a name="a-namedequepopfronta--dequepopfront"></a><a name="deque__pop_front"></a>  deque::pop_front  
 Удаляет элемент в начале очереди.  
  
```  
void pop_front();
```  
  
### <a name="remarks"></a>Примечания  
 Первый элемент не должен быть пустым. `pop_front` никогда не создает исключений.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_pop_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The second element is: " << c1.back( ) << endl;  
  
   c1.pop_front( );  
   cout << "After deleting the element at the beginning of the "  
      "deque, the first element is: " << c1.front( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The second element is: 2  
After deleting the element at the beginning of the deque, the first element is: 2  
```  
  
##  <a name="a-namedequepushbacka--dequepushback"></a><a name="deque__push_back"></a>  deque::push_back  
 Добавляет элемент в конец очереди.  
  
```  
void push_back(const Type& val);

void push_back(Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` val`|Элемент, добавляемый в конец очереди.|  
  
### <a name="remarks"></a>Примечания  
 При создании исключения очередь не изменяется, а исключение создается снова.  
  
##  <a name="a-namedequepushfronta--dequepushfront"></a><a name="deque__push_front"></a>  deque::push_front  
 Добавляет элемент в начало очереди.  
  
```  
    void push_front(const Type& val);

void push_front(Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` val`|Элемент, добавляемый в начало очереди.|  
  
### <a name="remarks"></a>Примечания  
 При создании исключения очередь не изменяется, а исключение создается снова.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_push_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_front( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "First element: " << c1.front( ) << endl;  
  
   c1.push_front( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New first element: " << c1.front( ) << endl;  
  
// move initialize a deque of strings  
   deque <string> c2;  
   string str("a");  
  
   c2.push_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
First element: 1  
New first element: 2  
Moved first element: a  
```  
  
##  <a name="a-namedequerbegina--dequerbegin"></a><a name="deque__rbegin"></a>  deque::rbegin  
 Возвращает итератор, указывающий на первый элемент в обращенной очереди.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный итератор произвольного доступа, указывающий на первый элемент в обращенной очереди или на последний элемент в необращенной очереди.  
  
### <a name="remarks"></a>Примечания  
 `rbegin` используется с обращенной очередью точно так же, как [begin](#deque__begin) используется с очередью.  
  
 Если возвращаемое значение `rbegin` присвоено `const_reverse_iterator`, то объект очереди нельзя изменить. Если возвращаемое значение `rbegin` присвоено `reverse_iterator`, то объект очереди можно изменить.  
  
 `rbegin` можно использовать для последовательного прохождения по очереди в обратную сторону.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_rbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
  
   // If the following line had replaced the line above, an error   
   // would have resulted in the line modifying an element   
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rbegin( );  
   cout << "Last element in the deque is " << *c1_rIter << "." << endl;  
  
   cout << "The deque contains the elements: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << "in that order.";  
   cout << endl;  
  
   // rbegin can be used to iterate through a deque in reverse order  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rbegin( );  
 *c1_rIter = 40;  // This would have caused an error if a   
                    // const_reverse iterator had been declared as   
                    // noted above  
   cout << "Last element in deque is now " << *c1_rIter << "." << endl;  
}  
```  
  
```Output  
Last element in the deque is 30.  
The deque contains the elements: 10 20 30 in that order.  
The reversed deque is: 30 20 10   
Last element in deque is now 40.  
```  
  
##  <a name="a-namedequereferencea--dequereference"></a><a name="deque__reference"></a>  deque::reference  
 Тип, предоставляющий ссылку на элемент, хранящийся в очереди.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_reference.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int &i = c1.front( );  
   int &j = c1.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequerenda--dequerend"></a><a name="deque__rend"></a>  deque::rend  
 Возвращает итератор, адресующий расположение после последнего элемента в обращенной очереди.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный итератор произвольного доступа, адресующий расположение после последнего элемента в обращенной очереди (расположение перед первым элементом в необращенной очереди).  
  
### <a name="remarks"></a>Примечания  
 `rend` используется с обращенной очередью точно так же, как [end](#deque__end) используется с очередью.  
  
 Если возвращаемое значение `rend` присвоено `const_reverse_iterator`, то объект очереди нельзя изменить. Если возвращаемое значение `rend` присвоено `reverse_iterator`, то объект очереди можно изменить.  
  
 `rend` можно использовать, чтобы проверить, достиг ли обратный итератор конца очереди.  
  
 Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_rend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
   // If the following line had replaced the line above, an error  
   // would have resulted in the line modifying an element  
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rend( );  
   c1_rIter --; // Decrementing a reverse iterator moves it forward   
                // in the deque (to point to the first element here)  
   cout << "The first element in the deque is: " << *c1_rIter << endl;  
  
   cout << "The deque is: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << endl;  
  
   // rend can be used to test if an iteration is through all of   
   // the elements of a reversed deque  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rend( );  
   c1_rIter--; // Decrementing the reverse iterator moves it backward   
               // in the reversed deque (to the last element here)  
 *c1_rIter = 40; // This modification of the last element would   
                   // have caused an error if a const_reverse   
                   // iterator had been declared (as noted above)  
   cout << "The modified reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The first element in the deque is: 10  
The deque is: 10 20 30   
The reversed deque is: 30 20 10   
The modified reversed deque is: 30 20 40   
```  
  
##  <a name="a-namedequeresizea--dequeresize"></a><a name="deque__resize"></a>  deque::resize  
 Указывает новый размер очереди.  
  
```  
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```  
  
### <a name="parameters"></a>Параметры  
 `_Newsize`  
 Новый размер очереди.  
  
 ` val`  
 Значение новых элементов, добавляемых в очередь, если новый размер больше исходного. Если значение не задано, новым элементам назначается значение по умолчанию для класса.  
  
### <a name="remarks"></a>Примечания  
 Если размер очереди меньше запрошенного размера, `_Newsize`, элементы добавляются в очередь, пока она не достигнет требуемого размера.  
  
 Если размер очереди больше запрошенного размера, ближайшие к концу очереди элементы удаляются, пока размер очереди не станет равным `_Newsize`.  
  
 Если текущий размер очереди совпадает с запрошенным, никакие действия не выполняются.  
  
 [size](#deque__size) — это текущий размер очереди.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_resize.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{   
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1.resize( 4,40 );  
   cout << "The size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is " << c1.back( ) << endl;  
  
   c1.resize( 5 );  
   cout << "The size of c1 is now: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
  
   c1.resize( 2 );  
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
}  
```  
  
```Output  
The size of c1 is: 4  
The value of the last element is 40  
The size of c1 is now: 5  
The value of the last element is now 0  
The reduced size of c1 is: 2  
The value of the last element is now 20  
```  
  
##  <a name="a-namedequereverseiteratora--dequereverseiterator"></a><a name="deque__reverse_iterator"></a>  deque::reverse_iterator  
 Тип, предоставляющий итератор произвольного доступа, который может читать или изменять любой элемент в обращенной очереди.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `reverse_iterator` используется для итерации по очереди.  
  
### <a name="example"></a>Пример  
  См. пример для rbegin.  
  
##  <a name="a-namedequeshrinktofita--dequeshrinktofit"></a><a name="deque__shrink_to_fit"></a>  deque::shrink_to_fit  
 Удаляет лишнюю емкость.  
  
```  
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Примечания  
 Переносимого способа определения, уменьшает ли `shrink_to_fit` хранилище, используемое объектом [deque](../standard-library/deque-class.md), не существует.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_shrink_to_fit.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   //deque <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
   v1.shrink_to_fit();  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
}  
```  
  
```Output  
Current size of v1 = 1  
Current size of v1 = 1  
```  
  
##  <a name="a-namedequesizea--dequesize"></a><a name="deque__size"></a>  deque::size  
 Возвращает число элементов в очереди.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина очереди.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   c1.push_back( 1 );  
   i = c1.size( );  
   cout << "The deque length is " << i << "." << endl;  
  
   c1.push_back( 2 );  
   i = c1.size( );  
   cout << "The deque length is now " << i << "." << endl;  
}  
```  
  
```Output  
The deque length is 1.  
The deque length is now 2.  
```  
  
##  <a name="a-namedequesizetypea--dequesizetype"></a><a name="deque__size_type"></a>  deque::size_type  
 Тип, который подсчитывает количество элементов в очереди.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>Пример  
  См. пример для [size](#deque__size).  
  
##  <a name="a-namedequeswapa--dequeswap"></a><a name="deque__swap"></a>  deque::swap  
 Меняет местами элементы двух объектов deque.  
  
```  
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>  
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Очередь, предоставляющая элементы для обмена местами, или очередь, элементы которой должны быть заменены на элементы очереди ` left`.  
  
 ` left`  
 Очередь, элементы которой должны быть заменены на элементы очереди ` right`.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_swap.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1, c2, c3;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 3 );  
   c2.push_back( 10 );  
   c2.push_back( 20 );  
   c3.push_back( 100 );  
  
   cout << "The original deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.swap( c2 );  
  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap( c1,c3 );  
  
   cout << "After swapping with c3, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap<>(c1, c2);  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The original deque c1 is: 1 2 3  
After swapping with c2, deque c1 is: 10 20  
After swapping with c3, deque c1 is: 100  
After swapping with c2, deque c1 is: 1 2 3  
```  
  
##  <a name="a-namedequevaluetypea--dequevaluetype"></a><a name="deque__value_type"></a>  deque::value_type  
 Тип, представляющий тип данных, хранящихся в очереди.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `value_type` — синоним параметра-шаблона **Type**.  
  
### <a name="example"></a>Пример  
  
```cpp 
// deque_value_type.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
int main( )   
{  
   using namespace std;  
   deque<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)


