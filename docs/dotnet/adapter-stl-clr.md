---
title: адаптер (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 06/15/2018
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/adapter>
- cliext::collection_adapter
- cliext::collection_adapter::base
- cliext::collection_adapter::begin
- cliext::collection_adapter
- cliext::collection_adapter::collection_adapter
- cliext::collection_adapter::difference_type
- cliext::collection_adapter::end
- cliext::collection_adapter::iterator
- cliext::collection_adapter::key_type
- cliext::collection_adapter::mapped_type
- cliext::collection_adapter::operator=
- cliext::collection_adapter::reference
- cliext::collection_adapter::size
- cliext::collection_adapter::size_type
- cliext::collection_adapter::swap
- cliext::collection_adapter::value_type
- cliext::make_collection
- cliext::range_adapter
- cliext::operator=
- cliext::range_adapter::operator=
- cliext::range_adapter::range_adapter
dev_langs:
- C++
helpviewer_keywords:
- <adapter> header [STL/CLR]
- adapter [STL/CLR]
- <cliext/adapter> header [STL/CLR]
- collection_adapter class [STL/CLR]
- base member [STL/CLR]
- begin member [STL/CLR]
- collection_adapter member [STL/CLR]
- difference_type member [STL/CLR]
- end member [STL/CLR]
- iterator member [STL/CLR]
- key_type member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- value_type member [STL/CLR]
- make_collection function [STL/CLR]
- range_adapter class [STL/CLR]
- operator= member [STL/CLR]
- range_adapter member [STL/CLR]
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a472284df67993a65de98df7db698ea533451ea3
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079440"
---
# <a name="adapter-stlclr"></a>adapter (STL/CLR)
Заголовок STL/CLR `<cliext/adapter>` определяет два класса шаблона (`collection_adapter` и `range_adapter`) и функцию шаблона `make_collection`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <cliext/adapter>  
```  

## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext адаптер >  
  
 **Пространство имен:** cliext 
  
## <a name="declarations"></a>Объявления  
  
|Класс|Описание:|  
|-----------|-----------------|  
|[collection_adapter (STL/CLR)](#collection_adapter)|Инкапсулирует коллекцию библиотеки базовых классов (BCL) в виде диапазона.|  
|[range_adapter (STL/CLR)](#range_adapter)|Создает оболочку для диапазона как коллекция BCL.|  

|Функция|Описание:|  
|--------------|-----------------|  
|[make_collection (STL/CLR)](#make_collection)|Создает адаптер диапазона с помощью пары итератора.|   
  
## <a name="members"></a>Участники

## <a name="collection_adapter"></a> collection_adapter (STL/CLR)
Инкапсулирует коллекцию .NET для использования в качестве контейнера STL/CLR. Объект `collection_adapter` — это класс шаблона, описывающий простого объекта-контейнера STL/CLR. Он инкапсулирует интерфейс библиотеки базовых классов (BCL) и возвращает пару итератор, который позволяет управлять управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
##### <a name="parameters"></a>Параметры  
 Свер  
 Тип упакованного коллекции.  
  
### <a name="specializations"></a>Специализации  
  
|Специализация|Описание:|  
|--------------------|-----------------|  
|IEnumerable|Последовательности элементов.|  
|ICollection|Поддерживает группу элементов.|  
|Интерфейс IList|Сохраняет упорядоченную группу элементов.|  
|IDictionary|Совокупность {ключ, значение} пары.|  
|Интерфейс IEnumerable\<значение >|Последовательности типизированных элементов.|  
|ICollection\<значение >|Поддерживает группу типизированных элементов.|  
|IList\<значение >|Сохраняет упорядоченную группу типизированных элементов.|  
|IDictionary\<значение >|Поддерживает набор типизированных {ключ, значение} пары.|  
  
### <a name="members"></a>Участники  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|[collection_adapter::difference_type (STL/CLR)](#difference_type)|Тип расстояния со знаком между двумя элементами.|  
|[collection_adapter::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|  
|[collection_adapter::key_type (STL/CLR)](#key_type)|Тип ключа словаря.|  
|[collection_adapter::mapped_type (STL/CLR)](#mapped_type)|Тип значения словаря.|  
|[collection_adapter::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|  
|[collection_adapter::size_type (STL/CLR)](#size_type)|Тип расстояния со знаком между двумя элементами.|  
|[collection_adapter::value_type (STL/CLR)](#value_type)|Тип элемента.|  
  
|Функция-член|Описание:|  
|---------------------|-----------------|  
|[collection_adapter::base (STL/CLR)](#base)|Обозначает упакованного интерфейса BCL.|  
|[collection_adapter::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|  
|[collection_adapter::collection_adapter (STL/CLR)](#collection_adapter_collection_adapter)|Создает объект адаптера.|  
|[collection_adapter::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|  
|[collection_adapter::size (STL/CLR)](#size)|Подсчитывает количество элементов.|  
|[collection_adapter::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[collection_adapter::operator= (STL/CLR)](#op_eq)|Заменяет дескриптор хранимых BCL.|  
  
### <a name="remarks"></a>Примечания  
 Используйте этот класс шаблона для управления BCL контейнера в качестве контейнера STL/CLR. `collection_adapter` Сохраняет дескриптор BCL интерфейс, который в свою очередь, управляющий последовательностью элементов. Объект `collection_adapter` объекта `X` возвращает пару итераторов ввода `X.begin()` и `X.end()` использовать посетить элементы, по порядку. Некоторые специализации также позволяют записывать `X.size()` для определения длины управляемой последовательности.  

## <a name="base"></a> collection_adapter::Base (STL/CLR)
Обозначает упакованного интерфейса BCL.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
Coll^ base();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает хранимые дескриптора интерфейса BCL.  
  
### <a name="example"></a>Пример  
  
```cpp
// cliext_collection_adapter_base.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("base() same = {0}", c1.base() == %c1);   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
base() same = True  
```  

## <a name="begin"></a> collection_adapter::Begin (STL/CLR)
Задает начало управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор ввода, указывающий первый элемент управляемой последовательности или непосредственно за концом пустой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_collection_adapter_begin.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mycoll::iterator it = c1.begin();   
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

## <a name="collection_adapter_collection_adapter"></a> collection_adapter::collection_adapter (STL/CLR)
Создает объект адаптера.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
collection_adapter();  
collection_adapter(collection_adapter<Coll>% right);  
collection_adapter(collection_adapter<Coll>^ right);  
collection_adapter(Coll^ collection);  
```  
  
#### <a name="parameters"></a>Параметры  
 коллекция  
 Дескриптор BCL программы-оболочки.  
  
 right  
 Копируемый объект.  
  
### <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `collection_adapter();`  
  
 Инициализирует дескриптор хранимых с `nullptr`.  
  
 Конструктор:  
  
 `collection_adapter(collection_adapter<Coll>% right);`  
  
 Инициализирует дескриптор хранимых с `right.` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Конструктор:  
  
 `collection_adapter(collection_adapter<Coll>^ right);`  
  
 Инициализирует дескриптор хранимых с `right->` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Конструктор:  
  
 `collection_adapter(Coll^ collection);`  
  
 Инициализирует дескриптор хранимых с с `collection`.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_collection_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
  
// construct an empty container   
    Mycoll c1;   
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);   
  
