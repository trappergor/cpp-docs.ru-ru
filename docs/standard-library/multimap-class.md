---
title: "Класс multimap | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- map/std::multimap
- map/std::multimap::allocator_type
- map/std::multimap::const_iterator
- map/std::multimap::const_pointer
- map/std::multimap::const_reference
- map/std::multimap::const_reverse_iterator
- map/std::multimap::difference_type
- map/std::multimap::iterator
- map/std::multimap::key_compare
- map/std::multimap::key_type
- map/std::multimap::mapped_type
- map/std::multimap::pointer
- map/std::multimap::reference
- map/std::multimap::reverse_iterator
- map/std::multimap::size_type
- map/std::multimap::value_type
- map/std::multimap::begin
- map/std::multimap::cbegin
- map/std::multimap::cend
- map/std::multimap::clear
- map/std::multimap::count
- map/std::multimap::crbegin
- map/std::multimap::crend
- map/std::multimap::emplace
- map/std::multimap::emplace_hint
- map/std::multimap::empty
- map/std::multimap::end
- map/std::multimap::equal_range
- map/std::multimap::erase
- map/std::multimap::find
- map/std::multimap::get_allocator
- map/std::multimap::insert
- map/std::multimap::key_comp
- map/std::multimap::lower_bound
- map/std::multimap::max_size
- map/std::multimap::rbegin
- map/std::multimap::rend
- map/std::multimap::size
- map/std::multimap::swap
- map/std::multimap::upper_bound
- map/std::multimap::value_comp
dev_langs: C++
helpviewer_keywords:
- std::multimap [C++]
- std::multimap [C++], allocator_type
- std::multimap [C++], const_iterator
- std::multimap [C++], const_pointer
- std::multimap [C++], const_reference
- std::multimap [C++], const_reverse_iterator
- std::multimap [C++], difference_type
- std::multimap [C++], iterator
- std::multimap [C++], key_compare
- std::multimap [C++], key_type
- std::multimap [C++], mapped_type
- std::multimap [C++], pointer
- std::multimap [C++], reference
- std::multimap [C++], reverse_iterator
- std::multimap [C++], size_type
- std::multimap [C++], value_type
- std::multimap [C++], begin
- std::multimap [C++], cbegin
- std::multimap [C++], cend
- std::multimap [C++], clear
- std::multimap [C++], count
- std::multimap [C++], crbegin
- std::multimap [C++], crend
- std::multimap [C++], emplace
- std::multimap [C++], emplace_hint
- std::multimap [C++], empty
- std::multimap [C++], end
- std::multimap [C++], equal_range
- std::multimap [C++], erase
- std::multimap [C++], find
- std::multimap [C++], get_allocator
- std::multimap [C++], insert
- std::multimap [C++], key_comp
- std::multimap [C++], lower_bound
- std::multimap [C++], max_size
- std::multimap [C++], rbegin
- std::multimap [C++], rend
- std::multimap [C++], size
- std::multimap [C++], swap
- std::multimap [C++], upper_bound
- std::multimap [C++], value_comp
ms.assetid: 8796ae05-37c4-475a-9e61-75fde9d4a463
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18d648f632a28214779c9424971f65e535a5e210
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multimap-class"></a>Класс multimap
Класс multimap в стандартной библиотеке С++ используется для хранения и извлечения данных из коллекции, в которой каждый элемент является парой, хранящей значение данных и ключ сортировки. Значение ключа может не быть уникальным и применяется для автоматической сортировки данных. Значение элементов в multimap, но не связанное с ним значение ключа, можно изменить напрямую. Значения ключей, связанные со старыми элементами, необходимо удалить и вставить новые значения ключей, связанные с новыми элементами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Key,   
    class Type,   
    class Traits=less <Key>,   
    class Allocator=allocator <pair  <const Key, Type>>>  
