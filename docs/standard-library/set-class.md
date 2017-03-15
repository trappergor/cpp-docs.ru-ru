---
title: "Класс set | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::set
- set
- set/std::set
- std.set
dev_langs:
- C++
helpviewer_keywords:
- set class
ms.assetid: 8991f9aa-5509-4440-adc1-371512d32018
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
ms.openlocfilehash: b779d47cdcf8d383b415b0412dcc77d8cdc78d7b
ms.lasthandoff: 02/24/2017

---
# <a name="set-class"></a>Класс set
Набор класса контейнеров стандартной библиотеки C++ используется для хранения и извлечения данных из коллекции, в которой значения элементов должны быть уникальными и в которой они служат в качестве значений ключей, согласно которым данные автоматически упорядочиваются. Значение элемента в наборе нельзя изменить напрямую. Вместо этого старые значения необходимо удалить и вставить элементы с новыми значениями.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Key,   
    class Traits=less<Key>,   
    class Allocator=allocator<Key>>  
class set  
```  
  
#### <a name="parameters"></a>Параметры  
 `Key`  
 Тип данных элемента для сохранения в наборе.  
  
 `Traits`  
 Тип, предоставляющий объект функции, который может сравнить два значения элемента как ключи сортировки, чтобы определить их относительный порядок в наборе. Этот аргумент является необязательным, и в качестве значения по умолчанию используется бинарный предикат **less** *\<Key>*.  
  
 В C++&14; вы можете включить разнородный поиск, указав предикат `std::less<>` или `std::greater<>`, не имеющий параметров типа. Дополнительные сведения см. в статье [Разнородный поиск в ассоциативных контейнерах](../standard-library/stl-containers.md#sequence_containers)  
  
 `Allocator`  
 Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для набора. Этот аргумент является необязательным, значение по умолчанию — **allocator***\<Key>.*  
  
## <a name="remarks"></a>Примечания  
 Набор стандартной библиотеки C++ — это:  
  
-   Ассоциативный контейнер, который является контейнером переменного размера, поддерживающим эффективное получение значений элементов на основе значения соответствующего ключа. Кроме того, это простой ассоциативный контейнер, поскольку его значения элементов являются значениями его ключей.  
  
-   Является реверсивным, поскольку предоставляет двунаправленный итератор для получения доступа к его элементам.  
  
-   Сортированный, поскольку его элементы упорядочены по значениям ключей в контейнере в соответствии с заданной функцией сравнения.  
  
-   Является уникальным, поскольку каждый его элемент должен обладать уникальным ключом. Поскольку набор также является простым ассоциативным контейнером, его элементы также являются уникальными.  
  
 Набор также определяют как класс шаблона, поскольку функции, которые он предоставляет, являются универсальными и, соответственно, не зависят от конкретного типа данных, содержащихся в виде элементов. Тип данных, подлежащий использованию, вместо этого определяется как параметры в шаблоне класса вместе с функцией и распределителем сравнения.  
  
 Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. Ассоциативные контейнеры оптимизированы для операций поиска, вставки и удаления. Функции-члены, которые явно поддерживают эти операции, являются эффективными и в среднем выполняют их пропорционально логарифму числа элементов в контейнере. Вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, которые ранее указывали конкретно на удаленные элементы.  
  
 Набор рекомендуется использовать в качестве ассоциативного контейнера, если условия, ассоциирующие значения с ключами, удовлетворяются приложением. Элементы набора являются уникальным и используются в качестве своих собственных ключей сортировки. Модель для этого типа структуры — упорядоченный список, например, ключевых слов, в котором слова не должны повторяться. Если допускается повторное использование слов, то подходящей структурой контейнера будет multiset. Если значения вносятся в список уникальных ключевых слов, сопоставление является подходящей структурой для размещения этих данных. Если же ключи не являются уникальными, предпочтительным контейнером является множественное сопоставление.  
  
 Набор определяет порядок расположения элементов в последовательности, которой он управляет, путем обращения к сохраненному объекту функции типа [key_compare](#set__key_compare). Этот сохраненный объект является функцией сравнения, доступ к которой можно получить путем вызова функции-члена [key_comp](#set__key_comp). В целом, упорядочиваемые элементы должны лишь подлежать сравнению "меньше чем" для установления такого порядка, чтобы, имея любые два элемента, можно было определить, что они равны (ни один не меньше другого) или что один меньше другого. Это приводит к упорядочению неравнозначных элементов. С более технической точки зрения, функция сравнения является бинарным предикатом, который вызывает строгого слабое упорядочение в стандартном математически смысле. Бинарный предикат *f*( *x,y*) является объектом функции, обладающим двумя объектами аргументов *x* и *y* и возвращаемым значением **true** или **false**. Порядок, заданный для набора, является строгим слабым порядком, если бинарный предикат является нерефлексивным, антисимметричным и переходящим и если эквивалентность является переходящей, где два *x* и *y* объекта определяются как эквивалентные, тогда как оба параметра *f*(*x,y*) и *f*(*y,x*) имеют значение false. Если более строгое условие равенства между ключами заменяет условие эквивалентности, порядок становится общим (т.е. все элементы упорядочиваются относительно друг друга), и сопоставленные ключи будут неотличимы друг от друга.  
  
 В C++&14; вы можете включить разнородный поиск, указав предикат `std::less<>` или `std::greater<>`, не имеющий параметров типа. Дополнительные сведения см. в статье [Разнородный поиск в ассоциативных контейнерах](../standard-library/stl-containers.md#sequence_containers)  
  
 Итератор, предоставляемый классом набора, является двусторонним итератором, но функции-члены класса [insert](#set__insert) и [set](#set__set) обладают версиями, принимающими в качестве параметров шаблона более слабый итератор ввода, чьи функциональные требования ниже, чем гарантированные классом двунаправленных итераторов. Различные концепции итераторов образуют семейство, связанное уточнениями функциональности. Каждая концепция итератора имеет собственный набор требований, а алгоритмы, работающие с ними, должны ограничивать свои предположения согласно требованиям, предоставляемым этим типом итератора. Можно предположить, что итератор ввода может быть разыменован для обращения к определенному объекту и инкрементирован до следующего итератора в последовательности. Это минимальный набор функциональных возможностей, но его достаточно, чтобы иметь возможность осмысленно говорить о диапазоне итераторов [ `First`, `Last`) в контексте функций-членов класса.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[set](#set__set)|Создает набор, который является пустым или копией части или целого другого набора.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#set__allocator_type)|Тип, представляющий класс `allocator` для объекта набора.|  
|[const_iterator](#set__const_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать тот или иной элемент `const` в наборе.|  
|[const_pointer](#set__const_pointer)|Тип, предоставляющий указатель на элемент `const` в наборе.|  
|[const_reference](#set__const_reference)|Тип, предоставляющий ссылку на элемент `const`, хранящийся в наборе для чтения и выполнения операций `const`.|  
|[const_reverse_iterator](#set__const_reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать любой элемент `const` в наборе.|  
|[difference_type](#set__difference_type)|Тип целого числа со знаком, пригодный для использования в качестве представления количества элементов в наборе в диапазоне между элементами, на которые указывают итераторы.|  
|[iterator](#set__iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять любой элемент в наборе.|  
|[key_compare](#set__key_compare)|Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в наборе.|  
|[key_type](#set__key_type)|Тип, описывающий объект, сохраненный как элемент набора в смысле его возможностей, присущих ключу сортировки.|  
|[pointer](#set__pointer)|Тип, предоставляющий указатель на элемент в наборе.|  
|[reference](#set__reference)|Тип, предоставляющий ссылку на элемент, хранящийся в наборе.|  
|[reverse_iterator](#set__reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном наборе.|  
|[size_type](#set__size_type)|Тип целого числа без знака, который может представлять число элементов в наборе.|  
|[value_compare](#set__value_compare)|Тип, предоставляющий объект функции, который может сравнить два элемента, чтобы определить их относительный порядок в наборе.|  
|[value_type](#set__value_type)|Тип, описывающий объект, сохраненный как элемент набора в смысле его возможностей, присущих значению.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[begin](#set__begin)|Возвращает итератор, обращающийся к первому элементу в наборе.|  
|[cbegin](#set__cbegin)|Возвращает итератор const, обращающийся к первому элементу в наборе.|  
|[cend](#set__cend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в наборе.|  
|[clear](#set__clear)|Стирает все элементы в наборе.|  
|[count](#set__count)|Возвращает число элементов в наборе, ключи которых соответствуют ключу, заданному параметром.|  
|[crbegin](#set__rbegin)|Возвращает итератор const, который обращается к первому элементу в обращенном наборе.|  
|[crend](#set__rend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном наборе.|  
|[emplace](#set__emplace)|Вставляет созданный на месте элемент в наборе.|  
|[emplace_hint](#set__emplace_hint)|Вставляет созданный на месте элемент в наборе с подсказкой о размещении.|  
|[empty](#set__empty)|Проверяет, пуст ли набор.|  
|[end](#set__end)|Возвращает итератор, который обращается к месту, следующему за последним элементом в наборе.|  
|[equal_range](#set__equal_range)|Возвращает пару итераторов соответственно на первый элемент в наборе с ключом, который больше, чем указанный ключ, и на первый элемент в наборе с ключом, который больше или равен данному ключу.|  
|[erase](#set__erase)|Удаляет элемент или диапазон элементов в наборе с заданных позиций или удаляет элементы, соответствующие заданному ключу.|  
|[find](#set__find)|Возвращает итератор, который обращается к местоположению элемента в наборе с ключом, эквивалентным указанному ключу.|  
|[get_allocator](#set__get_allocator)|Возвращает копию объекта `allocator`, который используется для создания набора.|  
|[insert](#set__insert)|Вставляет элемент или диапазон элементов в набор.|  
|[key_comp](#set__key_comp)|Извлекает копию объекта сравнения, который используется для упорядочивания ключей в наборе.|  
|[lower_bound](#set__lower_bound)|Возвращает итератор, указывающий на первый элемент в наборе с ключом, который больше или равен указанному ключу.|  
|[max_size](#set__max_size)|Возвращает максимальную длину набора.|  
|[rbegin](#set__rbegin)|Возвращает итератор, который обращается к первому элементу в обращенном наборе.|  
|[rend](#set__rend)|Возвращает итератор, который обращается к месту, следующему за последним элементом в обращенном наборе.|  
|[size](#set__size)|Возвращает количество элементов в наборе.|  
|[swap](#set__swap)|Обмен элементами между двумя наборами.|  
|[upper_bound](#set__upper_bound)|Возвращает итератор, указывающий на первый элемент в наборе с ключом, который больше указанного ключа.|  
|[value_comp](#set__value_comp)|Извлекает копию объекта сравнения, который используется для упорядочивания значений элементов в наборе.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[operator=](#set__operator_eq)|Заменяет элементы набора копией другого набора.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<set>  
  
 **Пространство имен:** std  
  
##  <a name="a-namesetallocatortypea--setallocatortype"></a><a name="set__allocator_type"></a>  set::allocator_type  
 Тип, представляющий класс распределителя для объекта-набора.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Примечания  
 **allocator_type** — синоним параметра шаблона [Allocator](../standard-library/set-class.md).  
  
 Возвращает объект-функцию, которую мультинабор использует для упорядочивания своих элементов, который является параметром-шаблоном `Allocator`.  
  
 Дополнительные сведения по `Allocator` см. в подразделе "Примечания" раздела [Класс set](../standard-library/set-class.md).  
  
### <a name="example"></a>Пример  
  Пример использования `allocator_type` см. в примере [get_allocator](#set__get_allocator).  
  
##  <a name="a-namesetbegina--setbegin"></a><a name="set__begin"></a>  set::begin  
 Возвращает итератор, обращающийся к первому элементу в наборе.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Двунаправленный итератор, адресующий первый элемент в наборе или положение после пустого набора.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение **begin** назначается `const_iterator`, то элементы в наборе изменить невозможно. Если возвращаемое значение **begin** назначается **итератору**, то элементы в объекте набора можно изменить.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_begin.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1;  
   set <int>::iterator s1_Iter;  
   set <int>::const_iterator s1_cIter;  
  
   s1.insert( 1 );  
   s1.insert( 2 );  
   s1.insert( 3 );  
  
   s1_Iter = s1.begin( );  
   cout << "The first element of s1 is " << *s1_Iter << endl;  
  
   s1_Iter = s1.begin( );  
   s1.erase( s1_Iter );  
  
   // The following 2 lines would err because the iterator is const  
   // s1_cIter = s1.begin( );  
   // s1.erase( s1_cIter );  
  
   s1_cIter = s1.begin( );  
   cout << "The first element of s1 is now " << *s1_cIter << endl;  
}  
```  
  