// construct with a handle   
    Mycoll c2(%d6x);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mycoll c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mycoll c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
base() null = True  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  

## <a name="difference_type"></a> collection_adapter::difference_type (STL/CLR)
Тип расстояния со знаком между двумя элементами.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип, описывающий счетчик знаком элементов.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_collection_adapter_difference_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mycoll::difference_type diff = 0;   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  

## <a name="end"></a> collection_adapter::End (STL/CLR)
Задает конец управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор ввода, указывающий на место сразу за конец управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_collection_adapter_end.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="iterator"></a> collection_adapter::iterator (STL/CLR)
Тип итератора для управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект незаданного типа `T1` , можно использовать в качестве итератора ввода для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_collection_adapter_iterator.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="key_type"></a> collection_adapter::key_type (STL/CLR)
Тип ключа словаря.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона `Key`, в специализации для `IDictionary` или `IDictionary<Value>`; в противном случае он не определен.  
  
### <a name="example"></a>Пример  
  
```cpp
// cliext_collection_adapter_key_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef cliext::collection_adapter<   
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;   
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;   
int main()   
    {   
    Mymap d1;   
    d1.insert(Mymap::make_value(L'a', 1));   
    d1.insert(Mymap::make_value(L'b', 2));   
    d1.insert(Mymap::make_value(L'c', 3));   
    Mycoll c1(%d1);   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mypair elem in c1)   
        {   
        Mycoll::key_type key = elem.Key;   
        Mycoll::mapped_type value = elem.Value;   
        System::Console::Write(" [{0} {1}]", key, value);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  

## <a name="mapped_type"></a> collection_adapter::mapped_type (STL/CLR)
Тип значения словаря.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef Value mapped_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона `Value`, в специализации для `IDictionary` или `IDictionary<Value>`; в противном случае он не определен.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_collection_adapter_mapped_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef cliext::collection_adapter<   
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;   
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;   
int main()   
    {   
    Mymap d1;   
    d1.insert(Mymap::make_value(L'a', 1));   
    d1.insert(Mymap::make_value(L'b', 2));   
    d1.insert(Mymap::make_value(L'c', 3));   
    Mycoll c1(%d1);   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mypair elem in c1)   
        {   
        Mycoll::key_type key = elem.Key;   
        Mycoll::mapped_type value = elem.Value;   
        System::Console::Write(" [{0} {1}]", key, value);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  

## <a name="op_eq"></a> collection_adapter::operator = (STL/CLR)
Заменяет дескриптор хранимых BCL.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
collection_adapter<Coll>% operator=(collection_adapter<Coll>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Адаптер для копирования.  
  
### <a name="remarks"></a>Примечания  
 Копирует оператор член `right` объекту, затем возвращает `*this`. Используется для замены сохраненного дескриптора BCL копию хранимой BCL дескриптора в `right`.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_collection_adapter_operator_as.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mycoll c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="reference"></a> collection_adapter::Reference (STL/CLR)
Тип ссылки на элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает ссылку на элемент.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_collection_adapter_reference.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Mycoll::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="size"></a> collection_adapter::size (STL/CLR)
Подсчитывает количество элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает длину управляемой последовательности. Он не определен в специализации для `IEnumerable` или `IEnumerable<Value>`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_collection_adapter_size.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
size() = 6  
```  