class multimap;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Key`  
 Тип данных ключа для сохранения в контейнере multimap.  
  
 `Type`  
 Тип данных элемента, который необходимо сохранить в контейнере multimap.  
  
 `Traits`  
 Тип, предоставляющий объект функции, который может сравнивать два значения элемента как ключи сортировки, чтобы определить их относительный порядок в контейнере multimap. Бинарный предикат `less<Key>` является значением по умолчанию.  
  
 В C++ 14 вы можете включить разнородный поиск, указав предикат `std::less<>` или `std::greater<>`, не имеющий параметров типа. Дополнительные сведения см. в статье [Разнородный поиск в ассоциативных контейнерах](../standard-library/stl-containers.md#sequence_containers)  
  
 `Allocator`  
 Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для сопоставления. Этот аргумент является необязательным, и значением по умолчанию является `allocator<pair <const Key, Type> >`.  
  
## <a name="remarks"></a>Примечания  
 Класс multimap в стандартной библиотеке С++ — это:  
  
-   Ассоциативный контейнер, который является контейнером переменного размера, поддерживающим эффективное получение значений элементов на основе значения соответствующего ключа.  
  
-   Реверсивный, поскольку он предоставляет двунаправленные итераторы для получения доступа к его элементам.  
  
-   Сортированный, поскольку его элементы упорядочены по значениям ключей в контейнере в соответствии с заданной функцией сравнения.  
  
-   Множественный, поскольку его элементы не обязательно должны иметь уникальные ключи, т. е. одному значению ключа может соответствовать много значений данных элементов, связанных с ним.  
  
-   Является контейнером ассоциативной пары, поскольку его значения данных элементов отличаются от его значений ключей.  
  
-   Шаблонный класс шаблона, поскольку функции, которые он предоставляет, являются универсальными и, соответственно, не зависят от конкретного типа данных, содержащихся в виде элементов или ключей. Типы данных, используемые для элементов и ключей, вместо этого определяются как параметры в шаблоне класса вместе с функцией и распределителем сравнения.  
  
 Итератор, предоставляемый классом map, является двунаправленным итератором, но функции-члены класса [insert](#insert) и [multimap](#multimap) имеют версии, которые принимают в качестве параметров-шаблонов более слабый итератор ввода, чьи функциональные требования ниже, чем гарантируемые классом двунаправленных итераторов. Различные концепции итераторов образуют семейство, связанное уточнениями функциональности. Каждая концепция итератора имеет собственный набор требований, а алгоритмы, работающие с ними, должны ограничивать свои предположения согласно требованиям, предоставляемым этим типом итератора. Можно предположить, что итератор ввода может быть разыменован для обращения к определенному объекту и инкрементирован до следующего итератора в последовательности. Это минимальный набор функциональных возможностей, но его достаточно, чтобы иметь возможность осмысленно говорить о диапазоне итераторов `[First, Last)`, в контексте функций-членов класса.  
  
 Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. Ассоциативные контейнеры оптимизированы для операций поиска, вставки и удаления. Функции-члены, которые явно поддерживают эти операции, являются эффективными и в среднем выполняют их пропорционально логарифму числа элементов в контейнере. Вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, которые ранее указывали конкретно на удаленные элементы.  
  
 Класс multimap рекомендуется использовать в качестве ассоциативного контейнера, если условия, ассоциирующие значения с ключами, удовлетворяются приложением. Модель для этого типа структуры — это упорядоченный список ключевых слов со связанными значениями строк, предоставляющими, например, определения, в которых слова не всегда обладают уникальными определениями. Если же ключевые слова обладают уникальными определениями, и ключи уникальны, то сопоставление будет предпочтительным контейнером. Если же сохранен только список слов, то в качестве контейнера необходимо выбрать набор. Если допускается повторное использование слов, то подходящей структурой контейнера будет multiset.  
  
 Мультиотображение упорядочивает контролируемую им последовательность посредством вызова хранимого объекта-функции типа [key_compare](#key_compare). Этот хранимый объект является функцией сравнения, доступ к которой можно получить через вызов функции-члена [key_comp](#key_comp). В целом, упорядочиваемые элементы должны лишь подлежать сравнению "меньше чем" для установления такого порядка, чтобы, имея любые два элемента, можно было определить, что они равны (ни один не меньше другого) или что один меньше другого. Это приводит к упорядочению неравнозначных элементов. С более технической точки зрения, функция сравнения является бинарным предикатом, который вызывает строгого слабое упорядочение в стандартном математически смысле. Бинарный предикат `f(x,y)` является объектом функции, обладающим двумя объектами аргументов `x` и `y`, а также возвращаемым значением true или false. Порядок, заданный для набора, является строгим слабым порядком, если бинарный предикат является нерефлексивным, антисимметричным и переходящим и если эквивалентность является переходящей, где два объекта `x` и `y` заданы как эквивалентные при том, что `f(x,y)` и `f(y,x)` имеют значение false. Если более строгое условие равенства между ключами заменяет условие эквивалентности, порядок становится общим (т.е. все элементы упорядочиваются относительно друг друга), и сопоставленные ключи будут неотличимы друг от друга.  
  
 В C++ 14 вы можете включить разнородный поиск, указав предикат `std::less<>` или `std::greater<>`, не имеющий параметров типа. Более подробные сведения см. в разделе [Разнородный поиск в ассоциативных контейнерах](../standard-library/stl-containers.md#sequence_containers)  
  
## <a name="members"></a>Участники  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[multimap](#multimap)|Создает контейнер `multimap`, который является пустым или копией части или целого другого контейнера `multimap`.|  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Тип, представляющий класс `allocator` для объекта `multimap`.|  
|[const_iterator](#const_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать тот или иной элемент `const` в контейнере `multimap`.|  
|[const_pointer](#const_pointer)|Тип, предоставляющий указатель на элемент `const` в контейнере `multimap`.|  
|[const_reference](#const_reference)|Тип, предоставляющий ссылку на элемент `const`, сохраненный в контейнере `multimap` для чтения и выполнения операций `const`.|  
|[const_reverse_iterator](#const_reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать любой элемент `const` в контейнере `multimap`.|  
|[difference_type](#difference_type)|Тип целого числа со знаком, пригодный для представления количества элементов в контейнере `multimap` в диапазоне между элементами, на которые указывают итераторы.|  
|[iterator](#iterator)|Тип, который предоставляет различие между 2 итераторами, относящимися к элементам в одном контейнере `multimap`.|  
|[key_compare](#key_compare)|Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в контейнере `multimap`.|  
|[key_type](#key_type)|Тип, описывающий объект ключа сортировки, составляющий каждый элемент контейнера `multimap`.|  
|[mapped_type](#mapped_type)|Тип, который представляет тип данных, хранящийся в контейнере `multimap`.|  
|[pointer](#pointer)|Тип, предоставляющий указатель на элемент `const` в контейнере `multimap`.|  
|[reference](#reference)|Тип, предоставляющий ссылку на элемент, хранящийся в контейнере `multimap`.|  
|[reverse_iterator](#reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном контейнере `multimap`.|  
|[size_type](#size_type)|Тип целого числа без знака, предоставляющий указатель на элемент `const` в контейнере `multimap`.|  
|[value_type](#value_type)|Тип, предоставляющий объект функции, который может сравнить два элемента в качестве ключей сортировки для определения их относительного порядка в контейнере `multimap`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[begin](#begin)|Возвращает итератор, обращающийся к первый элемент в контейнере `multimap`.|  
|[cbegin](#cbegin)|Возвращает итератор const, обращающийся к первому элементу в `multimap`.|  
|[cend](#cend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в `multimap`.|  
|[clear](#clear)|Стирает все элементы в `multimap`.|  
|[count](#count)|Возвращает число элементов в контейнере `multimap`, ключи которых соответствуют ключу, заданному параметром.|  
|[crbegin](#crbegin)|Возвращает итератор const, который обращается к первому элементу в обращенном контейнере `multimap`.|  
|[crend](#crend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном контейнере `multimap`.|  
|[emplace](#emplace)|Вставляет созданный на месте элемент в `multimap`.|  
|[emplace_hint](#emplace_hint)|Вставляет созданный на месте элемент в `multimap` с подсказкой о размещении|  
|[empty](#empty)|Проверяет, пуст ли `multimap`.|  
|[end](#end)|Возвращает итератор, который обращается к месту, следующему за последним элементом в контейнере `multimap`.|  
|[equal_range](#equal_range)|Находит диапазон элементов, где ключ элемента соответствует заданному значению.|  
|[erase](#erase)|Удаляет элемент или диапазон элементов в `multimap` с заданных позиций или удаляет элементы, соответствующие заданному ключу.|  
|[find](#find)|Возвращает итератор, который обращается к первому местоположению элемента в контейнере `multimap` с ключом, эквивалентным указанному ключу.|  
|[get_allocator](#get_allocator)|Возвращает копию объекта `allocator`, который используется для создания контейнера `multimap`.|  
|[insert](#insert)|Вставляет элемент или диапазон элементов в `multimap`.|  
|[key_comp](#key_comp)|Извлекает копию объекта сравнения, который используется для упорядочивания ключей в контейнере `multimap`.|  
|[lower_bound](#lower_bound)|Возвращает итератор, указывающий на первый элемент в контейнере `multimap` с ключом, который больше или равен указанному ключу.|  
|[max_size](#max_size)|Возвращает максимальную длину `multimap`.|  
|[rbegin](#rbegin)|Возвращает итератор, который обращается к первому элементу в обращенном контейнере `multimap`.|  
|[rend](#rend)|Возвращает итератор, который обращается к месту, следующему за последним элементом в обращенном контейнере `multimap`.|  
|[size](#size)|Возвращает количество элементов в контейнере `multimap`.|  
|[swap](#swap)|Выполняет обмен элементами между двумя объектами `multimap`.|  
|[upper_bound](#upper_bound)|Возвращает итератор, указывающий на первый элемент в контейнере `multimap` с ключом, который больше указанного ключа.|  
|[value_comp](#value_comp)|Функция-член возвращает объект функции, который определяет порядок элементов в `multimap` путем сравнения значения ключа.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор=](#op_eq)|Заменяет элементы `multimap` копией другого `multimap`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<map>  
  
 **Пространство имен:** std  
  
 Пары ( **ключ**, **значение**) хранятся в мультиотображении в виде объектов типа `pair`. Класс pair требует заголовка \<utility>, который автоматически включается \<map>.  
  
##  <a name="allocator_type"></a>  multimap::allocator_type  
 Тип, который представляет класс распределителя для объекта-мультиотображения.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="example"></a>Пример  
  См. пример для [get_allocator](#get_allocator) в качестве примера и использования `allocator_type`.  
  
##  <a name="begin"></a>  multimap::begin  
 Возвращает итератор, адресующий первый элемент в мультиотображении.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Двунаправленный итератор, адресующий первый элемент в мультиотображении или положение после пустого мультиотображения.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_begin.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multimap <int, int> m1;  
  
   multimap <int, int> :: iterator m1_Iter;  
   multimap <int, int> :: const_iterator m1_cIter;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 0, 0 ) );  
   m1.insert ( Int_Pair ( 1, 1 ) );  
   m1.insert ( Int_Pair ( 2, 4 ) );  
  
   m1_cIter = m1.begin ( );  
   cout << "The first element of m1 is " << m1_cIter -> first << endl;  
  
   m1_Iter = m1.begin ( );  
   m1.erase ( m1_Iter );  
  
   // The following 2 lines would err as the iterator is const  
   // m1_cIter = m1.begin ( );  
   // m1.erase ( m1_cIter );  
  
   m1_cIter = m1.begin( );  
   cout << "First element of m1 is now " << m1_cIter -> first << endl;  
}  
```  
  
```Output  
The first element of m1 is 0  
First element of m1 is now 1  
```  
  
##  <a name="cbegin"></a>  multimap::cbegin  
 Возвращает итератор `const`, направленный на первый элемент в диапазоне.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор двунаправленного доступа `const`, который указывает на первый элемент диапазона или расположение прямо за концом пустого диапазона (`cbegin() == cend()` для пустого диапазона).  
  
### <a name="remarks"></a>Примечания  
 Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.  
  
 Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В примере `Container` следует рассматривать как изменяемый (не-`const`) контейнер любого вида, который поддерживает `begin()` и `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="cend"></a>  multimap::cend  
 Возвращает итератор `const`, который обращается к месту, следующему сразу за последним элементом в диапазоне.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор двунаправленного доступа `const`, который указывает на позицию сразу за концом диапазона.  
  
### <a name="remarks"></a>Примечания  
 `cend` используется для проверки того, прошел ли итератор конец диапазона.  
  
 Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В примере `Container` следует рассматривать как изменяемый (не-`const`) контейнер любого вида, который поддерживает `end()` и `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.  
  
##  <a name="clear"></a>  multimap::clear  
 Стирает все элементы мультиотображения.  
  
```  
void clear();
```  
  
### <a name="example"></a>Пример  
  В следующем примере иллюстрируется использование функции-члена multimap::clear.  
  
```  
// multimap_clear.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap<int, int> m1;  
   multimap<int, int>::size_type i;  
   typedef pair<int, int> Int_Pair;  
  
   m1.insert(Int_Pair(1, 1));  
   m1.insert(Int_Pair(2, 4));  
  
   i = m1.size();  
   cout << "The size of the multimap is initially "  
        << i << "." << endl;  
  
   m1.clear();  
   i = m1.size();  
   cout << "The size of the multimap after clearing is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The size of the multimap is initially 2.  
The size of the multimap after clearing is 0.  
```  
  
