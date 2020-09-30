---
title: Класс initializer_list
description: Ссылка на класс initializer_list в стандартной библиотеке C++, реализованная корпорацией Майкрософт в Visual Studio.
ms.date: 01/28/2020
f1_keywords:
- initializer_list/std::initializer_list::initializer_list
- initializer_list/std::initializer_list::begin
- initializer_list/std::initializer_list::end
- initializer_list/std::initializer_list::size
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
helpviewer_keywords:
- std::initializer_list::initializer_list
- std::initializer_list::begin
- std::initializer_list::end
- std::initializer_list::size
ms.openlocfilehash: 232855fbcac1e4df9af7cf956fda80201326a401
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504641"
---
# <a name="initializer_list-class"></a>Класс initializer_list

Предоставляет доступ к массиву элементов, в котором каждый элемент имеет указанный тип.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class initializer_list
```

### <a name="parameters"></a>Параметры

*Тип*\
Тип данных элемента для сохранения в `initializer_list`.

## <a name="remarks"></a>Remarks

`initializer_list` можно создать при помощи списка заключенного в фигурные скобки инициализатора:

```cpp
initializer_list<int> i1{ 1, 2, 3, 4 };
```

компилятор преобразует списки заключенного в фигурные скобки инициализатора с однородными элементами в `initializer_list` каждый раз, когда сигнатуре функции требуется `initializer_list`. Дополнительные сведения об использовании см. в `initializer_list` разделе [унифицированная инициализация и делегирование конструкторов](../cpp/initializing-classes-and-structs-without-constructors-cpp.md) .

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[initializer_list](#initializer_list)|Создает объект типа `initializer_list`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|`value_type`|Тип элементов в `initializer_list`.|
|`reference`|Тип, предоставляющий ссылку на элемент в `initializer_list`.|
|`const_reference`|Тип, предоставляющий постоянную ссылку на элемент в `initializer_list`.|
|`size_type`|Тип, представляющий количество элементов в `initializer_list`.|
|`iterator`|Тип, предоставляющий итератор для `initializer_list`.|
|`const_iterator`|Тип, предоставляющий постоянный итератор для `initializer_list`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[начале](#begin)|Возвращает указатель на первый элемент в `initializer_list`.|
|[end](#end)|Возвращает указатель на позицию, следующую за последним элементом в `initializer_list`.|
|[size](#size)|Возвращает количество элементов в контейнере `initializer_list`.|

## <a name="requirements"></a>Требования

**Заголовок:**\<initializer_list>

**Пространство имен:** std

## <a name="initializer_listbegin"></a><a name="begin"></a> initializer_list:: Begin

Возвращает указатель на первый элемент в `initializer_list`.

```cpp
constexpr const InputIterator* begin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый элемент `initializer_list`. Если список пуст, указателем будет одинаковым для начала и конца списка.

## <a name="initializer_listend"></a><a name="end"></a> initializer_list:: end

Возвращает указатель на позицию, следующую за последним элементом в `initializer list`.

```cpp
constexpr const InputIterator* end() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на позицию, следующую за последним элементом в списке. Если список пуст, то он совпадает с указателем на первый элемент в списке.

## <a name="initializer_listinitializer_list"></a><a name="initializer_list"></a> initializer_list:: initializer_list

Создает объект типа `initializer_list`.

```cpp
constexpr initializer_list() noexcept;
initializer_list(const InputIterator First, const InputIterator Last);
```

### <a name="parameters"></a>Параметры

*Началь*\
Положение первого элемента в диапазоне копируемых элементов.

*Последняя*\
Положение первого элемента после диапазона копируемых элементов.

### <a name="remarks"></a>Remarks

Объект `initializer_list` основан на массиве объектов указанного типа. При копировании `initializer_list` создается второй экземпляр списка, указывающий на те же объекты; базовые объекты не копируются.

### <a name="example"></a>Пример

```cpp
// initializer_list_class.cpp
// compile with: /EHsc
#include <initializer_list>
#include <iostream>

int main()
{
    using namespace std;
    // Create an empty initializer_list c0
    initializer_list <int> c0;

    // Create an initializer_list c1 with 1 element
    initializer_list <int> c1{ 3 };

    // Create an initializer_list c2 with 5 elements
    initializer_list <int> c2{ 5, 4, 3, 2, 1 };

    // Create a copy, initializer_list c3, of initializer_list c2
    initializer_list <int> c3(c2);

    // Create a initializer_list c4 by copying the range c3[ first,  last)
    const int* c3_ptr = c3.begin();
    c3_ptr++;
    c3_ptr++;
    initializer_list <int> c4(c3.begin(), c3_ptr);

    // Move initializer_list c4 to initializer_list c5
    initializer_list <int> c5(move(c4));

    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    cout << "c2 =";
    for (auto c : c2)
        cout << " " << c;
    cout << endl;

    cout << "c3 =";
    for (auto c : c3)
        cout << " " << c;
    cout << endl;

    cout << "c5 =";
    for (auto c : c5)
        cout << " " << c;
    cout << endl;
}
```

```Output
c1 = 3
c2 = 5 4 3 2 1
c3 = 5 4 3 2 1
c5 = 5 4
```

## <a name="initializer_listsize"></a><a name="size"></a> initializer_list:: size

Возвращает количество элементов в списке.

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в списке.

## <a name="see-also"></a>См. также раздел

[<forward_list>](../standard-library/forward-list.md)