## <a name="size_type"></a> collection_adapter::size_type (STL/CLR)
Тип расстояния со знаком между двумя элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает элемент неотрицательное число.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_collection_adapter_size_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    Mycoll::size_type size = c1.size();   
    System::Console::WriteLine("size() = {0}", size);   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
size() = 6  
```  

## <a name="swap"></a> collection_adapter::Swap (STL/CLR)
Меняет местами содержимое двух контейнеров.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void swap(collection_adapter<Coll>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Контейнер для обмена содержимым.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет хранимых дескрипторы BCL между `*this` и `right`.  
  
### <a name="example"></a>Пример  
  
```cpp
// cliext_collection_adapter_swap.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> d2(5, L'x');   
    Mycoll c2(%d2);   
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
x x x x x  
x x x x x  
a b c  
```  

## <a name="value_type"></a> collection_adapter::value_type (STL/CLR)
Тип элемента.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона `Value`, если он имеется в специализации; в противном случае он является синонимом `System::Object^`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_collection_adapter_value_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display contents " a b c" using value_type   
    for (Mycoll::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        Mycoll::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="make_collection"></a> make_collection (STL/CLR)
Сделать `range_adapter` из пары итератора.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Iter>  
    range_adapter<Iter> make_collection(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>Параметры  
 `Iter`  
 Тип упакованного итераторов.  
  
 `first`  
 Первый итератор программы-оболочки.  
  
 `last`  
 Второй итератор программы-оболочки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция шаблона возвращает `gcnew range_adapter<Iter>(first, last)`. Можно использовать для создания `range_adapter<Iter>` объекта из пару итераторов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_make_collection.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in d1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Collections::ICollection^ p1 =   
        cliext::make_collection(d1.begin(), d1.end());   
    System::Console::WriteLine("Count = {0}", p1->Count);   
    System::Console::WriteLine("IsSynchronized = {0}",   
        p1->IsSynchronized);   
    System::Console::WriteLine("SyncRoot not nullptr = {0}",   
        p1->SyncRoot != nullptr);   
  
// copy the sequence   
    cli::array<System::Object^>^ a1 = gcnew cli::array<System::Object^>(5);   
  
    a1[0] = L'|';   
    p1->CopyTo(a1, 1);   
    a1[4] = L'|';   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
Count = 3  
IsSynchronized = False  
SyncRoot not nullptr = True  
 | a b c |  
```  