```Output  
The first element of s1 is 1  
The first element of s1 is now 2  
```  
  
##  <a name="a-namesetcbegina--setcbegin"></a><a name="set__cbegin"></a>  set::cbegin  
 Возвращает итератор `const`, направленный на первый элемент в диапазоне.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор двунаправленного доступа `const`, который указывает на первый элемент диапазона или расположение прямо за концом пустого диапазона (`cbegin() == cend()` для пустого диапазона).  
  
### <a name="remarks"></a>Примечания  
 Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.  
  
 Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере предположим, что `Container` является изменяемым контейнером (не `const`) любого типа, который поддерживает `begin()` и `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namesetcenda--setcend"></a><a name="set__cend"></a>  set::cend  
 Возвращает итератор `const`, который обращается к месту, следующему сразу за последним элементом в диапазоне.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор двунаправленного доступа `const`, который указывает на позицию сразу за концом диапазона.  
  
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
  
##  <a name="a-namesetcleara--setclear"></a><a name="set__clear"></a>  set::clear  
 Стирает все элементы в наборе.  
  
```  
void clear();
```  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_clear.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   set <int> s1;  
  
   s1.insert( 1 );  
   s1.insert( 2 );  
  
   cout << "The size of the set is initially " << s1.size( )  
        << "." << endl;  
  
   s1.clear( );  
   cout << "The size of the set after clearing is "   
        << s1.size( ) << "." << endl;  
}  
```  
  
```Output  
The size of the set is initially 2.  
The size of the set after clearing is 0.  
```  
  
##  <a name="a-namesetconstiteratora--setconstiterator"></a><a name="set__const_iterator"></a>  set::const_iterator  
 Тип, предоставляющий двунаправленный итератор, который может читать элемент **const** набора.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_iterator`нельзя использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  См. пример для [begin](#set__begin) в качестве примера использования `const_iterator`.  
  
##  <a name="a-namesetconstpointera--setconstpointer"></a><a name="set__const_pointer"></a>  set::const_pointer  
 Тип, предоставляющий указатель на элемент **const** в наборе.  
  
```  
typedef typename allocator_type::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_pointer`нельзя использовать для изменения значения элемента.  
  
 В большинстве случаев [const_iterator](#set__const_iterator) должен использоваться для доступа к элементам в объекте const set.  
  
##  <a name="a-namesetconstreferencea--setconstreference"></a><a name="set__const_reference"></a>  set::const_reference  
 Тип, предоставляющий ссылку на элемент **const**, который хранится в наборе, для чтения и выполнения операций **const**.  
  
```  
typedef typename allocator_type::const_reference const_reference;  
```  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_const_ref.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
  
   // Declare and initialize a const_reference &Ref1   
   // to the 1st element  
   const int &Ref1 = *s1.begin( );  
  
   cout << "The first element in the set is "  
        << Ref1 << "." << endl;  
  
   // The following line would cause an error because the   
   // const_reference cannot be used to modify the set  
   // Ref1 = Ref1 + 5;  
}  
```  
  
```Output  
The first element in the set is 10.  
```  
  
##  <a name="a-namesetconstreverseiteratora--setconstreverseiterator"></a><a name="set__const_reverse_iterator"></a>  set::const_reverse_iterator  
 Тип, предоставляющий двунаправленный итератор, который может считать любой элемент **const** в наборе.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_reverse_iterator` не может изменять значение элемента и используется для перебора набора в обратном порядке.  
  
### <a name="example"></a>Пример  
  См. пример для [rend](#set__rend) в качестве примера объявления и использования `const_reverse_iterator`.  
  
##  <a name="a-namesetcounta--setcount"></a><a name="set__count"></a>  set::count  
 Возвращает число элементов в наборе, ключи которых соответствуют ключу, заданному параметром.  
  
```  
size_type count(const Key& key) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` key`  
 Ключ для сравнения с ключами элементов набора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 1, если набор содержит элемент, ключ сортировки которого совпадает с ключом параметра. 0, если набор не содержит ни одного элемента с совпадающим ключом.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает число элементов в следующем диапазоне:  
  
 [ `lower_bound` (_ *Key* ), `upper_bound` (\_ *Key* ) ).  
  
### <a name="example"></a>Пример  
  В следующем примере иллюстрируется использование функции-члена set::count.  
  
```  
// set_count.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    set<int> s1;  
    set<int>::size_type i;  
  
    s1.insert(1);  
    s1.insert(1);  
  
    // Keys must be unique in set, so duplicates are ignored  
    i = s1.count(1);  
    cout << "The number of elements in s1 with a sort key of 1 is: "  
         << i << "." << endl;  
  
    i = s1.count(2);  
    cout << "The number of elements in s1 with a sort key of 2 is: "  
         << i << "." << endl;  
}  
```  
  
```Output  
The number of elements in s1 with a sort key of 1 is: 1.  
The number of elements in s1 with a sort key of 2 is: 0.  
```  
  
##  <a name="a-namesetcrbegina--setcrbegin"></a><a name="set__crbegin"></a>  set::crbegin  
 Возвращает итератор const, который обращается к первому элементу в обращенном наборе.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный обратный двунаправленный итератор, адресующий первый элемент в обратном наборе или элемент, который был последним элементом в наборе до изменения его порядка на противоположный.  
  
