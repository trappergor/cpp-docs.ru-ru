---
title: "Класс deque | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.deque"
  - "deque"
  - "std::deque"
  - "deque/std::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс deque, сведения о классе deque"
  - "deque - класс"
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# Класс deque
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Упорядочивает элементы заданного типа в линейном порядке и, подобно векторам, обеспечивает быстрый произвольный доступ к любому элементу и эффективную вставку и удаление в конце контейнера. Однако в отличие от объекта vector класс `deque` также поддерживает эффективную вставку и удаление в передней части контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```unstlib  
template <class Type,   
    class Allocator =allocator<Type>>  
class deque  
```  
  
#### <a name="parameters"></a>Параметры  
 `Type`  
 Тип данных элементов, сохраняемых в объекте deque.  
  
 `Allocator`  
 Тип, представляющий сохраненный объект распределителя, содержащий сведения о распределении и отмене распределения памяти для deque. Этот аргумент является необязательным, и значение по умолчанию — **распределителя \< тип>***.*  
  
## <a name="remarks"></a>Примечания  
 Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. [Векторы](vector%20Class.md) должны быть предпочитаемыми контейнерами для управления последовательностями, когда произвольный доступ к любому элементу крайне ценно и вставку или удаление элементов только необходимые в конце последовательности. Производительность контейнера списка руководителя, когда эффективный вставок и удалений (в постоянном времени) в любом месте последовательности крайне ценно. Таким операциям в середине последовательности требуются копии элементов и присвоения, пропорциональные количеству элементов в последовательности (линейное время).  
  
 Перераспределение объекта deque происходит, когда функция-член должна вставить или удалить элементы последовательности:  
  