##  <a name="const_iterator"></a>  multimap::const_iterator  
 Тип, предоставляющий двунаправленный итератор, который может читать элемент **const** в мультиотображении.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_iterator`нельзя использовать для изменения значения элемента.  
  
 `const_iterator`, определенный мультиотображением, указывает на объекты [value_type](#value_type) типа `pair`*\<***const Key**, **Type***>*. Значение ключа доступно через первый член пары, а значение сопоставленного элемента доступно через второй член пары.  
  
 Для разыменования `const_iterator` `cIter` наведите указатель на элемент в множественное сопоставление, используйте  **->**  оператор.  
  
 Для получения доступа к значению ключа для элемента используйте `cIter` -> **first**, что эквивалентно (\* `cIter`). **first**. Для получения доступа к значению сопоставленных данных элемента используйте `cIter` -> **second**, что эквивалентно (\* `cIter`). **second**.  
  
### <a name="example"></a>Пример  
  См. пример для [begin](#begin) в качестве примера использования `const_iterator`.  
  
##  <a name="const_pointer"></a>  multimap::const_pointer  
 Тип, предоставляющий указатель на элемент **const** в мультиотображении.  
  
```  
typedef typename allocator_type::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_pointer`нельзя использовать для изменения значения элемента.  
  
 В большинстве случаев для доступа к элементам в объекте-мультиотображении следует использовать [iterator](#iterator).  
  
##  <a name="const_reference"></a>  multimap::const_reference  
 Тип, который предоставляет ссылку на элемент **const**, хранящийся в мультиотображении, для чтения и выполнения операций **const**.  
  
```  
typedef typename allocator_type::const_reference const_reference;  
```  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_const_ref.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
  
   // Declare and initialize a const_reference &Ref1   
   // to the key of the first element  
   const int &Ref1 = ( m1.begin( ) -> first );  
  
   // The following line would cause an error because the   
   // non-const_reference cannot be used to access the key  
   // int &Ref1 = ( m1.begin( ) -> first );  
  
   cout << "The key of the first element in the multimap is "  
        << Ref1 << "." << endl;  
  
   // Declare and initialize a reference &Ref2   
   // to the data value of the first element  
   int &Ref2 = ( m1.begin( ) -> second );  
  
   cout << "The data value of the first element in the multimap is "  
        << Ref2 << "." << endl;  
}  
```  
  
```Output  
The key of the first element in the multimap is 1.  
The data value of the first element in the multimap is 10.  
```  
  
##  <a name="const_reverse_iterator"></a>  multimap::const_reverse_iterator  
 Тип, предоставляющий ссылку на двунаправленный итератор, который может читать любые элементы **const** в мультиотображении.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_reverse_iterator` не может изменять значение элемента и используется для перебора мультиотображения в обратном порядке.  
  
 `const_reverse_iterator`, определенный мультиотображением, указывает на объекты [value_type](#value_type) типа `pair`*\<***const Key**, **Type***>*. Значение ключа доступно через первый член пары, а значение сопоставленного элемента доступно через второй член пары.  
  
 Для разыменования `const_reverse_iterator` `crIter` наведите указатель на элемент в множественное сопоставление, используйте  **->**  оператор.  
  
 Для получения доступа к значению ключа для элемента используйте `crIter` -> **first**, что эквивалентно (\* `crIter`). **first**. Для получения доступа к значению сопоставленных данных элемента используйте `crIter` -> **second**, что эквивалентно (\* `crIter`). **first**.  
  
### <a name="example"></a>Пример  
  См. пример для [rend](#rend) в качестве примера объявления и использования `const_reverse_iterator`.  
  
##  <a name="count"></a>  multimap::count  
 Возвращает число элементов в мультиотображении, ключи которых совпадают с ключом, заданным параметром.  
  
```  
size_type count(const Key& key) const;
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ для сравнения с ключами элементов мультиотображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, ключи сортировки которых совпадают с ключом параметра. 0, если мультиотображение не содержит ни одного элемента с совпадающим ключом.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает число элементов в диапазоне  
  
 [ `lower_bound` (_ *Key* ), `upper_bound` (\_ *Key* ) )  
  
 имеющий значение ключа `key`.  
  
### <a name="example"></a>Пример  
  В следующем примере демонстрируется использование функции-члена multimap::count.  
  
```  
// multimap_count.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
    using namespace std;  
    multimap<int, int> m1;  
    multimap<int, int>::size_type i;  
    typedef pair<int, int> Int_Pair;  
  
    m1.insert(Int_Pair(1, 1));  
    m1.insert(Int_Pair(2, 1));  
    m1.insert(Int_Pair(1, 4));  
    m1.insert(Int_Pair(2, 1));  
  
    // Elements do not need to have unique keys in multimap,  
    // so duplicates are allowed and counted  
    i = m1.count(1);  
    cout << "The number of elements in m1 with a sort key of 1 is: "  
         << i << "." << endl;  
  
    i = m1.count(2);  
    cout << "The number of elements in m1 with a sort key of 2 is: "  
         << i << "." << endl;  
  
    i = m1.count(3);  
    cout << "The number of elements in m1 with a sort key of 3 is: "  
         << i << "." << endl;  
}  
```  
  
```Output  
The number of elements in m1 with a sort key of 1 is: 2.  
The number of elements in m1 with a sort key of 2 is: 2.  
The number of elements in m1 with a sort key of 3 is: 0.  
```  
  
##  <a name="crbegin"></a>  multimap::crbegin  
 Возвращает константный итератор, адресующий первый элемент в обратном мультиотображении.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный обратный двунаправленный итератор, адресующий первый элемент в обратном [мультиотображении](../standard-library/multimap-class.md) или адресующий то, что было последним элементом в `multimap` до замены его порядка на противоположный.  
  
### <a name="remarks"></a>Примечания  
 `crbegin` используется с обратным `multimap` так же, как [begin](#begin) используется с обычным `multimap`.  
  
 Если возвращаемое значение `crbegin`, то объект `multimap` невозможно изменить.  
  
 `crbegin` можно использовать для перебора `multimap` в обратном порядке.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_crbegin.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
  
   multimap <int, int> :: const_reverse_iterator m1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
   m1.insert ( Int_Pair ( 3, 30 ) );  
  
   m1_crIter = m1.crbegin( );  
   cout << "The first element of the reversed multimap m1 is "  
        << m1_crIter -> first << "." << endl;  
}  
```  
  
```Output  
The first element of the reversed multimap m1 is 3.  
```  
  
##  <a name="crend"></a>  multimap::crend  
 Возвращает константный итератор, адресующий положение после последнего элемента в обратном мультиотображении.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном [мультиотображении](../standard-library/multimap-class.md) (положение, которое предшествовало первому элементу в `multimap` до изменения его порядка на противоположный).  
  
### <a name="remarks"></a>Примечания  
 `crend` используется с обратным `multimap` так же, как [multimap::end](#end) используется с обычным `multimap`.  
  
 Если возвращаемое значение `crend`, то объект `multimap` невозможно изменить.  
  
 `crend` используется, чтобы проверить, достиг ли итератор конца `multimap`.  
  
 Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_crend.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
  
   multimap <int, int> :: const_reverse_iterator m1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
   m1.insert ( Int_Pair ( 3, 30 ) );  
  
   m1_crIter = m1.crend( );  
   m1_crIter--;  
   cout << "The last element of the reversed multimap m1 is "  
        << m1_crIter -> first << "." << endl;  
}  
```  
  
```Output  
The last element of the reversed multimap m1 is 1.  
```  
  
##  <a name="difference_type"></a>  multimap::difference_type  
 Целочисленный тип со знаком, который можно использовать для представления числа элементов в мультиотображении в диапазоне между элементами, на которые указывают итераторы.  
  
```  
typedef typename allocator_type::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `difference_type` — тип, возвращаемый при вычитании или приращении через итераторы контейнера. `difference_type` Обычно используется для представления количества элементов в диапазоне [*первый*, *последний*) между итераторами `first` и `last`, содержит элемент, который указывает по `first` и диапазон элементов, но не включающую, элемент, на который указывает `last`.  
  
 Обратите внимание, что хотя `difference_type` доступен для всех итераторов, удовлетворяющих требованиям итератора ввода, что включает класс двунаправленных итераторов, поддерживаемых обратимыми контейнерами, такими как набор, вычитание между итераторами поддерживается лишь итераторами произвольного доступа, предоставляемыми контейнерами произвольного доступа, такими как вектор.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <map>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 2, 20 ) );  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 3, 20 ) );  
  
   // The following will insert as multimap keys are not unique  
   m1.insert ( Int_Pair ( 2, 30 ) );     
  
   multimap <int, int>::iterator m1_Iter, m1_bIter, m1_eIter;     
   m1_bIter = m1.begin( );  
   m1_eIter = m1.end( );  
  
   // Count the number of elements in a multimap  
   multimap <int, int>::difference_type  df_count = 0;  
   m1_Iter = m1.begin( );  
   while ( m1_Iter != m1_eIter )  
   {  
      df_count++;  
      m1_Iter++;  
   }  
  
   cout << "The number of elements in the multimap m1 is: "   
        << df_count << "." << endl;  
}  
```  
  
```Output  
The number of elements in the multimap m1 is: 4.  
```  
  
##  <a name="emplace"></a>  multimap::emplace  
 Вставляет элемент, созданный на месте (операции копирования или перемещения не выполняются).  
  
```  
template <class... Args>  
iterator emplace(Args&&... args);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|`args`|Аргументы, передаваемые для создания элемента, вставляемого в мультиотображение.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий на вновь вставленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает недействительными никакие ссылки на элементы контейнера, но она может сделать недействительными все итераторы к контейнеру.  
  
 Если во время вставки создается исключение, контейнер не изменяется и исключение создается повторно.  
  
 [value_type](../standard-library/map-class.md#value_type) элемента — это pair, поэтому значением элемента будет упорядоченная пара, первый компонент которой равен значению ключа, а второй — значению данных элемента.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_emplace.cpp  
// compile with: /EHsc  
#include <map>  
#include <string>  
#include <iostream>  
  
using namespace std;  
  
template <typename M> void print(const M& m) {  
    cout << m.size() << " elements: " << endl;  
  
    for (const auto& p : m) {  
        cout << "(" << p.first <<  "," << p.second << ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    multimap<string, string> m1;  
  
    m1.emplace("Anna", "Accounting");  
    m1.emplace("Bob", "Accounting");  
    m1.emplace("Carmine", "Engineering");  
  
    cout << "multimap modified, now contains ";  
    print(m1);  
    cout << endl;  
  
    m1.emplace("Bob", "Engineering");  
  
    cout << "multimap modified, now contains ";  
    print(m1);  
    cout << endl;  
}  
  
```  
  
