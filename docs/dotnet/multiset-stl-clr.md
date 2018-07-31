---
title: мультинабор (STL/CLR) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset
- cliext::multiset::begin
- cliext::multiset::clear
- cliext::multiset::const_iterator
- cliext::multiset::const_reference
- cliext::multiset::const_reverse_iterator
- cliext::multiset::count
- cliext::multiset::difference_type
- cliext::multiset::empty
- cliext::multiset::end
- cliext::multiset::equal_range
- cliext::multiset::erase
- cliext::multiset::find
- cliext::multiset::generic_container
- cliext::multiset::generic_iterator
- cliext::multiset::generic_reverse_iterator
- cliext::multiset::generic_value
- cliext::multiset::insert
- cliext::multiset::iterator
- cliext::multiset::key_comp
- cliext::multiset::key_compare
- cliext::multiset::key_type
- cliext::multiset::lower_bound
- cliext::multiset::make_value
- cliext::multiset::multiset
- cliext::multiset::operator=
- cliext::multiset::rbegin
- cliext::multiset::reference
- cliext::multiset::rend
- cliext::multiset::reverse_iterator
- cliext::multiset::size
- cliext::multiset::size_type
- cliext::multiset::swap
- cliext::multiset::to_array
- cliext::multiset::upper_bound
- cliext::multiset::value_comp
- cliext::multiset::value_compare
- cliext::multiset::value_type
- cliext::multiset::operator!=
- cliext::multiset::operator<
- cliext::multiset::operator<=
- cliext::multiset::operator==
- cliext::multiset::operator>
- cliext::multiset::operator>=
dev_langs:
- C++
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- multiset class [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- map member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a6e9b02f1dde6ade6206cd61e61fae46f5dd1b8b
ms.sourcegitcommit: bad2441d1930275ff506d44759d283d94cccd1c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2018
ms.locfileid: "39376307"
---
# <a name="multiset-stlclr"></a>multiset (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины, имеющей двунаправленный доступ. Использовать контейнер `multiset` для управления последовательностью элементов как упорядоченный (почти) сбалансированного дерева узлов, каждый хранения одного элемента.  
  
 В следующем описании `GValue` совпадает со значением `GKey`, который в свою очередь является таким же, как *ключ* последний ссылочного типа, в противном случае он является `Key^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Key>  
    ref class multiset  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
### <a name="parameters"></a>Параметры  
 *Key*  
 Тип ключевой компонент элемента в управляемой последовательности.  

## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/set >  
  
 **Пространство имен:** cliext  

## <a name="declarations"></a>Объявления  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|[multiset::const_iterator (STL/CLR)](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|  
|[multiset::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|  
|[multiset::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[multiset::difference_type (STL/CLR)](#difference_type)|Тип расстояния (возможно, со знаком) между двумя элементами.|  
|[multiset::generic_container (STL/CLR)](#generic_container)|Тип универсального интерфейса для контейнера.|  
|[multiset::generic_iterator (STL/CLR)](#generic_iterator)|Тип итератора для универсального интерфейса для контейнера.|  
|[multiset::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[multiset::generic_value (STL/CLR)](#generic_value)|Тип элемента для универсального интерфейса для контейнера.|  
|[multiset::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|  
|[multiset::key_compare (STL/CLR)](#key_compare)|Делегат упорядочения для двух ключей.|  
|[multiset::key_type (STL/CLR)](#key_type)|Тип ключа упорядочения.|  
|[multiset::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|  
|[multiset::reverse_iterator (STL/CLR)](#reverse_iterator)|Тип обратного итератора для управляемой последовательности.|  
|[multiset::size_type (STL/CLR)](#size_type)|Тип (неотрицательное) расстояние между двумя элементами.|  
|[multiset::value_compare (STL/CLR)](#value_compare)|Делегат упорядочения для значения двух элементов.|  
|[multiset::value_type (STL/CLR)](#value_type)|Тип элемента.|  
  
|Функция-член|Описание:|  
|---------------------|-----------------|  
|[multiset::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|  
|[multiset::clear (STL/CLR)](#clear)|Удаляет все элементы.|  
|[multiset::count (STL/CLR)](#count)|Подсчитывает элементы, соответствующие заданному ключу.|  
|[multiset::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|  
|[multiset::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|  
|[multiset::equal_range (STL/CLR)](#equal_range)|Находит диапазон, соответствующий указанному ключу.|  
|[multiset::erase (STL/CLR)](#erase)|Удаляет элементы в указанных позициях.|  
|[multiset::find (STL/CLR)](#find)|Определяет элемент, соответствующий указанному ключу.|  
|[multiset::insert (STL/CLR)](#insert)|Добавляет элементы.|  
|[multiset::key_comp (STL/CLR)](#key_comp)|Копирует делегат упорядочения для двух ключей.|  
|[multiset::lower_bound (STL/CLR)](#lower_bound)|Начало находит диапазон, соответствующий указанному ключу.|  
|[multiset::make_value (STL/CLR)](#make_value)|Создает объект значения.|  
|[multiset::multiset (STL/CLR)](#multiset)|Создает объект контейнера.|  
|[multiset::rbegin (STL/CLR)](#rbegin)|Задает начало обратной управляемой последовательности.|  
|[multiset::rend (STL/CLR)](#rend)|Задает конец обратной управляемой последовательности.|  
|[multiset::size (STL/CLR)](#size)|Подсчитывает количество элементов.|  
|[multiset::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|  
|[multiset::to_array (STL/CLR)](#to_array)|Копирует управляемой последовательности в новый массив.|  
|[multiset::upper_bound (STL/CLR)](#upper_bound)|Находит конец диапазон, соответствующий указанному ключу.|  
|[multiset::value_comp (STL/CLR)](#value_comp)|Копирует делегат упорядочения для значения двух элементов.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[multiset::operator= (STL/CLR)](#op_as)|Заменяет управляемую последовательность.|  
|[operator!= (multiset) (STL/CLR)](#op_neq)|Определяет, если `multiset` объект не равным значению другого `multiset` объекта.|  
|[operator< (multiset) (STL/CLR)](#op_lt)|Определяет, если `multiset` объект меньше другого `multiset` объекта.|  
|[operator<= (multiset) (STL/CLR)](#op_lteq)|Определяет, если `multiset` объекта меньше или равно другому `multiset` объекта.|  
|[operator== (multiset) (STL/CLR)](#op_eq)|Определяет, если `multiset` объект равен другому `multiset` объекта.|  
|[operator> (multiset) (STL/CLR)](#op_gt)|Определяет, если `multiset` объект больше, чем другой `multiset` объекта.|  
|[operator>= (multiset) (STL/CLR)](#op_gteq)|Определяет, если `multiset` объекта больше или равно другому `multiset` объекта.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание:|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Сохранить группу элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательность типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|ITree\<ключ, значение >|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает хранилище для последовательность, в которой он управляет в виде отдельных узлов. Он добавляет элементы в (почти) дерева, которое отслеживает упорядоченный путем изменения связи между узлами, никогда не копируя содержимое одного узла на другой. Это означает, что можно вставлять и удалять элементы без нарушения работы остальных элементов.  
  
 Объект Упорядочивает управляемую им последовательность путем вызова объекта хранимых делегат типа [multiset::key_compare (STL/CLR)](../dotnet/multiset-key-compare-stl-clr.md). Объект хранимой делегата можно указать при создании мультинабора; Если указать объект делегата, значение по умолчанию является сравнение `operator<(key_type, key_type)`. Доступ к этот сохраненный объект, вызвав функцию-член [multiset::key_comp (STL/CLR)](../dotnet/multiset-key-comp-stl-clr.md)`()`.  
  
 Такой объект делегата должна налагать строгое слабое упорядочение на ключах типа [multiset::key_type (STL/CLR)](../dotnet/multiset-key-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y`:  
  
 `key_comp()(X, Y)` Возвращает результат же логическое значение при каждом вызове.  
  
 Если `key_comp()(X, Y)` имеет значение true, затем `key_comp()(Y, X)` должно иметь значение false.  
  
 Если `key_comp()(X, Y)` имеет значение true, затем `X` говорят, что допускается упорядочение перед `Y`.  
  
 Если `!key_comp()(X, Y) && !key_comp()(Y, X)` имеет значение true, затем `X` и `Y` называются имеют эквивалентное упорядочение.  
  
 Для любого элемента `X` , предшествующий `Y` в управляемой последовательности, `key_comp()(Y, X)` имеет значение false. (Для объекта делегата по умолчанию, ключи никогда не уменьшаются.) В отличие от шаблона класса [(STL/CLR) задайте](../dotnet/set-stl-clr.md), объект класса шаблона `multiset` не требует, что ключи для всех элементов являются уникальными. (Два или несколько ключей может иметь соответствующий порядок.)  
  
 Каждый элемент служит в качестве клю и значение. Последовательность представлена в виде, позволяющем выполнять поиска, вставки и удаления произвольного элемента с количеством операций, пропорционально логарифму числа элементов в последовательности (логарифмическом времени). Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
 Мультинабор поддерживает Двунаправленные итераторы, это означает, что при переходе на соседние элементы, задаваемые итератор, указывающий элемент в управляемой последовательности. Специальные головной узел соответствует итератора, возвращаемого методом [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`. Итератор для достижения последнего элемента в управляемой последовательности, можно уменьшить, при его наличии. Multiset итератора, чтобы достичь головного узла можно увеличить, а затем сравнивает равным `end()`. Но нельзя переименовать итератора, возвращаемого методом `end()`.  
  
 Обратите внимание, что нельзя ссылаться на элемент мультинабора, непосредственно заданным его порядкового номера--, требующий итератор произвольного доступа.  
  
 Multiset итератор хранит дескриптор multiset узел, который в свою очередь, сохраняет дескриптор для связанного контейнера. Вы можете использовать итераторы только с свои объекты связанного контейнера. Multiset итератор остается допустимым до тех пор, пока multiset узел связан с некоторых мультинабора. Кроме того, это допустимый итератор является dereferencable — его можно использовать для доступа к или изменить значение элемента, указываемый ею--до тех пор, пока оно не равно `end()`.  
  
 Стирание или удалении элемента вызывает деструктор для сохраненному значению. Уничтожение контейнера стирает все элементы. Таким образом контейнер, тип элементов которого является ссылочным классом, гарантирует, что ни один элемент пережить контейнера. Обратите внимание, что контейнер дескрипторов не *не* уничтожить его элементов.  
  
## <a name="members"></a>Участники

## <a name="begin"></a> MULTISET::Begin (STL/CLR)
Задает начало управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator begin();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает двунаправленный итератор, указывающий на первый элемент управляемой последовательности или непосредственно за окончание пустой последовательности. Используется для получения итератора, который обозначает `current` начало управляемой последовательности, а его состояние можно изменить при изменении длины управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_begin.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mymultiset::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
```  

## <a name="clear"></a> MULTISET::Clear (STL/CLR)
Удаляет все элементы.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void clear();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член эффективно вызывает [multiset::erase (STL/CLR)](../dotnet/multiset-erase-stl-clr.md) `(` [multiset::begin (STL/CLR)](../dotnet/multiset-begin-stl-clr.md) `(),` [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md) `())`. Используется, чтобы убедиться, что управляемая последовательность пуста.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_clear.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  

## <a name="const_iterator"></a> MULTISET::const_iterator (STL/CLR)
Тип постоянного итератора для управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект неопределенного типа `T2` , можно использовать в качестве константы двунаправленного итератора для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_const_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Mymultiset::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="const_reference"></a> MULTISET::const_reference (STL/CLR)
Тип постоянной ссылки на элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает постоянную ссылку на элемент.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_const_reference.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    Mymultiset::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        Mymultiset::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
``` 

## <a name="const_reverse_iterator"></a> MULTISET::const_reverse_iterator (STL/CLR)
Тип постоянного обратного итератора для управляемой последовательности...  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект неопределенного типа `T4` , можно использовать в качестве постоянного обратного итератора для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Mymultiset::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
```  
  
## <a name="count"></a> MULTISET::Count (STL/CLR)
Определяет количество элементов, соответствующих заданному ключу.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
size_type count(key_type key);  
```  
  
#### <a name="parameters"></a>Параметры  
 *key*  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает число элементов в управляемой последовательности, которые имеют эквивалентное упорядочение с *ключ*. Используется для определения количества элементов в данный момент в управляемой последовательности, соответствующие заданному ключу.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_count.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }   
```  
  
```Output  
 a b c  
count(L'A') = 0  
count(L'b') = 1  
count(L'C') = 0  
```  
  
## <a name="difference_type"></a> MULTISET::difference_type (STL/CLR)
Типы со знаком расстояния между двумя элементами.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает число возможно отрицательное элемент.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_difference_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mymultiset::difference_type diff = 0;   
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (Mymultiset::iterator it = c1.end(); it != c1.begin(); --it)   
        --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
end()-begin() = 3  
begin()-end() = -3  
```  

## <a name="empty"></a> MULTISET::Empty (STL/CLR)
Проверяет отсутствие элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
bool empty();  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение true для пустой управляемой последовательности. Это эквивалентно [multiset::size (STL/CLR)](../dotnet/multiset-size-stl-clr.md)`() == 0`. Оно позволяет проверить, является ли пустой мультинабор.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_empty.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="end"></a> MULTISET::End (STL/CLR)
Задает конец управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator end();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает двунаправленный итератор, указывающий на место сразу за концом управляемой последовательности. Используется для получения итератора, который задает конец управляемой последовательности; его состояние не изменяется при изменении длины управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_end.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Mymultiset::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
```  

## <a name="equal_range"></a> MULTISET::equal_range (STL/CLR)
Находит диапазон, соответствующий указанному ключу.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### <a name="parameters"></a>Параметры  
 *key*  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает пару итераторов `cliext::pair<iterator, iterator>(` [multiset::lower_bound (STL/CLR)](../dotnet/multiset-lower-bound-stl-clr.md) `(key),` [multiset::upper_bound (STL/CLR)](../dotnet/multiset-upper-bound-stl-clr.md)`(key))`. Используется для определения диапазона элементов в данный момент в управляемой последовательности, соответствующие заданному ключу.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_equal_range.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
typedef Mymultiset::pair_iter_iter Pairii;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" {0}", *pair1.first);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
equal_range(L'x') empty = True  
 b  
```  

## <a name="erase"></a> MULTISET::Erase (STL/CLR)
Удаляет элементы в указанных позициях.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
size_type erase(key_type key)  
```  
  
#### <a name="parameters"></a>Параметры  
 *Первый*  
 Начало диапазона для удаления.  
  
 *key*  
 Значение ключа для удаления.  
  
 *последний*  
 Конец диапазона для удаления.  
  
 *where*  
 Подлежащий удалению элемент.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член удаляет элемент управляемой последовательности, на которые указывают *где*и возвращает итератор, указывающий на первый элемент, оставшийся после удаления элемента или [multiset::end (STL / Среда CLR)](../dotnet/multiset-end-stl-clr.md) `()` Если такого элемента не существует. Используется для удаления одного элемента.  
  
 Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`) и возвращает итератор, указывающий на первый элемент, находящийся за всеми удаленными элементами, или `end()` Если такой элемент отсутствует существует... Используется для удаления ноль или более идущих подряд элементов.  
  
 Третья функция-член удаляет любой элемент управляемой последовательности, ключ которого имеет соответствующий порядок для *ключ*и возвращает количество удаленных элементов. Используется для удаления, а также подсчитать все элементы, соответствующие заданному ключу.  
  
 Каждый элемент стирания требуется время, пропорционально логарифму числа элементов в управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_erase.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.insert(L'd');   
    c1.insert(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    Mymultiset::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }   
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  

## <a name="find"></a> MULTISET::Find (STL/CLR)
Определяет элемент, соответствующий указанному ключу.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Параметры  
 *key*  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Если хотя бы один элемент управляемой последовательности, эквивалентное упорядочение с *ключ*, функция-член возвращает итератор, обозначающий один из этих элементов; в противном случае возвращается [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md) `()`. Используется для поиска элемента в данный момент в управляемой последовательности, соответствующий указанному ключу.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_find.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
```  
  
```Output  
 a b c  
find A = False  
find b = b  
find C = False  
```  

## <a name="generic_container"></a> MULTISET::generic_container (STL/CLR)
Тип универсального интерфейса для контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef Microsoft::VisualC::StlClr::  
    ITree<GKey, GValue>  
    generic_container;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает универсальный интерфейс для этого класса контейнера шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_generic_container.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.insert(L'e');   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a b c d  
a b c d e  
```  

## <a name="generic_iterator"></a> MULTISET::generic_iterator (STL/CLR)
Тип итератора для использования с универсальный интерфейс для контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerBidirectionalIterator<generic_value>  
    generic_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип Описывает универсальные итератор, который может использоваться с универсальным интерфейсом для этого класса контейнера шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultiset::generic_iterator gcit = gc1->begin();   
    Mymultiset::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a  
```  

## <a name="generic_reverse_iterator"></a> MULTISET::generic_reverse_iterator (STL/CLR)
Тип обратного итератора для использования с универсальный интерфейс для контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value>  
    generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип Описывает универсальные Обратный итератор, который может использоваться с универсальным интерфейсом для этого класса контейнера шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultiset::generic_reverse_iterator gcit = gc1->rbegin();   
    Mymultiset::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
c  
``` 

## <a name="generic_value"></a> MULTISET::generic_value (STL/CLR)
Тип элемента для использования с универсальный интерфейс для контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект типа `GValue` , описывающий значение хранимого элемента для использования с универсальный интерфейс для этого класса контейнера шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_generic_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultiset::generic_iterator gcit = gc1->begin();   
    Mymultiset::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a  
```   

## <a name="insert"></a> MULTISET::Insert (STL/CLR)
Добавляет элементы.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *Первый*  
 Начало диапазона для вставки.  
  
 *последний*  
 Конец диапазона для вставки.  
  
 *right*  
 Перечисление для вставки.  
  
 *Val*  
 Значение ключа для вставки.  
  
 *where*  
 Место в контейнере для вставки (подсказка).  
  
### <a name="remarks"></a>Примечания  
 Каждая из функций-членов вставляет последовательности, указываемой аргументом оставшимися операндами.  
  
 Первая функция-член вставляет элемент со значением *val*и возвращает итератор, указывающий на новый вставленный элемент. Используется для вставки одного элемента.  
  
 Вторая функция-член вставляет элемент со значением *val*, с использованием *где* как подсказку (для повышения производительности) и возвращает итератор, указывающий на новый вставленный элемент. Используется для вставки один элемент, который может быть смежными на элемент, который вы знаете.  
  
 Третья функция-член вставляет последовательность [`first`, `last`). Используется для вставки ноль или более элементов, копируемых из другой последовательности.  
  
 Четвертая функция-член вставляет последовательность, назначенному с помощью *правой*. Используется для вставки описываемого перечислитель последовательности.  
  
 Вставка каждого элемента занимает время, пропорционально логарифму числа элементов в управляемой последовательности. Вставка может происходить в амортизированном константном времени, тем не менее, учитывая подсказку, которая выделяет элемент рядом курсор.  
  
### <a name="example"></a>Пример  
  
```cpp
// cliext_multiset_insert.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    System::Console::WriteLine("insert(L'x') = {0}",   
        *c1.insert(L'x'));   
  
    System::Console::WriteLine("insert(L'b') = {0}",   
        *c1.insert(L'b'));   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymultiset c2;   
    Mymultiset::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymultiset c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
 a b c  
insert(L'x') = x  
insert(L'b') = b  
 a b b c x  
insert(begin(), L'y') = y  
 a b b c x y  
 a b b c x  
 a b b c x y  
```  

## <a name="iterator"></a> MULTISET::iterator (STL/CLR)
Тип итератора для управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект неопределенного типа `T1` , можно использовать в качестве двунаправленного итератора для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Mymultiset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="key_comp"></a> MULTISET::key_comp (STL/CLR)
Копирует делегат упорядочения для двух ключей.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
key_compare^key_comp();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает делегата упорядочения, используемый для упорядочения управляемой последовательности. Используется для сравнения двух ключей.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_multiset_key_comp.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mymultiset c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  

## <a name="key_compare"></a> MULTISET::key_compare (STL/CLR)
Делегат упорядочения для двух ключей.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>  
    key_compare;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для делегата, который определяет порядок его аргументы ключа.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_key_compare.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mymultiset c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  

## <a name="key_type"></a> MULTISET::key_type (STL/CLR)
Тип ключа упорядочения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра-шаблона *ключ*.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_key_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" using key_type   
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in key_type object   
        Mymultiset::key_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
a b c  
```  

## <a name="lower_bound"></a> MULTISET::lower_bound (STL/CLR)
Начало находит диапазон, соответствующий указанному ключу.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Параметры  
 *key*  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член определяет первый элемент `X` в управляемой последовательности с эквивалентным упорядочением для *ключ*. Если такого элемента не существует, она возвращает [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`; в противном случае она возвращает итератор, указывающий `X`. Используется для поиска в начало последовательности элементов в данный момент в управляемой последовательности, которые соответствуют заданному ключу.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_lower_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*lower_bound(L'a') = {0}",   
        *c1.lower_bound(L'a'));   
    System::Console::WriteLine("*lower_bound(L'b') = {0}",   
        *c1.lower_bound(L'b'));   
    return (0);   
    }  
