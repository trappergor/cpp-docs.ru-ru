---
title: Класс weak_ptr | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03cd10d3efac16521cf826f3d9081ec533b9abec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="weakptr-class"></a>Класс weak_ptr

Создает оболочку слабо связанного указателя.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _Ty>
   class weak_ptr {
public:
   typedef Ty element_type;
   weak_ptr();
   weak_ptr(const weak_ptr&);
   template <class Other>
      weak_ptr(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr(const shared_ptr<Other>&);
   weak_ptr& operator=(const weak_ptr&);
   template <class Other>
      weak_ptr& operator=(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr& operator=(shared_ptr<Other>&);
   void swap(weak_ptr&);
   void reset();
   long use_count() const;
   bool expired() const;
   shared_ptr<Ty> lock() const;
   };
```

### <a name="parameters"></a>Параметры

`Ty` Тип, управляемый слабым указателем.

## <a name="remarks"></a>Примечания

Класс шаблона описывает объект, который указывает на ресурс, находящийся под управлением одного или нескольких объектов [класса shared_ptr](../standard-library/shared-ptr-class.md). Объекты `weak_ptr`, которые указывают на ресурс, не влияют на количество ссылок на ресурс. Таким образом, когда последний объект `shared_ptr`, который управляет этим ресурсом, будет уничтожен, ресурс освободится, даже если существуют объекты `weak_ptr`, указывающие на этот ресурс. Это важно, чтобы избежать циклов в структурах данных.

Объект `weak_ptr` указывает на ресурс, если он был создан из объекта `shared_ptr`, который владеет этим ресурсом; если он был создан из объекта `weak_ptr`, который указывает на этот ресурс; или если этот ресурс был назначен ему с помощью [operator=](#op_eq). Объект `weak_ptr` не предоставляет прямой доступ к ресурсу, на который он указывает. Код, которому необходимо использовать ресурс, делает с это с помощью объекта `shared_ptr`, который владеет этим ресурсом. Этот объект создается функцией-членом [lock](#lock). Срок действия объекта `weak_ptr` истекает, если ресурс, на который он указывает, был освобожден, так как все объекты `shared_ptr`, владеющие ресурсом, были уничтожены. Вызов `lock` в объекте `weak_ptr` с истекшим сроком действия создает пустой объект shared_ptr.

Пустой объект weak_ptr не указывает на какие-либо ресурсы и не содержит блок управления. Его функция-член `lock` возвращает пустой объект shared_ptr.

Цикл происходит, если два или более ресурсов, управляемых объектами `shared_ptr` содержат ссылающиеся друг на друга объекты `shared_ptr`. Например, цикличный связанный список с тремя элементами содержит головной узел `N0`; этот узел включает объект `shared_ptr`, который владеет следующим узлом, `N1`; этот узел содержит объект `shared_ptr`, который владеет следующим узлом, `N2`; этот узел, в свою очередь, содержит объект `shared_ptr`, который владеет головным узлом `N0`, что создает цикл. В этой ситуации ни один из счетчиков ссылок не станет нулем, а узлы в цикле не будут освобождены. Чтобы исключить цикл, последний узел `N2` должен содержать объект `weak_ptr`, указывающий на `N0`, а не объект `shared_ptr`. Так как объект `weak_ptr` не владеет `N0`, он не влияет на количество ссылок `N0`, а при уничтожении последней ссылки программы на головной узел узлы в списке также будут уничтожены.

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[weak_ptr](#weak_ptr)|Создает документ `weak_ptr`.|

### <a name="methods"></a>Методы

|||
|-|-|
|[element_type](#element_type)|Тип элемента.|
|[expired](#expired)|Проверяет, истек ли срок действия владения.|
|[lock](#lock)|Получает эксклюзивные права владения ресурсом.|
|[owner_before](#owner_before)|Возвращает `true`, если этот объект `weak_ptr` заказывался раньше заданного указателя (или меньше него).|
|[reset](#reset)|Освобождает ресурс, которым владеет.|
|[swap](#swap)|Меняет местами два объекта `weak_ptr`.|
|[use_count](#use_count)|Считает количество назначенных объектов `shared_ptr`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_eq)|Заменяет ресурс, которым владеет.|

## <a name="requirements"></a>Требования

**Заголовок:** \<memory>

**Пространство имен:** std

## <a name="element_type"></a>  element_type

Тип элемента.

```cpp
typedef Ty element_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Ty`.

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

## <a name="expired"></a>  expired

Проверяет, истек ли срок действия владения.

```cpp
bool expired() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает `true`, если срок владения `*this` истек, в противном случае `false`.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_expired.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

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

## <a name="lock"></a>  lock

Получает эксклюзивные права владения ресурсом.

```cpp
shared_ptr<Ty> lock() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает пустой объект shared_ptr, если `*this` истек; в противном случае возвращается [класс shared_ptr](../standard-library/shared-ptr-class.md)\<за этот год > объект, которому принадлежит ресурс, `*this` указывает.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_lock.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

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

## <a name="op_eq"></a>  оператор=

Заменяет ресурс, которым владеет.

```cpp
weak_ptr& operator=(const weak_ptr& wp);

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Параметры

`Other` Тип, управляемый общий или слабый указатель на аргумент.

`wp` Слабый указатель для копирования.

`sp` Общий указатель для копирования.

### <a name="remarks"></a>Примечания

Все операторы освобождают ресурс, на который указывает `*this`, и назначают `*this` в качестве владельца ресурса, название которого указано в последовательности операндов. Если оператор завершается сбоем, значение `*this` остается неизменным.

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

## <a name="owner_before"></a>  owner_before

Возвращает `true`, если этот объект `weak_ptr` заказывался раньше заданного указателя (или меньше него).

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr);
```

### <a name="parameters"></a>Параметры

`ptr` `lvalue` Ссылка на каждый `shared_ptr` или `weak_ptr`.

### <a name="remarks"></a>Примечания

Функция-член шаблона возвращает `true` Если `*this` — `ordered before` `ptr`.

## <a name="reset"></a>  reset

Освобождает ресурс, которым владеет.

```cpp
void reset();
```

### <a name="remarks"></a>Примечания

Функция-член освобождает ресурс, на который указывает `*this`, и преобразует `*this` в пустой объект weak_ptr.

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

## <a name="swap"></a>  swap

Меняет местами два объекта `weak_ptr`.

```cpp
void swap(weak_ptr& wp);
```

### <a name="parameters"></a>Параметры

`wp` Слабый указатель для замены.

### <a name="remarks"></a>Примечания

Функция-член изменяет указатели на ресурсы с `*this` на `wp` и с `wp` на `*this`. Функция не изменяет подсчет ссылок для двух ресурсов и не создает исключений.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

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

## <a name="use_count"></a>  use_count

Считает количество назначенных объектов `shared_ptr`.

```cpp
long use_count() const;
```

### <a name="remarks"></a>Примечания

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

## <a name="weak_ptr"></a>  weak_ptr

Создает документ `weak_ptr`.

```cpp
weak_ptr();

weak_ptr(const weak_ptr& wp);

template <class Other>
weak_ptr(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Параметры

`Other` Тип, управляемый общий или слабый указатель на аргумент.

`wp` Слабый указатель для копирования.

`sp` Общий указатель для копирования.

### <a name="remarks"></a>Примечания

Каждый из конструкторов создает объект, который указывает на ресурс, имя которого указано в последовательности операндов.

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

## <a name="see-also"></a>См. также

[Класс shared_ptr](../standard-library/shared-ptr-class.md)<br/>