##  <a name="emplace_hint"></a>  multimap::emplace_hint  
 Вставляет элемент, созданный на месте (операции копирования или перемещения не выполняются) с подсказкой размещения.  
  
```  
template <class... Args>  
iterator emplace_hint(
    const_iterator where,  
    Args&&... args);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|`args`|Аргументы, передаваемые для создания элемента, вставляемого в мультиотображение.|  
|`where`|Место начала поиска правильной точки вставки. (Если эта точка находится непосредственно перед `where`, вставка может быть выполнена в постоянном времени с поправкой на амортизацию, а не в логарифмическом времени.)|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий на вновь вставленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает недействительными никакие ссылки на элементы контейнера, но она может сделать недействительными все итераторы к контейнеру.  
  
 Если во время размещения создается исключение, состояние контейнера не изменяется.  
  
 [value_type](../standard-library/map-class.md#value_type) элемента — это pair, поэтому значением элемента будет упорядоченная пара, первый компонент которой равен значению ключа, а второй — значению данных элемента.  
  
 Пример кода см. в разделе [map::emplace_hint](../standard-library/map-class.md#emplace_hint).  
  
##  <a name="empty"></a>  multimap::empty  
 Проверяет, что мультиотображение пусто.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если мультиотображение пустое; в противном случае **false**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_empty.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1, m2;  
  
   typedef pair <int, int> Int_Pair;  
   m1.insert ( Int_Pair ( 1, 1 ) );  
  
   if ( m1.empty( ) )  
      cout << "The multimap m1 is empty." << endl;  
   else  
      cout << "The multimap m1 is not empty." << endl;  
  
   if ( m2.empty( ) )  
      cout << "The multimap m2 is empty." << endl;  
   else  
      cout << "The multimap m2 is not empty." << endl;  
}  
```  
  
```Output  
The multimap m1 is not empty.  
The multimap m2 is empty.  
```  
  
##  <a name="end"></a>  multimap::end  
 Возврат итератора после конца.  
  
```  
const_iterator end() const;

 
 
iterator end();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор после конца. Если мультикарта пуста, то `multimap::end() == multimap::begin()`.  
  
### <a name="remarks"></a>Примечания  
 **end** используется для проверки, прошел ли итератор конец своего мультиотображения.  
  
 Не следует сбрасывать ссылку у значения, возвращаемого **end**.  
  
 Пример кода см. в разделе [multimap::find](#find).  
  
##  <a name="equal_range"></a>  multimap::equal_range  
 Находит диапазон элементов, где ключ элемента соответствует заданному значению.  
  
```  
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Аргумент-ключ для сравнения с ключом сортировки элемента из мультиотображения, в котором выполняется поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Пара итераторов, первый из которых является [lower_bound](#lower_bound) ключа, а второй — [upper_bound](#upper_bound) ключа.  
  
 Для доступа к первому итератору пары `pr`, возвращаемому функцией-членом, используйте `pr`. **first**, а для разыменования итератора нижней границы используйте \*(`pr`. **first**). Для доступа к второму итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **second**, а для разыменования итератора верхней границы используйте \*(`pr`. **second**).  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_equal_range.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   typedef multimap <int, int, less<int> > IntMMap;  
   IntMMap m1;  
   multimap <int, int> :: const_iterator m1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
   m1.insert ( Int_Pair ( 3, 30 ) );  
  
   pair <IntMMap::const_iterator, IntMMap::const_iterator> p1, p2;  
   p1 = m1.equal_range( 2 );  
  
   cout << "The lower bound of the element with "  
        << "a key of 2 in the multimap m1 is: "  
        << p1.first -> second << "." << endl;  
  
   cout << "The upper bound of the element with "  
        << "a key of 2 in the multimap m1 is: "  
        << p1.second -> second << "." << endl;  
  
   // Compare the upper_bound called directly   
   m1_RcIter = m1.upper_bound( 2 );  
  
   cout << "A direct call of upper_bound( 2 ) gives "  
        << m1_RcIter -> second << "," << endl  
        << " matching the 2nd element of the pair"  
        << " returned by equal_range( 2 )." << endl;  
  
   p2 = m1.equal_range( 4 );  
  
   // If no match is found for the key,  
   // both elements of the pair return end( )  
   if ( ( p2.first == m1.end( ) ) && ( p2.second == m1.end( ) ) )  
      cout << "The multimap m1 doesn't have an element "  
           << "with a key less than 4." << endl;  
   else  
      cout << "The element of multimap m1 with a key >= 40 is: "  
           << p1.first -> first << "." << endl;  
}  
```  
  
```Output  
The lower bound of the element with a key of 2 in the multimap m1 is: 20.  
The upper bound of the element with a key of 2 in the multimap m1 is: 30.  
A direct call of upper_bound( 2 ) gives 30,  
 matching the 2nd element of the pair returned by equal_range( 2 ).  
The multimap m1 doesn't have an element with a key less than 4.  
```  
  
##  <a name="erase"></a>  multimap::erase  
 Удаляет элемент или диапазон элементов в мультиотображении из указанных позиций или удаляет элементы, соответствующие заданному ключу.  
  
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
 Позиция после последнего элемента для удаления.  
  
 `Key`  
 Ключевое значение элементов для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Для первых двух функций-членов это двунаправленный итератор, обозначающий первый элемент, остающийся после любых удаленных элементов, или элемент в конце сопоставления, если таких элементов нет.  
  
 Для третьей функции-члена возвращается количество элементов, которые были удалены из мультиотображения.  
  
### <a name="remarks"></a>Примечания  
 Пример кода см. в разделе [map::erase](../standard-library/map-class.md#erase).  
  
##  <a name="find"></a>  multimap::find  
 Возвращает итератор, ссылающийся на элемент в мультикарте, ключ которого эквивалентен заданному ключу.  
  
```  
iterator find(const Key& key);

 
const_iterator find(const Key& key) const;
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Значение ключа, с которым сравнивается ключ сортировки элемента из мультикарты, по которой выполняется поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, ссылающийся на положение элемента с указанным ключом или на положение после последнего элемента в мультиотображении ( `multimap::end()`), если соответствие для ключа не найдено.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор, который ссылается на элемент в мультикарте с ключом сортировки, эквивалентным ключу аргумента согласно двоичному предикату, применяющему упорядочение на основе отношения сравнения «меньше».  
  
 Если возвращаемое значение **find** назначается **const_iterator**, то объект-мультиотображение изменить нельзя. Если возвращаемое значение **find** назначается **iterator**, то объект-мультиотображение можно изменить.  
  
### <a name="example"></a>Пример  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <map>  
#include <iostream>  
#include <vector>  
#include <string>  
#include <utility>  // make_pair()  
  
using namespace std;  
  
template <typename A, typename B> void print_elem(const pair<A, B>& p) {  
    cout << "(" << p.first << ", " << p.second << ") ";  
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
    multimap<int, string> m1({ { 40, "Zr" }, { 45, "Rh" } });  
    cout << "The starting multimap m1 is (key, value):" << endl;  
    print_collection(m1);  
  
    vector<pair<int, string>> v;  
    v.push_back(make_pair(43, "Tc"));  
    v.push_back(make_pair(41, "Nb"));  
    v.push_back(make_pair(46, "Pd"));  
    v.push_back(make_pair(42, "Mo"));  
    v.push_back(make_pair(44, "Ru"));  
    v.push_back(make_pair(44, "Ru")); // attempt a duplicate  
  
    cout << "Inserting the following vector data into m1:" << endl;  
    print_collection(v);  
  
    m1.insert(v.begin(), v.end());  
  
    cout << "The modified multimap m1 is (key, value):" << endl;  
    print_collection(m1);  
    cout << endl;  
    findit(m1, 45);  
    findit(m1, 6);  
}  
  
```  
  
##  <a name="get_allocator"></a>  multimap::get_allocator  
 Возвращает копию объекта-распределителя, использованного для создания мультиотображения.  
  
```  
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Распределитель, использованный мультиотображением.  
  