### <a name="remarks"></a>Примечания  
 `crbegin` используется с обратным набором так же, как [begin](#set__begin) используется с обычным набором.  
  
 Если возвращаемое значение `crbegin`, то объект набора изменить невозможно.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_crbegin.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   set <int> s1;  
   set <int>::const_reverse_iterator s1_crIter;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
   s1.insert( 30 );  
  
   s1_crIter = s1.crbegin( );  
   cout << "The first element in the reversed set is "  
        << *s1_crIter << "." << endl;  
}  
```  
  
```Output  
The first element in the reversed set is 30.  
```  
  
##  <a name="a-namesetcrenda--setcrend"></a><a name="set__crend"></a>  set::crend  
 Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном наборе.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный обратный двунаправленный итератор, адресующий расположение после последнего элемента в обратном наборе (расположение перед первым элементом в наборе до изменения его порядка на обратный).  
  
### <a name="remarks"></a>Примечания  
 `crend` используется с обратным набором так же, как [end](#set__end) используется с обычным набором.  
  
 Если возвращаемое значение `crend`, то объект набора изменить невозможно. Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.  
  
 `crend` используется, чтобы проверить, достиг ли обратный итератор конца набора.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_crend.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   set <int> s1;  
   set <int>::const_reverse_iterator s1_crIter;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
   s1.insert( 30 );  
  
   s1_crIter = s1.crend( );  
   s1_crIter--;  
   cout << "The last element in the reversed set is "  
        << *s1_crIter << "." << endl;  
}  
```  
  
##  <a name="a-namesetdifferencetypea--setdifferencetype"></a><a name="set__difference_type"></a>  set::difference_type  
 Тип целого числа со знаком, пригодный для использования в качестве представления количества элементов в наборе в диапазоне между элементами, на которые указывают итераторы.  
  
```  
typedef typename allocator_type::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `difference_type` — тип, возвращаемый при вычитании или приращении через итераторы контейнера. `difference_type` обычно используется для представления количества элементов в диапазоне *[ first, last)* между итераторами ` first` и ` last`, включает элемент, на который указывает ` first`, и диапазон элементов до элемента (но не включая его), на который указывает ` last`.  
  
 Обратите внимание, что хотя `difference_type` доступен для всех итераторов, удовлетворяющих требованиям итератора ввода, что включает класс двунаправленных итераторов, поддерживаемых обратимыми контейнерами, такими как набор, вычитание между итераторами поддерживается лишь итераторами произвольного доступа, предоставляемыми контейнерами произвольного доступа, такими как вектор.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <set>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
  
   set <int> s1;  
   set <int>::iterator s1_Iter, s1_bIter, s1_eIter;  
  
   s1.insert( 20 );  
   s1.insert( 10 );  
   s1.insert( 20 );   // won't insert as set elements are unique  
  
   s1_bIter = s1.begin( );  
   s1_eIter = s1.end( );  
  
   set <int>::difference_type   df_typ5, df_typ10, df_typ20;  
  
   df_typ5 = count( s1_bIter, s1_eIter, 5 );  
   df_typ10 = count( s1_bIter, s1_eIter, 10 );  
   df_typ20 = count( s1_bIter, s1_eIter, 20 );  
  
   // the keys, and hence the elements of a set are unique,  
   // so there is at most one of a given value  
   cout << "The number '5' occurs " << df_typ5  
        << " times in set s1.\n";  
   cout << "The number '10' occurs " << df_typ10  
        << " times in set s1.\n";  
   cout << "The number '20' occurs " << df_typ20  
        << " times in set s1.\n";  
  
   // count the number of elements in a set  
   set <int>::difference_type  df_count = 0;  
   s1_Iter = s1.begin( );  
   while ( s1_Iter != s1_eIter)     
   {  
      df_count++;  
      s1_Iter++;  
   }  
  
   cout << "The number of elements in the set s1 is: "   
        << df_count << "." << endl;  
}  
```  
  
```Output  
The number '5' occurs 0 times in set s1.  
The number '10' occurs 1 times in set s1.  
The number '20' occurs 1 times in set s1.  
The number of elements in the set s1 is: 2.  
```  
  
##  <a name="a-namesetemplacea--setemplace"></a><a name="set__emplace"></a>  set::emplace  
 Вставляет созданный элемент на место (операции копирования или перемещения не выполняются).  
  
```  
template <class... Args>  
pair<iterator, bool>  
emplace(
    Args&&... args);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`args`|Аргументы, передаваемые для создания элемента для вставки в набор, кроме случаев, когда сопоставление уже содержит элемент, значение которого правильным образом упорядочено.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 [Пара](../standard-library/pair-structure.md), чей компонент bool имеет значение true, если вставка была выполнена, и false, если сопоставление уже содержало элемент с эквивалентным значением в порядке. Компонент итератора пары возвращаемых значений возвращает адрес, где был вставлен новый элемент (если компонент bool имеет значение true) или где уже находился элемент (если компонент bool имеет значение false).  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает недействительными никакие итераторы или ссылки.  
  
 Если во время размещения создается исключение, состояние контейнера не изменяется.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_emplace.cpp  
// compile with: /EHsc  
#include <set>  
#include <string>  
#include <iostream>  
  
using namespace std;  
  
template <typename S> void print(const S& s) {  
    cout << s.size() << " elements: ";  
  
    for (const auto& p : s) {  
        cout << "(" << p << ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    set<string> s1;  
  
    auto ret = s1.emplace("ten");  
  
    if (!ret.second){  
        cout << "Emplace failed, element with value \"ten\" already exists."  
            << endl << "  The existing element is (" << *ret.first << ")"  
            << endl;  
        cout << "set not modified" << endl;  
    }  
    else{  
        cout << "set modified, now contains ";  
        print(s1);  
    }  
    cout << endl;  
  
    ret = s1.emplace("ten");  
  
    if (!ret.second){  
        cout << "Emplace failed, element with value \"ten\" already exists."  
            << endl << "  The existing element is (" << *ret.first << ")"  
            << endl;  
    }  
    else{  
        cout << "set modified, now contains ";  
        print(s1);  
    }  
    cout << endl;  
}  
  
```  
  
##  <a name="a-namesetemplacehinta--setemplacehint"></a><a name="set__emplace_hint"></a>  set::emplace_hint  
 Вставляет созданный элемент на место (операции копирования или перемещения не выполняются) с указанием о размещении.  
  
```  
template <class... Args>  
iterator emplace_hint(
    const_iterator where,  
    Args&&... args);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`args`|Аргументы, передаваемые для создания элемента, который будет вставлен в набор, кроме ситуации, когда набор уже содержит этот элемент или, в более общем случае, кроме ситуации, когда набор уже содержит элемент, ключ которого правильно упорядочен.|  
|`where`|Место начала поиска правильной точки вставки. (Если эта точка находится непосредственно перед `where`, вставка может быть выполнена в постоянном времени с поправкой на амортизацию, а не в логарифмическом времени.)|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор на вставленный элемент.  
  
 Если не удалось вставить элемент, так как он уже существует, возвращается итератор на существующий элемент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает недействительными никакие итераторы или ссылки.  
  
 Если во время размещения создается исключение, состояние контейнера не изменяется.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_emplace.cpp  
// compile with: /EHsc  
#include <set>  
#include <string>  
#include <iostream>  
  
using namespace std;  
  
template <typename S> void print(const S& s) {  
    cout << s.size() << " elements: " << endl;  
  
    for (const auto& p : s) {  
        cout << "(" << p <<  ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    set<string> s1;  
  
    // Emplace some test data  
    s1.emplace("Anna");  
    s1.emplace("Bob");  
    s1.emplace("Carmine");  
  
    cout << "set starting data: ";  
    print(s1);  
    cout << endl;  
  
    // Emplace with hint  
    // s1.end() should be the "next" element after this emplacement  
    s1.emplace_hint(s1.end(), "Doug");  
  
    cout << "set modified, now contains ";  
    print(s1);  
    cout << endl;  
}  
  
```  
  
##  <a name="a-namesetemptya--setempty"></a><a name="set__empty"></a>  set::empty  
 Проверяет, пуст ли набор.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если набор пуст; значение **false**, если набор не пуст.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_empty.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2;  
   s1.insert ( 1 );  
  
   if ( s1.empty( ) )  
      cout << "The set s1 is empty." << endl;  
   else  
      cout << "The set s1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The set s2 is empty." << endl;  
   else  
      cout << "The set s2 is not empty." << endl;  
}  
```  
  
```Output  
The set s1 is not empty.  
The set s2 is empty.  
```  
  
##  <a name="a-namesetenda--setend"></a><a name="set__end"></a>  set::end  
 Возврат итератора после конца.  
  
```  
const_iterator end() const;

 
 
iterator end();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор после конца. Если набор пуст, то `set::end() == set::begin()`.  
  
