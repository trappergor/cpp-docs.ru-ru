---
title: Функции &lt;memory&gt;
ms.date: 02/06/2019
f1_keywords:
- memory/std::addressof
- memory/std::align
- memory/std::allocate_shared
- memory/std::const_pointer_cast
- memory/std::declare_no_pointers
- memory/std::declare_reachable
- memory/std::default_delete
- memory/std::dynamic_pointer_cast
- memory/std::get_deleter
- memory/std::get_pointer_safety
- xmemory/std::get_temporary_buffer
- memory/std::make_shared
- memory/std::make_unique
- memory/std::owner_less
- xmemory/std::return_temporary_buffer
- memory/std::static_pointer_cast
- memory/std::swap
- memory/std::undeclare_no_pointers
- memory/std::undeclare_reachable
- memory/std::uninitialized_copy
- memory/std::uninitialized_copy_n
- memory/std::uninitialized_fill
- memory/std::uninitialized_fill_n
- memory/std::get_temporary_buffer
- memory/std::return_temporary_buffer
ms.assetid: 3e1898c2-44b7-4626-87ce-84962e4c6f1a
helpviewer_keywords:
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::swap [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
ms.openlocfilehash: 14818e93e79a0be9960ba67088f81d51d402b717
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448494"
---
# <a name="ltmemorygt-functions"></a>Функции &lt;memory&gt;

## <a name="addressof"></a>AddressOf

Получает истинный адрес объекта.

```cpp
template <class T>
    T* addressof(T& Val);
```

### <a name="parameters"></a>Параметры

*Val*\
Объект или функция, для которой необходимо получить истинный адрес.

### <a name="return-value"></a>Возвращаемое значение

Фактический адрес объекта или функции, на который ссылается *Val*, даже если `operator&()` существует перегруженный объект.

### <a name="remarks"></a>Примечания

## <a name="align"></a>нижнем

Помещает хранилище определенного размера — выровненное по заданной спецификации выравнивания — по первому возможному адресу заданного хранилища.

```cpp
void* align(
    size_t Alignment, // input
    size_t Size,      // input
    void*& Ptr,        // input/output
    size_t& Space     // input/output
);
```

### <a name="parameters"></a>Параметры

*Выравнивание*\
Граница выравнивания для выполнения попытки.

*Изменять*\
Размер в байтах для выровненного хранилища.

*Указатель*\
Начальный адрес доступного смежного пула хранилища для использования. Этот параметр также является выходным параметром и устанавливается для включения нового начального адреса, если выравнивание выполнено успешно. Если `align()` выполняется неудачно, этот параметр не изменяется.

*Модуль*\
Полный размер пространства, доступного `align()`, для использования при создании выровненного хранилища. Этот параметр также является параметром вывода и содержит откорректированное пространство, оставшееся в хранилище после вычитания выровненного хранилища и всей связанной с ним дополнительной нагрузки.

Если `align()` выполняется неудачно, этот параметр не изменяется.

### <a name="return-value"></a>Возвращаемое значение

Указатель null, если запрошенный выравниваемая буфер не умещается в доступном пространстве; в противном случае — новое значение *ptr*.

### <a name="remarks"></a>Примечания

Измененные *Параметры PTR* и *пробела* позволяют многократно `align()` вызывать один и тот же буфер, возможно, с разными значениями для *выравнивания* и *размера*. В следующем фрагменте кода показан один из способов использования `align()`.

```cpp
#include <type_traits> // std::alignment_of()
#include <memory>
//...
char buffer[256]; // for simplicity
size_t alignment = std::alignment_of<int>::value;
void * ptr = buffer;
std::size_t space = sizeof(buffer); // Be sure this results in the true size of your buffer

while (std::align(alignment, sizeof(MyObj), ptr, space)) {
    // You now have storage the size of MyObj, starting at ptr, aligned on
    // int boundary. Use it here if you like, or save off the starting address
    // contained in ptr for later use.
    // ...
    // Last, move starting pointer and decrease available space before
    // the while loop restarts.
    ptr = reinterpret_cast<char*>(ptr) + sizeof(MyObj);
    space -= sizeof(MyObj);
}
// At this point, align() has returned a null pointer, signaling it is not
// possible to allow more aligned storage in this buffer.
```

## <a name="allocate_shared"></a>allocate_shared

Создает `shared_ptr` для объектов, выделенных и созданных для заданного типа с помощью указанного распределителя. Возвращает `shared_ptr`.

```cpp
template <class Type, class Allocator, class... Types>
    shared_ptr<Type> allocate_shared(Allocator Alloc, Types&&... Args);
```

### <a name="parameters"></a>Параметры

*Идентификатор*\
Распределитель используется для создания объектов.

*Args*\
Ноль или более аргументов, которые будут объектами.

### <a name="remarks"></a>Примечания

Функция создает объект `shared_ptr<Type>`, указатель на который `Type(Args...)` выделяется и создается путем *выделения*.

## <a name="atomic_compare_exchange_strong"></a>atomic_compare_exchange_strong

```cpp
template<class T>
    bool atomic_compare_exchange_strong(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_weak"></a>atomic_compare_exchange_weak

```cpp
template<class T>
    bool atomic_compare_exchange_weak(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_strong_explicit"></a>atomic_compare_exchange_strong_explicit

```cpp
template<class T>
    bool atomic_compare_exchange_strong_explicit(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w, memory_order success, memory_order failure);
```

## <a name="atomic_compare_exchange_weak_explicit"></a>atomic_compare_exchange_weak_explicit

```cpp
template<class T>
    bool atomic_compare_exchange_weak_explicit(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w, memory_order success, memory_order failure);
```

## <a name="atomic_exchange"></a>atomic_exchange

```cpp
template<class T>
    shared_ptr<T> atomic_exchange(shared_ptr<T>* p, shared_ptr<T> r);
```

## <a name="atomic_exchange_explicit"></a>atomic_exchange_explicit

```cpp
template<class T>
    shared_ptr<T> atomic_exchange_explicit(shared_ptr<T>* p, shared_ptr<T> r, memory_order mo);
```

## <a name="atomic_is_lock_free"></a>atomic_is_lock_free

```cpp
template<class T>
    bool atomic_is_lock_free(const shared_ptr<T>* p);
```

## <a name="atomic_load"></a>atomic_load

```cpp
template<class T>
    shared_ptr<T> atomic_load(const shared_ptr<T>* p);
```

## <a name="atomic_load_explicit"></a>atomic_load_explicit

```cpp
template<class T>
    shared_ptr<T> atomic_load_explicit(const shared_ptr<T>* p, memory_order mo);
```

## <a name="atomic_store"></a>atomic_store

```cpp
template<class T>
    void atomic_store(shared_ptr<T>* p, shared_ptr<T> r);
```

## <a name="atomic_store_explicit"></a>atomic_store_explicit

```cpp
template<class T>
    void atomic_store_explicit(shared_ptr<T>* p, shared_ptr<T> r, memory_order mo);
```

## <a name="const_pointer_cast"></a>const_pointer_cast

Приведение константы к shared_ptr.

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> const_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Параметры

*Ty*\
Тип, управляемый возвращаемым общим указателем.

*Иной*\
Тип, управляемый общим указателем на аргумент.

*Иной*\
Общий указатель на аргумент.

### <a name="remarks"></a>Примечания

Функция-шаблон возвращает пустой объект shared_ptr, если `const_cast<Ty*>(sp.get())` возвращает указатель null; в противном случае возвращается [класс](../standard-library/shared-ptr-class.md)\<shared_ptr Ty > объект, `sp`владеющий ресурсом, владельцем которого является. Выражение `const_cast<Ty*>(sp.get())` должно быть допустимым.

### <a name="example"></a>Пример

```cpp
// std__memory__const_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int);
    std::shared_ptr<const int> sp1 =
        std::const_pointer_cast<const int>(sp0);

*sp0 = 3;
    std::cout << "sp1 == " << *sp1 << std::endl;

    return (0);
}
```

```Output
sp1 == 3
```

## <a name="declare_no_pointers"></a>declare_no_pointers

Сообщает сборщику мусора, что символы в блоке памяти, определенном указателем на базовый адрес и размером блока, не содержат трассируемых указателей.

```cpp
void declare_no_pointers(char* ptr, size_t _Size);
```

### <a name="parameters"></a>Параметры

*указатель*\
Адрес первого символа, который больше не содержит трассируемых указателей.

*_Size*\
Размер блока, начинающийся с указателя *ptr* и не содержащий отслеживаемых указателей.

### <a name="remarks"></a>Примечания

Функция информирует любой сборщик мусора о том, что диапазон адресов `[ ptr, ptr + _Size)` больше не содержит отслеживаемых указателей. (Все указатели на выделенное хранилище не должны быть разыменованы, если только они не были доступны.)

## <a name="declare_reachable"></a>declare_reachable

Уведомляет сборщик мусора, что указанный адрес относится к выделенной памяти и является доступным.

```cpp
void declare_reachable(void* ptr);
```

### <a name="parameters"></a>Параметры

*указатель*\
Указатель на доступную, выделенную, допустимую область хранения.

### <a name="remarks"></a>Примечания

Если значение *ptr* не равно null, функция информирует все сборщики *мусора о том* , что доступ к нему осуществляется в дальнейшем (указывает на допустимое выделенное хранилище).

## <a name="default_delete"></a>default_delete

Удаляет объекты, выделенные с помощью **оператора New**. Подходит для использования с `unique_ptr`.

```cpp
struct default_delete {
   constexpr default_delete() noexcept = default;
   template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>
        default_delete(const default_delete<Other>&) noexcept;
   void operator()(T* Ptr) const noexcept;
};
```

### <a name="parameters"></a>Параметры

*Указатель*\
Указатель на объект, который нужно удалить.

*Иной*\
Тип представленных в массиве элементов, который нужно удалить.

### <a name="remarks"></a>Примечания

Класс шаблона описывает объект `deleter` , который удаляет скалярные объекты, выделенные с помощью **оператора New**, которые подходят `unique_ptr`для использования с классом шаблона. Также имеет явную специализацию `default_delete<Type[]>`.

## <a name="destroy_at"></a>destroy_at

```cpp
template <class T>
    void destroy_at(T* location);
```

Эквивалентно `location->~T()`.

## <a name="destroy"></a>завершить

```cpp
template <class ForwardIterator>
    void destroy(ForwardIterator first, ForwardIterator last);
```

Эквивалентно `for (; first!=last; ++first) destroy_at(addressof(*first)); `.

## <a name="destroy_n"></a>destroy_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator destroy_n(ForwardIterator first, Size n);
```

Эквивалентно `for (; n > 0; (void)++first, --n) destroy_at(addressof(*first)); return first;`.

## <a name="dynamic_pointer_cast"></a>dynamic_pointer_cast

Динамическое приведение к типу shared_ptr.

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> dynamic_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Параметры

*Ty*\
Тип, управляемый возвращаемым общим указателем.

*Иной*\
Тип, управляемый общим указателем на аргумент.

*портов*\
Общий указатель на аргумент.

### <a name="remarks"></a>Примечания

Функция-шаблон возвращает пустой объект shared_ptr, если `dynamic_cast<Ty*>(sp.get())` возвращает указатель null; в противном случае возвращается [класс](../standard-library/shared-ptr-class.md)\<shared_ptr Ty > объект, владеющий ресурсом, владельцем которого является *SP*. Выражение `dynamic_cast<Ty*>(sp.get())` должно быть допустимым.

### <a name="example"></a>Пример

```cpp
// std__memory__dynamic_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    virtual ~base() {}
    int val;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::dynamic_pointer_cast<derived>(sp0);

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="get_deleter"></a>get_deleter

Получение метода удаления из shared_ptr.

```cpp
template <class D, class Ty>
    D* get_deleter(const shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Параметры

*ЧЕТЫРЕХМЕРНОГО*\
Тип метода удаления.

*Ty*\
Тип, управляемый общим указателем.

*портов*\
Общий указатель.

### <a name="remarks"></a>Примечания

Функция шаблона возвращает указатель на метод удаления типа *D* , который принадлежит к объекту [класса shared_ptr](../standard-library/shared-ptr-class.md) *SP*. Если *SP* не имеет функции удаления или если его тип удаления не относится к типу *D* , функция возвращает 0.

### <a name="example"></a>Пример

```cpp
// std__memory__get_deleter.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
};

struct deleter
{
    void operator()(base *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<base> sp0(new base);

    sp0->val = 3;
    std::cout << "get_deleter(sp0) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp0) != 0) << std::endl;

    std::shared_ptr<base> sp1(new base, deleter());

    sp0->val = 3;
    std::cout << "get_deleter(sp1) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp1) != 0) << std::endl;

    return (0);
}
```

```Output
get_deleter(sp0) != 0 == false
get_deleter(sp1) != 0 == true
```

## <a name="get_pointer_safety"></a>get_pointer_safety

Возвращает тип безопасности указателя, подразумеваемый любым сборщиком мусора.

```cpp
pointer_safety get_pointer_safety();
```

### <a name="remarks"></a>Примечания

Функция возвращает тип безопасности указателя, предполагаемый любым автоматическим сборщиком мусора.

## <a name="get_temporary_buffer"></a>get_temporary_buffer

Выделяет временное хранилище для последовательности элементов, которая не превышает заданное число элементов.

```cpp
template <class Type>
    pair<Type *, ptrdiff_t> get_temporary_buffer(ptrdiff_t count);
```

### <a name="parameters"></a>Параметры

*расчета*\
Максимальное количество запрошенных элементов, для которых нужно выделить память.

### <a name="return-value"></a>Возвращаемое значение

`pair`, первый компонент которого — это указатель на память, которая была выделена, а второй компонент — размер буфера (наибольшее количество элементов, которые он может сохранить).

### <a name="remarks"></a>Примечания

Функция делает запрос на выделение памяти, и она может не завершиться успешно. Если буфер не выделен, функция возвращает пару, второй компонент которой равен нулю, а первый компонент — пустой указатель.

Эта функция должна использоваться только для памяти, которая является временной.

### <a name="example"></a>Пример

```cpp
// memory_get_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
   // Create an array of ints
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300, 1000, 2000 };
   int count = sizeof ( intArray ) / sizeof ( int );
   cout << "The number of integers in the array is: "
      << count << "." << endl;

   pair<int *, ptrdiff_t> resultPair;
   resultPair = get_temporary_buffer<int>( count );

   cout << "The number of elements that the allocated memory\n"
        << "could store is given by: resultPair.second = "
        << resultPair.second << "." << endl;
}
```

```Output
The number of integers in the array is: 9.
The number of elements that the allocated memory
could store is given by: resultPair.second = 9.
```

## <a name="make_shared"></a>make_shared

Создает и возвращает `shared_ptr`, указывающий на выделенные объекты, созданные без аргументов или с помощью нескольких аргументов с использованием распределителя по умолчанию. Выделяет и создает объект указанного типа и `shared_ptr` для управления общим владением объекта и возвращает `shared_ptr`.

```cpp
template <class Type, class... Types>
    shared_ptr<Type> make_shared(Types&&... _Args);