### <a name="remarks"></a>Примечания  
 Распределители для класса multimap определяют, как класс управляет памятью. Распределители по умолчанию для классов контейнеров из стандартной библиотеки C++ достаточны для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_get_allocator.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int>::allocator_type m1_Alloc;  
   multimap <int, int>::allocator_type m2_Alloc;  
   multimap <int, double>::allocator_type m3_Alloc;  
   multimap <int, int>::allocator_type m4_Alloc;  
  
   // The following lines declare objects  
   // that use the default allocator.  
   multimap <int, int> m1;  
   multimap <int, int, allocator<int> > m2;  
   multimap <int, double, allocator<double> > m3;  
  
   m1_Alloc = m1.get_allocator( );  
   m2_Alloc = m2.get_allocator( );  
   m3_Alloc = m3.get_allocator( );  
  
   cout << "The number of integers that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << m2.max_size( ) << ".\n" << endl;  
  
   cout << "The number of doubles that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << m3.max_size( ) <<  ".\n" << endl;  
  
   // The following line creates a multimap m4  
   // with the allocator of multimap m1.  
   map <int, int> m4( less<int>( ), m1_Alloc );  
  
   m4_Alloc = m4.get_allocator( );  
  
   // Two allocators are interchangeable if  
   // storage allocated from each can be  
   // deallocated via the other  
   if( m1_Alloc == m4_Alloc )  
   {  
      cout << "The allocators are interchangeable."  
           << endl;  
   }  
   else     
   {  
      cout << "The allocators are not interchangeable."  
           << endl;  
   }  
}  
```  
  
##  <a name="insert"></a>  multimap::insert  
 Вставляет элемент или диапазон элементов в множественное сопоставление.  
  
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
|`Val`|Значение элемента, вставляемого в множественное сопоставление.|  
|`Where`|Место начала поиска правильной точки вставки. (Если эта точка находится непосредственно перед `Where`, вставка может быть выполнена в постоянном времени с поправкой на амортизацию, а не в логарифмическом времени.)|  
|`ValTy`|Параметр-шаблон, определяющий тип аргумента, с помощью которого сопоставление формирует элемент типа [value_type`Val` и точно пересылает ](../standard-library/map-class.md#value_type) в качестве аргумента.|  
|`First`|Позиция первого элемента, который следует скопировать.|  
|`Last`|Позиция непосредственно перед последним элементом, который следует скопировать.|  
|`InputIterator`|Аргумент функции-шаблона, который соответствует требованиям [итератора ввода](../standard-library/input-iterator-tag-struct.md), указывающего на элементы типа, которые можно использовать для создания объектов [value_type](../standard-library/map-class.md#value_type).|  
|`IList`|[initializer_list](../standard-library/initializer-list.md), из которого нужно скопировать элементы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одноэлементные функции-члены (1) и (2) возвращают итератор в позиции, где был вставлен новый элемент.  
  
 Одноэлементные функции-члены с подсказкой (3) и (4) возвращают итератор, указывающий на позицию, где был вставлен новый элемент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не делает никакие указатели или ссылки недействительными, но она может сделать недействительными все итераторы контейнера.  
  
 Если во время вставки одного элемента вызывается исключение, состояние контейнера не изменяется. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.  
  
 [value_type](../standard-library/map-class.md#value_type) контейнера — это определение типа, который принадлежит контейнеру. Для сопоставления `multimap<K, V>::value_type` — это `pair<const K, V>`. Значение элемента — это упорядоченная пара, в которой первый компонент эквивалентен значению ключа, а второй компонент — значению данных элемента.  
  
 Функция-член с диапазоном (5) вставляет последовательность значений элементов в множественное сопоставление, соответствующее каждому элементу, адресованному итератором в диапазоне `[First, Last)`. Следовательно, `Last` не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `m.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `m`.  
  
 Функция-член списка инициализатора (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в сопоставление.  
  
 Для вставки элемента, созданного на месте (то есть без операций копирования или перемещения), см. разделы [multimap::emplace](#emplace) и [multimap::emplace_hint](#emplace_hint).  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_insert.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
#include <string>  
#include <vector>  
#include <utility>  // make_pair()  
  
using namespace std;  
  
template <typename M> void print(const M& m) {  
    cout << m.size() << " elements: ";  
  
    for (const auto& p : m) {  
        cout << "(" << p.first << ", " << p.second << ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
  
    // insert single values   
    multimap<int, int> m1;  
    // call insert(const value_type&) version  
    m1.insert({ 1, 10 });  
    // call insert(ValTy&&) version   
    m1.insert(make_pair(2, 20));  
  
    cout << "The original key and mapped values of m1 are:" << endl;  
    print(m1);  
  
    // intentionally attempt a duplicate, single element  
    m1.insert(make_pair(1, 111));  
  
    cout << "The modified key and mapped values of m1 are:" << endl;  
    print(m1);  
  
    // single element, with hint  
    m1.insert(m1.end(), make_pair(3, 30));  
    cout << "The modified key and mapped values of m1 are:" << endl;  
    print(m1);  
    cout << endl;  
  
    // The templatized version inserting a jumbled range  
    multimap<int, int> m2;  
    vector<pair<int, int>> v;  
    v.push_back(make_pair(43, 294));  
    v.push_back(make_pair(41, 262));  
    v.push_back(make_pair(45, 330));  
    v.push_back(make_pair(42, 277));  
    v.push_back(make_pair(44, 311));  
  
    cout << "Inserting the following vector data into m2:" << endl;  
    print(v);  
  
    m2.insert(v.begin(), v.end());  
  
    cout << "The modified key and mapped values of m2 are:" << endl;  
    print(m2);  
    cout << endl;  
  
    // The templatized versions move-constructing elements  
    multimap<int, string>  m3;  
    pair<int, string> ip1(475, "blue"), ip2(510, "green");  
  
    // single element  
    m3.insert(move(ip1));  
    cout << "After the first move insertion, m3 contains:" << endl;  
    print(m3);  
  
    // single element with hint  
    m3.insert(m3.end(), move(ip2));  
    cout << "After the second move insertion, m3 contains:" << endl;  
    print(m3);  
    cout << endl;  
  
    multimap<int, int> m4;  
    // Insert the elements from an initializer_list  
    m4.insert({ { 4, 44 }, { 2, 22 }, { 3, 33 }, { 1, 11 }, { 5, 55 } });  
    cout << "After initializer_list insertion, m4 contains:" << endl;  
    print(m4);  
    cout << endl;  
}  
  
```  
  
##  <a name="iterator"></a>  multimap::iterator  
 Тип, предоставляющий двунаправленный итератор, который может читать или изменять любой элемент в мультиотображении.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 **Итератор**, определенный мультиотображением, указывает на объекты [value_type](#value_type) типа `pair`*\<***const Key**, **Type***>*. Значение ключа доступно через первый член пары, а значение сопоставленного элемента доступно через второй член пары.  
  
 Для разыменования **итератора**`Iter`, указывающего на элемент мультиотображения, используйте оператор **->**.  
  
 Для получения доступа к значению ключа для элемента используйте `Iter` -> **first**, что эквивалентно (\* `Iter`). **first**. Для получения доступа к значению сопоставленных данных элемента используйте `Iter` -> **second**, что эквивалентно (\* `Iter`). **second**.  
  
 Тип **итератор** можно использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  См. пример объявления и использования **итератора** в примере для [begin](#begin).  
  
##  <a name="key_comp"></a>  multimap::key_comp  
 Извлекает копию объекта сравнения, использованного для упорядочивания ключей в мультиотображении.  
  
```  
key_compare key_comp() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает объект-функцию, которую мультиотображение использует для упорядочивания своих элементов.  
  
### <a name="remarks"></a>Примечания  
 Хранимый объект определяет функцию-член  
  
 **bool operator**( **const Key&** *x*, **const Key&** *y*);  
  
 которая возвращает true, если *x* строго предшествует *y* в порядке сортировки.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_key_comp.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   multimap <int, int, less<int> > m1;  
   multimap <int, int, less<int> >::key_compare kc1 = m1.key_comp( ) ;  
   bool result1 = kc1( 2, 3 ) ;  
   if( result1 == true )     
   {  
      cout << "kc1( 2,3 ) returns value of true, "  
           << "where kc1 is the function object of m1."  
           << endl;  
   }  
   else     
   {  
      cout << "kc1( 2,3 ) returns value of false "  
           << "where kc1 is the function object of m1."  
           << endl;  
   }  
  
   multimap <int, int, greater<int> > m2;  
   multimap <int, int, greater<int> >::key_compare kc2 = m2.key_comp( );  
   bool result2 = kc2( 2, 3 ) ;  
   if( result2 == true )     
   {  
      cout << "kc2( 2,3 ) returns value of true, "  
           << "where kc2 is the function object of m2."  
           << endl;  
   }  
   else     
   {  
      cout << "kc2( 2,3 ) returns value of false, "  
           << "where kc2 is the function object of m2."  
           << endl;  
   }  
}  
```  
  
```Output  
kc1( 2,3 ) returns value of true, where kc1 is the function object of m1.  
kc2( 2,3 ) returns value of false, where kc2 is the function object of m2.  
```  
  
##  <a name="key_compare"></a>  multimap::key_compare  
 Тип, который предоставляет объект-функцию, которая может сравнить два ключа сортировки для определения относительного порядка двух элементов в мультиотображении.  
  
```  
typedef Traits key_compare;  
```  
  
### <a name="remarks"></a>Примечания  
 **key_compare** является синонимом параметра-шаблона `Traits`.  
  
 Более подробную информацию по `Traits` см. в разделе [Класс multimap](../standard-library/multimap-class.md).  
  
### <a name="example"></a>Пример  
  См. пример для [key_comp](#key_comp) в качестве примера объявления и использования `key_compare`.  
  
##  <a name="key_type"></a>  multimap::key_type  
 Тип, описывающий объект-ключ сортировки, который входит в каждый элемент мультиотображения.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Примечания  
 **key_type** является синонимом для параметра-шаблона `Key`.  
  
 Более подробную информацию по `Key` см. в подразделе "Примечания" раздела [Класс multimap](../standard-library/multimap-class.md).  
  
### <a name="example"></a>Пример  
  См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.  
  
##  <a name="lower_bound"></a>  multimap::lower_bound  
 Возвращает итератор, указывающий на первый элемент в мультиотображении с ключом, который равен указанному ключу или больше его.  
  
```  
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Аргумент-ключ для сравнения с ключом сортировки элемента из мультиотображения, в котором выполняется поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор или `const_iterator`, адресующий положение элемента в мультиотображении, ключ которого равен ключу-аргументу или больше его, или адресующий положение после последнего элемента в мультиотображении, если сопоставление для ключа не найдено.  
  
 Если возвращенное значение `lower_bound` назначается `const_iterator`, то объект-мультиотображение изменить нельзя. Если возвращенное значение `lower_bound` назначается **iterator**, то объект-мультиотображение можно изменить.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_lower_bound.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
   multimap <int, int> :: const_iterator m1_AcIter, m1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
   m1.insert ( Int_Pair ( 3, 20 ) );  
   m1.insert ( Int_Pair ( 3, 30 ) );  
  
   m1_RcIter = m1.lower_bound( 2 );  
   cout << "The element of multimap m1 with a key of 2 is: "  
        << m1_RcIter -> second << "." << endl;  
  
   m1_RcIter = m1.lower_bound( 3 );  
   cout << "The first element of multimap m1 with a key of 3 is: "  
        << m1_RcIter -> second << "." << endl;  
  
   // If no match is found for the key, end( ) is returned  
   m1_RcIter = m1.lower_bound( 4 );  
  
   if ( m1_RcIter == m1.end( ) )  
      cout << "The multimap m1 doesn't have an element "  
              << "with a key of 4." << endl;  
   else  
      cout << "The element of multimap m1 with a key of 4 is: "  
                << m1_RcIter -> second << "." << endl;  
  
   // The element at a specific location in the multimap can be  
   // found using a dereferenced iterator addressing the location  
   m1_AcIter = m1.end( );  
   m1_AcIter--;  
   m1_RcIter = m1.lower_bound( m1_AcIter -> first );  
   cout << "The first element of m1 with a key matching\n"  
        << "that of the last element is: "  
        << m1_RcIter -> second << "." << endl;  
  
   // Note that the first element with a key equal to  
   // the key of the last element is not the last element  
   if ( m1_RcIter == --m1.end( ) )  
      cout << "This is the last element of multimap m1."  
           << endl;  
   else  
      cout << "This is not the last element of multimap m1."  
           << endl;  
}  
```  
  
```Output  
The element of multimap m1 with a key of 2 is: 20.  
The first element of multimap m1 with a key of 3 is: 20.  
The multimap m1 doesn't have an element with a key of 4.  
The first element of m1 with a key matching  
that of the last element is: 20.  
This is not the last element of multimap m1.  
```  
  
##  <a name="mapped_type"></a>  multimap::mapped_type  
 Тип, представляющий тип данных, хранящихся в мультиотображении.  
  
```  
typedef Type mapped_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `mapped_type` является синонимом параметра-шаблона `Type`.  
  
 Более подробную информацию по `Type` см. в разделе [Класс multimap](../standard-library/multimap-class.md).  
  
### <a name="example"></a>Пример  
  См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.  
  
##  <a name="max_size"></a>  multimap::max_size  
 Возвращает максимальную длину мультиотображения.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимально возможная длина мультиотображения.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_max_size.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
   multimap <int, int> :: size_type i;  
  
   i = m1.max_size( );  
   cout << "The maximum possible length "  
        << "of the multimap is " << i << "." << endl;  
}  
```  
  
##  <a name="multimap"></a>  multimap::multimap  
 Создает мультиотображение, которое является пустым или копией всего или части другого мультиотображения.  
  
```  
multimap();

