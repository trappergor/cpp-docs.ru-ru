---
title: deque (STL/CLR) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque
- cliext::deque::assign
- cliext::deque::at
- cliext::deque::back
- cliext::deque::back_item
- cliext::deque::begin
- cliext::deque::clear
- cliext::deque::const_iterator
- cliext::deque::const_reference
- cliext::deque::const_reverse_iterator
- cliext::deque::deque
- cliext::deque::difference_type
- cliext::deque::empty
- cliext::deque::end
- cliext::deque::erase
- cliext::deque::front
- cliext::deque::front_item
- cliext::deque::generic_container
- cliext::deque::generic_iterator
- cliext::deque::generic_reverse_iterator
- cliext::deque::generic_value
- cliext::deque::insert
- cliext::deque::iterator
- cliext::deque::operator!=
- cliext::deque::operator[]
- cliext::deque::pop_back
- cliext::deque::pop_front
- cliext::deque::push_back
- cliext::deque::push_front
- cliext::deque::rbegin
- cliext::deque::reference
- cliext::deque::rend
- cliext::deque::resize
- cliext::deque::reverse_iterator
- cliext::deque::size
- cliext::deque::size_type
- cliext::deque::swap
- cliext::deque::to_array
- cliext::deque::value_type
- cliext::deque::operator<
- cliext::deque::operator<=
- cliext::deque::operator=
- cliext::deque::operator==
- cliext::deque::operator>
- cliext::deque::operator>=
dev_langs:
- C++
helpviewer_keywords:
- deque class [STL/CLR]
- <deque> header [STL/CLR]
- <cliext/deque> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- deque member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- operator!= member [STL/CLR]
- operator member [] [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3d5db6c886de547abd94ec0390f1056efef0091e
ms.sourcegitcommit: bad2441d1930275ff506d44759d283d94cccd1c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2018
ms.locfileid: "39376200"
---
# <a name="deque-stlclr"></a>deque (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с произвольного доступа. Использовать контейнер `deque` для управления последовательность элементов, выглядит как непрерывный блок памяти, но которого может расти или сокращаться на обоих концах без необходимости копировать все оставшиеся элементы. Таким образом его можно эффективно реализовать `double-ended queue`. (Поэтому имени.)  
  
 В следующем описании `GValue` совпадает со значением `Value` последний ссылочного типа, в противном случае он является `Value^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
### <a name="parameters"></a>Параметры  
 *GValue*  
 Универсальный тип элемента в управляемой последовательности.  
  
 *Значение*  
 Тип элемента в управляемой последовательности.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/deque >  
  
 **Пространство имен:** cliext  

## <a name="declarations"></a>Объявления  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|[deque::const_iterator (STL/CLR)](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|  
|[deque::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|  
|[deque::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[deque::difference_type (STL/CLR)](#difference_type)|Тип расстояния со знаком между двумя элементами.|  
|[deque::generic_container (STL/CLR)](#generic_container)|Тип универсального интерфейса для контейнера.|  
|[deque::generic_iterator (STL/CLR)](#generic_iterator)|Тип итератора для универсального интерфейса для контейнера.|  
|[deque::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[deque::generic_value (STL/CLR)](#generic_value)|Тип элемента для универсального интерфейса для контейнера.|  
|[deque::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|  
|[deque::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|  
|[deque::reverse_iterator (STL/CLR)](#reverse_iterator)|Тип обратного итератора для управляемой последовательности.|  
|[deque::size_type (STL/CLR)](#size_type)|Тип расстояния со знаком между двумя элементами.|  
|[deque::value_type (STL/CLR)](#value_type)|Тип элемента.|  
  
|Функция-член|Описание:|  
|---------------------|-----------------|  
|[deque::assign (STL/CLR)](#assign)|Заменяет все элементы.|  
|[deque::at (STL/CLR)](#at)|Обращается к элементу в указанной позиции.|  
|[deque::back (STL/CLR)](#back)|Обращается к последнему элементу.|  
|[deque::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|  
|[deque::clear (STL/CLR)](#clear)|Удаляет все элементы.|  
|[deque::deque (STL/CLR)](#deque)|Создает объект контейнера.|  
|[deque::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|  
|[deque::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|  
|[deque::erase (STL/CLR)](#erase)|Удаляет элементы в указанных позициях.|  
|[deque::front (STL/CLR)](#front)|Обращается к первому элементу.|  
|[deque::insert (STL/CLR)](#insert)|Добавляет элементы в указанной позиции.|  
|[deque::pop_back (STL/CLR)](#pop_back)|Удаляет последний элемент.|  
|[deque::pop_front (STL/CLR)](#pop_front)|Удаляет первый элемент.|  
|[deque::push_back (STL/CLR)](#push_back)|Добавляет новый последний элемент.|  
|[deque::push_front (STL/CLR)](#push_front)|Добавляет новый первый элемент.|  
|[deque::rbegin (STL/CLR)](#rbegin)|Задает начало обратной управляемой последовательности.|  
|[deque::rend (STL/CLR)](#rend)|Задает конец обратной управляемой последовательности.|  
|[deque::resize (STL/CLR)](#resize)|Изменяет количество элементов.|  
|[deque::size (STL/CLR)](#size)|Подсчитывает количество элементов.|  
|[deque::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|  
|[deque::to_array (STL/CLR)](#to_array)|Копирует управляемой последовательности в новый массив.|  
  
|Свойство.|Описание:|  
|--------------|-----------------|  
|[deque::back_item (STL/CLR)](#back_item)|Обращается к последнему элементу.|  
|[deque::front_item (STL/CLR)](#front_item)|Обращается к первому элементу.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[deque::operator!= (STL/CLR)](#op_neq)|Определяет, если два `deque` объекты не равны.|  
|[deque::operator(STL/CLR)](#operator)|Обращается к элементу в указанной позиции.|  
|[operator< (deque) (STL/CLR)](#op_lt)|Определяет, если `deque` объект меньше другого `deque` объекта.|  
|[operator<= (deque) (STL/CLR)](#op_lteq)|Определяет, если `deque` объекта меньше или равно другому `deque` объекта.|  
|[operator= (deque) (STL/CLR)](#op_as)|Заменяет управляемую последовательность.|  
|[operator== (deque) (STL/CLR)](#op_eq)|Определяет, если `deque` объект равен другому `deque` объекта.|  
|[operator> (deque) (STL/CLR)](#op_gt)|Определяет, если `deque` объект больше, чем другой `deque` объекта.|  
|[operator>= (deque) (STL/CLR)](#op_gteq)|Определяет, если `deque` объекта больше или равно другому `deque` объекта.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание:|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Сохранить группу элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательность типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|<xref:System.Collections.Generic.IList%601>|Ведение упорядоченная группа типизированных элементов.|  
|IDeque < значение\>|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает хранилище для управляемой последовательности с его помощью хранимые массив дескрипторов, которые определяют блоки `Value` элементов. Массив увеличивается по требованию. Рост происходит таким образом, добавляя или добавления нового элемента обходится в постоянном времени, что изменяются элементов не осталось. Можно также удалить элемент на обоих концах в константном времени и без нарушения работы остальных элементов. Таким образом, очередь является хорошим кандидатом для базового контейнера для шаблона класса [очереди (STL/CLR)](../dotnet/queue-stl-clr.md) или класс шаблона [стека (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 Объект `deque` объект поддерживает итераторов произвольного доступа, это означает, что можно ссылаться на элемент непосредственно, учитывая его порядкового номера, инвентаризации с нуля для первого элемента (внешний), чтобы [deque::size (STL/CLR)](#size) `() - 1` для последнего элемента (назад). Это также означает, что очередь является хорошим кандидатом для базового контейнера для шаблона класса [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Итератор deque сохраняет дескриптор объекта его связанные очереди, а также сдвиг элемент, указываемый ею. Вы можете использовать итераторы только с свои объекты связанного контейнера. Смещение элемента очереди — *не* обязательно так же, как его положение. На первый элемент, вставленный имеет нулевой сдвиг, далее добавленный элемент имеет уровень защиты 1, но Далее присоединяемый элемент имеет смещение -1.  
  
 Вставки или удаления элементов на обоих концах не *не* значение элемент, хранящийся в любой допустимый уровень защиты. Вставка или удаление внутренний элемент, однако *можно* изменить значение элемента, сохраняются на данный сдвиг, можно также изменить значение, обозначенное итератор. (Контейнер может потребоваться скопировать элементы вверх или вниз, чтобы создать брешь в системе перед вставкой или применить после стирания.) Тем не менее это итератор deque остается допустимым до тех пор, пока его смещение определяет допустимый элемент. Кроме того, допустимым итератором остается dereferencable — его можно использовать для доступа к или изменить значение элемента, указываемый ею--до тех пор, пока его смещение не равно смещение для итератора, возвращаемого методом `end()`.  
  
 Стирание или удалении элемента вызывает деструктор для сохраненному значению. Уничтожение контейнера стирает все элементы. Таким образом контейнер, тип элементов которого является ссылочным классом, гарантирует, что ни один элемент пережить контейнера. Обратите внимание, что контейнер дескрипторов не *не* уничтожить его элементов.  
 
## <a name="members"></a>Участники

## <a name="assign"></a> deque::Assign (STL/CLR)
Заменяет все элементы.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *count*  
 Число элементов для вставки.  
  
 *Первый*  
 Начало диапазона для вставки.  
  
 *последний*  
 Конец диапазона для вставки.  
  
 *right*  
 Перечисление для вставки.  
  
 *Val*  
 Значение элемента для вставки.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член заменяет управляемую последовательность на повторение *число* элементов со значением *val*. Он понадобится на весь контейнер с элементами, каждый из которых и то же значение.  
  
 Если `InIt` имеет целочисленный тип, вторая функция-член ведет себя так же, как `assign((size_type)first, (value_type)last)`. В противном случае он заменяет управляемую последовательность последовательностью [`first`, `last`). Оно позволяет сделать управляемую последовательность копией другой последовательности.  
  
 Третья функция-член заменяет управляемую последовательность последовательностью, назначенному с помощью перечислителя *правой*. Используется, чтобы сделать управляемую последовательность копией последовательности, описываемого перечислитель.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_assign.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  

## <a name="at"></a> deque::AT (STL/CLR)
Обращается к элементу в указанной позиции.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
reference at(size_type pos);  
```  
  
#### <a name="parameters"></a>Параметры  
 *торговых терминалов*  
 Позиция элемента, к которому осуществляется доступ.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает ссылку на элемент управляемой последовательности в положении *pos*. Используется для чтения или записи элемент, позиция которого известно.  
  
### <a name="example"></a>Пример  
  
```cpp
// cliext_deque_at.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  
  
## <a name="back"></a> deque::Back (STL/CLR)
Обращается к последнему элементу.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
reference back();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает ссылку на последний элемент управляемой последовательности, который должен быть пустым. Используется для доступа к последнего элемента, если известно, что он существует.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
back() = c  
 a b x  
```  
  
## <a name="back_item"></a> deque::back_item (STL/CLR)
Обращается к последнему элементу.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
property value_type back_item;  
```  
  
### <a name="remarks"></a>Примечания  
 Свойство обращается к последний элемент управляемой последовательности, который должен быть пустым. Используется для чтения или записи последнего элемента, если известно, что он существует.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_back_item.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back_item = c  
 a b x  
```  
  
## <a name="begin"></a> deque::Begin (STL/CLR)
Задает начало управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator begin();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор произвольного доступа, указывающий на первый элемент управляемой последовательности или непосредственно за окончание пустой последовательности. Используется для получения итератора, который обозначает `current` начало управляемой последовательности, а его состояние можно изменить при изменении длины управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_begin.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
 x y c  
```  

## <a name="clear"></a> deque::Clear (STL/CLR)
Удаляет все элементы.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void clear();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член эффективно вызывает [deque::erase (STL/CLR)](#erase) `(` [deque::begin (STL/CLR)](#begin) `(),` [deque::end (STL/CLR)](#end) `())`. Используется, чтобы убедиться, что управляемая последовательность пуста.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_clear.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
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

## <a name="const_iterator"></a> deque::const_iterator (STL/CLR)
Тип постоянного итератора для управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект неопределенного типа `T2` , можно использовать в качестве постоянного итератора произвольного доступа для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_const_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  
  
## <a name="const_reference"></a> deque::const_reference (STL/CLR)
Тип постоянной ссылки на элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает постоянную ссылку на элемент.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_const_reference.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        cliext::deque<wchar_t>::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  
  
## <a name="const_reverse_iterator"></a> deque::const_reverse_iterator (STL/CLR)
Тип постоянного обратного итератора для управляемой последовательности...  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект неопределенного типа `T4` , можно использовать в качестве постоянного обратного итератора для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_deque_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::deque<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::deque<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
```  

## <a name="deque"></a> deque::deque (STL/CLR)
Создает объект контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
deque();  
deque(deque<Value>% right);  
deque(deque<Value>^ right);  
explicit deque(size_type count);  
deque(size_type count, value_type val);  
template<typename InIt>  
    deque(InIt first, InIt last);  
deque(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *count*  
 Число элементов для вставки.  
  
 *Первый*  
 Начало диапазона для вставки.  
  
 *последний*  
 Конец диапазона для вставки.  
  
 *right*  
 Объект или диапазон для вставки.  
  
 *Val*  
 Значение элемента для вставки.  
  
### <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `deque();`  
  
 Инициализирует управляемую последовательность не содержит элементов. Используется для указания пустую начальную управляемую последовательность.  
  
 Конструктор:  
  
 `deque(deque<Value>% right);`  
  
 Инициализирует управляемую последовательность последовательностью [`right.begin()`, `right.end()`). Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объекта deque *правой*. Дополнительные сведения об итерациях см. в разделе [deque::begin (STL/CLR)](#begin) и [deque::end (STL/CLR)](#end).  
  
 Конструктор:  
  
 `deque(deque<Value>^ right);`  
  
 Инициализирует управляемую последовательность последовательностью [`right->begin()`, `right->end()`). Используется для указания начальной управляемой последовательности, который является копией последовательности, управляемой объекта deque, дескриптор которого *правой*.  
  
 Конструктор:  
  
 `explicit deque(size_type count);`  
  
 Инициализирует управляемую последовательность с помощью *число* элементы каждого со значением `value_type()`. Он понадобится на весь контейнер с элементами, каждый из которых значение по умолчанию.  
  
 Конструктор:  
  
 `deque(size_type count, value_type val);`  
  
 Инициализирует управляемую последовательность с помощью *число* элементы каждого со значением *val*. Он понадобится на весь контейнер с элементами, каждый из которых и то же значение.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 Инициализирует управляемую последовательность последовательностью [`first`, `last`). Используется, чтобы сделать управляемую последовательность копией другой последовательности.  
  
 Конструктор:  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Инициализирует управляемую последовательность последовательностью, назначенному с помощью перечислителя *правой*. Используется для создания копии другой последовательности, описываемого перечислитель управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_construct.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::deque<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::deque<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::deque<wchar_t>::iterator it = c3.end();   
    cliext::deque<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::deque<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::deque<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  

## <a name="difference_type"></a> deque::difference_type (STL/CLR)
Типы со знаком расстояния между двумя элементами.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает число со знаком элемент.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_deque_difference_type.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::deque<wchar_t>::difference_type diff = 0;   
    for (cliext::deque<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::deque<wchar_t>::iterator it = c1.end();   
        it != c1.begin(); --it) --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
end()-begin() = 3  
begin()-end() = -3  
```  
  
## <a name="empty"></a> deque::Empty (STL/CLR)
Проверяет отсутствие элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
bool empty();  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение true для пустой управляемой последовательности. Это эквивалентно [deque::size (STL/CLR)](#size)`() == 0`. Можно использовать для тестирования ли очередь пуста.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_empty.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
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

## <a name="end"></a> deque::End (STL/CLR)
Задает конец управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator end();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор произвольного доступа, указывающий на место сразу за концом управляемой последовательности. Используется для получения итератора, который обозначает `current` конец управляемой последовательности, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_end.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    cliext::deque<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
 a x y  
```  

## <a name="erase"></a> deque::Erase (STL/CLR)
Удаляет элементы в указанных позициях.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Параметры  
 *Первый*  
 Начало диапазона для удаления.  
  
 *последний*  
 Конец диапазона для удаления.  
  
 *where*  
 Подлежащий удалению элемент.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член удаляет элемент управляемой последовательности, на которые указывают *где*. Используется для удаления одного элемента.  
  
 Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`). Используется для удаления ноль или более идущих подряд элементов.  
  
 Обе функции-члены возвращают итератор, указывающий на первый элемент, находящийся за всеми удаленными элементами, или [deque::end (STL/CLR)](#end) `()` Если такого элемента не существует.  
  
 После удаления элементов, количество копий элемента является линейной, в число элементов между концом стирания и близкий конец последовательности. (После удаления одного или нескольких элементов на любом конце последовательности, возникают не одной копии элемента.)  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_erase.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::deque<wchar_t>::iterator it = c1.end();   
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

## <a name="front"></a> deque::Front (STL/CLR)
Обращается к первому элементу.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
reference front();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает ссылку на первый элемент управляемой последовательности, который должен быть пустым. Используется для чтения или записи первый элемент, если известно, что он существует.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_front.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
front() = a  
 x b c  
```  

## <a name="front_item"></a> deque::front_item (STL/CLR)
Обращается к первому элементу.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
property value_type front_item;  
```  
  
### <a name="remarks"></a>Примечания  
 Свойство обращается к первый элемент управляемой последовательности, который должен быть пустым. Используется для чтения или записи первый элемент, если известно, что он существует.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_front_item.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
front_item = a  
 x b c  
```  

## <a name="generic_container"></a> deque::generic_container (STL/CLR)
Тип универсального интерфейса для контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef Microsoft::VisualC::StlClr::  
    IDeque<generic_value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает универсальный интерфейс для этого класса контейнера шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_generic_container.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(gc1->end(), L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push_back(L'e');   
  
    System::Collections::IEnumerator^ enum1 =   
        gc1->GetEnumerator();   
    while (enum1->MoveNext())   
        System::Console::Write(" {0}", enum1->Current);   
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

## <a name="generic_iterator"></a> deque::generic_iterator (STL/CLR)
Тип итератора для использования с универсальный интерфейс для контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerRandomAccessIterator<generic_value> generic_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип Описывает универсальные итератор, который может использоваться с универсальным интерфейсом для этого класса контейнера шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::deque<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::deque<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

## <a name="generic_reverse_iterator"></a> deque::generic_reverse_iterator (STL/CLR)
Тип обратного итератора для использования с универсальный интерфейс для контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип Описывает универсальные Обратный итератор, который может использоваться с универсальным интерфейсом для этого класса контейнера шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::deque<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();   
    cliext::deque<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a c c  
```  

## <a name="generic_value"></a> deque::generic_value (STL/CLR)
Тип элемента для использования с универсальный интерфейс для контейнера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект типа `GValue` , описывающий значение хранимого элемента для использования с универсальный интерфейс для этого класса контейнера шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_generic_value.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::deque<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::deque<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

## <a name="insert"></a> deque::Insert (STL/CLR)
Добавляет элементы в указанной позиции.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *count*  
 Число элементов для вставки.  
  
 *Первый*  
 Начало диапазона для вставки.  
  
 *последний*  
 Конец диапазона для вставки.  
  
 *right*  
 Перечисление для вставки.  
  
 *Val*  
 Значение элемента для вставки.  
  
 *where*  
 Место в контейнере, чтобы вставить перед.  
  
### <a name="remarks"></a>Примечания  
 Каждая члена функций операций вставки, прежде чем элемент, на которые указывают *где* в управляемой последовательности, последовательность, определяемое оставшимися операндами.  
  
 Первая функция-член вставляет элемент со значением *val* и возвращает итератор, указывающий на новый вставленный элемент. Используется для вставки одного элемента перед импортом, назначенному с помощью итератора.  
  
 Вторая функция-член вставляет повторение из *число* элементов со значением *val*. Используется для вставки ноль или более идущих подряд элементов, которые являются копиями все то же значение.  
  
 Если `InIt` имеет целочисленный тип, первая функция-член ведет себя так же, как `insert(where, (size_type)first, (value_type)last)`. В противном случае она вставляет последовательность [`first`, `last`). Используется для вставки ноль или более идущих подряд элементов, копируемых из другой последовательности.  
  
 Четвертая функция-член вставляет последовательность, назначенному с помощью *правой*. Используется для вставки описываемого перечислитель последовательности.  
  
 При вставке один элемент, количество копий элемента является линейной, в число элементов между курсор и близкий конец последовательности. (При вставке один или несколько элементов на любом конце последовательности, возникают не одной копии элемента.) Если `InIt` является итератора ввода, третья функция-член фактически выполняет единый вставки для каждого элемента в последовательности. В противном случае — при вставке `N` элементов, количество копий элемента линейное в `N` плюс количество элементов между курсор и близкий конец последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_insert.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  

## <a name="iterator"></a> deque::iterator (STL/CLR)
Тип итератора для управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp 
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект неопределенного типа `T1` , можно использовать в качестве итератора произвольного доступа для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    it = c1.begin();   
    *it = L'x';   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
x b c  
```  

## <a name="op_neq"></a> deque::operator! = (STL/CLR)
Deque не равны сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Value>  
    bool operator!=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(left == right)`. Можно использовать для тестирования ли *левой* не упорядочен так же, как *правой* когда два объекта deque, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_operator_ne.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="operator"></a> deque::operator(STL/CLR)
Обращается к элементу в указанной позиции.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
reference operator[](size_type pos);  
```  
  
#### <a name="parameters"></a>Параметры  
 *торговых терминалов*  
 Позиция элемента, к которому осуществляется доступ.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член возвращает referene элемент в позиции *pos*. Используется для доступа к элементу, позиция которого известно.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_operator_sub.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using subscripting   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1[1] = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a x c  
```  

## <a name="pop_back"></a> deque::pop_back (STL/CLR)
Удаляет последний элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void pop_back();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член Удаляет последний элемент управляемой последовательности, который должен быть пустым. Используется для сокращения очереди на один элемент в серверной части.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_pop_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_back();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b  
```  

## <a name="pop_front"></a> deque::pop_front (STL/CLR)
Удаляет первый элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void pop_front();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член удаляет первый элемент управляемой последовательности, который должен быть пустым. Используется для сокращения очереди на один элемент в начале.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_pop_front.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_front();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
b c  
```  
  
## <a name="push_back"></a> deque::push_back (STL/CLR)
Добавляет новый последний элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void push_back(value_type val);  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член вставляет элемент со значением `val` в конце управляемой последовательности. Используется для добавления другого элемента в очередь.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_push_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="push_front"></a> deque::push_front (STL/CLR)
Добавляет новый первый элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void push_front(value_type val);  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член вставляет элемент со значением `val` в начало управляемой последовательности. Используется для добавления другого элемента в очередь.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_push_front.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_front(L'a');   
    c1.push_front(L'b');   
    c1.push_front(L'c');   
  
// display contents " c b a"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
```  

## <a name="rbegin"></a> deque::rbegin (STL/CLR)
Задает начало обратной управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает Обратный итератор, который задает последний элемент управляемой последовательности или непосредственно перед началом пустой последовательности. Таким образом, он задает `beginning` обратной последовательности. Используется для получения итератора, который обозначает `current` начало отображаемой в обратном порядке управляемой последовательности, а его состояние можно изменить при изменении длины управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_rbegin.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
 a y x  
```  

## <a name="reference"></a> deque::Reference (STL/CLR)
Тип ссылки на элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает ссылку на элемент.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_deque_reference.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::deque<wchar_t>::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
  
// modify contents " a b c"   
    for (it = c1.begin(); it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::deque<wchar_t>::reference ref = *it;   
  
        ref += (wchar_t)(L'A' - L'a');   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
A B C  
```  

## <a name="rend"></a> deque::rend (STL/CLR)
Задает конец обратной управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает Обратный итератор, указывающий непосредственно перед началом управляемой последовательности. Таким образом, он задает `end` обратной последовательности. Используется для получения итератора, который обозначает `current` конец отображаемой в обратном порядке управляемой последовательности, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_deque_rend.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
 y x c  
```  

## <a name="resize"></a> deque::Resize (STL/CLR)
Изменяет количество элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>Параметры  
 *new_size*  
 Новый размер управляемой последовательности.  
  
 *Val*  
 Значение элемента-заполнителя.  
  
### <a name="remarks"></a>Примечания  
 Убедитесь, что функции-члены обоих [deque::size (STL/CLR)](#size) `()` этого момента возвращает *new_size*. Если это вынуждает сделать более длинной управляемую последовательность, первая функция-член добавляет элементы со значением `value_type()`, тогда как вторая функция-член добавляет элементы со значением *val*. Чтобы сделать управляемую последовательность более короткой, обе функции-члены фактически удалить последний элемент [deque::size (STL/CLR)](#size) `() -` `new_size` раз. Она понадобится, чтобы обеспечить размер управляемой последовательности *new_size*, сокращение или заполнения текущего управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  

## <a name="reverse_iterator"></a> deque::reverse_iterator (STL/CLR)
Тип обратного итератора для управляемой последовательности.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект неопределенного типа `T3` , можно использовать в качестве обратного итератора для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp 
// cliext_deque_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
x b a  
```  
 
## <a name="size"></a> deque::size (STL/CLR)
Подсчитывает количество элементов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
size_type size();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает длину управляемой последовательности. Используется для определения числа элементов в данный момент в управляемой последовательности. Если вас интересуют ли последовательность имеет ненулевой размер, см. в разделе [deque::empty (STL/CLR)](#empty)`()`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_size.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
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

## <a name="size_type"></a> deque::size_type (STL/CLR)
Тип расстояния со знаком между двумя элементами.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает элемент неотрицательное число.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_size_type.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::deque<wchar_t>::size_type diff = c1.end() - c1.begin();   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  

## <a name="swap"></a> deque::Swap (STL/CLR)
Меняет местами содержимое двух контейнеров.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void swap(deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *right*  
 Контейнер для обмена содержимым.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами управляемые последовательности между `*this` и *правой*. Она делает это в константном времени и не создает исключения. Можно использовать как быстрый способ местами содержимое двух контейнеров.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_swap.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> c2(5, L'x');   
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

## <a name="to_array"></a> deque::to_array (STL/CLR)
Копирует управляемой последовательности в новый массив.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает массив, содержащий управляемой последовательности. Вы можете использовать его для получения копии управляемой последовательности в форме массива.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_to_array.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
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
  
## <a name="value_type"></a> deque::value_type (STL/CLR)
Тип элемента.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра-шаблона *значение*.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_value_type.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::deque<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::deque<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="op_lt"></a> оператор&lt; (deque) (STL/CLR)
Очередь меньше, чем сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Value>  
    bool operator<(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Оператор функция возвращает значение true, если, для низшей позиции `i` для которого `!(right[i] < left[i])` верно, кроме того, `left[i] < right[i]`. В противном случае возвращается `left->size() < right->size()` можно использовать для тестирования ли *левой* упорядочен до *правой* когда два объекта deque, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_operator_lt.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="op_lteq"></a> оператор&lt;= (deque) (STL/CLR)
Deque меньше или равно сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Value>  
    bool operator<=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(right < left)`. Можно использовать для тестирования ли *левой* не упорядочен после *правой* когда два объекта deque, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_operator_le.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="op_as"></a> оператор = (deque) (STL/CLR)
Заменяет управляемую последовательность.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
deque<Value>% operator=(deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *right*  
 Контейнер для копирования.  
  
### <a name="remarks"></a>Примечания  
 Копирует оператор член *правой* объекту, затем возвращает `*this`. Оно позволяет заменить управляемую последовательность копией управляемой последовательности в *правой*.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_operator_as.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
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
  
## <a name="op_eq"></a> оператор == (deque) (STL/CLR)
Deque равны сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Value>  
    bool operator==(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает значение true, только в том случае, если управляются последовательностей *левой* и *правой* имеют одинаковую длину и для каждой позиции `i`, `left[i] ==` `right[i]`. Можно использовать для тестирования ли *левой* упорядочен так же, как *правой* когда два объекта deque, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_operator_eq.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="op_gt"></a> оператор&gt; (deque) (STL/CLR)
Очередь больше, чем сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Value>  
    bool operator>(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `right` `<` `left`. Можно использовать для тестирования ли *левой* упорядочен после *правой* когда два объекта deque, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_operator_gt.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="op_gteq"></a> оператор&gt;= (deque) (STL/CLR)
Сравнение больше или равно deque.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Value>  
    bool operator>=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 *left*  
 Левый контейнер для сравнения.  
  
 *right*  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(left` `<` `right)`. Можно использовать для тестирования ли *левой* не упорядочен до *правой* когда два объекта deque, по сравнению с элементом за элементом.  
  
### <a name="example"></a>Пример  
  
```cpp  
// cliext_deque_operator_ge.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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