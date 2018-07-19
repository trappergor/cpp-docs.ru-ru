---
title: Программа (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
dev_langs:
- C++
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fcc97e5037898b3a9c39a6c72ed21b2c19a4c777
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2018
ms.locfileid: "36306025"
---
# <a name="utility-stlclr"></a>utility (STL/CLR)
Включать заголовок STL/CLR `<cliext/utility>` для определения шаблона класса `pair` и некоторые вспомогательные функции шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <utility>  
```

## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/программа >  
  
 **Пространство имен:** cliext  
  
## <a name="declarations"></a>Объявления  
  
|Класс|Описание:|  
|-----------|-----------------|  
|[pair (STL/CLR)](#pair)|Перенос пара элементов.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[operator== (pair) (STL/CLR)](#op_eq)|Пара равно сравнения.|  
|[operator!= (pair) (STL/CLR)](#op_neq)|Пары сравнения не равны.|  
|[operator< (pair) (STL/CLR)](#op_lt)|Пара меньше, чем сравнения.|  
|[оператор\<= (пару) (STL/CLR)](#op_lteq)|Меньше или равно пары сравнения.|  
|[operator> (pair) (STL/CLR)](#op_gt)|Пара больше сравнения.|  
|[operator>= (pair) (STL/CLR)](#op_gteq)|Пара, больше или равно сравнения.|  
  
|Функция|Описание:|  
|--------------|-----------------|  
|[make_pair (STL/CLR)](#make_pair)|Сделать пару из пары значений.|  

## <a name="members"></a>Участники

##<a name="pair"></a> пара (STL/CLR)
Класс шаблона описывает объект, который создает оболочку для пары значений.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>Параметры  
 Значение1  
 Тип первого упакованного значения.  
  
 Value2  
 Тип упакованного значение секунд.  
  
## <a name="members"></a>Участники  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|[pair::first_type (STL/CLR)](#first_type)|Тип упакованного значения первой.|  
|[pair::second_type (STL/CLR)](#second_type)|Тип упакованного значение второго.|  
  
|Объект члена|Описание:|  
|-------------------|-----------------|  
|[pair::first (STL/CLR)](#first)|Первый сохраненное значение.|  
|[pair::second (STL/CLR)](#second)|Второй сохраненное значение.|  
  
|Функция-член|Описание:|  
|---------------------|-----------------|  
|[pair::pair (STL/CLR)](#pair_pair)|Создает объект пары.|  
|[pair::swap (STL/CLR)](#swap)|Меняет местами содержимое двух пар.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[pair::operator= (STL/CLR)](#op_as)|Заменяет хранимых пара значений.|  
  
## <a name="remarks"></a>Примечания  
 Объект сохраняет пару значений. Используйте этот класс шаблона для объединения двух значений в один объект. Кроме того, объект `cliext::pair` (описанным ниже) сохраняет только управляемых типов, для хранения пару неуправляемые типы используют `std::pair`, объявленные в `<utility>`.  


## <a name="first"></a> Pair::First (STL/CLR)
Первое упакованное значение.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
Value1 first;  
```  
  
### <a name="remarks"></a>Примечания  
 Объект сохраняет первое упакованное значение.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_first.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  

## <a name="first_type"></a> Pair::first_type (STL/CLR)
Тип упакованного значения первой.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef Value1 first_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Value1`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_first_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  

## <a name="op_as"></a> Pair::operator = (STL/CLR)
Заменяет хранимых пара значений.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Пара для копирования.  
  
### <a name="remarks"></a>Примечания  
 Копирует оператор член `right` объекту, затем возвращает `*this`. Используется для замены хранимой пара значений копию хранимой пары значений в `right`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_operator_as.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
// assign to a new pair   
    cliext::pair<wchar_t, int> c2;   
    c2 = c1;   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 3]  
```  

## <a name="pair_pair"></a> Pair::Pair (STL/CLR)
Создает объект пары.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Пара для хранения.  
  
 val1  
 Первое значение для хранения.  
  
 val2  
 Второе значение для хранения.  
  
### <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `pair();`  
  
 Инициализирует хранимых паре со значениями по умолчанию создан.  
  
 Конструктор:  
  
 `pair(pair<Value1, Value2>% right);`  
  
 Инициализирует хранимых пары с `right.` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) и `right.` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 Инициализирует хранимых пары с `right->` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) и `right>` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).  
  
 Конструктор:  
  
 `pair(Value1 val1, Value2 val2);`  
  
 Инициализирует хранимых пары с с `val1` и `val2`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