explicit multimap(
    const Traits& Comp);

multimap(
    const Traits& Comp,  
    const Allocator& Al);

map(
    const multimap& Right);

multimap(
    multimap&& Right);

multimap(
    initializer_list<value_type> IList);

multimap(
    initializer_list<value_type> IList,  
    const Compare& Comp);

multimap(
    initializer_list<value_type> IList,  
    const Compare& Comp,   
    const Allocator& Al);

template <class InputIterator>  
multimap(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
multimap(
 InputIterator First,  
    InputIterator Last,  
    const Traits& Comp);

template <class InputIterator>  
multimap(
 InputIterator First,  
    InputIterator Last,  
    const Traits& Comp,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|`Al`|Класс распределителя памяти для использования для этого объекта-мультиотображения. Значение по умолчанию — Allocator.|  
|`Comp`|Функция сравнения типа **constTraits**, используемая для упорядочивания элементов в мультиотображении. Значение по умолчанию — **Traits**.|  
|`Right`|Сопоставление, копией которого будет создаваемое сопоставление.|  
|`First`|Положение первого элемента в диапазоне копируемых элементов.|  
|`Last`|Положение первого элемента после диапазона копируемых элементов.|  
|`IList`|Объект initializer_list, из которого копируются элементы.|  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы сохраняют тип объекта-распределителя, управляющего памятью для мультиотображения. Затем его можно получить путем вызова [get_allocator](#get_allocator). Параметр распределителя часто опускается в объявлениях классов и макросах предварительной обработки, используемых для замены альтернативных распределителей.  
  
 Все конструкторы инициализируют свои мультиотображения.  
  
 Все конструкторы сохраняют объект-функцию типа `Traits`, используемую для установления порядка ключей мультиотображения. Затем эту функцию можно получить путем вызова [key_comp](#key_comp).  
  
 Первые три конструктора указывают пустое начальное мультиотображение, второй указывает тип функции сравнения ( `Comp`) для использования при установлении порядка элементов, а третий явно указывает тип распределителя ( `Al`) для использования. Ключевое слово `explicit` подавляет некоторые виды автоматического преобразования типов.  
  
 Четвертый конструктор указывает копию мультиотображения `Right`.  
  
 Пятый конструктор указывает копию мультиотображения путем перемещения `Right`.  
  
 Шестой, седьмой и восьмой конструкторы копируют члены initializer_list.  
  
 Следующие три конструктора копируют диапазон `[First, Last)` мультиотображения с повышением точности при указании типа функции сравнения класса **Traits** и распределителя.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_ctor.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    typedef pair <int, int> Int_Pair;  
  
    // Create an empty multimap m0 of key type integer  
    multimap <int, int> m0;  
  
    // Create an empty multimap m1 with the key comparison  
    // function of less than, then insert 4 elements  
    multimap <int, int, less<int> > m1;  
    m1.insert(Int_Pair(1, 10));  
    m1.insert(Int_Pair(2, 20));  
    m1.insert(Int_Pair(3, 30));  
    m1.insert(Int_Pair(4, 40));  
  
    // Create an empty multimap m2 with the key comparison  
    // function of geater than, then insert 2 elements  
    multimap <int, int, less<int> > m2;  
    m2.insert(Int_Pair(1, 10));  
    m2.insert(Int_Pair(2, 20));  
  
    // Create a multimap m3 with the   
    // allocator of multimap m1  
    multimap <int, int>::allocator_type m1_Alloc;  
    m1_Alloc = m1.get_allocator();  
    multimap <int, int> m3(less<int>(), m1_Alloc);  
    m3.insert(Int_Pair(3, 30));  
  
    // Create a copy, multimap m4, of multimap m1  
    multimap <int, int> m4(m1);  
  
    // Create a multimap m5 by copying the range m1[ first,  last)  
    multimap <int, int>::const_iterator m1_bcIter, m1_ecIter;  
    m1_bcIter = m1.begin();  
    m1_ecIter = m1.begin();  
    m1_ecIter++;  
    m1_ecIter++;  
    multimap <int, int> m5(m1_bcIter, m1_ecIter);  
  
    // Create a multimap m6 by copying the range m4[ first,  last)  
    // and with the allocator of multimap m2  
    multimap <int, int>::allocator_type m2_Alloc;  
    m2_Alloc = m2.get_allocator();  
    multimap <int, int> m6(m4.begin(), ++m4.begin(), less<int>(), m2_Alloc);  
  
    cout << "m1 =";  
    for (auto i : m1)  
        cout << i.first << " " << i.second << ", ";  
    cout << endl;  
  
    cout << "m2 =";  
    for (auto i : m2)  
        cout << i.first << " " << i.second << ", ";  
    cout << endl;  
  
    cout << "m3 =";  
    for (auto i : m3)  
        cout << i.first << " " << i.second << ", ";  
    cout << endl;  
  
    cout << "m4 =";  
    for (auto i : m4)  
        cout << i.first << " " << i.second << ", ";  
    cout << endl;  
  
    cout << "m5 =";  
    for (auto i : m5)  
        cout << i.first << " " << i.second << ", ";  
    cout << endl;  
  
    cout << "m6 =";  
    for (auto i : m6)  
        cout << i.first << " " << i.second << ", ";  
    cout << endl;  
  
    // Create a multimap m8 by copying in an initializer_list  
    multimap<int, int> m8{ { { 1, 1 }, { 2, 2 }, { 3, 3 }, { 4, 4 } } };  
    cout << "m8: = ";  
    for (auto i : m8)  
        cout << i.first << " " << i.second << ", ";  
    cout << endl;  
  
    // Create a multimap m9 with an initializer_list and a comparator  
    multimap<int, int> m9({ { 5, 5 }, { 6, 6 }, { 7, 7 }, { 8, 8 } }, less<int>());  
    cout << "m9: = ";  
    for (auto i : m9)  
        cout << i.first << " " << i.second << ", ";  
    cout << endl;  
  
    // Create a multimap m10 with an initializer_list, a comparator, and an allocator  
    multimap<int, int> m10({ { 9, 9 }, { 10, 10 }, { 11, 11 }, { 12, 12 } }, less<int>(), m9.get_allocator());  
    cout << "m10: = ";  
    for (auto i : m10)  
        cout << i.first << " " << i.second << ", ";  
    cout << endl;  
  
}  
  
```  
  
##  <a name="op_eq"></a>  multimap::operator=  
 Заменяет элементы мультиотображения копией другого мультиотображения.  
  
```  
multimap& operator=(const multimap& right);

multimap& operator=(multimap&& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|`right`|[Мультиотображение](../standard-library/multimap-class.md), которое будет копироваться в `multimap`.|  
  
### <a name="remarks"></a>Примечания  
 После удаления всех существующих элементов в объекте `multimap` `operator=` копирует или перемещает содержимое `right` в объект `multimap`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_operator_as.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
   {  
   using namespace std;  
   multimap<int, int> v1, v2, v3;  
   multimap<int, int>::iterator iter;  
  
   v1.insert(pair<int, int>(1, 10));  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
   }  
```  
  
##  <a name="pointer"></a>  multimap::pointer  
 Тип, предоставляющий указатель на элемент мультиотображения.  
  
```  
typedef typename allocator_type::pointer pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип **pointer** может использоваться для изменения значения элемента.  
  
 В большинстве случаев для доступа к элементам в объекте-мультиотображении следует использовать [iterator](#iterator).  
  
##  <a name="rbegin"></a>  multimap::rbegin  
 Возвращает итератор, адресующий первый элемент в обратном мультиотображении.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный двунаправленный итератор, адресующий первый элемент в обратном мультиотображении или адресующий то, что было последним элементом в мультиотображении до изменения его порядка на противоположный.  
  
### <a name="remarks"></a>Примечания  
 `rbegin` используется с обратным мультиотображением так же, как [begin](#begin) используется с прямым мультиотображением.  
  
 Если возвращенное значение `rbegin` назначается `const_reverse_iterator`, то объект-мультиотображение изменить нельзя. Если возвращенное значение `rbegin` назначается `reverse_iterator`, то объект-мультиотображение можно изменить.  
  
 `rbegin` можно использовать для перебора мультиотображения в обратном порядке.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_rbegin.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
  
   multimap <int, int> :: iterator m1_Iter;  
   multimap <int, int> :: reverse_iterator m1_rIter;  
   multimap <int, int> :: const_reverse_iterator m1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
   m1.insert ( Int_Pair ( 3, 30 ) );  
  
   m1_rIter = m1.rbegin( );  
   cout << "The first element of the reversed multimap m1 is "  
        << m1_rIter -> first << "." << endl;  
  
   // begin can be used to start an iteration   
   // throught a multimap in a forward order  
   cout << "The multimap is: ";  
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)  
      cout << m1_Iter -> first << " ";  
      cout << "." << endl;  
  
   // rbegin can be used to start an iteration   
   // throught a multimap in a reverse order  
   cout << "The reversed multimap is: ";  
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)  
      cout << m1_rIter -> first << " ";  
      cout << "." << endl;  
  
   // A multimap element can be erased by dereferencing its key   
   m1_rIter = m1.rbegin( );  
   m1.erase ( m1_rIter -> first );  
  
   m1_rIter = m1.rbegin( );  
   cout << "After the erasure, the first element "  
        << "in the reversed multimap is "  
        << m1_rIter -> first << "." << endl;  
}  
```  
  
```Output  
The first element of the reversed multimap m1 is 3.  
The multimap is: 1 2 3 .  
The reversed multimap is: 3 2 1 .  
After the erasure, the first element in the reversed multimap is 2.  
```  
  
##  <a name="reference"></a>  multimap::reference  
 Тип, который предоставляет ссылку на элемент, хранящийся в мультиотображении.  
  
```  
typedef typename allocator_type::reference reference;  
```  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_ref.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
  
   // Declare and initialize a const_reference &Ref1   
   // to the key of the first element  
   const int &Ref1 = ( m1.begin( ) -> first );  
  
   // The following line would cause an error because the   
   // non-const_reference cannot be used to access the key  
   // int &Ref1 = ( m1.begin( ) -> first );  
  
   cout << "The key of first element in the multimap is "  
        << Ref1 << "." << endl;  
  
   // Declare and initialize a reference &Ref2   
   // to the data value of the first element  
   int &Ref2 = ( m1.begin( ) -> second );  
  
   cout << "The data value of first element in the multimap is "  
        << Ref2 << "." << endl;  
  
   // The non-const_reference can be used to modify the   
   // data value of the first element  
   Ref2 = Ref2 + 5;  
   cout << "The modified data value of first element is "  
        << Ref2 << "." << endl;  
}  
```  
  
```Output  
The key of first element in the multimap is 1.  
The data value of first element in the multimap is 10.  
The modified data value of first element is 15.  
```  
  
##  <a name="rend"></a>  multimap::rend  
 Возвращает итератор, адресующий положение после последнего элемента в обратном мультиотображении.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном мультиотображении (положение, которое предшествовало первому элементу в мультиотображении до изменения его порядка на противоположный).  
  
### <a name="remarks"></a>Примечания  
 `rend` используется с обратным мультиотображением так же, как [end](../standard-library/map-class.md#end) используется с обычным мультиотображением.  
  
 Если возвращенное значение `rend` назначается `const_reverse_iterator`, то объект-мультиотображение изменить нельзя. Если возвращенное значение `rend` назначается `reverse_iterator`, то объект-мультиотображение можно изменить.  
  
 `rend` можно использовать для проверки, достиг ли обратный итератор конца своего мультиотображения.  
  
 Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_rend.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
  
   multimap <int, int> :: iterator m1_Iter;  
   multimap <int, int> :: reverse_iterator m1_rIter;  
   multimap <int, int> :: const_reverse_iterator m1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
   m1.insert ( Int_Pair ( 3, 30 ) );  
  
   m1_rIter = m1.rend( );  
   m1_rIter--;  
   cout << "The last element of the reversed multimap m1 is "  
        << m1_rIter -> first << "." << endl;  
  
   // begin can be used to start an iteration   
   // throught a multimap in a forward order  
   cout << "The multimap is: ";  
   for ( m1_Iter = m1.begin( ) ; m1_Iter != m1.end( ); m1_Iter++)  
      cout << m1_Iter -> first << " ";  
      cout << "." << endl;  
  
   // rbegin can be used to start an iteration   
   // throught a multimap in a reverse order  
   cout << "The reversed multimap is: ";  
   for ( m1_rIter = m1.rbegin( ) ; m1_rIter != m1.rend( ); m1_rIter++)  
      cout << m1_rIter -> first << " ";  
      cout << "." << endl;  
  
   // A multimap element can be erased by dereferencing to its key   
   m1_rIter = --m1.rend( );  
   m1.erase ( m1_rIter -> first );  
  
   m1_rIter = m1.rend( );  
   m1_rIter--;  
   cout << "After the erasure, the last element "  
        << "in the reversed multimap is "  
        << m1_rIter -> first << "." << endl;  
}  
```  
  
```Output  
The last element of the reversed multimap m1 is 1.  
The multimap is: 1 2 3 .  
The reversed multimap is: 3 2 1 .  
After the erasure, the last element in the reversed multimap is 2.  
```  
  
##  <a name="reverse_iterator"></a>  multimap::reverse_iterator  
 Тип, предоставляющий двунаправленный итератор, который может читать и изменять элемент в обратном мультиотображении.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `reverse_iterator` используется для перебора мультиотображения в обратном порядке.  
  
 `reverse_iterator`, определенный мультиотображением, указывает на объекты [value_type](#value_type) типа `pair`*\<***const Key**, **Type***>*. Значение ключа доступно через первый член пары, а значение сопоставленного элемента доступно через второй член пары.  
  
 Для разыменования `reverse_iterator` `rIter` наведите указатель на элемент в множественное сопоставление, используйте оператор "->".  
  
 Для получения доступа к значению ключа для элемента используйте `rIter` -> **first**, что эквивалентно (\* `rIter`). **first**. Для получения доступа к значению сопоставленных данных элемента используйте `rIter` -> **second**, что эквивалентно (\* `rIter`). **first**.  
  
### <a name="example"></a>Пример  
  См. пример для [rbegin](#rbegin) в качестве примера объявления и использования `reverse_iterator`.  
  
##  <a name="size"></a>  multimap::size  
 Возвращает число элементов в мультиотображении.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина мультиотображения.  
  
### <a name="example"></a>Пример  
  В следующем примере демонстрируется использование функции-члена multimap::size.  
  
```  
// multimap_size.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    multimap<int, int> m1, m2;  
    multimap<int, int>::size_type i;  
    typedef pair<int, int> Int_Pair;  
  
    m1.insert(Int_Pair(1, 1));  
    i = m1.size();  
    cout << "The multimap length is " << i << "." << endl;  
  
    m1.insert(Int_Pair(2, 4));  
    i = m1.size();  
    cout << "The multimap length is now " << i << "." << endl;  
}  
```  
  
```Output  
The multimap length is 1.  
The multimap length is now 2.  
```  
  
##  <a name="size_type"></a>  multimap::size_type  
 Тип целого числа без знака, который подсчитывает число элементов в мультиотображении.  
  
```  
typedef typename allocator_type::size_type size_type;  
```  
  
### <a name="example"></a>Пример  
  См. пример для [size](#size) в качестве примера объявления и использования `size_type`  
  
##  <a name="swap"></a>  multimap::swap  
 Обмен элементами между двумя мультиотображениями.  
  
```  
void swap(
    multimap<Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Мультиотображение, предоставляющее элементы для обмена, или мультиотображение, элементы которого должны быть заменены на элементы мультиотображения `left`.  
  
### <a name="remarks"></a>Примечания  
 Функция-член не делает недействительным ссылки, указатели или итераторы, обозначающие элементы в двух мультиотображениях, для которых выполняется обмен элементами.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_swap.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1, m2, m3;  
   multimap <int, int>::iterator m1_Iter;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
   m1.insert ( Int_Pair ( 3, 30 ) );  
   m2.insert ( Int_Pair ( 10, 100 ) );  
   m2.insert ( Int_Pair ( 20, 200 ) );  
   m3.insert ( Int_Pair ( 30, 300 ) );  
  
   cout << "The original multimap m1 is:";  
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )  
      cout << " " << m1_Iter -> second;  
   cout   << "." << endl;  
  
   // This is the member function version of swap  
   m1.swap( m2 );  
  
   cout << "After swapping with m2, multimap m1 is:";  
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )  
      cout << " " << m1_Iter -> second;  
   cout  << "." << endl;  
  
   // This is the specialized template version of swap  
   swap( m1, m3 );  
  
   cout << "After swapping with m3, multimap m1 is:";  
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )  
      cout << " " << m1_Iter -> second;  
   cout   << "." << endl;  
}  
```  
  
```Output  
The original multimap m1 is: 10 20 30.  
After swapping with m2, multimap m1 is: 100 200.  
After swapping with m3, multimap m1 is: 300.  
```  
  
##  <a name="upper_bound"></a>  multimap::upper_bound  
 Возвращает итератор, указывающий на первый элемент в мультиотображении с ключом, который больше указанного ключа.  
  
```  
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Аргумент-ключ для сравнения с ключом сортировки элемента из мультиотображения, в котором выполняется поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор или `const_iterator`, адресующий положение элемента в мультиотображении с ключом, который равен ключу-аргументу или больше него, либо адресует положение после последнего элемента в мультиотображении, если соответствие для ключа не найдено.  
  
 Если возвращенное значение назначается `const_iterator`, то объект-мультиотображение изменить нельзя. Если возвращенное значение назначается **iterator**, то объект-мультиотображение можно изменить.  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_upper_bound.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multimap <int, int> m1;  
   multimap <int, int> :: const_iterator m1_AcIter, m1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   m1.insert ( Int_Pair ( 1, 10 ) );  
   m1.insert ( Int_Pair ( 2, 20 ) );  
   m1.insert ( Int_Pair ( 3, 30 ) );  
   m1.insert ( Int_Pair ( 3, 40 ) );  
  
   m1_RcIter = m1.upper_bound( 1 );  
   cout << "The 1st element of multimap m1 with "  
        << "a key greater than 1 is: "  
        << m1_RcIter -> second << "." << endl;  
  
   m1_RcIter = m1.upper_bound( 2 );  
   cout << "The first element of multimap m1 with a key "  
        << " greater than 2 is: "  
        << m1_RcIter -> second << "." << endl;  
  
   // If no match is found for the key, end( ) is returned  
   m1_RcIter = m1.lower_bound( 4 );  
  
   if ( m1_RcIter == m1.end( ) )  
      cout << "The multimap m1 doesn't have an element "  
           << "with a key of 4." << endl;  
   else  
      cout << "The element of multimap m1 with a key of 4 is: "  
           << m1_RcIter -> second << "." << endl;  
  
   // The element at a specific location in the multimap can be  
   // found using a derefenced iterator addressing the location  
   m1_AcIter = m1.begin( );  
   m1_RcIter = m1.upper_bound( m1_AcIter -> first );  
   cout << "The first element of m1 with a key greater than\n"  
        << "that of the initial element of m1 is: "  
        << m1_RcIter -> second << "." << endl;  
}  
```  
  
```Output  
The 1st element of multimap m1 with a key greater than 1 is: 20.  
The first element of multimap m1 with a key  greater than 2 is: 30.  
The multimap m1 doesn't have an element with a key of 4.  
The first element of m1 with a key greater than  
that of the initial element of m1 is: 20.  
```  
  
##  <a name="value_comp"></a>  multimap::value_comp  
 Функция-член возвращает объект-функцию, которая определяет порядок элементов в мультиотображении путем сравнения их значений ключа.  
  
```  
value_compare value_comp() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает объект-функцию сравнения, которую мультиотображение использует для упорядочения своих элементов.  
  