## <a name="range_adapter"></a> range_adapter (STL/CLR)
Класс шаблона, который создает оболочку для пары итераторы, которые позволяют реализовать несколько интерфейсов в библиотеке базовых классов (BCL). Range_adapter позволяет управлять диапазон STL/CLR, как если бы оно коллекции BCL.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Параметры  
 Iter  
 Тип, связанный с упакованного итераторов.  
  
### <a name="members"></a>Участники  
  
|Функция-член|Описание:|  
|---------------------|-----------------|  
|[range_adapter::range_adapter (STL/CLR)](#range_adapter_range_adapter)|Создает объект адаптера.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[range_adapter::operator= (STL/CLR)](#range_adapter_op_eq)|Заменяет сохраненный итератор пары.|  
  
### <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание:|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|Перебор элементов в коллекции.|  
|<xref:System.Collections.ICollection>|Поддерживает группу элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Перебор типизированных элементов в коллекции...|  
|<xref:System.Collections.Generic.ICollection%601>|Поддерживает группу типизированных элементов.|  
  
### <a name="remarks"></a>Примечания  
 Range_adapter сохраняет пару итераторов, которые в свою очередь разделения последовательность элементов. Объект реализует четыре BCL интерфейсы, которые позволяют выполнять итерацию по элементам в порядке. Используйте этот класс шаблона для работы с STL/CLR диапазоны как контейнеры BCL.  

## <a name="range_adapter_op_eq"></a> range_adapter::operator = (STL/CLR)
Заменяет сохраненный итератор пары.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
range_adapter<Iter>% operator=(range_adapter<Iter>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Адаптер для копирования.  
  
### <a name="remarks"></a>Примечания  
 Копирует оператор член `right` объекту, затем возвращает `*this`. Используется для замены сохраненного итератора пары копии сохраненного итератора пары в `right`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_range_adapter_operator_as.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Myrange c1(d1.begin(), d1.end());   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myrange c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="range_adapter_range_adapter"></a> range_adapter::range_adapter (STL/CLR)
Создает объект адаптера.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
range_adapter();  
range_adapter(range_adapter<Iter>% right);  
range_adapter(range_adapter<Iter>^ right);  
range_adapter(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>Параметры  
 first  
 Первый итератор программы-оболочки.  
  
 last  
 Второй итератор программы-оболочки.  
  
 right  
 Копируемый объект.  
  
### <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `range_adapter();`  
  
 Инициализирует пары сохраненный итератор с итераторами создаваемый по умолчанию.  
  
 Конструктор:  
  
 `range_adapter(range_adapter<Iter>% right);`  
  
 Инициализирует сохраненный итератор пары путем копирования пары, хранящиеся в `right`.  
  
 Конструктор:  
  
 `range_adapter(range_adapter<Iter>^ right);`  
  
 Инициализирует сохраненный итератор пары путем копирования пары, хранящиеся в `*right`.  
  
 Конструктор:  
  
 `range_adapter(Iter^ first, last);`  
  
 Инициализирует пары сохраненный итератор с `first` и `last`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_range_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// construct an empty adapter   
    Myrange c1;   
  
// construct with an iterator pair   
    Myrange c2(d1.begin(), d1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another adapter   
    Myrange c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying an adapter handle   
    Myrange c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c  
```  