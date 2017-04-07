---
title: "Класс array (стандартная библиотека C++ ) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- array
- std::array
- array/std::array
- std::array::const_iterator
- array/std::array::const_iterator
- std::array::const_pointer
- array/std::array::const_pointer
- std::array::const_reference
- array/std::array::const_reference
- std::array::const_reverse_iterator
- array/std::array::const_reverse_iterator
- std::array::difference_type
- array/std::array::difference_type
- std::array::iterator
- array/std::array::iterator
- std::array::pointer
- array/std::array::pointer
- std::array::reference
- array/std::array::reference
- std::array::reverse_iterator
- array/std::array::reverse_iterator
- std::array::size_type
- array/std::array::size_type
- std::array::value_type
- array/std::array::value_type
- std::array::assign
- array/std::array::assign
- std::array::at
- array/std::array::at
- std::array::back
- array/std::array::back
- std::array::begin
- array/std::array::begin
- std::array::cbegin
- array/std::array::cbegin
- std::array::cend
- array/std::array::cend
- std::array::crbegin
- array/std::array::crbegin
- std::array::crend
- array/std::array::crend
- std::array::data
- array/std::array::data
- std::array::empty
- array/std::array::empty
- std::array::end
- array/std::array::end
- std::array::fill
- array/std::array::fill
- std::array::front
- array/std::array::front
- std::array::max_size
- array/std::array::max_size
- std::array::rbegin
- array/std::array::rbegin
- std::array::rend
- array/std::array::rend
- std::array::size
- array/std::array::size
- std::array::swap
- array/std::array::swap
- std::array::operator=
- array/std::array::operator=
- std::array::operator[]
- array/std::array::operator[]
dev_langs:
- C++
helpviewer_keywords:
- array class
ms.assetid: fdfd43a5-b2b5-4b9e-991f-93bf10fb4293
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
ms.openlocfilehash: 0e5e79e423d268da61ac9062edd099330f742b59
ms.lasthandoff: 02/24/2017

---
# <a name="array-class-c-standard-library"></a>Класс array (стандартная библиотека C++)
Описывает объект, управляющий последовательностью из элементов `N` типа `Ty`. Последовательность хранится как массив `Ty` в объекте `array<Ty, N>`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Ty, std::size_t N>  
class array;  
```  
  
#### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Ty`|Тип элемента.|  
|`N`|Количество элементов|  
  
## <a name="members"></a>Члены  
  