```

### <a name="parameters"></a>Параметры

*_Args*\
Без аргументов или несколько аргументов конструктора. Функция определяет перегрузку конструктора, которую нужно вызвать, на основе переданных аргументов.

### <a name="remarks"></a>Примечания

Используйте одновременно `make_shared` как простой и эффективный способ создания объекта и `shared_ptr` для управления общим доступом к объекту. Семантически следующие два оператора эквивалентны:

```cpp
auto sp = std::shared_ptr<Example>(new Example(argument));
auto msp = std::make_shared<Example>(argument);
```

Однако первый оператор назначает два выделения, и при сбое выделения `shared_ptr` после успешного выделения объекта `Example` происходит утечка неименованного объекта `Example`. Оператор с `make_shared` проще, поскольку используется только один вызов функции. Он более эффективен, так как библиотека может создать одно и то же выделение для объекта и интеллектуального указателя. Это более быстрый способ, и меньше фрагментируется память, и, кроме того, становится невозможным возникновение исключения только в одном выделении из двух. Благодаря более оптимальному расположению кода, указывающего на объект и обновляющего счетчики в интеллектуальном указателе, повышается производительность.

Если общий доступ к объекту не требуется, рассмотрите возможность использования [make_unique](../standard-library/memory-functions.md#make_unique). Если необходимо указать пользовательский распределитель для объекта, используйте [allocate_shared](../standard-library/memory-functions.md#allocate_shared). Вы не можете использовать `make_shared`, если объект требует пользовательский метод удаления, так как метод удаления невозможно передать в качестве аргумента.

В приведенном ниже примере показано, как можно создавать общие указатели на тип, задавая определенные перегрузки конструктора.

### <a name="example"></a>Пример

```cpp
// stl_make_shared.cpp
// Compile by using: cl /W4 /EHsc stl_make_shared.cpp
#include <iostream>
#include <string>
#include <memory>
#include <vector>

