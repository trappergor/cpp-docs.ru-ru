---
title: "Функции &lt;memory&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
- memory/std::get_temporary_buffer
- memory/std::make_shared
- memory/std::make_unique
- memory/std::owner_less
- memory/std::return_temporary_buffer
- memory/std::static_pointer_cast
- memory/std::swap
- memory/std::undeclare_no_pointers
- memory/std::undeclare_reachable
- memory/std::uninitialized_copy
- memory/std::uninitialized_copy_n
- memory/std::uninitialized_fill
- memory/std::uninitialized_fill_n
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
- memory/std::get_temporary_buffer
- memory/std::make_shared
- memory/std::make_unique
- memory/std::owner_less
- memory/std::return_temporary_buffer
- memory/std::static_pointer_cast
- memory/std::undeclare_no_pointers
- memory/std::undeclare_reachable
- memory/std::uninitialized_copy
- memory/std::uninitialized_copy_n
- memory/std::uninitialized_fill
- memory/std::uninitialized_fill_n
dev_langs:
- C++
ms.assetid: 3e1898c2-44b7-4626-87ce-84962e4c6f1a
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 4d6d010f7f910a89565ef8cd7c07ddbb2f054759
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="ltmemorygt-functions"></a>Функции &lt;memory&gt;
||||  
|-|-|-|  
|[addressof](#addressof)|[align](#align)|[allocate_shared](#allocate_shared)|  
|[const_pointer_cast](#const_pointer_cast)|[declare_no_pointers](#declare_no_pointers)|[declare_reachable](#declare_reachable)|  
|[default_delete](#default_delete)|[dynamic_pointer_cast](#dynamic_pointer_cast)|[get_deleter](#get_deleter)|  
|[get_pointer_safety](#get_pointer_safety)|[get_temporary_buffer](#get_temporary_buffer)|[make_shared](#make_shared)|  
|[make_unique](#make_unique)|[owner_less](#owner_less)|[return_temporary_buffer](#return_temporary_buffer)|  
|[static_pointer_cast](#static_pointer_cast)|[swap (стандартная библиотека C++)](#swap)|[undeclare_no_pointers](#undeclare_no_pointers)|  
|[undeclare_reachable](#undeclare_reachable)|[uninitialized_copy](#uninitialized_copy)|[uninitialized_copy_n](#uninitialized_copy_n)|  
|[uninitialized_fill](#uninitialized_fill)|[uninitialized_fill_n](#uninitialized_fill_n)|  
  
##  <a name="addressof"></a>  addressof  
 Получает истинный адрес объекта.  
  
```  
template <class T>  
T* addressof(T& Val);
```  
  
### <a name="parameters"></a>Параметры  
 `Val`  
 Объект или функция, для которой необходимо получить истинный адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Фактический адрес объекта или функции, на который ссылается `Val`, даже если существует `operator&()` с перегрузкой.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="align"></a>  align  
 Помещает хранилище определенного размера — выровненное по заданной спецификации выравнивания — по первому возможному адресу заданного хранилища.  
  
```  
void* align(
    size_t Alignment, // input  
    size_t Size,   // input  
    void*& Ptr        // input/output  
    size_t& Space     // input/output);
```  
  
### <a name="parameters"></a>Параметры  
 `Alignment`  
 Граница выравнивания для выполнения попытки.  
  
 `Size`  
 Размер в байтах для выровненного хранилища.  
  
 `Ptr`  
 Начальный адрес доступного смежного пула хранилища для использования. Этот параметр также является параметром вывода и будет содержать новый начальный адрес, если выравнивание выполняется успешно.  
  
 Если `align()` выполняется неудачно, этот параметр не изменяется.  
  
 `Space`  
 Полный размер пространства, доступного `align()`, для использования при создании выровненного хранилища. Этот параметр также является параметром вывода и содержит откорректированное пространство, оставшееся в хранилище после вычитания выровненного хранилища и всей связанной с ним дополнительной нагрузки.  
  
 Если `align()` выполняется неудачно, этот параметр не изменяется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель null, если запрошенный выровненный буфер не может поместиться в свободное пространство; в противном случае — новое значение `Ptr`.  
  
### <a name="remarks"></a>Примечания  
 Измененные параметры `Ptr` и `Space` позволяют вызывать `align()` повторно для того же буфера, возможно, с различными значениями для `Alignment` и `Size`. В следующем фрагменте кода показан один из способов использования `align()`.  
  
```cpp  
#include <type_traits> // std::alignment_of()  
#include <memory>  
//...  
char buffer[256]; // for simplicity  
size_t alignment = std::alignment_of<int>::value;  
void * ptr = buffer;  
std::size_t space = sizeof(buffer); // Be sure this results in the true size of your buffer  
  
while (alignment, sizeof(MyObj), ptr, space)) {  
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
  
##  <a name="allocate_shared"></a>  allocate_shared  
 Создает `shared_ptr` для объектов, выделенных и созданных для заданного типа с помощью указанного распределителя. Возвращает `shared_ptr`.  
  
```  
template <class Type, class Allocator, class... Types>  
shared_ptr<Type>  
allocate_shared(Allocator Alloc, Types&&... Args);
```  
  
### <a name="parameters"></a>Параметры  
 `Alloc`  
 Распределитель используется для создания объектов.  
  
 `Args`  
 Ноль или более аргументов, которые будут объектами.  
  
### <a name="remarks"></a>Примечания  
 Функция создает объект `shared_ptr``<Type>`, указатель на `Type(``Args``...)`, как выделенный и созданный `Alloc`.  
  
##  <a name="const_pointer_cast"></a>  const_pointer_cast  
 Приведение константы к shared_ptr.  
  
```  
template <class Ty, class Other>  
shared_ptr<Ty>  
const_pointer_cast(const shared_ptr<Other>& sp);
```  
  
### <a name="parameters"></a>Параметры  
 `Ty`  
 Тип, управляемый возвращаемым общим указателем.  
  
 `Other`  
 Тип, управляемый общим указателем на аргумент.  
  
 `Other`  
 Общий указатель на аргумент.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает пустой объект shared_ptr, если `const_cast<Ty*>(sp.get())` возвращает пустой указатель; в противном случае возвращается объект [класса shared_ptr](../standard-library/shared-ptr-class.md)`<Ty>`, владеющий ресурсом, который принадлежит `sp`. Выражение `const_cast<Ty*>(sp.get())` должно быть допустимым.  
  
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
  
##  <a name="declare_no_pointers"></a>  declare_no_pointers  
 Сообщает сборщику мусора, что символы в блоке памяти, определенном указателем на базовый адрес и размером блока, не содержат трассируемых указателей.  
  
```  
void declare_no_pointers(
    char* ptr,   
    size_t _Size);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`ptr`|Адрес первого символа, который больше не содержит трассируемых указателей.|  
|`_Size`|Размер блока, который начинается с `ptr` и не содержит трассируемых указателей.|  
  
### <a name="remarks"></a>Примечания  
 Функция сообщает любой `garbage collector` , диапазон адресов `[ ptr, ptr + _Size)` больше не будут содержать трассируемые указатели. (Все указатели на выделенную память не должны быть разыменованными, кроме случаев, когда они были `reachable`.)  
  
##  <a name="declare_reachable"></a>  declare_reachable  
 Уведомляет сборщик мусора, что указанный адрес относится к выделенной памяти и является доступным.  
  
```  
void declare_reachable(void* ptr);
```  
  
### <a name="parameters"></a>Параметры  
 `ptr`  
 Указатель на доступную, выделенную, допустимую область хранения.  
  
### <a name="remarks"></a>Примечания  
 Если `ptr` не равно null, функция сообщает любому сборщику мусора, что `ptr` далее является доступным (указывает на допустимую выделенную память).  
  
##  <a name="default_delete"></a>  default_delete  
 Удаляет объекты, выделенные с помощью `operator new`. Подходит для использования с `unique_ptr`.  
```  
struct default_delete {
   constexpr default_delete() noexcept = default;
   template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>  
   default_delete(const default_delete<Other>&) noexcept;
   void operator()(T* Ptr) const noexcept;     };  
```
### <a name="parameters"></a>Параметры  
 `Ptr`  
 Указатель на объект, который нужно удалить.  
  
 Другое  
 Тип представленных в массиве элементов, который нужно удалить.  
  
### <a name="remarks"></a>Примечания  
 Класс шаблона описывает `deleter`, который удаляет скалярные объекты, выделенные с помощью `operator new`; может использоваться с классом шаблона `unique_ptr`. Также имеет явную специализацию `default_delete<Type[]>`.  
  
##  <a name="dynamic_pointer_cast"></a>  dynamic_pointer_cast  
 Динамическое приведение к типу shared_ptr.  
  
```  
template <class Ty, class Other>  
shared_ptr<Ty>  
dynamic_pointer_cast(const shared_ptr`<`Other>& sp);
```  
  
### <a name="parameters"></a>Параметры  
 `Ty`  
 Тип, управляемый возвращаемым общим указателем.  
  
 `Other`  
 Тип, управляемый общим указателем на аргумент.  
  
 `sp`  
 Общий указатель на аргумент.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает пустой объект shared_ptr, если `dynamic_cast<Ty*>(sp.get())` возвращает пустой указатель; в противном случае возвращается объект [класса shared_ptr](../standard-library/shared-ptr-class.md)`<Ty>`, владеющий ресурсом, который принадлежит `sp`. Выражение `dynamic_cast<Ty*>(sp.get())` должно быть допустимым.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__memory__dynamic_pointer_cast.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
struct base   
    {   
    virtual ~base()   
        {   
        }   
  
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
  
##  <a name="get_deleter"></a>get_deleter
 Получение метода удаления из shared_ptr.  
  
```  
template <class D, class Ty>  
D *get_deleter(const shared_ptr<Ty>& sp);
```  
  
### <a name="parameters"></a>Параметры  
 `D`  
 Тип метода удаления.  
  
 `Ty`  
 Тип, управляемый общим указателем.  
  
 `Other`  
 Общий указатель.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона возвращает указатель на метод удаления типа `D`, который принадлежит к [класс shared_ptr](../standard-library/shared-ptr-class.md), объект `sp`. Если `sp` имеет не имеет метода удаления или если его метод удаления — не типа `D`, функция возвращает значение 0.  
  
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
  
##  <a name="get_pointer_safety"></a>  get_pointer_safety  
 Возвращает тип безопасности указателя, подразумеваемый любым сборщиком мусора.  
  
```  
pointer_safety get_pointer_safety();
```  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает тип безопасности указателя, подразумеваемый любым автоматическим `garbage collector`.  
  
##  <a name="get_temporary_buffer"></a>  get_temporary_buffer  
 Выделяет временное хранилище для последовательности элементов, которая не превышает заданное число элементов.  
  
```  
template <class Type>  
pair<Type *, ptrdiff_t> get_temporary_buffer(ptrdiff_t count);
```  
  
### <a name="parameters"></a>Параметры  
 `count`  
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
  
##  <a name="make_shared"></a>  make_shared  
 Создает и возвращает `shared_ptr`, указывающий на выделенные объекты, созданные без аргументов или с помощью нескольких аргументов с использованием распределителя по умолчанию. Выделяет и создает объект указанного типа и `shared_ptr` для управления общим владением объекта и возвращает `shared_ptr`.  
  
```  
template <class Type, class... Types>  
shared_ptr<Type>  
make_shared(
    Types&&... _Args);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Args`|Без аргументов или несколько аргументов конструктора. Функция определяет перегрузку конструктора, которую нужно вызвать, на основе переданных аргументов.|  
  
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
  
##  <a name="make_unique"></a>  make_unique  
 Создает и возвращает [unique_ptr](../standard-library/unique-ptr-class.md) на объект указанного типа, который создается с помощью использования указанных аргументов.  
  
```scr  
// make_unique<T>template <class T,   
    class... Types>  
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
template <class T,   
    class... Types>  
typename enable_if<extent<T>::value != 0,   
    void>::type make_unique(Types&&...) = delete;  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип объекта, на который будет указывать `unique_ptr`.  
  
 `Types`  
 Типы аргументов конструктора, определяемые `Args`.  
  
 `Args`  
 Аргументы для передачи конструктору объекта типа `T`.  
  
 `Elem`  
 Массив элементов типа `T`.  
  
 `Size`  
 Количество элементов, для которых нужно выделить место в новом массиве.  
  
### <a name="remarks"></a>Примечания  
 Первая перегрузка используется для одиночных объектов, вторая перегрузка вызывается для массивов, а третья перегрузка не позволяет указывать размер массива в аргументе type (make_unique\<T[N]>); эта конструкция не поддерживается текущим стандартом. При использовании `make_unique` для создания `unique_ptr` в массив требуется инициализировать элементы массива отдельно. Если вы рассматриваете возможность использования этой перегрузки, возможно, лучше будет использовать [std::vector](../standard-library/vector-class.md).  
  
 Так как `make_unique` тщательно реализована для безопасности исключений, рекомендуется использовать `make_unique` вместо прямого вызова конструкторов `unique_ptr`.  
  
### <a name="example"></a>Пример  
  В следующем примере показано, как использовать `make_unique`. Дополнительные примеры см. в разделе [Примеры: создание и использование экземпляров unique_ptr](../cpp/how-to-create-and-use-unique-ptr-instances.md).  
  
 [!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]  
  
  При появлении ошибки C2280 в связи с `unique_ptr`, это почти наверняка связано с тем, что вы пытаетесь вызвать его конструктор копированием, который является удаленной функцией.  
  
##  <a name="owner_less"></a>  owner_less  
 Разрешает смешанные сравнения общих и слабых указателей на основе собственности. Возвращает `true`, если левый параметр размещен по порядку перед правым параметром функцией-членом `owner_before`.  
  
```  
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
 `_left`  
 Общий или слабый указатель.  
  
 `right`  
 Общий или слабый указатель.  
  
### <a name="remarks"></a>Примечания  
 Классы-шаблоны определяют все свои операторы-члены как возвращающие `left``.owner_before(``right``)`.  
  
##  <a name="return_temporary_buffer"></a>  return_temporary_buffer  
 Отменяет выделение временной памяти, выделенной с помощью функции шаблона `get_temporary_buffer`.  
  
```  
template <class Type>  
void return_temporary_buffer(Type* _Pbuf);
```  
  
### <a name="parameters"></a>Параметры  
 *_Pbuf*  
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
  
##  <a name="static_pointer_cast"></a>  static_pointer_cast  
 Статическое приведение к shared_ptr.  
  
```  
template <class Ty, class Other>  
shared_ptr<Ty>  
static_pointer_cast(const shared_ptr<Other>& sp);
```  
  
### <a name="parameters"></a>Параметры  
 `Ty`  
 Тип, управляемый возвращаемым общим указателем.  
  
 `Other`  
 Тип, управляемый общим указателем на аргумент.  
  
 `Other`  
 Общий указатель на аргумент.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает пустой объект shared_ptr, если `sp` — это пустой объект `shared_ptr`; в противном случае возвращается объект [класса shared_ptr](../standard-library/shared-ptr-class.md)`<Ty>`, которому принадлежит ресурс, владельцем которого является `sp`. Выражение `static_cast<Ty*>(sp.get())` должно быть допустимым.  
  
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
  
##  <a name="swap"></a> swap (стандартная библиотека C++)  
 Переключение двух объектов shared_ptr или weak_ptr.  
  
```  
template <class Ty, class Other>  
void swap(shared_ptr<Ty>& left, shared_ptr<Other>& right);

template <class Ty, class Other>  
void swap(weak_ptr<Ty>& left, weak_ptr<Other>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `Ty`  
 Тип, управляемый левым общим указателем или слабым указателем.  
  
 `Other`  
 Тип, управляемый правым общим указателем или слабым указателем.  
  
 `left`  
 Левый общий или слабый указатель.  
  
 `right`  
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
  
##  <a name="undeclare_no_pointers"></a>  undeclare_no_pointers  
 Сообщает сборщику мусора, что символы в блоке памяти, определенном указателем на базовый адрес и размером блока, теперь могут содержать трассируемые указатели.  
  
```  
void undeclare_no_pointers(
    char* ptr,   
    size_t _Size);
```  
  
### <a name="remarks"></a>Примечания  
 Функция сообщает любой `garbage collector` , диапазон адресов `[ptr, ptr + _Size)` , теперь могут содержать `traceable pointers`.  
  
##  <a name="undeclare_reachable"></a>  undeclare_reachable  
 Уведомляет `garbage_collector`, что указанная область памяти является недоступной.  
  
```  
template <class Type>  
Type *undeclare_reachable(Type* ptr);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`ptr`|Указатель на адрес памяти, который нужно объявить недоступным.|  
  
### <a name="remarks"></a>Примечания  
 Если `ptr` не `null`, функция сообщает любому `garbage collector`, что `ptr` впредь не `reachable`. Она возвращает указатель `safely derived`, равный `ptr`.  
  
##  <a name="uninitialized_copy"></a>  uninitialized_copy  
 Копирует объекты из указанного исходного диапазона в неинициализированный конечный диапазон.  
  
```  
template <class InputIterator, class ForwardIterator>  
ForwardIterator uninitialized_copy(InputIterator first, InputIterator last, ForwardIterator dest);
```  
  
### <a name="parameters"></a>Параметры  
 `first`  
 Итератор ввода, обращающийся к первому элементу в исходном диапазоне.  
  
 `last`  
 Итератор ввода, обращающийся к последнему элементу в исходном диапазоне.  
  
 `dest`  
 Прямой оператор, обращающийся к первому элементу в диапазоне назначения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямой итератор, обращающийся к первой позиции после диапазон назначения, если исходный диапазон был пуст и итератор обращен * first.*  
  
### <a name="remarks"></a>Примечания  
 Этот алгоритм позволяет отделить выделение памяти от создания объекта.  
  
 Шаблонная функция фактически выполняется.  
  
```  
while (first!= last)  
    new ((void*)&* dest ++)  
    iterator_traits<InputIterator>::value_type (* first ++);

return first;  
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
  
##  <a name="uninitialized_copy_n"></a>  uninitialized_copy_n  
 Создает копию заданного числа элементов из итератора ввода. Копии помещаются в прямой итератор.  
  
```  
template <class InputIterator, class Size, class ForwardIterator>  
ForwardIterator uninitialized_copy_n(
    InputIterator first,   
    Size count,  
    ForwardIterator dest);
```  
  
### <a name="parameters"></a>Параметры  
 `first`  
 Итератор ввода, который ссылается на объект, подлежащий копированию.  
  
 `count`  
 Целочисленный тип со знаком или без знака, указывающий количество операций копирования объекта.  
  
 `dest`  
 Прямой итератор, ссылающийся на место размещения новых копий.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямой итератор, обращающийся к первой позиции после места назначения. Если исходный диапазон был пуст, итератор адреса `first`.  
  
### <a name="remarks"></a>Примечания  
 Шаблонная функция фактически выполняет следующее.  
  
```cpp  
    for (; 0 < count; --count)  
        new ((void *)&* dest++) iterator_traits<InputIterator>::value_type(*first++);  
    return dest;  
```  
  
 если код не создает исключение. В этом случае все созданные объекты уничтожаются, и создается исключение.  
  
##  <a name="uninitialized_fill"></a>  uninitialized_fill  
 Копирует объекты с указанным значением в неинициализированный конечный диапазон.  
  
```  
template <class ForwardIterator, class Type>  
void uninitialized_fill(ForwardIterator first, ForwardIterator last, const Type& val);
```  
  
### <a name="parameters"></a>Параметры  
 `first`  
 Прямой итератор, обращающийся к первому элементу в диапазоне назначения, подлежащем инициализации.  
  
 `last`  
 Прямой итератор, обращающийся к последнему элементу в диапазоне назначения, подлежащем инициализации.  
  
 `val`  
 Значение, используемое для инициализации диапазона назначения.  
  
### <a name="remarks"></a>Примечания  
 Этот алгоритм позволяет отделить выделение памяти от создания объекта.  
  
 Шаблонная функция фактически выполняется.  
  
```  
while (first != last)  
    new ((void*)&* first ++)  
    iterator_traits<ForwardIterator>::value_type (_Val);
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
  
##  <a name="uninitialized_fill_n"></a>  uninitialized_fill_n  
 Копирует объекты с указанным значением в указанное число элементов в неинициализированном диапазоне назначения.  
  
```  
template <class FwdIt, class Size, class Type>  
void uninitialized_fill_n(ForwardIterator first, Size count, const Type& val);
```  
  
### <a name="parameters"></a>Параметры  
 `first`  
 Прямой оператор, обращающийся к первому элементу в диапазоне назначения, подлежащем инициализации.  
  
 `count`  
 Число подлежащих инициализации элементов.  
  
 `val`  
 Значение, используемое для инициализации диапазона назначения.  
  
### <a name="remarks"></a>Примечания  
 Этот алгоритм позволяет отделить выделение памяти от создания объекта.  
  
 Шаблонная функция фактически выполняется.  
  
```cpp  
while (0 <count--)  
    new ((void*)&* first ++)  
    iterator_traits<ForwardIterator>::value_type(val);
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
  
## <a name="see-also"></a>См. также  
 [\<memory>](../standard-library/memory.md)