|||  
|-|-|  
|Определение типа|Описание|  
|[array::const_iterator](#array__const_iterator)|Тип постоянного итератора для управляемой последовательности.|  
|[array::const_pointer](#array__const_pointer)|Тип постоянного указателя на элемент.|  
|[array::const_reference](#array__const_reference)|Тип постоянной ссылки на элемент.|  
|[array::const_reverse_iterator](#array__const_reverse_iterator)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[array::difference_type](#array__difference_type)|Тип расстояния со знаком между двумя элементами.|  
|[array::iterator](#array__iterator)|Тип итератора для управляемой последовательности.|  
|[array::pointer](#array__pointer)|Тип указателя на элемент.|  
|[array::reference](#array__reference)|Тип ссылки на элемент.|  
|[array::reverse_iterator](#array__reverse_iterator)|Тип обратного итератора для управляемой последовательности.|  
|[array::size_type](#array__size_type)|Тип беззнакового расстояния между двумя элементами.|  
|[array::value_type](#array__value_type)|Тип элемента.|  
  
|||  
|-|-|  
|Функция-член|Описание|  
|[array::array](#array__array)|Создает объект массива.|  
|[array::assign](#array__assign)|Заменяет все элементы.|  
|[array::at](#array__at)|Обращается к элементу в указанной позиции.|  
|[array::back](#array__back)|Обращается к последнему элементу.|  
|[array::begin](#array__begin)|Задает начало управляемой последовательности.|  
|[array::cbegin](#array__cbegin)|Возвращает постоянный итератор произвольного доступа, указывающий на первый элемент в массиве.|  
|[array::cend](#array__cend)|Возвращает постоянный итератор произвольного доступа, указывающий на предпоследнюю позицию массива.|  
|[array::crbegin](#array__crbegin)|Возвращает константный итератор, который указывает на первый элемент в обращенном массиве.|  
|[array::crend](#array__crend)|Возвращает постоянный итератор, который указывает на последний элемент в обратном массиве.|  
|[array::data](#array__data)|Получает адрес первого элемента.|  
|[array::empty](#array__empty)|Проверяет наличие элементов.|  
|[array::end](#array__end)|Задает конец управляемой последовательности.|  
|[array::fill](#array__fill)|Заменяет все элементы указанным значением.|  
|[array::front](#array__front)|Обращается к первому элементу.|  
|[array::max_size](#array__max_size)|Подсчитывает количество элементов.|  
|[array::rbegin](#array__rbegin)|Задает начало обратной управляемой последовательности.|  
|[array::rend](#array__rend)|Задает конец обратной управляемой последовательности.|  
|[array::size](#array__size)|Подсчитывает количество элементов.|  
|[array::swap](#array__swap)|Меняет местами содержимое двух контейнеров.|  
  
|||  
|-|-|  
|Оператор|Описание|  
|[array::operator=](#array__operator_eq)|Заменяет управляемую последовательность.|  
|[array::operator[]](#array__operator_at)|Обращается к элементу в указанной позиции.|  
  
## <a name="remarks"></a>Примечания  
 У этого типа есть конструктор по умолчанию `array()` и оператор присваивания по умолчанию `operator=`. Тип удовлетворяет требованиям для `aggregate`. Поэтому объекты типа `array<Ty, N>` можно инициализировать с помощью агрегатного инициализатора. Например:  
  
```  
array<int, 4> ai = { 1, 2, 3 };  
```  
  
 создает объект `ai`, содержащий четыре целочисленных значения, инициализирует первые три элемента как 1, 2 и 3 соответственно и инициализирует четвертый элемент как 0.  
  
## <a name="requirements"></a>Требования  
 **Header:** \<array>  
  
 **Пространство имен:** std  
  
##  <a name="array__array"></a>  array::array  
 Создает объект массива.  
  
```  
array();

array(const array& right);
```  
  
### <a name="parameters"></a>Параметры  
*right*  
 Объект или диапазон для вставки.  
  
### <a name="remarks"></a>Примечания  
Конструктор по умолчанию `array()` оставляет управляемую последовательность неинициализированной (или инициализированной по умолчанию). Он используется для указания неинициализированной управляемой последовательности.  
  
Конструктор копий `array(const array& right)` инициализирует управляемую последовательность с помощью последовательности [*right*`.begin()`, *right*`.end()`). Он используется для указания начальной управляемой последовательности, которая является копией последовательности, управляемой объектом массива *right*.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_array.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1(c0);   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
##  <a name="array__assign"></a>  array::assign  
Устаревший в C ++&11;, заменен на [fill](#array__fill). Заменяет все элементы.  
  
```  
void assign(const Ty& val);
```  
  
### <a name="parameters"></a>Параметры  
 `val`  
 Присваиваемое значение.  
  
### <a name="remarks"></a>Примечания  
 Функция-член заменяет последовательность, управляемую `*this`, на повторение элементов `N` со значением `val`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_assign.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1;   
    c1.assign(4);   
  
// display contents " 4 4 4 4"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 4 4 4  
```  
  
##  <a name="array__at"></a>  array::at  
 Обращается к элементу в указанной позиции.  
  
```  
reference at(size_type off);

constexpr const_reference at(size_type off) const;
```  
  
### <a name="parameters"></a>Параметры  
 `off`  
 Позиция элемента, к которому осуществляется доступ.  
  
### <a name="remarks"></a>Примечания  
 Функции-члены возвращают ссылку на элемент управляемой последовательности в позиции `off`. Если эта позиция недопустима, функция выдает объект класса `out_of_range`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_at.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display odd elements " 1 3"   
    std::cout << " " << c0.at(1);   
    std::cout << " " << c0.at(3);   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
##  <a name="array__back"></a>  array::back  
 Обращается к последнему элементу.  
  
```  
reference back();

constexpr const_reference back() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функции-члены возвращают ссылку на последний элемент управляемой последовательности, который должен быть не пустым.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_back.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    std::cout << " " << c0.back();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="array__begin"></a>  array::begin  
 Задает начало управляемой последовательности.  
  
```  
iterator begin() noexcept;  
const_iterator begin() const noexcept;  
```  
  
### <a name="remarks"></a>Примечания  
 Функции-члены возвращают итератор произвольного доступа, указывающий на первый элемент последовательности (или на место сразу за концом пустой последовательности)).  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_begin.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::iterator it2 = c0.begin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="array__cbegin"></a>  array::cbegin  
 Возвращает итератор `const`, направленный на первый элемент в диапазоне.  
  
```  
const_iterator cbegin() const noexcept;  
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
  
##  <a name="array__cend"></a>  array::cend  
 Возвращает итератор `const`, который обращается к месту, следующему сразу за последним элементом в диапазоне.  
  
```  
const_iterator cend() const noexcept;  
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
  
##  <a name="array__const_iterator"></a>  array::const_iterator  
 Тип постоянного итератора для управляемой последовательности.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве постоянного итератора с произвольным доступом для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_const_iterator.cpp  
// compile with: /EHsc /W4  
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> MyArray;   
  
int main()   
{   
    MyArray c0 = {0, 1, 2, 3};   
  
    // display contents " 0 1 2 3"   
    std::cout << "it1:";  
    for ( MyArray::const_iterator it1 = c0.begin();   
          it1 != c0.end();   
          ++it1 ) {  
       std::cout << " " << *it1;   
    }  
    std::cout << std::endl;   
  
    // display first element " 0"   
    MyArray::const_iterator it2 = c0.begin();   
    std::cout << "it2:";  
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
}  
  
```  
  
```Output  
it1: 0 1 2 3                                  
  
it2: 0  
  
```  
  
##  <a name="array__const_pointer"></a>  array::const_pointer  
 Тип постоянного указателя на элемент.  
  
```  
typedef const Ty *const_pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве постоянного указателя на элементы последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_const_pointer.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::const_pointer ptr = &*c0.begin();   
    std::cout << " " << *ptr;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="array__const_reference"></a>  array::const_reference  
 Тип постоянной ссылки на элемент.  
  
```  
typedef const Ty& const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект, который можно использовать в качестве постоянной ссылки на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_const_reference.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::const_reference ref = *c0.begin();   
    std::cout << " " << ref;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="array__const_reverse_iterator"></a>  array::const_reverse_iterator  
 Тип постоянного обратного итератора для управляемой последовательности.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве постоянного обратного итератора для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_const_reverse_iterator.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::const_reverse_iterator it2 = c0.rbegin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="array__crbegin"></a>  array::crbegin  
 Возвращает константный итератор, который указывает на первый элемент в обращенном массиве.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный обратный итератор произвольного доступа, указывающий на первый элемент в обращенном массиве или на элемент, который был последним в массиве до его обращения.  
  
### <a name="remarks"></a>Примечания  
 Если возвращается значение `crbegin`, то объект массива невозможно изменить.  
  
### <a name="example"></a>Пример  
  
```cpp  
// array_crbegin.cpp  
// compile with: /EHsc  
#include <array>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   array<int, 2> v1 = {1, 2};  
   array<int, 2>::iterator v1_Iter;  
   array<int, 2>::const_reverse_iterator v1_rIter;  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of array is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed array is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of array is 1.  
The first element of the reversed array is 2.  
```  
  
##  <a name="array__crend"></a>  array::crend  
 Возвращает константный итератор, который обращается к месту, следующему за последним элементом в обращенном массиве.  
  
```  
const_reverse_iterator crend() const noexcept;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный обратный итератор произвольного доступа, адресующий расположение после последнего элемента в обращенном массиве (расположение перед первым элементом в необращенном массиве).  
  
### <a name="remarks"></a>Примечания  
 `crend` используется с обращенным массивом точно так же, как [array::cend](#array__cend) используется с массивом.  
  
 Если возвращается значение `crend` (соответственно уменьшенное), объект массива нельзя изменить.  
  
 `crend` используется, чтобы проверить, достиг ли обратный итератор конца массива.  
  
 Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.  
  
### <a name="example"></a>Пример  
  
```cpp  
// array_crend.cpp  
// compile with: /EHsc  
#include <array>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   array<int, 2> v1 = {1, 2};  
   array<int, 2>::const_reverse_iterator v1_rIter;  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="array__data"></a>  array::data  
 Получает адрес первого элемента.  
  
```  
Ty *data();

const Ty *data() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функции-члены возвращают адрес первого элемента в управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_data.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::pointer ptr = c0.data();   
    std::cout << " " << *ptr;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="array__difference_type"></a>  array::difference_type  
 Тип расстояния со знаком между двумя элементами.  
  
```  
typedef std::ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип целого числа со знаком описывает объект, который может представлять разницу между адресами любых двух элементов в управляемой последовательности. Это синоним для типа `std::ptrdiff_t`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_difference_type.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display distance first-last " -4"   
    Myarray::difference_type diff = c0.begin() - c0.end();   
    std::cout << " " << diff;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
-4  
```  
  
##  <a name="array__empty"></a>  array::empty  
 Проверяет отсутствие элементов.  
  
```  
constexpr bool empty() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает значение true, только если `N == 0`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_empty.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display whether c0 is empty " false"   
    std::cout << std::boolalpha << " " << c0.empty();   
    std::cout << std::endl;   
  
    std::array<int, 0> c1;   
  
// display whether c1 is empty " true"   
    std::cout << std::boolalpha << " " << c1.empty();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
false  
true  
```  
  
##  <a name="array__end"></a>  array::end  
 Задает конец управляемой последовательности.  
  
```  
reference end();

const_reference end() const;
```  
  
### <a name="remarks"></a>Примечания  
 Первые две функции-члена возвращают итератор произвольного доступа, указывающий на место сразу за концом последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_end.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::iterator it2 = c0.end();   
    std::cout << " " << *--it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="array__fill"></a>  array::fill  
 Удаляет массив и копирует указанные элементы в пустой массив.  
  
```  
void fill(const Type& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`val`|Значение элемента, вставляемого в массив.|  
  
### <a name="remarks"></a>Примечания  
 `fill` заменяет каждый элемент массива на указанное значение.  
  
### <a name="example"></a>Пример  
  
```cpp  
// array_fill.cpp  
// compile with: /EHsc  
#include <array>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   array<int, 2> v1 = {1, 2};  
   array<int, 2>::iterator iter;  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v1.fill(3);  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="array__front"></a>  array::front  
 Обращается к первому элементу.  
  
```  
reference front();

constexpr const_reference front() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функции-члены возвращают ссылку на первый элемент управляемой последовательности, который должен быть не пустым.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_front.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    std::cout << " " << c0.front();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="array__iterator"></a>  array::iterator  
 Тип итератора для управляемой последовательности.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве итератора с произвольным доступом для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_iterator.cpp   
// compile with: /EHsc /W4  
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> MyArray;   
  
int main()   
{   
    MyArray c0 = {0, 1, 2, 3};   
  
    // display contents " 0 1 2 3"   
    std::cout << "it1:";  
    for ( MyArray::iterator it1 = c0.begin();   
          it1 != c0.end();   
          ++it1 ) {  
       std::cout << " " << *it1;   
    }  
    std::cout << std::endl;   
  
    // display first element " 0"   
    MyArray::iterator it2 = c0.begin();   
    std::cout << "it2:";  
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
}  
  
```  
  
```Output  
it1: 0 1 2 3                                  
  
it2: 0  
  
```  
  
##  <a name="array__max_size"></a>  array::max_size  
 Подсчитывает количество элементов.  
  
```  
constexpr size_type max_size() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает значение `N`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_max_size.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display (maximum) size " 4"   
    std::cout << " " << c0.max_size();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4  
```  
  
##  <a name="array__operator_at"></a>  array::operator[]  
 Обращается к элементу в указанной позиции.  
  
```  
reference operator[](size_type off);

constexpr const_reference operator[](size_type off) const;
```  
  
### <a name="parameters"></a>Параметры  
 `off`  
 Позиция элемента, к которому осуществляется доступ.  
  
### <a name="remarks"></a>Примечания  
 Функции-члены возвращают ссылку на элемент управляемой последовательности в позиции `off`. Если эта позиция недопустима, поведение станет неопределенным.  
  
Имеется также не являющаяся членом функция [get](array-functions.md#get_function), которая может получать ссылку на элемент `array`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_operator_sub.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display odd elements " 1 3"   
    std::cout << " " << c0[1];   
    std::cout << " " << c0[3];   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
1 3  
```  
  
##  <a name="array__operator_eq"></a>  array::operator=  
 Заменяет управляемую последовательность.  
  
```  
array <Value>%  operator=(array <Value>% right);
```  
  
### <a name="parameters"></a>Параметры  
 right  
 Контейнер для копирования.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член присваивает каждому элементу `right` соответствующий элемент управляемой последовательности, а затем возвращает `*this`. Он позволяет заменить управляемую последовательность копией управляемой последовательности в `right`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_operator_as.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1;   
    c1 = c0;   
  
// display copied contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
##  <a name="array__pointer"></a>  array::pointer  
 Тип указателя на элемент.  
  
```  
typedef Ty *pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве указателя на элементы последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_pointer.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::pointer ptr = &*c0.begin();   
    std::cout << " " << *ptr;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="array__rbegin"></a>  array::rbegin  
 Задает начало обратной управляемой последовательности.  
  
```  
reverse_iterator rbegin()noexcept;  
const_reverse_iterator rbegin() const noexcept;  
```  
  
### <a name="remarks"></a>Примечания  
 Первые две функции-члена возвращают обратный итератор, указывающий на место сразу за концом управляемой последовательности. Таким образом, задается начало обратной последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_rbegin.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::const_reverse_iterator it2 = c0.rbegin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="array__reference"></a>  array::reference  
 Тип ссылки на элемент.  
  
```  
typedef Ty& reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект, который можно использовать в качестве ссылки на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_reference.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::reference ref = *c0.begin();   
    std::cout << " " << ref;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="array__rend"></a>  array::rend  
 Задает конец обратной управляемой последовательности.  
  
```  
reverse_iterator rend()noexcept;  
const_reverse_iterator rend() const noexcept;  
```  
  
### <a name="remarks"></a>Примечания  
 Функции-члены возвращают обратный итератор, указывающий на первый элемент последовательности (или непосредственно за окончание пустой последовательности)). Таким образом, он задает конец обратной последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_rend.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::const_reverse_iterator it2 = c0.rend();   
    std::cout << " " << *--it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="array__reverse_iterator"></a>  array::reverse_iterator  
 Тип обратного итератора для управляемой последовательности.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве обратного итератора для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_reverse_iterator.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::reverse_iterator it2 = c0.rbegin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="array__size"></a>  array::size  
 Подсчитывает количество элементов.  
  
```  
constexpr size_type size() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает значение `N`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_size.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display size " 4"   
    std::cout << " " << c0.size();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4  
```  
  
##  <a name="array__size_type"></a>  array::size_type  
 Тип беззнакового расстояния между двумя элементами.  
  
```  
typedef std::size_t size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Целочисленный тип без знака описывает объект, который может представлять длину любой управляемой последовательности. Это синоним для типа `std::size_t`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_size_type.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display distance last-first " 4"   
    Myarray::size_type diff = c0.end() - c0.begin();   
    std::cout << " " << diff;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4  
```  
  
##  <a name="array__swap"></a>  array::swap  
Выполняет обмен содержимым между этим и другим массивом.  
  
```  
void swap(array& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Массив для обмена содержимым.  
  
### <a name="remarks"></a>Примечания  
Функция-член меняет местами управляемые последовательности между `*this` и `right`. Он выполняет присваивания элементов и вызовы конструктора у количестве, пропорционально пропорциональном `N`.  

Имеется также не являющаяся членом функция [swap](array-functions.md#swap_function), которая может переставлять местами два экземпляра `array`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_swap.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1 = {4, 5, 6, 7};   
    c0.swap(c1);   
  
// display swapped contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    swap(c0, c1);   
  
// display swapped contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 5 6 7  
0 1 2 3  
```  
  
##  <a name="array__value_type"></a>  array::value_type  
 Тип элемента.  
  
```  
typedef Ty value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Ty`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__array__array_value_type.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        {   
        Myarray::value_type val = *it;   
        std::cout << " " << val;   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
## <a name="see-also"></a>См. также  
 [\<array>](../standard-library/array.md)


