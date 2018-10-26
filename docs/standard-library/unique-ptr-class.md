---
title: Класс unique_ptr | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::unique_ptr
- memory/std::unique_ptr::deleter_type
- memory/std::unique_ptr::element_type
- memory/std::unique_ptr::pointer
- memory/std::unique_ptr::get
- memory/std::unique_ptr::get_deleter
- memory/std::unique_ptr::release
- memory/std::unique_ptr::reset
- memory/std::unique_ptr::swap
dev_langs:
- C++
helpviewer_keywords:
- std::unique_ptr [C++]
- std::unique_ptr [C++], deleter_type
- std::unique_ptr [C++], element_type
- std::unique_ptr [C++], pointer
- std::unique_ptr [C++], get
- std::unique_ptr [C++], get_deleter
- std::unique_ptr [C++], release
- std::unique_ptr [C++], reset
- std::unique_ptr [C++], swap
ms.assetid: acdf046b-831e-4a4a-83aa-6d4ee467db9a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f148d548cb9d3c93e94f51c1cd8c90fae69527f8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075740"
---
# <a name="uniqueptr-class"></a>Класс unique_ptr

Содержит указатель на собственный объект или массив. Данный объект или массив не принадлежит никаким другим объектам `unique_ptr`. Данный объект удаляется при удалении объекта `unique_ptr`.

## <a name="syntax"></a>Синтаксис

```cpp
class unique_ptr {
public:
    unique_ptr();
    unique_ptr(nullptr_t Nptr);
    explicit unique_ptr(pointer Ptr);
    unique_ptr(pointer Ptr,
        typename conditional<is_reference<Del>::value, Del,
        typename add_reference<const Del>::type>::type Deleter);
    unique_ptr(pointer Ptr,
        typename remove_reference<Del>::type&& Deleter);
    unique_ptr(unique_ptr&& Right);
    template <class T2, Class Del2>
    unique_ptr(unique_ptr<T2, Del2>&& Right);
    unique_ptr(const unique_ptr& Right) = delete;
    unique_ptr& operator=(const unique_ptr& Right) = delete;
};

//Specialization for arrays:
template <class T, class D>
class unique_ptr<T[], D> {
public:
    typedef pointer;
    typedef T element_type;
    typedef D deleter_type;
    constexpr unique_ptr() noexcept;
    template <class U>
    explicit unique_ptr(U p) noexcept;
    template <class U>
    unique_ptr(U p, see below d) noexcept;
    template <class U>
    unique_ptr(U p, see below d) noexcept;
    unique_ptr(unique_ptr&& u) noexcept;
    constexpr unique_ptr(nullptr_t) noexcept : unique_ptr() { }     template <class U, class E>
        unique_ptr(unique_ptr<U, E>&& u) noexcept;
    ~unique_ptr();
    unique_ptr& operator=(unique_ptr&& u) noexcept;
    template <class U, class E>
    unique_ptr& operator=(unique_ptr<U, E>&& u) noexcept;
    unique_ptr& operator=(nullptr_t) noexcept;
    T& operator[](size_t i) const;

    pointer get() const noexcept;
    deleter_type& get_deleter() noexcept;
    const deleter_type& get_deleter() const noexcept;
    explicit operator bool() const noexcept;
    pointer release() noexcept;
    void reset(pointer p = pointer()) noexcept;
    void reset(nullptr_t = nullptr) noexcept;
    template <class U>
    void reset(U p) noexcept = delete;
    void swap(unique_ptr& u) noexcept;  // disable copy from lvalue unique_ptr(const unique_ptr&) = delete;
    unique_ptr& operator=(const unique_ptr&) = delete;
};
```

### <a name="parameters"></a>Параметры

*Справа*<br/>
Объект `unique_ptr`.

*Nptr*<br/>
Интерфейс `rvalue` типа `std::nullptr_t`.

*PTR*<br/>
Объект `pointer`.

*Метод удаления*<br/>
Функция `deleter`, которая привязана к `unique_ptr`.

## <a name="exceptions"></a>Исключения

`unique_ptr` не генерирует исключения.

## <a name="remarks"></a>Примечания

Класс `unique_ptr` заменяет значение `auto_ptr` и может использоваться в качестве элемента контейнеров стандартной библиотеки C++.