### <a name="remarks"></a>Примечания  
 **end** используется, чтобы проверить, прошел ли итератор за конец набора.  
  
 Не следует сбрасывать ссылку у значения, возвращаемого **end**.  
  
 Пример кода см. в разделе [set::find](#set__find).  
  
##  <a name="a-namesetequalrangea--setequalrange"></a><a name="set__equal_range"></a>  set::equal_range  
 Возвращает пару итераторов соответственно на первый элемент в наборе с ключом, который не меньше, чем указанный ключ, и на первый элемент в наборе с ключом, который больше данного ключа.  
  
```  
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```  
  
### <a name="parameters"></a>Параметры  
 ` key`  
 Ключ-аргумент, который будет сравниваться с ключом сортировки элемента из набора, в котором выполняется поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Пара итераторов, первый из которых — [lower_bound](#set__lower_bound) ключа, а второй — [upper_bound](#set__upper_bound) ключа.  
  
 Для доступа к первому итератору пары `pr`, возвращаемому функцией-членом, используйте `pr`. **first**, а для сброса ссылки на итератор нижней границы — \*( `pr`. **first**). Для доступа ко второму итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **second**, а для сброса ссылки на итератор верхней границы — \*( `pr`. **second**).  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_equal_range.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   typedef set<int, less< int > > IntSet;  
   IntSet s1;  
   set <int, less< int > > :: const_iterator s1_RcIter;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
   s1.insert( 30 );  
  
   pair <IntSet::const_iterator, IntSet::const_iterator> p1, p2;  
   p1 = s1.equal_range( 20 );  
  
   cout << "The upper bound of the element with "  
        << "a key of 20 in the set s1 is: "  
        << *(p1.second) << "." << endl;  
  
   cout << "The lower bound of the element with "  
        << "a key of 20 in the set s1 is: "  
        << *(p1.first) << "." << endl;  
  
   // Compare the upper_bound called directly   
   s1_RcIter = s1.upper_bound( 20 );  
   cout << "A direct call of upper_bound( 20 ) gives "  
        << *s1_RcIter << "," << endl  
        << "matching the 2nd element of the pair"  
        << " returned by equal_range( 20 )." << endl;  
  
   p2 = s1.equal_range( 40 );  
  
   // If no match is found for the key,  
   // both elements of the pair return end( )  
   if ( ( p2.first == s1.end( ) ) && ( p2.second == s1.end( ) ) )  
      cout << "The set s1 doesn't have an element "  
           << "with a key less than 40." << endl;  
   else  
      cout << "The element of set s1 with a key >= 40 is: "  
           << *(p1.first) << "." << endl;  
}  
```  
  
```Output  
The upper bound of the element with a key of 20 in the set s1 is: 30.  
The lower bound of the element with a key of 20 in the set s1 is: 20.  
A direct call of upper_bound( 20 ) gives 30,  
matching the 2nd element of the pair returned by equal_range( 20 ).  
The set s1 doesn't have an element with a key less than 40.  
```  
  
##  <a name="a-nameseterasea--seterase"></a><a name="set__erase"></a>  set::erase  
 Удаляет элемент или диапазон элементов в наборе с заданных позиций или удаляет элементы, соответствующие заданному ключу.  
  
```  
iterator erase(
    const_iterator Where);

iterator erase(
    const_iterator First,  
    const_iterator Last);

size_type erase(
    const key_type& Key);
```  
  
### <a name="parameters"></a>Параметры  
 `Where`  
 Положение удаляемого элемента.  
  
 `First`  
 Положение первого удаляемого элемента.  
  
 `Last`  
 Положение перед последним удаляемым элементом.  
  
 `Key`  
 Значение ключа удаляемых элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Для первых двух функций-членов это двунаправленный итератор, обозначающий первый элемент, остающийся после любых удаленных элементов, или элемент в конце набора, если таких элементов нет.  
  
 Третья функция-член возвращает количество элементов, которые были удалены из набора.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_erase.cpp  
// compile with: /EHsc  
#include <set>  
#include <string>  
#include <iostream>  
#include <iterator> // next() and prev() helper functions  
  
using namespace std;  
  
using myset = set<string>;  
  
void printset(const myset& s) {  
    for (const auto& iter : s) {  
        cout << " [" << iter << "]";  
    }  
    cout << endl << "size() == " << s.size() << endl << endl;  
}  
  
int main()  
{  
    myset s1;  
  
    // Fill in some data to test with, one at a time  
    s1.insert("Bob");  
    s1.insert("Robert");  
    s1.insert("Bert");  
    s1.insert("Rob");  
    s1.insert("Bobby");  
  
    cout << "Starting data of set s1 is:" << endl;  
    printset(s1);  
    // The 1st member function removes an element at a given position  
    s1.erase(next(s1.begin()));  
    cout << "After the 2nd element is deleted, the set s1 is:" << endl;  
    printset(s1);  
  
    // Fill in some data to test with, one at a time, using an intializer list  
    myset s2{ "meow", "hiss", "purr", "growl", "yowl" };  
  
    cout << "Starting data of set s2 is:" << endl;  
    printset(s2);  
    // The 2nd member function removes elements  
    // in the range [First, Last)  
    s2.erase(next(s2.begin()), prev(s2.end()));  
    cout << "After the middle elements are deleted, the set s2 is:" << endl;  
    printset(s2);  
  
    myset s3;  
  
    // Fill in some data to test with, one at a time, using emplace  
    s3.emplace("C");  
    s3.emplace("C#");  
    s3.emplace("D");  
    s3.emplace("D#");  
    s3.emplace("E");  
    s3.emplace("E#");  
    s3.emplace("F");  
    s3.emplace("F#");  
    s3.emplace("G");  
    s3.emplace("G#");  
    s3.emplace("A");  
    s3.emplace("A#");  
    s3.emplace("B");  
  
    cout << "Starting data of set s3 is:" << endl;  
    printset(s3);  
    // The 3rd member function removes elements with a given Key  
    myset::size_type count = s3.erase("E#");  
    // The 3rd member function also returns the number of elements removed  
    cout << "The number of elements removed from s3 is: " << count << "." << endl;  
    cout << "After the element with a key of \"E#\" is deleted, the set s3 is:" << endl;  
    printset(s3);  
}  
  
```  
  
##  <a name="a-namesetfinda--setfind"></a><a name="set__find"></a>  set::find  
 Возвращает итератор, ссылающийся на элемент в наборе, ключ которого эквивалентен заданному ключу.  
  
```  
iterator find(const Key& key);

 
const_iterator find(const Key& key) const;
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Значение ключа, с которым сравнивается ключ сортировки элемента из набора, по которому выполняется поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, ссылающийся на расположение элемента с указанным ключом или на расположение элемента после последнего элемента в наборе (`set::end()`), если для ключа не найдено совпадений.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор, который ссылается на элемент в наборе с ключом, эквивалентным аргументу `key` согласно двоичному предикату, применяющему упорядочение на основе отношения сравнения «меньше».  
  
 Если возвращаемое значение **find** назначается **const_iterator**, то объект набора невозможно изменить. Если возвращаемое значение **find** назначается **iterator**, то объект набора можно изменить  
  
### <a name="example"></a>Пример  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <set>  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename T> void print_elem(const T& t) {  
    cout << "(" << t << ") ";  
}  
  
template <typename T> void print_collection(const T& t) {  
    cout << t.size() << " elements: ";  
  
    for (const auto& p : t) {  
        print_elem(p);  
    }  
    cout << endl;  
}  
  
template <typename C, class T> void findit(const C& c, T val) {  
    cout << "Trying find() on value " << val << endl;  
    auto result = c.find(val);  
    if (result != c.end()) {  
        cout << "Element found: "; print_elem(*result); cout << endl;  
    } else {  
        cout << "Element not found." << endl;  
    }  
}  
  
int main()  
{  
    set<int> s1({ 40, 45 });  
    cout << "The starting set s1 is: " << endl;  
    print_collection(s1);  
  
    vector<int> v;  
    v.push_back(43);  
    v.push_back(41);  
    v.push_back(46);  
    v.push_back(42);  
    v.push_back(44);  
    v.push_back(44); // attempt a duplicate  
  
    cout << "Inserting the following vector data into s1: " << endl;  
    print_collection(v);  
  
    s1.insert(v.begin(), v.end());  
  
    cout << "The modified set s1 is: " << endl;  
    print_collection(s1);  
    cout << endl;  
    findit(s1, 45);  
    findit(s1, 6);  
}  
  
```  
  
##  <a name="a-namesetgetallocatora--setgetallocator"></a><a name="set__get_allocator"></a>  set::get_allocator  
 Возвращает копию объекта-распределителя, использованного для создания набора.  
  
```  
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Распределитель, использующийся набор для управления памятью, который является параметром-шаблоном `Allocator`.  
  
 Дополнительные сведения по `Allocator` см. в подразделе "Примечания" раздела [Класс set](../standard-library/set-class.md).  
  
### <a name="remarks"></a>Примечания  
 Распределители для класса набора определяют, как этот класс управляет хранилищем. Для большинства задач программирования достаточно иметь распределители по умолчанию, поставляемые вместе с классами контейнеров стандартной библиотеки C++. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_get_allocator.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int>::allocator_type s1_Alloc;  
   set <int>::allocator_type s2_Alloc;  
   set <double>::allocator_type s3_Alloc;  
   set <int>::allocator_type s4_Alloc;  
  
   // The following lines declare objects  
   // that use the default allocator.  
   set <int> s1;  
   set <int, allocator<int> > s2;  
   set <double, allocator<double> > s3;  
  
   s1_Alloc = s1.get_allocator( );  
   s2_Alloc = s2.get_allocator( );  
   s3_Alloc = s3.get_allocator( );  
  
   cout << "The number of integers that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << s2.max_size( ) << "." << endl;  
  
   cout << "\nThe number of doubles that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << s3.max_size( ) <<  "." << endl;  
  
   // The following line creates a set s4  
   // with the allocator of multiset s1.  
   set <int> s4( less<int>( ), s1_Alloc );  
  
   s4_Alloc = s4.get_allocator( );  
  
   // Two allocators are interchangeable if  
   // storage allocated from each can be  
   // deallocated by the other  
   if( s1_Alloc == s4_Alloc )  
   {  
      cout << "\nThe allocators are interchangeable."  
           << endl;  
   }  
   else  
   {  
      cout << "\nThe allocators are not interchangeable."  
           << endl;  
   }  
}  
```  
  
##  <a name="a-namesetinserta--setinsert"></a><a name="set__insert"></a>  set::insert  
 Вставляет элемент или диапазон элементов в набор.  
  
```  
// (1) single element  
pair<iterator, bool> insert(
    const value_type& Val);

 
// (2) single element, perfect forwarded  
template <class ValTy>  
pair<iterator, bool>  
insert(
    ValTy&& Val);

 
// (3) single element with hint  
iterator insert(
    const_iterator Where,  
    const value_type& Val);

 
// (4) single element, perfect forwarded, with hint  
template <class ValTy>  
iterator insert(
    const_iterator Where,  
    ValTy&& Val);

 
// (5) range   
template <class InputIterator>   
void insert(
    InputIterator First,  
    InputIterator Last);

 
// (6) initializer list  
void insert(
    initializer_list<value_type>  
IList);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Val`|Значение элемента, вставляемого в набор, если оно уже не содержит элемент, значение которого эквивалентно упорядочено.|  
|`Where`|Место начала поиска правильной точки вставки. (Если эта точка находится непосредственно перед `Where`, вставка может быть выполнена в постоянном времени с поправкой на амортизацию, а не в логарифмическом времени.)|  
|`ValTy`|Параметр шаблона, определяющий тип аргумента, с помощью которого набор формирует элемент типа [value_type](../standard-library/map-class.md#map__value_type) и точно пересылает `Val` как аргумент.|  
|`First`|Позиция первого элемента, который следует скопировать.|  
|`Last`|Позиция непосредственно перед последним элементом, который следует скопировать.|  
|`InputIterator`|Аргумент функции-шаблона, который соответствует требованиям [итератора ввода](../standard-library/input-iterator-tag-struct.md), указывающего на элементы типа, которые можно использовать для создания объектов [value_type](../standard-library/map-class.md#map__value_type).|  
|`IList`|[initializer_list](../standard-library/initializer-list.md), из которого нужно скопировать элементы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одноэлементные функции члены (1) и (2) возвращают [пару](../standard-library/pair-structure.md), компонент `bool` которой имеет значение true, если была осуществлена вставка, и значение false, если набор уже содержал элемент с эквивалентным порядковым значением. Компонент итератора пары возвращаемых значений указывает на вставленный элемент, если значение компонента `bool` равно true, или на существующий элемент, если значение компонента `bool` равно false.  
  
 Одноэлеметные функции-члены с подсказкой (3) и (4) возвращают итератор, который указывает на позицию, где новый элемент был вставлен, или, если элемент с эквивалентным ключом уже существует, указывает на существующий элемент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает никакие итераторы, указатели или ссылки недействительными.  
  
 Если во время вставки одного элемента вызывается исключение, состояние контейнера не изменяется. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.  
  
 Для доступа к компоненту итератора `pair``pr`, возвращаемого одноэлементными функциями-членами, используйте `pr.first`. Для разыменования итератора в возвращенной паре используйте `*pr.first` (эта функция возвращает сам элемент). Для доступа к компоненту `bool` используйте `pr.second`. См. пример кода далее в этой статье.  
  
 [value_type контейнера](../standard-library/map-class.md#map__value_type) — это определение типа, которое принадлежит контейнеру, а для набора `set<V>::value_type` — это `const V`.  
  
 Функция-член с диапазоном (5) вставляет последовательность значений элементов в набор, соответствующий каждому элементу, адресованному итератором в диапазоне `[First, Last)`. Следовательно, `Last` не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `s.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `s`. Вставляются только элементы с уникальными значениями в диапазоне. Повторяющиеся значения игнорируются. Чтобы увидеть, какие элементы отклонены, используйте одноэлементные версии `insert`.  
  
 Функция-член списка инициализаторов (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в набор.  
  
 Для вставки элемента, созданного на месте (то есть без операций копирования или перемещения) см. разделы [set::emplace](#set__emplace) и [set::emplace_hint](#set__emplace_hint).  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_insert.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename S> void print(const S& s) {  
    cout << s.size() << " elements: ";  
  
    for (const auto& p : s) {  
        cout << "(" << p << ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
  
    // insert single values   
    set<int> s1;  
    // call insert(const value_type&) version  
    s1.insert({ 1, 10 });  
    // call insert(ValTy&&) version   
    s1.insert(20);  
  
    cout << "The original set values of s1 are:" << endl;  
    print(s1);  
  
    // intentionally attempt a duplicate, single element  
    auto ret = s1.insert(1);  
    if (!ret.second){  
        auto elem = *ret.first;  
        cout << "Insert failed, element with value 1 already exists."  
            << endl << "  The existing element is (" << elem << ")"  
            << endl;  
    }  
    else{  
        cout << "The modified set values of s1 are:" << endl;  
        print(s1);  
    }  
    cout << endl;  
  
    // single element, with hint  
    s1.insert(s1.end(), 30);  
    cout << "The modified set values of s1 are:" << endl;  
    print(s1);  
    cout << endl;  
  
    // The templatized version inserting a jumbled range  
    set<int> s2;  
    vector<int> v;  
    v.push_back(43);  
    v.push_back(294);  
    v.push_back(41);  
    v.push_back(330);  
    v.push_back(42);  
    v.push_back(45);  
  
    cout << "Inserting the following vector data into s2:" << endl;  
    print(v);  
  
    s2.insert(v.begin(), v.end());  
  
    cout << "The modified set values of s2 are:" << endl;  
    print(s2);  
    cout << endl;  
  
    // The templatized versions move-constructing elements  
    set<string>  s3;  
    string str1("blue"), str2("green");  
  
    // single element  
    s3.insert(move(str1));  
    cout << "After the first move insertion, s3 contains:" << endl;  
    print(s3);  
  
    // single element with hint  
    s3.insert(s3.end(), move(str2));  
    cout << "After the second move insertion, s3 contains:" << endl;  
    print(s3);  
    cout << endl;  
  
    set<int> s4;  
    // Insert the elements from an initializer_list  
    s4.insert({ 4, 44, 2, 22, 3, 33, 1, 11, 5, 55 });  
    cout << "After initializer_list insertion, s4 contains:" << endl;  
    print(s4);  
    cout << endl;  
}  
  
```  
  
##  <a name="a-namesetiteratora--setiterator"></a><a name="set__iterator"></a>  set::iterator  
 Тип, предоставляющий константный [двунаправленный итератор](../standard-library/bidirectional-iterator-tag-struct.md), который может читать любой элемент в наборе.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="example"></a>Пример  
  Пример объявления и использования **итератора** см. в разделе [begin](#set__begin).  
  
##  <a name="a-namesetkeycompa--setkeycomp"></a><a name="set__key_comp"></a>  set::key_comp  
 Извлекает копию объекта сравнения, который используется для упорядочивания ключей в наборе.  
  
```  
key_compare key_comp() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает объект-функцию, которую набор использует для упорядочивания своих элементов, что является параметром-шаблоном `Traits`.  
  
 Дополнительные сведения о `Traits` см. в разделе [Класс set](../standard-library/set-class.md).  
  
### <a name="remarks"></a>Примечания  
 Сохраненный объект определяет функцию-член:  
  
 **bool operator()**( **const Key&**`_xVal`, **const Key&**`_yVal`);  
  
 которая возвращает **true**, если `_xVal` предшествует `_yVal` в порядке сортировки и не равен ему.  
  
 Обратите внимание, что и [key_compare](#set__key_compare), и [value_compare](#set__value_compare) — синонимы параметра-шаблона **Traits**. Оба типа предоставляются для классов set и multiset, где они идентичны, для совместимости с классами map и multimap, где они различаются.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_key_comp.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   set <int, less<int> > s1;  
   set<int, less<int> >::key_compare kc1 = s1.key_comp( ) ;  
   bool result1 = kc1( 2, 3 ) ;  
   if( result1 == true )     
   {  
      cout << "kc1( 2,3 ) returns value of true, "  
           << "where kc1 is the function object of s1."  
           << endl;  
   }  
   else     
   {  
      cout << "kc1( 2,3 ) returns value of false "  
           << "where kc1 is the function object of s1."  
           << endl;  
   }  
  
   set <int, greater<int> > s2;  
   set<int, greater<int> >::key_compare kc2 = s2.key_comp( ) ;  
   bool result2 = kc2( 2, 3 ) ;  
   if(result2 == true)     
   {  
      cout << "kc2( 2,3 ) returns value of true, "  
           << "where kc2 is the function object of s2."  
           << endl;  
   }  
   else     
   {  
      cout << "kc2( 2,3 ) returns value of false, "  
           << "where kc2 is the function object of s2."  
           << endl;  
   }  
}  
```  
  
```Output  
kc1( 2,3 ) returns value of true, where kc1 is the function object of s1.  
kc2( 2,3 ) returns value of false, where kc2 is the function object of s2.  
```  
  
##  <a name="a-namesetkeycomparea--setkeycompare"></a><a name="set__key_compare"></a>  set::key_compare  
 Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в наборе.  
  
```  
typedef Traits key_compare;  
```  
  
### <a name="remarks"></a>Примечания  
 `key_compare` является синонимом для параметра-шаблона `Traits`.  
  
 Дополнительные сведения о `Traits` см. в разделе [Класс set](../standard-library/set-class.md).  
  
 Обратите внимание, что и `key_compare`, и [value_compare](#set__value_compare) — синонимы параметра-шаблона **Traits**. Оба типа предоставляются для классов set и multiset, где они идентичны, для совместимости с классами map и multimap, где они различаются.  
  
### <a name="example"></a>Пример  
  См. пример для [key_comp](#set__key_comp) в качестве примера объявления и использования `key_compare`.  
  
##  <a name="a-namesetkeytypea--setkeytype"></a><a name="set__key_type"></a>  set::key_type  
 Тип, описывающий объект, сохраненный как элемент набора в смысле его возможностей, присущих ключу сортировки.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `key_type` является синонимом для параметра-шаблона `Key`.  
  
 Дополнительные сведения по `Key` см. в подразделе "Примечания" раздела [Класс set](../standard-library/set-class.md).  
  
 Обратите внимание, что и `key_type`, и [value_type](#set__value_type) — синонимы для параметра-шаблона **Key**. Оба типа предоставляются для классов set и multiset, где они идентичны, для совместимости с классами map и multimap, где они различаются.  
  
### <a name="example"></a>Пример  
  См. пример для [value_type](#set__value_type) в качестве примера объявления и использования `key_type`.  
  
##  <a name="a-namesetlowerbounda--setlowerbound"></a><a name="set__lower_bound"></a>  set::lower_bound  
 Возвращает итератор, указывающий на первый элемент в наборе с ключом, который больше или равен указанному ключу.  
  
```  
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```  
  
### <a name="parameters"></a>Параметры  
 ` key`  
 Ключ-аргумент, который будет сравниваться с ключом сортировки элемента из набора, в котором выполняется поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор или `const_iterator`, который адресует положение элемента в наборе с ключом, который равен ключу-аргументу или больше него, либо адресует положение после последнего элемента в наборе, если соответствие для ключа не найдено.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_lower_bound.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1;  
   set <int> :: const_iterator s1_AcIter, s1_RcIter;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
   s1.insert( 30 );  
  
   s1_RcIter = s1.lower_bound( 20 );  
   cout << "The element of set s1 with a key of 20 is: "  
        << *s1_RcIter << "." << endl;  
  
   s1_RcIter = s1.lower_bound( 40 );  
  
   // If no match is found for the key, end( ) is returned  
   if ( s1_RcIter == s1.end( ) )  
      cout << "The set s1 doesn't have an element "  
           << "with a key of 40." << endl;  
   else  
      cout << "The element of set s1 with a key of 40 is: "  
           << *s1_RcIter << "." << endl;  
  
   // The element at a specific location in the set can be found   
   // by using a dereferenced iterator that addresses the location  
   s1_AcIter = s1.end( );  
   s1_AcIter--;  
   s1_RcIter = s1.lower_bound( *s1_AcIter );  
   cout << "The element of s1 with a key matching "  
        << "that of the last element is: "  
        << *s1_RcIter << "." << endl;  
}  
```  
  
```Output  
The element of set s1 with a key of 20 is: 20.  
The set s1 doesn't have an element with a key of 40.  
The element of s1 with a key matching that of the last element is: 30.  
```  
  
##  <a name="a-namesetmaxsizea--setmaxsize"></a><a name="set__max_size"></a>  set::max_size  
 Возвращает максимальную длину набора.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимально возможная длина набора.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_max_size.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   set <int> s1;  
   set <int>::size_type i;  
  
   i = s1.max_size( );     
   cout << "The maximum possible length "  
        << "of the set is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namesetoperatoreqa--setoperator"></a><a name="set__operator_eq"></a>  set::operator=  
 Заменяет элементы этого `set` элементами из другого `set`.  
  
```  
set& operator=(const set& right);

set& operator=(set&& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` right`|`set`, предоставляющий новые элементы для назначения `set`.|  
  
### <a name="remarks"></a>Примечания  
 Первая версия `operator=` использует [ссылку lvalue](../cpp/lvalue-reference-declarator-amp.md) для ` right`, чтобы копировать элементы из ` right` в `set`.  
  
 Вторая версия использует [ссылку rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) для right. Она перемещает элементы из ` right` в `set`.  
  
 Все элементы в этом `set` до выполнения функции оператора отбрасываются.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_operator_as.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
   {  
   using namespace std;  
   set<int> v1, v2, v3;  
   set<int>::iterator iter;  
  
   v1.insert(10);  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
   }  
```  
  
##  <a name="a-namesetpointera--setpointer"></a><a name="set__pointer"></a>  set::pointer  
 Тип, предоставляющий указатель на элемент в наборе.  
  
```  
typedef typename allocator_type::pointer pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип **pointer** можно использовать для изменения значения элемента.  
  
 В большинстве случаев для доступа к элементам в объекте-наборе следует использовать [итератор](#set__iterator).  
  
##  <a name="a-namesetrbegina--setrbegin"></a><a name="set__rbegin"></a>  set::rbegin  
 Возвращает итератор, который обращается к первому элементу в обращенном наборе.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный двунаправленный итератор, адресующий первый элемент в обратном наборе или элемент, который был последним элементом в наборе до изменения его порядка на противоположный.  
  
### <a name="remarks"></a>Примечания  
 `rbegin` используется с обратным набором так же, как [begin](#set__begin) используется с обычным набором.  
  
 Если возвращенное значение `rbegin` назначается `const_reverse_iterator`, то объект-набор изменить нельзя. Если возвращенное значение `rbegin` назначается `reverse_iterator`, то объект-набор можно изменить.  
  
 `rbegin` можно использовать для последовательного прохождения по списку в обратную сторону.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_rbegin.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   set <int> s1;  
   set <int>::iterator s1_Iter;  
   set <int>::reverse_iterator s1_rIter;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
   s1.insert( 30 );  
  
   s1_rIter = s1.rbegin( );  
   cout << "The first element in the reversed set is "  
        << *s1_rIter << "." << endl;  
  
   // begin can be used to start an iteration   
   // throught a set in a forward order  
   cout << "The set is:";  
   for ( s1_Iter = s1.begin( ) ; s1_Iter != s1.end( ); s1_Iter++ )  
      cout << " " << *s1_Iter;  
   cout << endl;  
  
   // rbegin can be used to start an iteration   
   // throught a set in a reverse order  
   cout << "The reversed set is:";  
   for ( s1_rIter = s1.rbegin( ) ; s1_rIter != s1.rend( ); s1_rIter++ )  
      cout << " " << *s1_rIter;  
   cout << endl;  
  
   // A set element can be erased by dereferencing to its key   
   s1_rIter = s1.rbegin( );  
   s1.erase ( *s1_rIter );  
  
   s1_rIter = s1.rbegin( );  
   cout << "After the erasure, the first element "  
        << "in the reversed set is "<< *s1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element in the reversed set is 30.  
The set is: 10 20 30  
The reversed set is: 30 20 10  
After the erasure, the first element in the reversed set is 20.  
```  
  
##  <a name="a-namesetreferencea--setreference"></a><a name="set__reference"></a>  set::reference  
 Тип, предоставляющий ссылку на элемент, хранящийся в наборе.  
  
```  
typedef typename allocator_type::reference reference;  
```  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_reference.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
  
   // Declare and initialize a reference &Ref1 to the 1st element  
   const int &Ref1 = *s1.begin( );  
  
   cout << "The first element in the set is "  
        << Ref1 << "." << endl;  
}  
```  
  
```Output  
The first element in the set is 10.  
```  
  
##  <a name="a-namesetrenda--setrend"></a><a name="set__rend"></a>  set::rend  
 Возвращает итератор, который обращается к месту, следующему за последним элементом в обращенном наборе.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный двунаправленный итератор, адресующий расположение после последнего элемента в обратном наборе (расположение перед первым элементом в наборе до изменения его порядка на обратный).  
  
### <a name="remarks"></a>Примечания  
 `rend` используется с обратным набором так же, как [end](#set__end) используется с обычным набором.  
  
 Если возвращенное значение `rend` назначается `const_reverse_iterator`, то объект-набор изменить нельзя. Если возвращенное значение `rend` назначается `reverse_iterator`, то объект-набор можно изменить. Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.  
  
 `rend` используется, чтобы проверить, достиг ли обратный итератор конца набора.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_rend.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   set <int> s1;  
   set <int>::iterator s1_Iter;  
   set <int>::reverse_iterator s1_rIter;  
   set <int>::const_reverse_iterator s1_crIter;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
   s1.insert( 30 );  
  
   s1_rIter = s1.rend( );  
   s1_rIter--;  
   cout << "The last element in the reversed set is "  
        << *s1_rIter << "." << endl;  
  
   // end can be used to terminate an iteration   
   // throught a set in a forward order  
   cout << "The set is: ";  
   for ( s1_Iter = s1.begin( ) ; s1_Iter != s1.end( ); s1_Iter++ )  
      cout << *s1_Iter << " ";  
   cout << "." << endl;  
  
   // rend can be used to terminate an iteration   
   // throught a set in a reverse order  
   cout << "The reversed set is: ";  
   for ( s1_rIter = s1.rbegin( ) ; s1_rIter != s1.rend( ); s1_rIter++ )  
      cout << *s1_rIter << " ";  
   cout << "." << endl;  
  
   s1_rIter = s1.rend( );  
   s1_rIter--;  
   s1.erase ( *s1_rIter );  
  
   s1_rIter = s1.rend( );  
   --s1_rIter;  
   cout << "After the erasure, the last element in the "  
        << "reversed set is " << *s1_rIter << "." << endl;  
}  
```  
  
##  <a name="a-namesetreverseiteratora--setreverseiterator"></a><a name="set__reverse_iterator"></a>  set::reverse_iterator  
 Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном наборе.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `reverse_iterator` используется для перебора набора в обратном порядке.  
  
### <a name="example"></a>Пример  
  См. пример объявления и использования `reverse_iterator` в примере для [rbegin](#set__rbegin).  
  
##  <a name="a-namesetseta--setset"></a><a name="set__set"></a>  set::set  
 Создает набор, который является пустым или копией части или целого другого набора.  
  
```  
set();

explicit set(
    const Traits& Comp);

set(
    const Traits& Comp,  
    const Allocator& Al);

set(
    const set& Right);

set(
    set&& Right);

set(
    initializer_list<Type> IList);

set(
    initializer_list<Type> IList,  
    const Compare& Comp);

set(
    initializer_list<Type> IList,  
    const Compare& Comp,   
    const Allocator& Al);

 
template <class InputIterator>  
set(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
set(
 InputIterator First,  
    InputIterator Last,  
    const Traits& Comp);

template <class InputIterator>  
set(
 InputIterator First,  
    InputIterator Last,  
    const Traits& Comp,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Al`|Класс распределителя хранилища, который необходимо использовать для данного объекта-набора, значение которого по умолчанию — **Allocator**.|  
|`Comp`|Функция сравнения типа `const Traits` используется для упорядочивания элементов в наборе, который по умолчанию имеет значение `Compare`.|  
|`Rght`|Набор, для которого создаваемый набор станет копией.|  
|`First`|Положение первого элемента в диапазоне копируемых элементов.|  
|`Last`|Положение первого элемента после диапазона копируемых элементов.|  
|`IList`|Объект initializer_list, из которого копируются элементы.|  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы сохраняют тип объекта-распределителя, управляющего памятью для набора. Затем его можно получить путем вызова [get_allocator](#set__get_allocator). Параметр распределителя часто опускается в объявлениях классов и макросах предварительной обработки, используемых для замены альтернативных распределителей.  
  
 Все конструкторы инициализируют свои наборы.  
  
 Все конструкторы хранят объект-функцию типа **Traits**, которая используется для упорядочивания ключей набора. Затем функцию можно получить путем вызова [key_comp](#set__key_comp).  
  
 Первые три конструктора указывают пустой начальный набор, второй указывает тип функции сравнения ( `comp`) для использовании при установлении порядка элементов, а третий явно указывает тип распределителя ( `al`) для использования. Ключевое слово **explicit** подавляет некоторые виды автоматического преобразования типов.  
  
 Четвертый конструктор указывает копию набора `right`.  
  
 Следующие три конструктора используют initializer_list, чтобы указать элементы.  
  
 Следующие три конструктора копируют диапазон[ `first`, `last`) набора с повышением точности при указании типа функции сравнения класса **Traits** и **распределителя**.  
  
 Восьмой конструктор указывает копию набора путем перемещения `right`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_set.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    // Create an empty set s0 of key type integer  
    set <int> s0;  
  
    // Create an empty set s1 with the key comparison  
    // function of less than, then insert 4 elements  
    set <int, less<int> > s1;  
    s1.insert(10);  
    s1.insert(20);  
    s1.insert(30);  
    s1.insert(40);  
  
    // Create an empty set s2 with the key comparison  
    // function of less than, then insert 2 elements  
    set <int, less<int> > s2;  
    s2.insert(10);  
    s2.insert(20);  
  
    // Create a set s3 with the   
    // allocator of set s1  
    set <int>::allocator_type s1_Alloc;  
    s1_Alloc = s1.get_allocator();  
    set <int> s3(less<int>(), s1_Alloc);  
    s3.insert(30);  
  
    // Create a copy, set s4, of set s1  
    set <int> s4(s1);  
  
    // Create a set s5 by copying the range s1[ first,  last)  
    set <int>::const_iterator s1_bcIter, s1_ecIter;  
    s1_bcIter = s1.begin();  
    s1_ecIter = s1.begin();  
    s1_ecIter++;  
    s1_ecIter++;  
    set <int> s5(s1_bcIter, s1_ecIter);  
  
    // Create a set s6 by copying the range s4[ first,  last)  
    // and with the allocator of set s2  
    set <int>::allocator_type s2_Alloc;  
    s2_Alloc = s2.get_allocator();  
    set <int> s6(s4.begin(), ++s4.begin(), less<int>(), s2_Alloc);  
  
    cout << "s1 =";  
    for (auto i : s1)  
        cout << " " << i;  
    cout << endl;  
  
    cout << "s2 = " << *s2.begin() << " " << *++s2.begin() << endl;  
  
    cout << "s3 =";  
    for (auto i : s3)  
        cout << " " << i;  
    cout << endl;  
  
    cout << "s4 =";  
    for (auto i : s4)  
        cout << " " << i;  
    cout << endl;  
  
    cout << "s5 =";  
    for (auto i : s5)  
        cout << " " << i;  
    cout << endl;  
  
    cout << "s6 =";  
    for (auto i : s6)  
        cout << " " << i;  
    cout << endl;  
  
    // Create a set by moving s5  
    set<int> s7(move(s5));  
    cout << "s7 =";  
    for (auto i : s7)  
        cout << " " << i;  
    cout << endl;  
  
    // Create a set with an initializer_list  
    cout << "s8 =";  
    set<int> s8{ { 1, 2, 3, 4 } };  
    for (auto i : s8)  
        cout << " " << i;  
    cout << endl;  
  
    cout << "s9 =";  
    set<int> s9{ { 5, 6, 7, 8 }, less<int>() };  
    for (auto i : s9)  
        cout << " " << i;  
    cout << endl;  
  
    cout << "s10 =";  
    set<int> s10{ { 10, 20, 30, 40 }, less<int>(), s9.get_allocator() };  
    for (auto i : s10)  
        cout << " " << i;  
    cout << endl;  
}  
  
```  
  
```Output  
s1 = 10 20 30 40s2 = 10 20s3 = 30s4 = 10 20 30 40s5 = 10 20s6 = 10s7 = 10 20s8 = 1 2 3 4s9 = 5 6 7 8s10 = 10 20 30 40  
```  
  
##  <a name="a-namesetsizea--setsize"></a><a name="set__size"></a>  set::size  
 Возвращает количество элементов в наборе.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина набора.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_size.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1;  
   set <int> :: size_type i;  
  
   s1.insert( 1 );  
   i = s1.size( );  
   cout << "The set length is " << i << "." << endl;  
  
   s1.insert( 2 );  
   i = s1.size( );  
   cout << "The set length is now " << i << "." << endl;  
}  
```  
  
```Output  
The set length is 1.  
The set length is now 2.  
```  
  
##  <a name="a-namesetsizetypea--setsizetype"></a><a name="set__size_type"></a>  set::size_type  
 Тип целого числа без знака, который может представлять число элементов в наборе.  
  
```  
typedef typename allocator_type::size_type size_type;  
```  
  
### <a name="example"></a>Пример  
  См. пример для [size](#set__size) в качестве примера объявления и использования `size_type`  
  
##  <a name="a-namesetswapa--setswap"></a><a name="set__swap"></a>  set::swap  
 Обмен элементами между двумя наборами.  
  
```  
void swap(
    set<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Набор-аргумент предоставляет элементы для обмена с целевым набором.  
  
### <a name="remarks"></a>Примечания  
 Функция-член не делает недействительными никакие ссылки, указатели или итераторы, обозначающие элементы в двух наборах, между которыми выполняется обмен элементами.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_swap.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3;  
   set <int>::iterator s1_Iter;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
   s1.insert( 30 );  
   s2.insert( 100 );  
   s2.insert( 200 );  
   s3.insert( 300 );  
  
   cout << "The original set s1 is:";  
   for ( s1_Iter = s1.begin( ); s1_Iter != s1.end( ); s1_Iter++ )  
      cout << " " << *s1_Iter;  
   cout   << "." << endl;  
  
   // This is the member function version of swap  
   s1.swap( s2 );  
  
   cout << "After swapping with s2, list s1 is:";  
   for ( s1_Iter = s1.begin( ); s1_Iter != s1.end( ); s1_Iter++ )  
      cout << " " << *s1_Iter;  
   cout  << "." << endl;  
  
   // This is the specialized template version of swap  
   swap( s1, s3 );  
  
   cout << "After swapping with s3, list s1 is:";  
   for ( s1_Iter = s1.begin( ); s1_Iter != s1.end( ); s1_Iter++ )  
      cout << " " << *s1_Iter;  
   cout   << "." << endl;  
}  
```  
  
```Output  
The original set s1 is: 10 20 30.  
After swapping with s2, list s1 is: 100 200.  
After swapping with s3, list s1 is: 300.  
```  
  
##  <a name="a-namesetupperbounda--setupperbound"></a><a name="set__upper_bound"></a>  set::upper_bound  
 Возвращает итератор, указывающий на первый элемент в наборе с ключом, который больше указанного ключа.  
  
```  
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```  
  
### <a name="parameters"></a>Параметры  
 ` key`  
 Ключ-аргумент, который будет сравниваться с ключом сортировки элемента из набора, в котором выполняется поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Итератор** или `const_iterator`, который адресует положение элемента в наборе с ключом, который больше ключа-аргумента, либо адресует положение после последнего элемента в наборе, если соответствие для ключа не найдено.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_upper_bound.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   set <int> s1;  
   set <int> :: const_iterator s1_AcIter, s1_RcIter;  
  
   s1.insert( 10 );  
   s1.insert( 20 );  
   s1.insert( 30 );  
  
   s1_RcIter = s1.upper_bound( 20 );  
   cout << "The first element of set s1 with a key greater "  
        << "than 20 is: " << *s1_RcIter << "." << endl;  
  
   s1_RcIter = s1.upper_bound( 30 );  
  
   // If no match is found for the key, end( ) is returned  
   if ( s1_RcIter == s1.end( ) )  
      cout << "The set s1 doesn't have an element "  
           << "with a key greater than 30." << endl;  
   else  
      cout << "The element of set s1 with a key > 40 is: "  
           << *s1_RcIter << "." << endl;  
  
   // The element at a specific location in the set can be found   
   // by using a dereferenced iterator addressing the location  
   s1_AcIter = s1.begin( );  
   s1_RcIter = s1.upper_bound( *s1_AcIter );  
   cout << "The first element of s1 with a key greater than"  
        << endl << "that of the initial element of s1 is: "  
        << *s1_RcIter << "." << endl;  
}  
```  
  
```Output  
The first element of set s1 with a key greater than 20 is: 30.  
The set s1 doesn't have an element with a key greater than 30.  
The first element of s1 with a key greater than  
that of the initial element of s1 is: 20.  
```  
  
##  <a name="a-namesetvaluecompa--setvaluecomp"></a><a name="set__value_comp"></a>  set::value_comp  
 Извлекает копию объекта сравнения, который используется для упорядочивания значений элементов в наборе.  
  
```  
value_compare value_comp() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает объект-функцию, которую набор использует для упорядочивания своих элементов, что является параметром-шаблоном `Traits`.  
  
 Дополнительные сведения о `Traits` см. в разделе [Класс set](../standard-library/set-class.md).  
  
### <a name="remarks"></a>Примечания  
 Сохраненный объект определяет функцию-член:  
  
 **bool operator**( **const Key&**`_xVal`, **const Key&**`_yVal`);  
  
 которая возвращает **true**, если `_xVal` предшествует `_yVal` в порядке сортировки и не равен ему.  
  
 Обратите внимание, что и [value_compare](#set__value_compare), и [key_compare](#set__key_compare) являются синонимами для параметра-шаблона **Traits**. Оба типа предоставляются для классов set и multiset, где они идентичны, для совместимости с классами map и multimap, где они различаются.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_value_comp.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   set <int, less<int> > s1;  
   set <int, less<int> >::value_compare vc1 = s1.value_comp( );  
   bool result1 = vc1( 2, 3 );  
   if( result1 == true )     
   {  
      cout << "vc1( 2,3 ) returns value of true, "  
           << "where vc1 is the function object of s1."  
           << endl;  
   }  
   else     
   {  
      cout << "vc1( 2,3 ) returns value of false, "  
           << "where vc1 is the function object of s1."  
           << endl;  
   }  
  
   set <int, greater<int> > s2;  
   set<int, greater<int> >::value_compare vc2 = s2.value_comp( );  
   bool result2 = vc2( 2, 3 );  
   if( result2 == true )     
   {  
      cout << "vc2( 2,3 ) returns value of true, "  
           << "where vc2 is the function object of s2."  
           << endl;  
   }  
   else     
   {  
      cout << "vc2( 2,3 ) returns value of false, "  
           << "where vc2 is the function object of s2."  
           << endl;  
   }  
}  
```  
  
```Output  
vc1( 2,3 ) returns value of true, where vc1 is the function object of s1.  
vc2( 2,3 ) returns value of false, where vc2 is the function object of s2.  
```  
  
##  <a name="a-namesetvaluecomparea--setvaluecompare"></a><a name="set__value_compare"></a>  set::value_compare  
 Тип, предоставляющий объект функции, который может сравнить значениях двух элементов, чтобы определить их относительный порядок в наборе.  
  
```  
typedef key_compare value_compare;  
```  
  
### <a name="remarks"></a>Примечания  
 `value_compare` является синонимом для параметра-шаблона `Traits`.  
  
 Дополнительные сведения о `Traits` см. в разделе [Класс set](../standard-library/set-class.md).  
  
 Обратите внимание, что и [key_compare](#set__key_compare), и **value_compare** — синонимы параметра-шаблона **Traits**. Оба типа предоставляются для классов set и multiset, где они идентичны, для совместимости с классами map и multimap, где они различаются.  
  
### <a name="example"></a>Пример  
  См. пример для [value_comp](#set__value_comp) в качестве примера объявления и использования `value_compare`.  
  
##  <a name="a-namesetvaluetypea--setvaluetype"></a><a name="set__value_type"></a>  set::value_type  
 Тип, описывающий объект, который сохранен как элемент набора в смысле его возможностей, присущих значению.  
  
```  
typedef Key value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `value_type` является синонимом для параметра-шаблона `Key`.  
  
 Дополнительные сведения по `Key` см. в подразделе "Примечания" раздела [Класс set](../standard-library/set-class.md).  
  
 Обратите внимание, что и [key_type](#set__key_type), и `value_type` являются синонимами для параметра-шаблона **Key**. Оба типа предоставляются для классов set и multiset, где они идентичны, для совместимости с классами map и multimap, где они различаются.  
  
### <a name="example"></a>Пример  
  
```cpp  
// set_value_type.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1;  
   set <int>::iterator s1_Iter;  
  
   set <int>::value_type svt_Int;   // Declare value_type  
   svt_Int = 10;            // Initialize value_type  
  
   set <int> :: key_type skt_Int;   // Declare key_type  
   skt_Int = 20;             // Initialize key_type  
  
   s1.insert( svt_Int );         // Insert value into s1  
   s1.insert( skt_Int );         // Insert key into s1  
  
   // A set accepts key_types or value_types as elements  
   cout << "The set has elements:";  
   for ( s1_Iter = s1.begin( ) ; s1_Iter != s1.end( ); s1_Iter++)  
      cout << " " << *s1_Iter;  
   cout << "." << endl;  
}  
```  
  
```Output  
The set has elements: 10 20.  
```  
  
## <a name="see-also"></a>См. также  
 [\<set>](../standard-library/set.md)   
 [Контейнеры](../cpp/containers-modern-cpp.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)