class Song {
public:
   std::wstring title_;
   std::wstring artist_;

   Song(std::wstring title, std::wstring artist) : title_(title), artist_(artist) {}
   Song(std::wstring title) : title_(title), artist_(L"Unknown") {}
};

void CreateSharedPointers() {
   // Okay, but less efficient to have separate allocations for
   // Song object and shared_ptr control block.
   auto song = new Song(L"Ode to Joy", L"Beethoven");
   std::shared_ptr<Song> sp0(song);

   // Use make_shared function when possible. Memory for control block
   // and Song object are allocated in the same call:
   auto sp1 = std::make_shared<Song>(L"Yesterday", L"The Beatles");
   auto sp2 = std::make_shared<Song>(L"Blackbird", L"The Beatles");

   // make_shared infers which constructor to use based on the arguments.
   auto sp3 = std::make_shared<Song>(L"Greensleeves");

   // The playlist vector makes copies of the shared_ptr pointers.
   std::vector<std::shared_ptr<Song>> playlist;
   playlist.push_back(sp0);
   playlist.push_back(sp1);
   playlist.push_back(sp2);
   playlist.push_back(sp3);
   playlist.push_back(sp1);
   playlist.push_back(sp2);
   for (auto&& sp : playlist) {
      std::wcout << L"Playing " << sp->title_ <<
         L" by " << sp->artist_ << L", use count: " <<
         sp.use_count() << std::endl;
   }
}