-   Если элемент вставляется пустая последовательность, или если элемент удаляется оставить пустую последовательность, затем итераторы ранее, возвращаемый методом [Начать](#deque__begin) и [end](#deque__end) становятся недействительными.  
  
-   Если элемент вставляется в первую позицию deque, то все итераторы, но не ссылки, которые определяют существующие элементы, становятся недействительными.  
  
-   Если элемент вставляется в конце deque, затем [end](#deque__end) и всех итераторов, но нет ссылок, которые обозначают становятся недействительными существующие элементы.  
  
-   Если элемент удаляется в передней части объекта deque, только этот итератор и ссылки на удаленный элемент становятся недействительными.  
  
-   Если последний элемент удаляется из конца объекта deque, только этот итератор последнего элемента и ссылки на удаленный элемент становятся недействительными.  
  
 В противном случае вставка или удаление элемента делает недействительными все итераторы и ссылки.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[deque](#deque__deque)|Создает `deque.` несколько конструкторов, позволяющие настроить содержимое нового `deque` различными способами: пуста; загрузке с указанным количеством пустые элементы; содержимое перемещаемые или копируемые из другого `deque`; содержимое копируется или перемещается с помощью итератора, и один элемент копируется в `deque`` count` раз. Некоторые конструкторы позволяют использовать настраиваемый `allocator` для создания элементов.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#deque__allocator_type)|Тип, представляющий класс `allocator` для объекта `deque`.|  
|[const_iterator](#deque__const_iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать элементы в `deque` как `const` и обращаться к ним.|  
|[const_pointer](#deque__const_pointer)|Тип, предоставляющий указатель на элемент в `deque` как `const.`.|  
|[const_reference](#deque__const_reference)|Тип, предоставляющий ссылку на элемент в `deque` для считывания и выполнения других операций в качестве `const.`.|  
|[const_reverse_iterator](#deque__const_reverse_iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать элементы в `deque` как `const` и обращаться к ним. Объект deque просматривается в обратном порядке. Дополнительные сведения см. в разделе [класс reverse_iterator](../standard-library/reverse-iterator-class.md)|  
|[difference_type](#deque__difference_type)|Тип, предоставляющий разницу между двумя итераторами произвольного доступа, ссылающимися на элементы в одном и том же `deque`.|  
|[итератор](#deque__iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать или изменять любой элемент в `deque`.|  
|[указатель](#deque__pointer)|Тип, предоставляющий указатель на элемент в `deque`.|  
|[ссылка](#deque__reference)|Тип, предоставляющий ссылку на элемент, хранящийся в контейнере `deque`.|  
|[Обратный итератор](#deque__reverse_iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать или изменять элемент в `deque`. Объект deque просматривается в обратном порядке.|  
|[size_type](#deque__size_type)|Тип, считающий количество элементов в `deque`.|  
|[value_type](#deque__value_type)|Тип, который представляет тип данных, хранящийся в контейнере `deque`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[Назначение](#deque__assign)|Удаляет элементы из `deque` и копирует новую последовательность элементов в целевой объект `deque`.|  
|[в](#deque__at)|Возвращает ссылку на элемент в заданном положении в `deque`.|  
|[Назад](#deque__back)|Возвращает ссылку на последний элемент в `deque`.|  
|[начать](#deque__begin)|Возвращает итератор произвольного доступа, указывающий на первый элемент в `deque`.|  
|[deque::cbegin](#deque__cbegin)|Возвращает константный итератор, который указывает на первый элемент в `deque`.|  
|[deque::cend](#deque__cend)|Возвращает итератор `const` произвольного доступа, который указывает на позицию, следующую за концом `deque`.|  
|[Очистка](#deque__clear)|Стирает все элементы в `deque`.|  
|[deque::crbegin](#deque__crbegin)|Возвращает константный итератор произвольного доступа, указывающий на первый элемент в `deque`, просматриваемый в обратном порядке.|  
|[deque::crend](#deque__crend)|Возвращает константный итератор произвольного доступа, указывающий на первый элемент в `deque`, просматриваемый в обратном порядке.|  
|[deque::emplace](#deque__emplace)|Вставляет элемент, созданный на месте, в указанное положение в `deque`.|  
|[deque::emplace_back](#deque__emplace_back)|Добавляет элемент, созданный на месте, в конец `deque`.|  
|[deque::emplace_front](#deque__emplace_front)|Добавляет элемент, созданный на месте, в начало `deque`.|  
|[пустой](#deque__empty)|Возвращает `true`, если `deque` не содержит элементов, и `false`, если он содержит один или несколько элементов.|  
|[конец](#deque__end)|Возвращает итератор произвольного доступа, который указывает на позицию, следующую за концом `deque`.|  
|[Стирание](#deque__erase)|Удаляет элемент или диапазон элементов с указанных позиций в `deque`.|  
|[передний план](#deque__front)|Возвращает ссылку на первый элемент в `deque`.|  
|[get_allocator](#deque__get_allocator)|Возвращает копию объекта `allocator`, который используется для создания `deque`.|  
|[Вставка](#deque__insert)|Вставляет элемент, несколько элементов или диапазон элементов в `deque` в заданной позиции.|  
|[max_size](#deque__max_size)|Возвращает максимально возможную длину `deque`.|  
|[pop_back](#deque__pop_back)|Удаляет элемент в конце `deque`.|  
|[pop_front](#deque__pop_front)|Удаляет элемент в начале `deque`.|  
|[push_back](#deque__push_back)|Добавляет элемент в конец `deque`.|  
|[push_front](#deque__push_front)|Добавляет элемент в начало `deque`.|  
|[rbegin](#deque__rbegin)|Возвращает итератор произвольного доступа, указывающий на первый элемент в обратном `deque`.|  
|[rend](#deque__rend)|Возвращает итератор произвольного доступа, указывающий на расположение после последнего элемента в обратном `deque`.|  
|[Изменение размеров](#deque__resize)|Указывает новый размер `deque`.|  
|[deque::shrink_to_fit](#deque__shrink_to_fit)|Удаляет лишнюю емкость.|  
|[размер](#deque__size)|Возвращает количество элементов в контейнере `deque`.|  
|[Переключение](#deque__swap)|Выполняет обмен элементами между двумя объектами `deque`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор &#91; &#93;](#deque__operator_at)|Возвращает ссылку на элемент `deque` в указанной позиции.|  
|[deque::operator =](#deque__operator_eq)|Заменяет элементы `deque` копией другого `deque`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок**: \< deque>  
  
##  <a name="a-namedequeallocatortypea-dequeallocatortype"></a><a name="deque__allocator_type"></a>  deque::allocator_type  
 Тип, представляющий класс распределителя для объекта deque.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Примечания  
 **allocator_type** является синонимом параметра шаблона **распределителя**.  
  
### <a name="example"></a>Пример  
  В примере показано [get_allocator](#deque__get_allocator).  
  
##  <a name="a-namedequeassigna-dequeassign"></a><a name="deque__assign"></a>  deque::Assign  
 Удаляет элементы из deque и копирует новый набор элементов deque целевой.  
  
```  
template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);

void assign(
    size_type Count,  
    const Type& Val);

void assign(
    initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>Параметры  
 `First`  
 Положение первого элемента в диапазоне элементов для копирования из deque аргумента.  
  
 `Last`  
 Положение первого элемента после диапазона элементов, копируемых из deque аргумента.  
  
 `Count`  
 Количество копий элемента, вставляемого в deque.  
  
 `Val`  
 Значение элемента, вставляемого в deque.  
  
 `IList`  
 Объект initializer_list, вставляемого в deque.  
  
### <a name="remarks"></a>Примечания  
 После удаления всех существующих элементов в целевом deque `assign` либо вставляет указанный диапазон элементов из исходного deque или некоторые другие deque в целевой deque, либо вставляет копии нового элемента с указанным значением в целевой deque.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeata-dequeat"></a><a name="deque__at"></a>  deque::AT  
 Возвращает ссылку на элемент в указанной позиции в deque.  
  
```  
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Pos`  
 Индекс (или позицию) элемента ссылка в deque.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `_Pos` больше, чем размер deque **в** приводит к возникновению исключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение **в** назначается `const_reference`, объект deque не может быть изменен. Если возвращаемое значение **в** назначается **ссылки**, deque объект может быть изменен.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequebacka-dequeback"></a><a name="deque__back"></a>  deque::Back  
 Возвращает ссылку на последний элемент deque.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последний элемент deque. Если deque пуст, возвращаемое значение не определено.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение **обратно** назначается `const_reference`, объект deque не может быть изменен. Если возвращаемое значение **обратно** назначается **ссылки**, deque объект может быть изменен.  
  
 При компиляции с параметром _SECURE_SCL 1 возникнет ошибка времени выполнения, при попытке доступа к элементу в пустой deque.  Дополнительные сведения см. в разделе [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequebegina-dequebegin"></a><a name="deque__begin"></a>  deque::BEGIN  
 Возвращает итератор, обращающийся к первому элементу в deque.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор произвольного доступа, обращающийся к первому элементу в deque или на позицию после пустой deque.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение **Начать** назначается `const_iterator`, объект deque не может быть изменен. Если возвращаемое значение **Начать** назначается **итератор**, deque объект может быть изменен.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequecbegina-dequecbegin"></a><a name="deque__cbegin"></a>  deque::cbegin  
 Возвращает итератор `const`, направленный на первый элемент в диапазоне.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор случайного доступа `const`, который указывает на первый элемент диапазона или расположение прямо за концом пустого диапазона (`cbegin() == cend()` для пустого диапазона).  
  
### <a name="remarks"></a>Примечания  
 Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.  
  
 Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Как правило, он используется в сочетании с [автоматически](../cpp/auto-cpp.md) ключевым словом вывода, типа, как показано в следующем примере. В примере рассмотрим `Container` является изменяемым (отличного от `const`) контейнер для любого типа, который поддерживает `begin()` и `cbegin()`.  
  
```cpp  
 
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namedequecenda-dequecend"></a><a name="deque__cend"></a>  deque::cend  
 Возвращает итератор `const`, который обращается к месту, следующему сразу за последним элементом в диапазоне.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор произвольного доступа, который указывает на место сразу после конца диапазона.  
  
### <a name="remarks"></a>Примечания  
 `cend` используется для проверки того, прошел ли итератор конец диапазона.  
  
 Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Как правило, он используется в сочетании с [автоматически](../cpp/auto-cpp.md) ключевым словом вывода, типа, как показано в следующем примере. В примере рассмотрим `Container` является изменяемым (отличного от `const`) контейнер для любого типа, который поддерживает `end()` и `cend()`.  
  
```cpp  
 
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.  
  
##  <a name="a-namedequecleara-dequeclear"></a><a name="deque__clear"></a>  deque::Clear  
 Удаляет все элементы deque.  
  
```  
void clear();
```  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeconstiteratora-dequeconstiterator"></a><a name="deque__const_iterator"></a>  deque::const_iterator  
 Тип, который предоставляет итератор произвольного доступа, доступ и чтение **const** элемент deque.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_iterator`нельзя использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  В примере показано [обратно](#deque__back).  
  
##  <a name="a-namedequeconstpointera-dequeconstpointer"></a><a name="deque__const_pointer"></a>  deque::const_pointer  
 Предоставляет указатель на `const` элемент deque.  
  
```unstlib  
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_pointer`нельзя использовать для изменения значения элемента.  [Итератор](#deque__iterator) чаще используется для доступа к элементу deque.  
  
##  <a name="a-namedequeconstreferencea-dequeconstreference"></a><a name="deque__const_reference"></a>  deque::const_reference  
 Тип, предоставляющий ссылку на **const** элемент, хранящийся в deque для чтения и выполнения **const** операций.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_reference`нельзя использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeconstreverseiteratora-dequeconstreverseiterator"></a><a name="deque__const_reverse_iterator"></a>  deque::const_reverse_iterator  
 Тип, предоставляющий итератор произвольного доступа, который может читать любой **const** элемент deque.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_reverse_iterator` Невозможно изменить значение элемента и используется для итерации по deque в обратном порядке.  
  
### <a name="example"></a>Пример  
  В примере показано [rbegin](#deque__rbegin) пример того, как объявить и использовать итератор.  
  
##  <a name="a-namedequecrbegina-dequecrbegin"></a><a name="deque__crbegin"></a>  deque::crbegin  
 Возвращает константный итератор на первый элемент в обратном deque.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Постоянный Обратный итератор произвольного доступа, обращающийся к первому элементу в обратном [deque](../standard-library/deque-class.md) или решить, что было последним элементом в необращенном `deque`.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `crbegin`, то объект `deque` невозможно изменить.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequecrenda-dequecrend"></a><a name="deque__crend"></a>  deque::crend  
 Возвращает константный итератор, адресующий расположение после последнего элемента в обратном deque.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Постоянный Обратный итератор произвольного доступа, который обращается к месту, следующему за последним элементом в обратном [deque](../standard-library/deque-class.md) (расположение перед первым элементом в необращенном deque).  
  
### <a name="remarks"></a>Примечания  
 `crend` используется с обратном `deque` так же, как [array::cend](../standard-library/array-class-stl.md#array__cend) используется с `deque`.  
  
 Возвращаемое значение из `crend` (соответственно уменьшенное), `deque` объект не может быть изменен.  
  
 `crend` может использоваться, чтобы проверить, достиг ли Обратный итератор конца его deque.  
  
 Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequedequea-dequedeque"></a><a name="deque__deque"></a>  deque::deque  
 Создает deque определенного размера или с элементами определенного значения, или с определенным распределителем или как копию всех или части некоторых других deque.  
  
```  
deque();

explicit deque(
    const Allocator& Al);

explicit deque(
    size_type Count);

deque(
    size_type Count,  
    const Type& Val);

deque(
    size_type Count,  
    const Type& Val,  
    const Allocator& Al);

deque(
    const deque& Right);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last,  
    const Allocator& Al);

deque(
    initializer_list<value_type>  
IList,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Al`|Класс распределителя для использования с данным объектом.|  
|`Count`|Число элементов в сконструированный deque.|  
|`Val`|Значение элементов в сконструированный deque.|  
|`Right`|Deque, сконструированный deque которого является копией.|  
|`First`|Положение первого элемента в диапазоне копируемых элементов.|  
|`Last`|Положение первого элемента за пределами диапазона копируемых элементов.|  
|`IList`|Объект initializer_list, который необходимо скопировать.|  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы хранят объект распределителя ( `Al`) и инициализировать deque.  
  
 Первые два конструктора определяют пустой исходный deque; Второй контроллер также указывает тип распределителя ( `_Al`) для использования.  
  
 Третий конструктор задает повторение указанного числа ( ` count`) элементов значения по умолчанию для класса `Type`.  
  
 Четвертый и пятый конструкторы указывают повтор ( `Count`) элементов со значением ` val`.  
  
 Шестой конструктор задает копию deque `Right`.  
  
 Седьмой и восьмой конструкторы копируют диапазон `[First, Last)` из deque.  
  
 Седьмой конструктор перемещает deque `Right`.  
  
 Восьмой конструктор копируется initializer_list.  
  
 Ни один из конструкторов не выполняет промежуточные перераспределения.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequedifferencetypea-dequedifferencetype"></a><a name="deque__difference_type"></a>  deque::difference_type  
 Тип, предоставляющий разницу между двумя итераторами, ссылающимися на элементы в одном deque.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `difference_type` также можно описать как число элементов между двумя указателями.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeemplacea-dequeemplace"></a><a name="deque__emplace"></a>  deque::emplace  
 Вставляет элемент, созданный на месте в deque в заданной позиции.  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`_Where`|Позиция в [deque](../standard-library/deque-class.md) куда вставляется первый элемент.|  
|` val`|Значение элемента, вставляемого в `deque`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция возвращает итератор, который указывает на позицию, где был вставлен новый элемент deque.  
  
### <a name="remarks"></a>Примечания  
 Любая операция вставки может быть дорогостоящей см. в разделе `deque` обсуждение `deque` производительности.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeemplacebacka-dequeemplaceback"></a><a name="deque__emplace_back"></a>  deque::emplace_back  
 Добавляет элемент, созданный на месте в конец deque.  
  
```  
void emplace_back(Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` val`|Элемент, добавляемый в конец [deque](../standard-library/deque-class.md).|  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeemplacefronta-dequeemplacefront"></a><a name="deque__emplace_front"></a>  deque::emplace_front  
 Добавляет элемент, созданный на месте в конец deque.  
  
```  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` val`|Элемент, добавляемый в начало [deque](../standard-library/deque-class.md).|  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeemptya-dequeempty"></a><a name="deque__empty"></a>  deque::Empty  
 Проверяет deque пуст.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если deque пуст; **false** Если deque не пуст.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeenda-dequeend"></a><a name="deque__end"></a>  deque::End  
 Возвращает итератор, адресующий расположение после последнего элемента в deque.  
  
```  
const_iterator end() const;

iterator end();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор произвольного доступа, который обращается к месту, следующему за последним элементом в deque. Если deque является пустым, то deque::end == deque::begin.  
  
### <a name="remarks"></a>Примечания  
 **конец** используется для проверки необходимости итератор достигло конца его deque.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeerasea-dequeerase"></a><a name="deque__erase"></a>  deque::Erase  
 Удаляет элемент или диапазон элементов в deque из заданных позиций.  
  
```  
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```  
  
### <a name="parameters"></a>Параметры  
 `_Where`  
 Положение элемента, удаляемого из deque.  
  
 ` first`  
 Положение первого элемента, удаляемого из deque.  
  
 ` last`  
 Положение после последнего элемента, удаляемого из deque.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор произвольного доступа, который обозначает первый элемент, оставшийся после удаленных элементов или указатель в конец deque, если такого элемента не существует.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о **стереть**, в разделе [deque::erase и deque::clear](../misc/deque-erase-and-deque-clear.md).  
  
 **стереть** никогда не создает исключение.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequefronta-dequefront"></a><a name="deque__front"></a>  deque::Front  
 Возвращает ссылку на первый элемент в deque.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если deque пуст, возвращаемое значение не определено.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `front` назначается `const_reference`, объект deque не может быть изменен. Если возвращаемое значение `front` назначается **ссылки**, deque объект может быть изменен.  
  
 При компиляции с параметром _SECURE_SCL 1 возникнет ошибка времени выполнения, при попытке доступа к элементу в пустой deque.  Дополнительные сведения см. в разделе [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequegetallocatora-dequegetallocator"></a><a name="deque__get_allocator"></a>  deque::get_allocator  
 Возвращает копию объекта распределителя, использованного для создания deque.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Распределитель, используемый deque.  
  
### <a name="remarks"></a>Примечания  
 Распределители для класса deque определяют, как класс управляет хранилищем. Для большинства задач программирования достаточно распределителей по умолчанию, доступных вместе с классами контейнеров STL. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeinserta-dequeinsert"></a><a name="deque__insert"></a>  deque::INSERT  
 Вставляет элемент или количество элементов или диапазон элементов в deque в заданной позиции.  
  
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
|`Where`|Позиция в целевой deque, куда вставляется первый элемент.|  
|`Val`|Значение элемента, вставляемого в deque.|  
|`Count`|Число элементов, вставляемых в deque.|  
|`First`|Положение первого элемента в диапазоне элементов массива deque аргумент для копирования.|  
|`Last`|Положение первого элемента после диапазона элементов в deque аргумент для копирования.|  
|`IList`|Initializer_list вставляемые элементы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Две первые функции вставки возвращают итератор, который указывает на позицию, где был вставлен новый элемент deque.  
  
### <a name="remarks"></a>Примечания  
 Любая операция вставки может быть дорогостоящей.  
  
##  <a name="a-namedequeiteratora-dequeiterator"></a><a name="deque__iterator"></a>  deque::iterator  
 Тип, который предоставляет итератор произвольного доступа, который может читать или изменять любой элемент в deque.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип **итератор** можно использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  В примере показано [Начать](#deque__begin).  
  
##  <a name="a-namedequemaxsizea-dequemaxsize"></a><a name="deque__max_size"></a>  deque::max_size  
 Возвращает максимальную длину deque.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимально возможная длина deque.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeoperatorata-dequeoperator"></a><a name="deque__operator_at"></a>  deque::operator]  
 Возвращает ссылку на элемент deque в указанной позиции.  
  
```  
reference operator[](size_type _Pos);

const_reference operator[](size_type _Pos) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Pos`  
 Положение элемента deque ссылаться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент, позиция которого указан в аргументе. Если заданная позиция больше, чем размер deque, результат не определен.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `operator[]` назначается `const_reference`, объект deque не может быть изменен. Если возвращаемое значение `operator[]` назначается **ссылки**, deque объект может быть изменен.  
  
 При компиляции с параметром _SECURE_SCL 1 возникнет ошибка времени выполнения, при попытке доступа к элементу за пределами deque.  Дополнительные сведения см. в разделе [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeoperatoreqa-dequeoperator"></a><a name="deque__operator_eq"></a>  deque::operator =  
 Заменяет элементы этого deque, с помощью элементов из другой deque.  
  
```  
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` right`|Deque, который предоставляет новое содержимое.|  
  
### <a name="remarks"></a>Примечания  
 Первый переопределение копирует элементы из этого deque ` right`, источнике назначения. Второй переопределение перемещение элементов в этом deque из ` right`.  
  
 Элементы, содержащиеся в этом deque перед выполнением оператора, удаляются.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequepointera-dequepointer"></a><a name="deque__pointer"></a>  deque::pointer  
 Предоставляет указатель на элемент в [deque](../standard-library/deque-class.md).  
  
```unstlib  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип **указатель** можно использовать для изменения значения элемента.  [Итератор](#deque__iterator) чаще используется для доступа к элементу deque.  
  
##  <a name="a-namedequepopbacka-dequepopback"></a><a name="deque__pop_back"></a>  deque::pop_back  
 Удаляет элемент в конце deque.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>Примечания  
 Последний элемент не может быть пустым. `pop_back` никогда не создает исключение.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequepopfronta-dequepopfront"></a><a name="deque__pop_front"></a>  deque::pop_front  
 Удаляет элемент в начале deque.  
  
```  
void pop_front();
```  
  
### <a name="remarks"></a>Примечания  
 Первый элемент не может быть пустым. `pop_front` никогда не создает исключение.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequepushbacka-dequepushback"></a><a name="deque__push_back"></a>  deque::push_back  
 Добавляет элемент в конец deque.  
  
```  
void push_back(const Type& val);

void push_back(Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` val`|Элемент, добавляемый в конец deque.|  
  
### <a name="remarks"></a>Примечания  
 Если создается исключение, deque остается без изменений, и создается исключение.  
  
##  <a name="a-namedequepushfronta-dequepushfront"></a><a name="deque__push_front"></a>  deque::push_front  
 Добавляет элемент в начало deque.  
  
```  
    void push_front(const Type& val);

void push_front(Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` val`|Элемент, добавляемый в начало deque.|  
  
### <a name="remarks"></a>Примечания  
 Если создается исключение, deque остается без изменений, и создается исключение.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequerbegina-dequerbegin"></a><a name="deque__rbegin"></a>  deque::rbegin  
 Возвращает итератор на первый элемент в обратном deque.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный итератор произвольного доступа, обращающийся к первому элементу в обратном deque или адресации, что было последним элементом в необращенном deque.  
  
### <a name="remarks"></a>Примечания  
 `rbegin` используется с обратном deque как [Начать](#deque__begin) используется с deque.  
  
 Если возвращаемое значение `rbegin` назначается `const_reverse_iterator`, объект deque не может быть изменен. Если возвращаемое значение `rbegin` назначается `reverse_iterator`, deque объект может быть изменен.  
  
 `rbegin` может использоваться для перебора deque назад.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequereferencea-dequereference"></a><a name="deque__reference"></a>  deque::Reference  
 Тип, предоставляющий ссылку на элемент, хранящийся в deque.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequerenda-dequerend"></a><a name="deque__rend"></a>  deque::rend  
 Возвращает итератор, адресующий расположение после последнего элемента в обратном deque.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный итератор произвольного доступа, который обращается к месту, следующему за последним элементом в обратном deque (расположение перед первым элементом в необращенном deque).  
  
### <a name="remarks"></a>Примечания  
 `rend` используется с обратном deque как [окончания](#deque__end) используется с deque.  
  
 Если возвращаемое значение `rend` назначается `const_reverse_iterator`, объект deque не может быть изменен. Если возвращаемое значение `rend` назначается `reverse_iterator`, deque объект может быть изменен.  
  
 `rend` можно использовать для проверки Обратный итератор достигло конца его deque.  
  
 Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequeresizea-dequeresize"></a><a name="deque__resize"></a>  deque::Resize  
 Размер deque.  
  
```  
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```  
  
### <a name="parameters"></a>Параметры  
 `_Newsize`  
 Новый размер deque.  
  
 ` val`  
 Значение новых элементов, добавляемых deque, если новый размер больше, исходный размер. Если значение задано, новые элементы назначается значение по умолчанию для класса.  
  
### <a name="remarks"></a>Примечания  
 Если размер deque меньше запрошенного размера, `_Newsize`, элементы добавляются к deque, пока достигнет требуемого размера.  
  
 Если запрошенный размер превышает размер deque ближайший к концу deque элементы удаляются, пока не достигнет размера deque `_Newsize`.  
  
 Если текущий размер deque совпадает с запрошенный размер, никакие действия не выполняются.  
  
 [размер](#deque__size) соответствует текущему размеру deque.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequereverseiteratora-dequereverseiterator"></a><a name="deque__reverse_iterator"></a>  deque::reverse_iterator  
 Тип, который предоставляет итератор произвольного доступа, который может читать или изменять любой элемент в обратном deque.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `reverse_iterator` использовать для перебора deque.  
  
### <a name="example"></a>Пример  
  См. пример для rbegin.  
  
##  <a name="a-namedequeshrinktofita-dequeshrinktofit"></a><a name="deque__shrink_to_fit"></a>  deque::shrink_to_fit  
 Удаляет лишнюю емкость.  
  
```  
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Примечания  
 Никоим образом не переносимой ли `shrink_to_fit` уменьшает хранилища, используемый [deque](../standard-library/deque-class.md).  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequesizea-dequesize"></a><a name="deque__size"></a>  deque::size  
 Возвращает количество элементов в deque.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина deque.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequesizetypea-dequesizetype"></a><a name="deque__size_type"></a>  deque::size_type  
 Тип, который подсчитывает число элементов в deque.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>Пример  
  В примере показано [размер](#deque__size).  
  
##  <a name="a-namedequeswapa-dequeswap"></a><a name="deque__swap"></a>  deque::Swap  
 Меняет местами элементы двух объектов deque.  
  
```  
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>  
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Deque, предоставляющий элементы для обмена или deque, элементы которого являются местами с элементами deque ` left`.  
  
 ` left`  
 Deque, элементы которого являются местами с элементами deque ` right`.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namedequevaluetypea-dequevaluetype"></a><a name="deque__value_type"></a>  deque::value_type  
 Тип, представляющий тип данных, хранящихся в deque.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `value_type` является синонимом параметра шаблона **типа**.  
  
### <a name="example"></a>Пример  
  
```  
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
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)