Используйте вспомогательную функцию [make_unique](../standard-library/memory-functions.md#make_unique) для создания экземпляров `unique_ptr`.

`unique_ptr` — единственное средство управления ресурсом. Каждый объект `unique_ptr` сохраняет указатель на объект, которым обладает, или нулевой указатель. Владельцем ресурса может только один объект `unique_ptr`; при удалении объекта `unique_ptr`, который был владельцем ресурса, этот ресурс освобождается. Объект `unique_ptr` можно перемещать, но нельзя копировать; дополнительные сведения см. в разделе [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

Ресурс освобождается путем обращения к хранимому объекту `deleter` типа `Del`, которому известны принципы выделения ресурсов для конкретного объекта `unique_ptr`. Значение по умолчанию `deleter` `default_delete<T>` предполагается, что ресурс, на которые указывают `ptr` выделяется с помощью `new`, и может освобождаться путем вызова `delete _Ptr`. (Частичная специализация `unique_ptr<T[]>`управляет объектами массива, выделенными при помощи `new[]`, и обладает объектом `deleter` `default_delete<T[]>` по умолчанию для обращения к функции delete[] `ptr`.)

Сохраненный указатель на принадлежащий ресурс, `stored_ptr` относится к типу `pointer`. Он имеет значение `Del::pointer`, если определен, и значение `T *`, если не определен. Сохраненный объект `deleter` `stored_deleter` не занимает пространство в объекте, если `deleter` не сохраняет данные о состоянии. Обратите внимание, что `Del` может быть ссылочным типом.

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[unique_ptr](#unique_ptr)|Для `unique_ptr` предусмотрено семь конструкторов.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[deleter_type](#deleter_type)|Синоним параметра шаблона `Del`.|
|[element_type](#element_type)|Синоним параметра шаблона `T`.|
|[pointer](#pointer)|Синоним для `Del::pointer`, если определен; в противном случае — значение `T *`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[get](#get)|Возвращает `stored_ptr`.|
|[get_deleter](#get_deleter)|Возвращает ссылку на `stored_deleter`.|
|[release](#release)|сохраняет `pointer()` в `stored_ptr` и возвращает его предыдущее содержимое.|
|[reset](#reset)|Высвобождает текущий занятый ресурс и принимает новый ресурс.|
|[swap](#swap)|Выполняет обмен ресурса и `deleter` с указанным значением `unique_ptr`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|**operator bool**|Оператор возвращает значение типа, которое можно преобразовать в **bool**. Результат преобразования **bool** — **true** при `get() != pointer()`, в противном случае **false**.|
|`operator->`|Функция-член возвращает значение `stored_ptr`.|
|`operator*`|Функция-член возвращает значение `*stored_ptr`.|
|[unique_ptr operator=](#unique_ptr_operator_eq)|Присваивает значение `unique_ptr`(или `pointer-type`) текущему `unique_ptr`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<memory>

**Пространство имен:** std

## <a name="deleter_type"></a>  deleter_type

Этот тип является синонимом для параметра шаблона `Del`.

```cpp
typedef Del deleter_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Del`.

## <a name="element_type"></a>  element_type

Этот тип является синонимом для параметра шаблона `Type`.

```cpp
typedef Type element_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Ty`.

## <a name="get"></a>  unique_ptr::get

Возвращает `stored_ptr`.

```cpp
pointer get() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает значение `stored_ptr`.

## <a name="get_deleter"></a>  unique_ptr::get_deleter

Возвращает ссылку на `stored_deleter`.

```cpp
Del& get_deleter();

const Del& get_deleter() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на `stored_deleter`.

## <a name="unique_ptr_operator_eq"></a>  unique_ptr operator=

Назначает адрес предоставленного `unique_ptr` текущему.

```cpp
unique_ptr& operator=(unique_ptr&& right);
template <class U, Class Del2>
unique_ptr& operator=(unique_ptr<Type, Del>&& right);
unique_ptr& operator=(pointer-type);
```

### <a name="parameters"></a>Параметры

Ссылка `unique_ptr`, используемая для назначения значения текущему `unique_ptr`.

### <a name="remarks"></a>Примечания

Функции-члены вызывают `reset(right.release())` и перемещают `right.stored_deleter` в `stored_deleter`, а затем возвращают `*this`.

## <a name="pointer"></a>  pointer

Синоним для `Del::pointer`, если определен; в противном случае — значение `Type *`.

```cpp
typedef T1 pointer;
```

### <a name="remarks"></a>Примечания

Данный тип — это синоним для `Del::pointer`, если он определен; в противном случае — значение `Type *`.

## <a name="release"></a>  unique_ptr::release

Освобождает владение возвращаемого сохраненного указателя в вызывающий объект и задает сохраненному указателю значение **nullptr**.

```cpp
pointer release();
```

### <a name="remarks"></a>Примечания

Используйте `release` для получения прав на владение необработанным указателем, сохраненным `unique_ptr`. Вызывающий объект отвечает за удаление возвращаемого указателя. Указателю `unique-ptr` присвоено пустое состояние, созданное по умолчанию. Для `unique_ptr` можно назначить другой указатель совместимого типа после вызова `release`.

### <a name="example"></a>Пример

В этом примере показано, каким образом объект, вызывающий освобождение, отвечает за возвращенный объект.

```cpp
// stl_release_unique.cpp
// Compile by using: cl /W4 /EHsc stl_release_unique.cpp
#include <iostream>
#include <memory>

struct Sample {
   int content_;
   Sample(int content) : content_(content) {
      std::cout << "Constructing Sample(" << content_ << ")" << std::endl;
   }
   ~Sample() {
      std::cout << "Deleting Sample(" << content_ << ")" << std::endl;
   }
};

void ReleaseUniquePointer() {
   // Use make_unique function when possible.
   auto up1 = std::make_unique<Sample>(3);
   auto up2 = std::make_unique<Sample>(42);

   // Take over ownership from the unique_ptr up2 by using release
   auto ptr = up2.release();
   if (up2) {
      // This statement does not execute, because up2 is empty.
      std::cout << "up2 is not empty." << std::endl;
   }
   // We are now responsible for deletion of ptr.
   delete ptr;
   // up1 deletes its stored pointer when it goes out of scope.
}

int main() {
   ReleaseUniquePointer();
}
```

Выходные данные компьютера

```Output
Constructing Sample(3)
Constructing Sample(42)
Deleting Sample(42)
Deleting Sample(3)

```

## <a name="reset"></a>  unique_ptr::reset

Принимает право на владение параметром указателя, а затем удаляет исходный сохраненный указатель. Если новый указатель совпадает с исходным сохраненным указателем `reset` удаляет указатель и задает для сохраненного указателя **nullptr**.

```cpp
void reset(pointer ptr = pointer());
void reset(nullptr_t ptr);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ptr*|Указатель на ресурс для получения права на владение.|

### <a name="remarks"></a>Примечания

Используйте `reset` Чтобы изменить сохраненный [указатель](#pointer) владельцем `unique_ptr` для *ptr* , а затем удалите исходный сохраненный указатель. Если указатель `unique_ptr` не был пуст, `reset` вызывает функцию удаления, возвращенную [get_deleter](#get_deleter), для исходного сохраненного указателя.

Так как `reset` сначала сохраняет новый указатель *ptr*и затем удаляет исходный сохраненный указатель, возможна `reset` немедленно удалить *ptr* Если это так же, как исходный сохраненный указатель.

## <a name="swap"></a>  unique_ptr::swap

Меняет местами указатели между двумя объектами `unique_ptr`.

```cpp
void swap(unique_ptr& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Объект `unique_ptr`, используемый для замены указателей.

### <a name="remarks"></a>Примечания

Эта функция-член меняет местами `stored_ptr` с `right.stored_ptr` и `stored_deleter` с `right.stored_deleter`.

## <a name="unique_ptr"></a>  unique_ptr::unique_ptr

Для `unique_ptr` предусмотрено семь конструкторов.

```cpp
unique_ptr();

unique_ptr(nullptr_t);
explicit unique_ptr(pointer ptr);

unique_ptr(
    Type* ptr,
    typename conditional<
    is_reference<Del>::value,
    Del,
    typename add_reference<const Del>::type>::type _Deleter);

unique_ptr(pointer ptr, typename remove_reference<Del>::type&& _Deleter);
unique_ptr(unique_ptr&& right);
template <class Ty2, Class Del2>
unique_ptr(unique_ptr<Ty2, Del2>&& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ptr*|Указатель на ресурс, который будет назначен `unique_ptr.`.|
|*_Deleter*|`deleter`, который будет назначен `unique_ptr`.|
|*right*|Объект `rvalue reference` в `unique_ptr`, из которого поля `unique_ptr` присваиваются перемещением в созданный `unique_ptr`.|

### <a name="remarks"></a>Примечания

Первые два конструктора создают объект, который не управляет никакими ресурсами. Третий конструктор сохраняет *ptr* в `stored_ptr`. Четвертый конструктор сохраняет *ptr* в `stored_ptr` и `deleter` в `stored_deleter`.

Пятый конструктор сохраняет *ptr* в `stored_ptr` и перемещает `deleter` в `stored_deleter`. Шестой и седьмой конструкторы сохраняют `right.release()` в `stored_ptr` и перемещают `right.get_deleter()` в `stored_deleter`.

## <a name="dtorunique_ptr"></a>  unique_ptr ~unique_ptr

Деструктор для `unique_ptr`, уничтожает объект `unique_ptr`.

```cpp
~unique_ptr();
```

### <a name="remarks"></a>Примечания

Деструктор вызывает `get_deleter()(stored_ptr)`.

## <a name="see-also"></a>См. также

[\<memory>](../standard-library/memory.md)<br/>