int main() {
   CreateSharedPointers();
}
```

В примере получается следующий результат.

```Output
Playing Ode to Joy by Beethoven, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
Playing Greensleeves by Unknown, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
```

## <a name="make_unique"></a>make_unique

Создает и возвращает [unique_ptr](../standard-library/unique-ptr-class.md) на объект указанного типа, который создается с помощью использования указанных аргументов.

```cpp
// make_unique<T>
template <class T, class... Types>
    unique_ptr<T> make_unique(Types&&... Args)
    {
        return (unique_ptr<T>(new T(forward<Types>(Args)...)));
    }

// make_unique<T[]>
template <class T>
    make_unique(size_t Size)
    {
        return (unique_ptr<T>(new Elem[Size]()));
    }

// make_unique<T[N]> disallowed
template <class T, class... Types>
    typename enable_if<extent<T>::value != 0, void>::type make_unique(Types&&...) = delete;
```

### <a name="parameters"></a>Параметры

*T*\
Тип объекта, на который будет указывать `unique_ptr`.

*Типы*\
Типы аргументов конструктора, заданные аргументом *args*.

*Args*\
Аргументы, передаваемые конструктору объекта типа *T*.

*Elem*\
Массив элементов типа *T*.

*Изменять*\
Количество элементов, для которых нужно выделить место в новом массиве.

### <a name="remarks"></a>Примечания

Первая перегрузка используется для единичных объектов, вторая перегрузка вызывается для массивов, а Третья перегрузка не позволяет указать размер массива в аргументе типа (make_unique\<T [N] >); Эта конструкция не поддерживается текущей Standard. При использовании `make_unique` для создания `unique_ptr` в массив требуется инициализировать элементы массива отдельно. Если вы рассматриваете возможность использования этой перегрузки, возможно, лучше будет использовать [std::vector](../standard-library/vector-class.md).

Так как `make_unique` тщательно реализована для безопасности исключений, рекомендуется использовать `make_unique` вместо прямого вызова конструкторов `unique_ptr`.

### <a name="example"></a>Пример

В следующем примере показано, как использовать `make_unique`. Дополнительные примеры см. в статье [Практическое руководство. Создание и использование экземпляров](../cpp/how-to-create-and-use-unique-ptr-instances.md)unique_ptr.

[!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]

При появлении ошибки C2280 в связи с `unique_ptr`, это почти наверняка связано с тем, что вы пытаетесь вызвать его конструктор копированием, который является удаленной функцией.

## <a name="owner_less"></a>owner_less

Разрешает смешанные сравнения общих и слабых указателей на основе собственности. Возвращает **значение true** , если левый параметр упорядочивается до правого параметра функцией `owner_before`-членом.

```cpp
template <class Type>
    struct owner_less; // not defined