### <a name="remarks"></a>Примечания  
 Для мультиотображения *m*, если два элемента *e*1( *k*1, *d*1) и *e*2( *k*2, `d`2) являются объектами типа `value_type`, где *k*1 и *k*2 — их ключи типа `key_type`, а `d`1 и `d`2 — их данные типа `mapped_type`, то *m.*`value_comp`( *e*1, *e*2) эквивалентно *m.*`key_comp`( *k*1, *k*2).  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_value_comp.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   multimap <int, int, less<int> > m1;  
   multimap <int, int, less<int> >::value_compare vc1 = m1.value_comp( );  
   multimap<int,int>::iterator Iter1, Iter2;  
  
   Iter1= m1.insert ( multimap <int, int> :: value_type ( 1, 10 ) );  
   Iter2= m1.insert ( multimap <int, int> :: value_type ( 2, 5 ) );  
  
   if( vc1( *Iter1, *Iter2 ) == true )     
   {  
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."  
           << endl;  
   }  
   else     
   {  
      cout << "The element ( 1,10 ) does "  
           << "not precede the element ( 2,5 )."  
           << endl;  
   }  
  
   if( vc1( *Iter2, *Iter1 ) == true )     
   {  
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."  
           << endl;  
   }  
   else     
   {  
      cout << "The element ( 2,5 ) does "  
           << "not precede the element ( 1,10 )."  
           << endl;  
   }  
}  
```  
  
```Output  
The element ( 1,10 ) precedes the element ( 2,5 ).  
The element ( 2,5 ) does not precede the element ( 1,10 ).  
```  
  
##  <a name="value_type"></a>  multimap::value_type  
 Тип, представляющий тип объекта, который хранится в виде элемента в мультиотображении.  
  
```  
typedef pair<const Key, Type> value_type;  
```  
  
### <a name="example"></a>Пример  
  
```cpp  
// multimap_value_type.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   typedef pair <const int, int> cInt2Int;  
   multimap <int, int> m1;  
   multimap <int, int> :: key_type key1;  
   multimap <int, int> :: mapped_type mapped1;  
   multimap <int, int> :: value_type value1;  
   multimap <int, int> :: iterator pIter;  
  
   // value_type can be used to pass the correct type  
   // explicitely to avoid implicit type conversion  
   m1.insert ( multimap <int, int> :: value_type ( 1, 10 ) );  
  
   // Compare another way to insert objects into a hash_multimap  
   m1.insert ( cInt2Int ( 2, 20 ) );  
  
   // Initializing key1 and mapped1  
   key1 = ( m1.begin( ) -> first );  
   mapped1 = ( m1.begin( ) -> second );  
  
   cout << "The key of first element in the multimap is "  
        << key1 << "." << endl;  
  
   cout << "The data value of first element in the multimap is "  
        << mapped1 << "." << endl;  
  
   // The following line would cause an error because  
   // the value_type is not assignable  
   // value1 = cInt2Int ( 4, 40 );  
  
   cout  << "The keys of the mapped elements are:";  
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )  
      cout << " " << pIter -> first;  
   cout << "." << endl;  
  
   cout  << "The values of the mapped elements are:";  
   for ( pIter = m1.begin( ) ; pIter != m1.end( ) ; pIter++ )  
      cout << " " << pIter -> second;  
   cout << "." << endl;  
}  
```  
  
```Output  
The key of first element in the multimap is 1.  
The data value of first element in the multimap is 10.  
The keys of the mapped elements are: 1 2.  
The values of the mapped elements are: 10 20.  
```  
  
## <a name="see-also"></a>См. также  
 [Члены \<map>](http://msdn.microsoft.com/en-us/7e8f0bc2-6034-40f6-9d14-76d4cef86308)   
 [Контейнеры](../cpp/containers-modern-cpp.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)