```Output  
[\0, 0]  
[x, 3]  
[x, 3]  
[x, 3]  
```  

## <a name="second"></a> Pair::Second (STL/CLR)
Второе значение в оболочку.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
Value2 second;  
```  
  
### <a name="remarks"></a>Примечания  
 Объект сохраняет значение второго оболочку.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_second.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  

## <a name="second_type"></a> Pair::second_type (STL/CLR)
Тип упакованного значение второго.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef Value2 second_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Value2`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_second_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```    

## <a name="swap"></a> Pair::Swap (STL/CLR)
Меняет местами содержимое двух пар.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void swap(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Пара для обмена содержимым.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет хранимых пары значений между `*this` и `right`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_swap.cpp   
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

## <a name="make_pair"></a> make_pair (STL/CLR)
Сделать `pair` из пары значений.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### <a name="parameters"></a>Параметры  
 `Value1`  
 Тип упакованного значения первой.  
  
 `Value2`  
 Тип упакованного значение второго.  
  
 `first`  
 Первое значение программы-оболочки.  
  
 `second`  
 Второе значение для упаковки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция шаблона возвращает `pair<Value1, Value2>(first, second)`. Можно использовать для создания `pair<Value1, Value2>` объекта из пары значений.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[y, 4]  
```  

## <a name="op_neq"></a> оператор! = (пару) (STL/CLR)
Пары сравнения не равны.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator!=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый пара для сравнения.  
  
 right  
 Правый пара для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(left == right)`. Можно использовать для тестирования ли `left` не упорядочен таким же, как `right` при две пары, сравниваемые элемент элемент.  
  
### <a name="example"></a>Пример  
  
```cpp
// cliext_pair_operator_ne.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] != [x 3] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[x 3] != [x 4] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] != [x 3] is False  
[x 3] != [x 4] is True  
```  
  
## <a name="op_lt"></a> оператор&lt; (пару) (STL/CLR)
Пара меньше, чем сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator<(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый пара для сравнения.  
  
 right  
 Правый пара для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second`. Можно использовать для тестирования ли `left` упорядочен до `right` при две пары, сравниваемые элемент элемент.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_operator_lt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] < [x 3] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[x 3] < [x 4] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] < [x 3] is False  
[x 3] < [x 4] is True  
```  

## <a name="op_lteq"></a> оператор&lt;= (пару) (STL/CLR)
Меньше или равно пары сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator<=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый пара для сравнения.  
  
 right  
 Правый пара для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(right < left)`. Можно использовать для тестирования ли `left` не упорядочен после `right` при две пары, сравниваемые элемент элемент.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_operator_le.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] <= [x 3] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] <= [x 3] is True  
[x 4] <= [x 3] is False  
```  
  
## <a name="op_eq"></a> оператор == (пару) (STL/CLR)
Пара равно сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator==(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый пара для сравнения.  
  
 right  
 Правый пара для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `left.first ==` `right.first &&` `left.second ==` `right.second`. Можно использовать для тестирования ли `left` упорядочен таким же, как `right` при две пары, сравниваемые элемент элемент.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_operator_eq.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] == [x 3] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[x 3] == [x 4] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] == [x 3] is True  
[x 3] == [x 4] is False  
```  

## <a name="op_gt"></a> оператор&gt; (пару) (STL/CLR)
Пара больше сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator>(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый пара для сравнения.  
  
 right  
 Правый пара для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `right` `<` `left`. Можно использовать для тестирования ли `left` упорядочен после `right` при две пары, сравниваемые элемент элемент.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_operator_gt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] > [x 3] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[x 4] > [x 3] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] > [x 3] is False  
[x 4] > [x 3] is True  
```  

## <a name="op_gteq"></a> оператор&gt;= (пару) (STL/CLR)
Пара, больше или равно сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator>=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый пара для сравнения.  
  
 right  
 Правый пара для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(left < right)`. Можно использовать для тестирования ли `left` не упорядочен до `right` при две пары, сравниваемые элемент элемент.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_pair_operator_ge.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] >= [x 3] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] >= [x 3] is True  
[x 3] >= [x 4] is False  
```  