template <class Type>
struct owner_less<shared_ptr<Type>> {
    bool operator()(
    const shared_ptr<Type>& left,
    const shared_ptr<Type>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Type>& right);
};

template <class Type>
struct owner_less<weak_ptr<Type>>
    bool operator()(
    const weak_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Ty>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);
};
```

### <a name="parameters"></a>Параметры

*_left*\
Общий или слабый указатель.

*Правильно*\
Общий или слабый указатель.

### <a name="remarks"></a>Примечания

Классы-шаблоны определяют все свои операторы-члены как возвращающие `left.owner_before(right)`.

## <a name="return_temporary_buffer"></a>return_temporary_buffer

Отменяет выделение временной памяти, выделенной с помощью функции шаблона `get_temporary_buffer`.

```cpp
template <class Type>
    void return_temporary_buffer(Type* _Pbuf);
```

### <a name="parameters"></a>Параметры

*_Pbuf*\
Указатель на память, которую нужно освободить.

### <a name="remarks"></a>Примечания

Эта функция должна использоваться только для памяти, которая является временной.

### <a name="example"></a>Пример

```cpp
// memory_ret_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
   // Create an array of ints
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300 };
   int count = sizeof ( intArray ) / sizeof ( int );
   cout << "The number of integers in the array is: "
         << count << "." << endl;

   pair<int *, ptrdiff_t> resultPair;
   resultPair = get_temporary_buffer<int>( count );

   cout << "The number of elements that the allocated memory\n"
         << " could store is given by: resultPair.second = "
         << resultPair.second << "." << endl;

   int* tempBuffer = resultPair.first;

   // Deallocates memory allocated with get_temporary_buffer
   return_temporary_buffer ( tempBuffer );
}
```

```Output
The number of integers in the array is: 7.
The number of elements that the allocated memory
could store is given by: resultPair.second = 7.
```

## <a name="static_pointer_cast"></a>static_pointer_cast

Статическое приведение к shared_ptr.

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> static_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Параметры

*Ty*\
Тип, управляемый возвращаемым общим указателем.

*Иной*\
Тип, управляемый общим указателем на аргумент.

*Иной*\
Общий указатель на аргумент.

### <a name="remarks"></a>Примечания

Функция-шаблон возвращает пустой объект shared_ptr, если `sp` является пустым `shared_ptr` объектом; в противном случае возвращается [класс](../standard-library/shared-ptr-class.md)\<shared_ptr Ty `sp`> объект, владеющий ресурсом, владельцем которого является. Выражение `static_cast<Ty*>(sp.get())` должно быть допустимым.

### <a name="example"></a>Пример

```cpp
// std__memory__static_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::static_pointer_cast<derived>(sp0);

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="swap"></a>позиции