```  
  
```Output  
 a b c  
lower_bound(L'x')==end() = True  
*lower_bound(L'a') = a  
*lower_bound(L'b') = b  
```  

## <a name="make_value"></a> MULTISET::make_value (STL/CLR)
Создает объект значения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
static value_type make_value(key_type key);  
```  
  
#### <a name="parameters"></a>Параметры  
 *key*  
 Значение ключа для использования.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает `value_type` ключ которого *ключ*. Используется для создания объекта, подходящий для использования с несколько других функций-членов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_make_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(Mymultiset::make_value(L'a'));   
    c1.insert(Mymultiset::make_value(L'b'));   
    c1.insert(Mymultiset::make_value(L'c'));   
  
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
a b c  
```  

## <a name="multiset"></a> MULTISET::MULTISET (STL/CLR)
Создает объект контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
multiset();  
explicit multiset(key_compare^ pred);  
multiset(multiset<Key>% right);  
multiset(multiset<Key>^ right);  
template<typename InIter>  
    multisetmultiset(InIter first, InIter last);  
template<typename InIter>  
    multiset(InIter first, InIter last,  
        key_compare^ pred);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### <a name="parameters"></a>Параметры  
 *Первый*  
 Начало диапазона для вставки.  
  
 *последний*  
 Конец диапазона для вставки.  
  
 *Пред*  
 Упорядочение предикат для управляемой последовательности.  
  
 *right*  
 Объект или диапазон для вставки.  
  
### <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `multiset();`  
  
 Инициализирует управляемую последовательность не содержит элементов, со значением по умолчанию, упорядочение предикат `key_compare()`. Используется для указания пустой начальной управляемой последовательности, со значением по умолчанию, упорядочение предикат.  
  
 Конструктор:  
  
 `explicit multiset(key_compare^ pred);`  
  
 Инициализирует управляемую последовательность не содержит элементов, с помощью предикат упорядочения *pred*. Используется для указания пустой начальной управляемой последовательности, указанный предикат упорядочения.  
  
 Конструктор:  
  
 `multiset(multiset<Key>% right);`  
  
 Инициализирует управляемую последовательность последовательностью [`right.begin()`, `right.end()`), с помощью упорядочения предикат по умолчанию. Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объект-мультинабор *правой*, со значением по умолчанию, упорядочение предикат.  
  
 Конструктор:  
  
 `multiset(multiset<Key>^ right);`  
  
 Инициализирует управляемую последовательность последовательностью [`right->begin()`, `right->end()`), с помощью упорядочения предикат по умолчанию. Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объект-мультинабор *правой*, со значением по умолчанию, упорядочение предикат.  
  
 Конструктор:  
  
 `template<typename InIter> multiset(InIter first, InIter last);`  
  
 Инициализирует управляемую последовательность последовательностью [`first`, `last`), с помощью упорядочения предикат по умолчанию. Используется для создания копии другой последовательности, управляемой последовательности с помощью упорядочения предикат по умолчанию.  
  
 Конструктор:  
  
 `template<typename InIter> multiset(InIter first, InIter last, key_compare^ pred);`  
  
 Инициализирует управляемую последовательность последовательностью [`first`, `last`), с помощью предикат упорядочения *pred*. Используется для создания копии другой последовательности, с указанным предикатом упорядочения управляемой последовательности.  
  
 Конструктор:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Инициализирует управляемую последовательность последовательностью, назначенному с помощью перечислителя *правой*, со значением по умолчанию, упорядочение предикат. Используется, чтобы сделать управляемую последовательность копией другую последовательность, описываемого перечислитель, с помощью упорядочения предикат по умолчанию.  
  
 Конструктор:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Инициализирует управляемую последовательность последовательностью, назначенному с помощью перечислителя *правой*, с помощью предикат упорядочения *pred*. Используется для создания копии другой последовательности, описываемого перечислитель, с указанным предикатом упорядочения управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
// construct an empty container   
    Mymultiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mymultiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultiset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
size() = 0  
 a b c  
size() = 0  
 c b a  
 a b c  
 c b a  
 a b c  
 c b a  
 c b a  
 a b c  
```  

