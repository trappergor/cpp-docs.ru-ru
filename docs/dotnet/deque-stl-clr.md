---
title: deque (STL/CLR) | Документы Microsoft
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
ms.openlocfilehash: 881db763518f31d9682ba050e460d4a3f7b39317
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079829"
---
# <a name="deque-stlclr"></a>deque (STL/CLR)
Класс шаблона описывает объект, управляющий последовательностью элементов переменной длины с произвольного доступа. Используйте контейнер `deque` для управления последовательность элементов, выглядит как непрерывный блок памяти, но который можете увеличить или уменьшить конце без необходимости копировать все оставшиеся элементы. Поэтому он может реализовывать эффективно `double-ended queue`. (Поэтому имя.)  
  
 В следующем описании `GValue` совпадает со значением `Value` Если последний является типом ссылки, в этом случае он является `Value^`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
 GValue  
 Универсальный тип элемента в управляемой последовательности.  
  
 Значение  
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
|[deque::generic_iterator (STL/CLR)](#generic_iterator)|Тип итератора для универсальный интерфейс для контейнера.|  
|[deque::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Тип обратного итератора для универсальный интерфейс для контейнера.|  
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
|[deque::insert (STL/CLR)](#insert)|Добавляет элементы в заданной позиции.|  
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
|[operator> (deque) (STL/CLR)](#op_gt)|Определяет, если `deque` объект больше другого `deque` объекта.|  
|[operator>= (deque) (STL/CLR)](#op_gteq)|Определяет, если `deque` объекта больше или равно другому `deque` объекта.|  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание:|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Создание дубликата объекта.|  
|<xref:System.Collections.IEnumerable>|Последовательность элементов.|  
|<xref:System.Collections.ICollection>|Ведение группы элементов.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательности типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Ведение группы типизированных элементов.|  
|<xref:System.Collections.Generic.IList%601>|Ведение упорядоченная группа типизированных элементов.|  
|IDeque < значение\>|Ведение универсального контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Объект выделяет и освобождает память для им последовательность через хранимые массива дескрипторов, которые определяют блоки `Value` элементов. Массив увеличивается по требованию. Увеличение размера происходит таким образом, добавляя или добавления нового элемента обходится в константном времени, что изменяются элементов не осталось. Можно также удалить элемент на концах в константном времени и без нарушения работы оставшиеся элементы. Таким образом, deque является хорошим кандидатом для базового контейнера для шаблона класса [очереди (STL/CLR)](../dotnet/queue-stl-clr.md) или класс шаблона [стека (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 Объект `deque` объект поддерживает итераторами произвольного доступа, это означает, что можно ссылаться на элемент, непосредственно заданным его порядкового номера, начиная с нуля для первого элемента (внешнего) для [deque::size (STL/CLR)](#size) `() - 1` для последнего элемента (назад). Это также означает, что deque является хорошим кандидатом для базового контейнера для шаблона класса [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Итератор deque сохраняет дескриптор объекта его связанный deque, а также смещение элемента, на которую он обозначает. Вы можете использовать итераторы только с свои объекты связанного контейнера. Смещение элемента deque — `not` обязательно таким же, как его положение. Первый элемент вставлен имеет смещение ноль, далее добавленный элемент имеет смещение 1, но Далее присоединяемый элемент имеет смещение -1.  
  
 Вставки или удаления элементов на концах не `not` изменить значение на элемент, хранящийся в любой допустимый уровень защиты. Вставка или удаление внутренний элемент, однако `can` изменить значение элемента, сохраняются на данный сдвиг, можно также изменить значение, обозначенное итератор. (Контейнер может потребоваться копировать элементы вверх или вниз для создания отверстия перед вставкой или применить после очистки.) Тем не менее итератор deque остается допустимым до тех пор, пока его смещение определяет допустимый элемент. Кроме того, остается dereferencable допустимым итератором, его можно использовать для доступа или изменить значение элемента, он обозначает — при условии, что его смещение не равно смещение для итератора, возвращаемого методом `end()`.  
  
 Удаление или удалении элементов вызывает деструктор для сохраненное значение. Уничтожение контейнера удаляет все элементы. Таким образом контейнера, тип элементов которого является класс ссылки гарантирует, что ни один элемент пережить контейнера. Тем не менее, делает это контейнер, содержащий дескрипторы `not` уничтожить его элементов.  
 
## <a name="members"></a>Участники

## <a name="assign"></a> deque::Assign (STL/CLR)
Заменяет все элементы.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 `count`  
 Число элементов для вставки.  
  
 `first`  
 Начало диапазона для вставки.  
  
 `last`  
 Конец диапазона для вставки.  
  
 `right`  
 Перечисление для вставки.  
  
 `val`  
 Значение элемента, который требуется вставить.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член заменяет управляемую последовательность Повтор `count` элементов со значением `val`. Используется для заполнения элементов контейнера всех, имеющих то же значение.  
  
 Если `InIt` имеет целочисленный тип, вторая функция-член работает так же, как `assign((size_type)first, (value_type)last)`. В противном случае заменяет управляемую последовательность последовательностью [`first`, `last`). Используется для управляемой последовательности копии сделать другую последовательность.  
  
 Третья функция-член заменяет управляемую последовательность последовательности, указанной с помощью перечислителя `right`. Используется, чтобы сделать копию последовательности, описываемого перечислитель управляемой последовательности.  
  
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
  
```  
reference at(size_type pos);  
```  
  
#### <a name="parameters"></a>Параметры  
 pos  
 Позиция элемента, к которому осуществляется доступ.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает ссылку на элемент управляемой последовательности в позиции `pos`. Используется для чтения или записи элемент, позиция которого известно.  
  
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
  
```  
reference back();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает ссылку на последний элемент управляемой последовательности, который должен быть пустым. Используется для доступа к последним элементом, если известно, что он существует.  
  
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
  
```  
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
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор произвольного доступа, указывающий первый элемент управляемой последовательности или непосредственно за концом пустой последовательности. Используется для получения итератора, который обозначает `current` начало управляемой последовательности, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
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
  
```  
void clear();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член вызывает [deque::erase (STL/CLR)](#erase) `(` [deque::begin (STL/CLR)](#begin) `(),` [deque::end (STL/CLR)](#end) `())`. Используется, чтобы обеспечить пустой управляемой последовательности.  
  
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
  
```  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект незаданного типа `T2` , можно использовать в качестве постоянного итератора произвольного доступа для управляемой последовательности.  
  
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
  
```  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип, описывающий константную ссылку на элемент.  
  
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
  
```  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект незаданного типа `T4` , можно использовать в качестве постоянного обратного итератора для управляемой последовательности.  
  
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
  
```  
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
 `count`  
 Число элементов для вставки.  
  
 `first`  
 Начало диапазона для вставки.  
  
 `last`  
 Конец диапазона для вставки.  
  
 `right`  
 Объект или диапазон для вставки.  
  
 `val`  
 Значение элемента, который требуется вставить.  
  
### <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `deque();`  
  
 Инициализирует управляемой последовательности без элементов. Используется, чтобы указать пустую начальную управляемую последовательность.  
  
 Конструктор:  
  
 `deque(deque<Value>% right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right.begin()`, `right.end()`). Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объекта deque `right`. Дополнительные сведения об итераторах см. в разделе [deque::begin (STL/CLR)](#begin) и [deque::end (STL/CLR)](#end).  
  
 Конструктор:  
  
 `deque(deque<Value>^ right);`  
  
 Инициализирует управляемой последовательности с последовательностью [`right->begin()`, `right->end()`). Используется для указания начальной управляемой последовательности, который представляет собой копию последовательности, управляемой с дескриптором объекта deque `right`.  
  
 Конструктор:  
  
 `explicit deque(size_type count);`  
  
 Инициализирует управляемой последовательности с `count` элементы каждого со значением `value_type()`. Используется для заполнения контейнера с элементами, каждый из которых по умолчанию.  
  
 Конструктор:  
  
 `deque(size_type count, value_type val);`  
  
 Инициализирует управляемой последовательности с `count` элементы каждого со значением `val`. Используется для заполнения элементов контейнера всех, имеющих то же значение.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 Инициализирует управляемой последовательности с последовательностью [`first`, `last`). Используется для создания копии другой последовательности управляемой последовательности.  
  
 Конструктор:  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Инициализирует управляемой последовательности с последовательности, указанной с помощью перечислителя `right`. Используется для создания копии другой последовательности, описываемого перечислитель управляемой последовательности.  
  
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
Тип расстояния со знаком между двумя элементами.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип, описывающий счетчик знаком элементов.  
  
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
  
```  
bool empty();  
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение true для пустой управляемой последовательности. Это эквивалентно [deque::size (STL/CLR)](#size)`() == 0`. Используется, чтобы проверить, является ли объект deque пустым.  
  
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
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор произвольного доступа, указывающий на место сразу за конец управляемой последовательности. Используется для получения итератора, который обозначает `current` конец управляемой последовательности, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
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
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Параметры  
 `first`  
 Начало диапазона для удаления.  
  
 `last`  
 Конец диапазона для удаления.  
  
 `where`  
 Подлежащий удалению элемент.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член удаляет элемент управляемой последовательности, указанный параметром `where`. Используется для удаления одного элемента.  
  
 Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`). Используется для удаления ноль или более последовательных элементов.  
  
 Обе функции-члены возвращают итератор, указывающий на первый элемент, находящийся за всеми удаленными элементами, или [deque::end (STL/CLR)](#end) `()` Если такого элемента не существует.  
  
 После удаления элементов, количество копий элемента линейно количество элементов между концом стирания и дальнюю конец последовательности. (После удаления одного или нескольких элементов на любом конце последовательности, выполнено ни одной копии элемента.)  
  
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
  
```  
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
  
```  
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
  
```  
typedef Microsoft::VisualC::StlClr::  
    IDeque<generic_value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип, описывающий универсальный интерфейс для класса контейнера шаблона.  
  
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
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerRandomAccessIterator<generic_value> generic_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип Описывает универсальные итератор, который может использоваться с универсальный интерфейс для класса контейнера шаблона.  
  
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
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип Описывает универсальные Обратный итератор, который может использоваться с универсальный интерфейс для класса контейнера шаблона.  
  
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
  
```  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект типа `GValue` , описывающий значение хранимого элемента для использования с универсальный интерфейс для класса контейнера шаблона.  
  
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
Добавляет элементы в заданной позиции.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Параметры  
 `count`  
 Число элементов для вставки.  
  
 `first`  
 Начало диапазона для вставки.  
  
 `last`  
 Конец диапазона для вставки.  
  
 `right`  
 Перечисление для вставки.  
  
 `val`  
 Значение элемента, который требуется вставить.  
  
 `where`  
 Место в контейнере, чтобы вставить перед.  
  
### <a name="remarks"></a>Примечания  
 Каждый член функции вставки перед элементом, на который указывает `where` в управляемой последовательности, последовательность указанный оставшимися операндами.  
  
 Первая функция-член вставляет элемент со значением `val` и возвращает итератор, указывающий на вставленный элемент. Используется для вставки одного элемента перед импортом, назначенному с помощью итератора.  
  
 Вторая функция-член вставляет повторение `count` элементов со значением `val`. Используется для вставки ноль или более смежных элементов, которые являются все копии и то же значение.  
  
 Если `InIt` имеет целочисленный тип, первая функция-член ведет себя так же, как `insert(where, (size_type)first, (value_type)last)`. В противном случае он вставляет последовательность [`first`, `last`). Используется для вставки ноль или более смежных элементов, копируемых из другой последовательности.  
  
 Четвертая функция-член вставляет последовательность, назначенному с помощью `right`. Используется для вставки последовательности, описываемого перечислителя.  
  
 При вставке один элемент, количество копий элемента линейно количество элементов между курсор и дальнюю конец последовательности. (При вставке один или несколько элементов на любом конце последовательности, выполнено ни одной копии элемента.) Если `InIt` является итератором ввода третья функция-член выполняет один вставки для каждого элемента в последовательности. В противном случае — при вставке `N` элементов, количество копий элемента линейно `N` плюс количество элементов между курсор и дальнюю конец последовательности.  
  
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
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект незаданного типа `T1` , можно использовать в качестве итератора произвольного доступа для управляемой последовательности.  
  
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
Deque равно сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    bool operator!=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 `left`  
 Левый контейнер для сравнения.  
  
 `right`  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(left == right)`. Можно использовать для тестирования ли `left` не упорядочен таким же, как `right` при двух объектов deque, сравниваемые элемент элемент.  
  
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
  
```  
reference operator[](size_type pos);  
```  
  
#### <a name="parameters"></a>Параметры  
 pos  
 Позиция элемента, к которому осуществляется доступ.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член возвращает referene на элемент в позиции `pos`. Используется для доступа к элементу, позиция которого известно.  
  
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
  
```  
void pop_back();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член Удаляет последний элемент управляемой последовательности, который должен быть пустым. Используется для сокращения deque на один элемент на задней панели.  
  
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
  
```  
void pop_front();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член удаляет первый элемент управляемой последовательности, который должен быть пустым. Используется для сокращения deque на один элемент в начале.  
  
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
  
```  
void push_back(value_type val);  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член вставляет элемент со значением `val` на конец управляемой последовательности. Используется для добавления другого элемента deque.  
  
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
  
```  
void push_front(value_type val);  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член вставляет элемент со значением `val` в начало управляемой последовательности. Используется, чтобы добавить другой элемент для deque.  
  
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
  
```  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает Обратный итератор, который задает последний элемент управляемой последовательности или начало пустую последовательность. Таким образом, он обозначает `beginning` обратной последовательности. Используется для получения итератора, который обозначает `current` начало управляемой последовательности, отображаемой в обратном порядке, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
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
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает ссылку на элемент.  
  
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
  
```  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор, указывающий начало управляемой последовательности. Таким образом, он обозначает `end` обратной последовательности. Используется для получения итератора, который обозначает `current` конец управляемой последовательности, отображаемой в обратном порядке, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
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
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>Параметры  
 new_size  
 Новый размер управляемой последовательности.  
  
 Функция Val  
 Значение элемента-заполнителя.  
  
### <a name="remarks"></a>Примечания  
 Убедитесь, что функции-члены обоих [deque::size (STL/CLR)](#size) `()` исходя из возвращает `new_size`. Если это вынуждает сделать более длинной управляемую последовательность, первая функция-член добавляет элементы со значением `value_type()`, тогда как вторая функция-член добавляет элементы со значением `val`. Чтобы сделать более короткие управляемой последовательности, обе функции-члены фактически удалить последний элемент [deque::size (STL/CLR)](#size) `() -` `new_size` раз. Используется, чтобы обеспечить размер управляемой последовательности `new_size`, trimming или заполнения текущего управляемой последовательности.  
  
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
  
```  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает объект незаданного типа `T3` , можно использовать в качестве обратного итератора для управляемой последовательности.  
  
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
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает длину управляемой последовательности. Используется для определения количества элементов в данный момент в управляемой последовательности. Если вас интересует ли последовательность имеет ненулевое значение, размер, в разделе [deque::empty (STL/CLR)](#empty)`()`.  
  
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
Тип расстояния со знаком между двумя элемент.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает элемент неотрицательное число.  
  
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
  
```  
void swap(deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Контейнер для обмена содержимым.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами управляемые последовательности между `*this` и `right`. Она делает это в константном времени, и он не создает исключений. Используется в качестве быстро меняет местами содержимое двух контейнеров.  
  
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
  
```  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает массив, содержащий управляемой последовательности. Используется для получения копии управляемой последовательности в виде массива.  
  
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
  
```  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Value`.  
  
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
Deque меньше, чем сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    bool operator<(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый контейнер для сравнения.  
  
 right  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Оператор функция возвращает значение true, если для нижнюю позицию `i` которого `!(right[i] < left[i])` верно, кроме того, `left[i] < right[i]`. В противном случае он возвращает `left->size() < right->size()` использовать для тестирования ли `left` упорядочен до `right` при двух объектов deque, сравниваемые элемент элемент.  
  
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
  
```  
template<typename Value>  
    bool operator<=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый контейнер для сравнения.  
  
 right  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(right < left)`. Можно использовать для тестирования ли `left` не упорядочен после `right` при двух объектов deque, сравниваемые элемент элемент.  
  
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
  
```  
deque<Value>% operator=(deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Контейнер для копирования.  
  
### <a name="remarks"></a>Примечания  
 Копирует оператор член `right` объекту, затем возвращает `*this`. Он позволяет заменить управляемую последовательность копией управляемой последовательности в `right`.  
  
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
Сравнение равно deque.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    bool operator==(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый контейнер для сравнения.  
  
 right  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает значение true, только в том случае, если последовательности, на которые управляются `left` и `right` имеют одинаковую длину и для каждого положения `i`, `left[i] ==` `right[i]`. Можно использовать для тестирования ли `left` упорядочен таким же, как `right` при двух объектов deque, сравниваемые элемент элемент.  
  
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
Deque больше сравнения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    bool operator>(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый контейнер для сравнения.  
  
 right  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `right` `<` `left`. Можно использовать для тестирования ли `left` упорядочен после `right` при двух объектов deque, сравниваемые элемент элемент.  
  
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
Сравнение deque больше или равно.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    bool operator>=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый контейнер для сравнения.  
  
 right  
 Правый контейнер для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Функция оператор возвращает `!(left` `<` `right)`. Можно использовать для тестирования ли `left` не упорядочен до `right` при двух объектов deque, сравниваемые элемент элемент.  
  
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
 