Переключение двух объектов shared_ptr или weak_ptr.

```cpp
template <class Ty, class Other>
    void swap(shared_ptr<Ty>& left, shared_ptr<Other>& right);

template <class Ty, class Other>
    void swap(weak_ptr<Ty>& left, weak_ptr<Other>& right);
```

### <a name="parameters"></a>Параметры

*Ty*\
Тип, управляемый левым общим указателем или слабым указателем.

*Иной*\
Тип, управляемый правым общим указателем или слабым указателем.

*слева*\
Левый общий или слабый указатель.

*Правильно*\
Правый общий или слабый указатель.

### <a name="remarks"></a>Примечания

Функция шаблона вызывает `left.swap(right)`.

### <a name="example"></a>Пример

```cpp
// std__memory__swap.cpp
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

## <a name="undeclare_no_pointers"></a>undeclare_no_pointers

Сообщает сборщику мусора, что символы в блоке памяти, определенном указателем на базовый адрес и размером блока, теперь могут содержать трассируемые указатели.

```cpp
void undeclare_no_pointers(char* ptr, size_t _Size);
```

### <a name="remarks"></a>Примечания

Функция информирует любой сборщик мусора о том, что диапазон адресов `[ptr, ptr + _Size)` теперь может содержать отслеживаемые указатели.

## <a name="undeclare_reachable"></a>undeclare_reachable

Отменяет объявление достижимости для указанного расположения в памяти.

```cpp
template <class Type>
    Type *undeclare_reachable(Type* ptr);
```

### <a name="parameters"></a>Параметры

*указатель*\
Указатель на адрес памяти, который нужно объявить недоступным.

### <a name="remarks"></a>Примечания

Если значение *ptr* не равно **nullptr**, функция сообщает сборщику мусора о том, что *ptr* больше не доступен. Он возвращает безопасный указатель, который сравнивается со значением *ptr*.

## <a name="uninitialized_copy"></a>uninitialized_copy

Копирует объекты из указанного исходного диапазона в неинициализированный конечный диапазон.

```cpp
template <class InputIterator, class ForwardIterator>
    ForwardIterator uninitialized_copy(InputIterator first, InputIterator last, ForwardIterator dest);