## <a name="op_as"></a> MULTISET::operator = (STL/CLR)
Заменяет управляемую последовательность.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
multiset<Key>% operator=(multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *right*  
 Контейнер для копирования.  
  
### <a name="remarks"></a>Примечания  
 Копирует оператор член *правой* объекту, затем возвращает `*this`. Оно позволяет заменить управляемую последовательность копией управляемой последовательности в *правой*.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_operator_as.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2 = c1;   
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
a b c  
a b c  
```  

## <a name="rbegin"></a> MULTISET::rbegin (STL/CLR)
Задает начало обратной управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает Обратный итератор, который задает последний элемент управляемой последовательности или непосредственно перед началом пустой последовательности. Таким образом, он задает `beginning` обратной последовательности. Используется для получения итератора, который обозначает `current` начало отображаемой в обратном порядке управляемой последовательности, а его состояние можно изменить при изменении длины управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_rbegin.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Mymultiset::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
```  
  
## <a name="reference"></a> MULTISET::Reference (STL/CLR)
Тип ссылки на элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает ссылку на элемент.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_reference.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    Mymultiset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Mymultiset::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="rend"></a> MULTISET::rend (STL/CLR)
Задает конец обратной управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает Обратный итератор, указывающий непосредственно перед началом управляемой последовательности. Таким образом, он задает `end` обратной последовательности. Используется для получения итератора, который обозначает `current` конец отображаемой в обратном порядке управляемой последовательности, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_rend.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mymultiset::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
```  

## <a name="reverse_iterator"></a> MULTISET::reverse_iterator (STL/CLR)
Тип обратного итератора для управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект неопределенного типа `T3` , можно использовать в качестве обратного итератора для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Mymultiset::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
```  
  
## <a name="size"></a> MULTISET::size (STL/CLR)
Подсчитывает количество элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
size_type size();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает длину управляемой последовательности. Используется для определения числа элементов в данный момент в управляемой последовательности. Если вас интересуют ли последовательность имеет ненулевой размер, см. в разделе [multiset::empty (STL/CLR)](../dotnet/multiset-empty-stl-clr.md)`()`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_size.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 0 after clearing  
size() = 2 after adding 2  
```  
  
## <a name="size_type"></a> MULTISET::size_type (STL/CLR)
Тип расстояния со знаком между двумя элементами.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает элемент неотрицательное число.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_size_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mymultiset::size_type diff = 0;   
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  

## <a name="swap"></a> MULTISET::Swap (STL/CLR)
Меняет местами содержимое двух контейнеров.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void swap(multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *right*  
 Контейнер для обмена содержимым.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами управляемые последовательности между `this` и *правой*. Она делает это в константном времени и не создает исключения. Можно использовать как быстрый способ местами содержимое двух контейнеров.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_swap.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    Mymultiset c2;   
    c2.insert(L'd');   
    c2.insert(L'e');   
    c2.insert(L'f');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
a b c  
d e f  
d e f  
a b c  
```  

## <a name="to_array"></a> MULTISET::to_array (STL/CLR)
Копирует управляемой последовательности в новый массив.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
cli::array<value_type>^ to_array();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает массив, содержащий управляемой последовательности. Вы можете использовать его для получения копии управляемой последовательности в форме массива.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_to_array.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c d  
a b c  
```  

## <a name="upper_bound"></a> MULTISET::upper_bound (STL/CLR)
Находит конец диапазон, соответствующий указанному ключу.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Параметры  
 *key*  
 Искомое значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член определяет последний элемент `X` в управляемой последовательности с эквивалентным упорядочением для *ключ*. Если такого элемента не существует или если `X` является последним элементом в управляемой последовательности, он возвращает [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`; в противном случае она возвращает итератор, указывающий первый элемент после `X`. Оно позволяет найти конец последовательности элементов в данный момент в управляемой последовательности, которые соответствуют заданному ключу.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_upper_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
```  
  
```Output  
 a b c  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = b  
*upper_bound(L'b') = c  
```  
  
## <a name="value_comp"></a> MULTISET::value_comp (STL/CLR)
Копирует делегат упорядочения для значения двух элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
value_compare^ value_comp();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает делегата упорядочения, используемый для упорядочения управляемой последовательности. Оно позволяет сравнить значения двух элементов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_value_comp.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
```  

## <a name="value_compare"></a> MULTISET::value_compare (STL/CLR)
Делегат упорядочения для значения двух элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для делегата, который определяет порядок аргументов значение.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_value_compare.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
```  

## <a name="value_type"></a> MULTISET::value_type (STL/CLR)
Тип элемента.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef generic_value value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `generic_value`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_value_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" using value_type   
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in value_type object   
        Mymultiset::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  
  
## <a name="op_neq"></a> оператор! = (multiset) (STL/CLR)
Список не равен сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Key>  
    bool operator!=(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(left == right)`. Можно использовать для тестирования ли *левой* не упорядочен так же, как *правой* при двух мультинаборах, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_operator_ne.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }   
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  

