---
title: Класс weak_ptr
ms.date: 07/29/2019
f1_keywords:
- memory/std::weak_ptr
- memory/std::weak_ptr::element_type
- memory/std::weak_ptr::expired
- memory/std::weak_ptr::lock
- memory/std::weak_ptr::owner_before
- memory/std::weak_ptr::reset
- memory/std::weak_ptr::swap
- memory/std::weak_ptr::use_count
- memory/std::weak_ptr::operator=
helpviewer_keywords:
- std::weak_ptr [C++]
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
ms.openlocfilehash: 2591c4cd124f83085235828d3eb29ab1a90d894a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72684075"
---
# <a name="weak_ptr-class"></a>Класс weak_ptr

Создает оболочку слабо связанного указателя.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T> class weak_ptr;
```

### <a name="parameters"></a>Параметры

*T* \
Тип, управляемый слабым указателем.

## <a name="remarks"></a>Заметки

Шаблон класса описывает объект, указывающий на ресурс, который управляется одним или несколькими объектами [shared_ptr](shared-ptr-class.md) . Объекты `weak_ptr`, указывающие на ресурс, не влияют на счетчик ссылок ресурса. Когда удаляется последний объект `shared_ptr`, который управляет этим ресурсом, ресурс будет освобожден, даже если имеются `weak_ptr` объекты, указывающие на этот ресурс. Такое поведение важно для предотвращения циклов в структурах данных.

Объект `weak_ptr` указывает на ресурс, если он был создан из объекта `shared_ptr`, который владеет этим ресурсом; если он был создан из объекта `weak_ptr`, который указывает на этот ресурс; или если этот ресурс был назначен ему с помощью [operator=](#op_eq). Объект `weak_ptr` не предоставляет прямой доступ к ресурсу, на который он указывает. Код, которому необходимо использовать ресурс, делает с это с помощью объекта `shared_ptr`, который владеет этим ресурсом. Этот объект создается функцией-членом [lock](#lock). Срок действия объекта `weak_ptr` истек, когда ресурс, на который он указывает, был освобожден, так как все объекты `shared_ptr`, владеющие ресурсом, были уничтожены. Вызов `lock` в объекте `weak_ptr` с истекшим сроком действия создает пустой объект shared_ptr.

Пустой объект weak_ptr не указывает на ресурсы и не имеет управляющего блока. Его функция-член `lock` возвращает пустой объект shared_ptr.

Цикл происходит, если два или более ресурсов, управляемых объектами `shared_ptr` содержат ссылающиеся друг на друга объекты `shared_ptr`. Например, цикличный связанный список с тремя элементами содержит головной узел `N0`; этот узел включает объект `shared_ptr`, который владеет следующим узлом, `N1`; этот узел содержит объект `shared_ptr`, который владеет следующим узлом, `N2`; этот узел, в свою очередь, содержит объект `shared_ptr`, который владеет головным узлом `N0`, что создает цикл. В этом случае количество ссылок никогда не становится нулевым, а узлы в цикле никогда не освобождаются. Чтобы исключить цикл, последний узел `N2` должен содержать объект `weak_ptr`, указывающий на `N0`, а не объект `shared_ptr`. Поскольку объект `weak_ptr` не владеет `N0` он не влияет на счетчик ссылок `N0`, а при уничтожении последней ссылки программы на головной узел узлы в списке также будут уничтожены.

## <a name="members"></a>Члены

|||
|-|-|
| **Конструкторы** | |
|[weak_ptr](#weak_ptr)|Создает документ `weak_ptr`.|
| **Деструкторы** | |
|[~ weak_ptr](#tilde-weak_ptr)|Создает документ `weak_ptr`.|
| **Typedefs** | |
|[element_type](#element_type)|Тип элемента.|
| **Функции элементов** | |
|[expired](#expired)|Проверяет, истек ли срок действия владения.|
|[lock](#lock)|Получает эксклюзивные права владения ресурсом.|
|[owner_before](#owner_before)|Возвращает **значение true** , если это `weak_ptr` упорядочивается до (или меньше) указанного указателя.|
|[reset](#reset)|Освобождает ресурс, которым владеет.|
|[swap](#swap)|Меняет местами два объекта `weak_ptr`.|
|[use_count](#use_count)|Подсчитывает число объектов `shared_ptr`.|
| **Инструкции** | |
|[оператор=](#op_eq)|Заменяет ресурс, которым владеет.|

## <a name="element_type"></a>element_type

Тип элемента.

```cpp
typedef T element_type; // through C++17
using element_type = remove_extent_t<T>; // C++20
```

### <a name="remarks"></a>Заметки

Этот тип является синонимом для параметра шаблона `T`.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::weak_ptr<int>::element_type val = *wp0.lock();

    std::cout << "*wp0.lock() == " << val << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
```

## <a name="expired"></a>истек

Проверяет, истек ли срок владения, т. е. объект, на который указывает ссылка, удален.

```cpp
bool expired() const noexcept;
```

### <a name="remarks"></a>Заметки

Функция члена возвращает **значение true** , если срок действия `*this` истек; в противном случае — **значение false**.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_expired.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="lock"></a>скрыть

Получает `shared_ptr`, который предоставляет право владения ресурсом.

```cpp
shared_ptr<T> lock() const noexcept;
```

### <a name="remarks"></a>Заметки