```

### <a name="parameters"></a>Параметры

*началь*\
Итератор ввода, обращающийся к первому элементу в исходном диапазоне.

*Последняя*\
Итератор ввода, обращающийся к последнему элементу в исходном диапазоне.

*dest*\
Прямой оператор, обращающийся к первому элементу в диапазоне назначения.

### <a name="return-value"></a>Возвращаемое значение

Прямой итератор, обращающийся к первой позиции за пределами целевого диапазона, если исходный диапазон не был пустым.

### <a name="remarks"></a>Примечания

Этот алгоритм позволяет отделить выделение памяти от создания объекта.

Шаблонная функция фактически выполняется.

```cpp
while (first != last) {
    new (static_cast<void*>(&* dest++))
        typename iterator_traits<InputIterator>::value_type(*first++);
}
return dest;
```

если код не создает исключение. В этом случае все созданные объекты уничтожаются, и создается исключение.

### <a name="example"></a>Пример

```cpp
// memory_uninit_copy.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer
{
public:
    Integer(int x) : val(x) {}
    int get() { return val; }
private:
    int val;
};

int main()
{
    int Array[] = { 10, 20, 30, 40 };
    const int N = sizeof(Array) / sizeof(int);

    int i;
    cout << "The initialized Array contains " << N << " elements: ";
    for (i = 0; i < N; i++)
    {
        cout << " " << Array[i];
    }
    cout << endl;

    Integer* ArrayPtr = (Integer*)malloc(N * sizeof(int));
    Integer* LArrayPtr = uninitialized_copy(
        Array, Array + N, ArrayPtr);  // C4996

    cout << "Address of position after the last element in the array is: "
        << &Array[0] + N << endl;
    cout << "The iterator returned by uninitialized_copy addresses: "
        << (void*)LArrayPtr << endl;
    cout << "The address just beyond the last copied element is: "
        << (void*)(ArrayPtr + N) << endl;

    if ((&Array[0] + N) == (void*)LArrayPtr)
        cout << "The return value is an iterator "
        << "pointing just beyond the original array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the original array." << endl;

    if ((void*)LArrayPtr == (void*)(ArrayPtr + N))
        cout << "The return value is an iterator "
        << "pointing just beyond the copied array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the copied array." << endl;

    free(ArrayPtr);

    cout << "Note that the exact addresses returned will vary\n"
        << "with the memory allocation in individual computers."
        << endl;
}
```

## <a name="uninitialized_copy_n"></a>uninitialized_copy_n

Создает копию заданного числа элементов из итератора ввода. Копии помещаются в прямой итератор.

```cpp
template <class InputIterator, class Size, class ForwardIterator>
ForwardIterator uninitialized_copy_n(
    InputIterator first,
    Size count,
    ForwardIterator dest);
```

### <a name="parameters"></a>Параметры

*началь*\
Итератор ввода, который ссылается на объект, подлежащий копированию.

*расчета*\
Целочисленный тип со знаком или без знака, указывающий количество операций копирования объекта.

*dest*\
Прямой итератор, ссылающийся на место размещения новых копий.

### <a name="return-value"></a>Возвращаемое значение

Прямой итератор, обращающийся к первой позиции после места назначения. Если исходный диапазон был пустым, итератор *сначала*обращается к нему.

### <a name="remarks"></a>Примечания

Шаблонная функция фактически выполняет следующее.

```cpp
    for (; 0 < count; --count)
        new (static_cast<void*>(&* dest++))
            typename iterator_traits<InputIterator>::value_type(*first++);
    return dest;
```

если код не создает исключение. В этом случае все созданные объекты уничтожаются, и создается исключение.

## <a name="uninitialized_default_construct"></a>uninitialized_default_construct

```cpp
template <class ForwardIterator>
    void uninitialized_default_construct(ForwardIterator first, ForwardIterator last); 
```

### <a name="remarks"></a>Примечания

То же, что:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type;
```

## <a name="uninitialized_default_construct_n"></a>uninitialized_default_construct_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator uninitialized_default_construct_n(ForwardIterator first, Size n)
```

### <a name="remarks"></a>Примечания

То же, что:

```cpp
for (; n>0; (void)++first, --n)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type; return first;
```

## <a name="uninitialized_fill"></a>uninitialized_fill

Копирует объекты с указанным значением в неинициализированный конечный диапазон.

```cpp
template <class ForwardIterator, class Type>
    void uninitialized_fill(ForwardIterator first, ForwardIterator last, const Type& val);
```

### <a name="parameters"></a>Параметры

*началь*\
Прямой итератор, обращающийся к первому элементу в диапазоне назначения, подлежащем инициализации.

*Последняя*\
Прямой итератор, обращающийся к последнему элементу в диапазоне назначения, подлежащем инициализации.

*Val*\
Значение, используемое для инициализации диапазона назначения.

### <a name="remarks"></a>Примечания

Этот алгоритм позволяет отделить выделение памяти от создания объекта.

Шаблонная функция фактически выполняется.

```cpp
while (first != last)
    new (static_cast<void*>(&* first ++))
        typename iterator_traits<ForwardIterator>::value_type (val);