## <a name="op_lt"></a> оператор&lt; (multiset) (STL/CLR)
Список меньше, чем сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Key>  
    bool operator<(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Оператор функция возвращает значение true, если, для низшей позиции `i` для которого `!(right[i] < left[i])` верно, кроме того, `left[i] < right[i]`. В противном случае возвращается `left->size() < right->size()` можно использовать для тестирования ли *левой* упорядочен до *правой* при двух мультинаборах, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_operator_lt.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }   
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  

## <a name="op_lteq"></a> оператор&lt;= (multiset) (STL/CLR)
Меньше или равно списка сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Key>  
    bool operator<=(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(right < left)`. Можно использовать для тестирования ли *левой* не упорядочен после *правой* при двух мультинаборах, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_operator_le.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }   
```  
  
```Output  
 a b c  
 a b d  
[a b c] <= [a b c] is True  
[a b d] <= [a b c] is False  
```  

## <a name="op_eq"></a> оператор == (multiset) (STL/CLR)
Сравнение равно списка.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Key>  
    bool operator==(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает значение true, только в том случае, если управляются последовательностей *левой* и *правой* имеют одинаковую длину и для каждой позиции `i`, `left[i] ==` `right[i]`. Можно использовать для тестирования ли *левой* упорядочен так же, как *правой* при двух мультинаборах, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_operator_eq.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }   
```  
  
```Output  
 a b c  
 a b d  
[a b c] == [a b c] is True  
[a b c] == [a b d] is False  
```  

## <a name="op_gt"></a> оператор&gt; (multiset) (STL/CLR)
Список больше, чем сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Key>  
    bool operator>(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `right` `<` `left`. Можно использовать для тестирования ли *левой* упорядочен после *правой* при двух мультинаборах, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_operator_gt.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }   
```  
  
```Output  
 a b c  
 a b d  
[a b c] > [a b c] is False  
[a b d] > [a b c] is True  
```  

## <a name="op_gteq"></a> оператор&gt;= (multiset) (STL/CLR)
Список, больше или равно сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Key>  
    bool operator>=(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(left < right)`. Можно использовать для тестирования ли *левой* не упорядочен до *правой* при двух мультинаборах, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_multiset_operator_ge.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }   
```  
  
```Output  
 a b c  
 a b d  
[a b c] >= [a b c] is True  
[a b c] >= [a b d] is False  
```  