Функция члена возвращает пустой объект [shared_ptr](shared-ptr-class.md) , если срок действия `*this` истек. в противном случае возвращается объект `shared_ptr<T>`, которому принадлежит ресурс, который `*this` указывает на. Возвращает значение, эквивалентное атомарному выполнению `expired() ? shared_ptr<T>() : shared_ptr<T>(*this)`.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_lock.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="op_eq"></a>Оператор =

Заменяет ресурс, которым владеет.

```cpp
weak_ptr& operator=(const weak_ptr& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& ptr) noexcept;
```

### <a name="parameters"></a>Параметры

*Другие* \
Тип, управляемый общим или слабым указателем аргумента.

\ *ptr*
Слабый указатель или общий указатель для копирования.

### <a name="remarks"></a>Заметки

Все операторы освобождают ресурс, на который сейчас указывает, `*this` и назначает владение ресурсом с именем *ptr* для `*this`. Если оператор завершается с ошибкой, он оставляет `*this` без изменений. Каждый оператор имеет результат, эквивалентный `weak_ptr(ptr).swap(*this)`.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::shared_ptr<int> sp1(new int(10));
    wp0 = sp1;
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::weak_ptr<int> wp1;
    wp1 = wp0;
    std::cout << "*wp1.lock() == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
*wp0.lock() == 10
*wp1.lock() == 10
```

## <a name="owner_before"></a>owner_before

Возвращает **значение true** , если это `weak_ptr` упорядочивается до (или меньше) указанного указателя.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr) const noexcept;

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr) const noexcept;
```

### <a name="parameters"></a>Параметры

\ *ptr*
Ссылка lvalue либо на `shared_ptr`, либо на `weak_ptr`.

### <a name="remarks"></a>Заметки

Функция-член шаблона возвращает **значение true** , если `*this` упорядочивается до *ptr*.

## <a name="reset"></a>перезапуск

Освобождает принадлежащий ресурс.

```cpp
void reset() noexcept;
```

### <a name="remarks"></a>Заметки

Функция члена освобождает ресурс, на который указывает, `*this` и преобразует `*this` в пустой объект `weak_ptr`.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp(new int(5));
    std::weak_ptr<int> wp(sp);
    std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    wp.reset();
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    return (0);
}
```

```Output
*wp.lock() == 5
wp.expired() == false
wp.expired() == true
```

## <a name="swap"></a>позиции

Меняет местами два объекта `weak_ptr`.

```cpp
void swap(weak_ptr& wp) noexcept;
```

Также включает специализацию:

```cpp
template<class T>
void swap(weak_ptr<T>& a, weak_ptr<T>& b) noexcept;
```

### <a name="parameters"></a>Параметры

\ *ВЧ*
Слабый указатель, который будет заменен.

### <a name="remarks"></a>Заметки

После `swap` ресурс, на который первоначально указывался `*this`, указывает *WP*, а ресурс, на который первоначально указывался *WP* , указывает на `*this`. Функция не изменяет счетчики ссылок для этих двух ресурсов и не создает никаких исключений. Воздействие специализации шаблона эквивалентно `a.swap(b)`.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="use_count"></a>use_count

Подсчитывает количество объектов `shared_ptr`, владеющих общим ресурсом.

```cpp
long use_count() const noexcept;
```

### <a name="remarks"></a>Заметки

Функция-член возвращает число объектов `shared_ptr`, которые являются владельцем ресурса, на который указывает `*this`.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    return (0);
}
```

```Output
wp.use_count() == 1
wp.use_count() == 2
```

## <a name="weak_ptr"></a>weak_ptr

Создает документ `weak_ptr`.

```cpp
constexpr weak_ptr() noexcept;

weak_ptr(const weak_ptr& wp) noexcept;

weak_ptr(weak_ptr&& wp) noexcept;

template <class Other>
weak_ptr(const weak_ptr<Other>& wp) noexcept;

template <class Other>
weak_ptr(weak_ptr<Other>&& sp) noexcept;

template <class Other>
weak_ptr(const shared_ptr<Other>& sp) noexcept;
```

### <a name="parameters"></a>Параметры

*Другие* \
Тип, которым управляет общий или слабый указатель на аргумент. Эти конструкторы не участвуют в разрешении перегрузки, если _другие \*_ не совместимы с `element_type*`.

\ *ВЧ*
Слабый указатель для копирования.

\ *SP*
Общий указатель для копирования.

### <a name="remarks"></a>Заметки

Конструктор по умолчанию конструирует пустой объект `weak_ptr`. Конструкторы, которые принимают аргумент, создают пустой объект `weak_ptr`, если указатель аргумента пуст. В противном случае они создают объект `weak_ptr`, указывающий на ресурс с именем, указанным в аргументе. Счетчик ссылок общего объекта не изменен.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp0;
    std::cout << "wp0.expired() == " << std::boolalpha
        << wp0.expired() << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp1(sp1);
    std::cout << "*wp1.lock() == "
        << *wp1.lock() << std::endl;

    std::weak_ptr<int> wp2(wp1);
    std::cout << "*wp2.lock() == "
        << *wp2.lock() << std::endl;

    return (0);
}
```

```Output
wp0.expired() == true
*wp1.lock() == 5
*wp2.lock() == 5
```

## <a name="tilde-weak_ptr"></a>~ weak_ptr

Удаляет `weak_ptr`.

```cpp
~weak_ptr();
```

### <a name="remarks"></a>Заметки

Деструктор уничтожает этот `weak_ptr`, но не влияет на счетчик ссылок объекта, на который его хранятся точки указателя.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](cpp-standard-library-header-files.md)\
[\<memory>](memory.md)\
[класс shared_ptr](shared-ptr-class.md)