```

если код не создает исключение. В этом случае все созданные объекты уничтожаются, и создается исключение.

### <a name="example"></a>Пример

```cpp
// memory_uninit_fill.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

class Integer {         // No default constructor
   public:
      Integer( int x ) : val( x ) {}
      int get( ) { return val; }
   private:
      int val;
};

int main( )
{
   const int N = 10;
   Integer val ( 25 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill( Array, Array + N, val );
   int i;
   cout << "The initialized Array contains: ";
      for ( i = 0 ; i < N; i++ )
      {
         cout << Array [ i ].get( ) << " ";
      }
   cout << endl;
}
```

```Output
The initialized Array contains: 25 25 25 25 25 25 25 25 25 25
```

## <a name="uninitialized_fill_n"></a>uninitialized_fill_n

Копирует объекты с указанным значением в указанное число элементов в неинициализированном диапазоне назначения.

```cpp
template <class FwdIt, class Size, class Type>
    void uninitialized_fill_n(ForwardIterator first, Size count, const Type& val);
```

### <a name="parameters"></a>Параметры

*началь*\
Прямой оператор, обращающийся к первому элементу в диапазоне назначения, подлежащем инициализации.

*расчета*\
Число подлежащих инициализации элементов.

*Val*\
Значение, используемое для инициализации диапазона назначения.

### <a name="remarks"></a>Примечания

Этот алгоритм позволяет отделить выделение памяти от создания объекта.

Шаблонная функция фактически выполняется.

```cpp
while (0 < count--)
    new (static_cast<void*>(&* first++))
        typename iterator_traits<ForwardIterator>::value_type(val);
```

если код не создает исключение. В этом случае все созданные объекты уничтожаются, и создается исключение.

### <a name="example"></a>Пример

```cpp
// memory_uninit_fill_n.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer {   // No default constructor
public:
   Integer( int x ) : val( x ) {}
   int get( ) { return val; }
private:
   int val;
};

int main() {
   const int N = 10;
   Integer val ( 60 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill_n( Array, N, val );  // C4996
   int i;
   cout << "The uninitialized Array contains: ";
   for ( i = 0 ; i < N; i++ )
      cout << Array [ i ].get( ) <<  " ";
}
```

## <a name="uninitialized_move"></a>uninitialized_move

```cpp
template <class InputIterator, class ForwardIterator>
    ForwardIterator uninitialized_move(InputIterator first, InputIterator last, ForwardIterator result); 
```

### <a name="remarks"></a>Примечания

То же, что:

```cpp
for (; first != last; (void)++result, ++first)
    ::new (static_cast<void*>(addressof(*result)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first)); 
        return result;
```

При возникновении исключения некоторые объекты в диапазоне могут остаться в допустимом, но неопределенном состоянии.

## <a name="uninitialized_move_n"></a>uninitialized_move_n

```cpp
template <class InputIterator, class Size, class ForwardIterator>
    pair<InputIterator, ForwardIterator> uninitialized_move_n(InputIterator first, Size n, ForwardIterator result);
```

### <a name="remarks"></a>Примечания

То же, что:

```cpp
for (; n > 0; ++result, (void) ++first, --n)
    ::new (static_cast<void*>(addressof(*result)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first)); return {first,result};
```

При возникновении исключения некоторые объекты в диапазоне могут остаться в допустимом, но неопределенном состоянии.

## <a name="uninitialized_value_construct"></a>uninitialized_value_construct

```cpp
template <class ForwardIterator>
    void uninitialized_value_construct(ForwardIterator first, ForwardIterator last);
```

### <a name="remarks"></a>Примечания

То же, что:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type();
```

## <a name="uninitialized_value_construct_n"></a>uninitialized_value_construct_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator uninitialized_value_construct_n(ForwardIterator first, Size n);
```

То же, что:
```cpp
for (; n>0; (void)++first, --n)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type(); return first;
```

## <a name="uses_allocator_v"></a>uses_allocator_v

```cpp
template <class T, class Alloc>
    inline constexpr bool uses_allocator_v = uses_allocator<T, Alloc>::value;
```

## <a name="see-also"></a>См. также

[\<memory>](../standard-library/memory.md)
