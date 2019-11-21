---
title: Интеллектуальные указатели (современный C++)
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 909ef870-904c-49b6-b8cd-e9d0b7dc9435
ms.openlocfilehash: a18a5daa45f4f913b6b6dd714956f8592ca0a8d0
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246345"
---
# <a name="smart-pointers-modern-c"></a>Интеллектуальные указатели (современный C++)

In modern C++ programming, the Standard Library includes *smart pointers*, which are used to help ensure that programs are free of memory and resource leaks and are exception-safe.

## <a name="uses-for-smart-pointers"></a>Использование интеллектуальных указателей

Smart pointers are defined in the `std` namespace in the [\<memory>](../standard-library/memory.md) header file. They are crucial to the [RAII](objects-own-resources-raii.md) or *Resource Acquisition Is Initialization* programming idiom. Главная задача этой идиомы — обеспечить, чтобы одновременно с получением ресурса производилась инициализация объекта, чтобы все ресурсы для объекта создавались и подготавливались в одной строке кода. На практике основным принципом RAII является предоставление владения любым ресурсом в куче (например, динамически выделенной памятью или дескрипторами системных объектов) объекту, выделенному стеком, деструктор которого содержит код для удаления или освобождения ресурса, а также весь связанный код очистки.

В большинстве случаев при инициализации необработанного указателя или дескриптора ресурса для указания на фактический ресурс следует сразу же передать указатель в интеллектуальный указатель. В современном C++ необработанные указатели используются только в небольших блоках кода с ограниченной областью, циклах или вспомогательных функциях, когда важна производительность и вероятность проблем с владением низкая.

В следующем примере сравниваются объявления необработанного и интеллектуального указателей.

[!code-cpp[smart_pointers_intro#1](codesnippet/CPP/smart-pointers-modern-cpp_1.cpp)]

Как показано в примере, интеллектуальный указатель — это шаблон класса, который объявляется в стеке и инициализируется с помощью необработанного указателя, указывающего на размещенный в куче объект. После инициализации интеллектуальный указатель становится владельцем необработанного указателя. Это означает, что интеллектуальный указатель отвечает за удаление памяти, заданной необработанным указателем. Деструктор интеллектуального указателя содержит вызов для удаления, и поскольку интеллектуальный указатель объявлен в стеке, его деструктор вызывается, как только интеллектуальный указатель оказывается вне области, даже если исключение создается где-либо в другой части стека.

Доступ к инкапсулированному указателю осуществляется с помощью знакомых операторов указателя `->` и `*`, которые класс интеллектуального указателя перегружает для возврата инкапсулированного необработанного указателя.

Этот интеллектуальный указатель C++ напоминает создание объектов в таких языках, как C#: вы создаете объект, а система удаляет его в правильный момент. Отличие заключается в том, что отсутствует отдельный сборщик мусора, работающий в фоновом режиме; память управляется через стандартные правила области C++, чтобы среда выполнения функционировала быстрее и эффективнее.

> [!IMPORTANT]
>  Всегда создавайте интеллектуальные указатели в отдельной строке кода; ни в коем случае не делайте это в списке параметров, чтобы не произошла небольшая утечка ресурсов, связанная с определенными правилами выделения памяти спискам параметров.

The following example shows how a `unique_ptr` smart pointer type from the C++ Standard Library could be used to encapsulate a pointer to a large object.

[!code-cpp[smart_pointers_intro#2](codesnippet/CPP/smart-pointers-modern-cpp_2.cpp)]

В этом примере показаны следующие важные шаги, необходимые для использования интеллектуальных указателей.

1. Объявите интеллектуальный указатель как автоматическую (локальную) переменную. (Do not use the **new** or `malloc` expression on the smart pointer itself.)

1. В параметре типа укажите тип, на который указывает инкапсулированный указатель.

1. Pass a raw pointer to a **new**-ed object in the smart pointer constructor. (Некоторые служебные функции или конструкторы интеллектуальных указателей делают это автоматически.)

1. Используйте перегруженные операторы `->` и `*` для доступа к объекту.

1. Интеллектуальный указатель удаляет объект автоматически.

Интеллектуальные указатели разработаны для обеспечения максимальной эффективности в отношении памяти и производительности. Например, единственный элемент данных в `unique_ptr` — это инкапсулированный указатель. Это означает, что размер `unique_ptr` точно такой же, как и у указателя — 4 или 8 байтов. Accessing the encapsulated pointer by using the smart pointer overloaded * and -> operators is not significantly slower than accessing the raw pointers directly.

Интеллектуальные указатели имеют собственные функции-члены, доступ к которым осуществляется с помощью нотации с "точками". For example, some C++ Standard Library smart pointers have a reset member function that releases ownership of the pointer. Это полезно, когда нужно освободить память, принадлежащую интеллектуальному указателю, не дожидаясь, пока интеллектуальный указатель окажется вне области, как показано в следующем примере.

[!code-cpp[smart_pointers_intro#3](codesnippet/CPP/smart-pointers-modern-cpp_3.cpp)]

Интеллектуальные указатели обычно предоставляют способ прямого доступа к необработанному указателю. C++ Standard Library smart pointers have a `get` member function for this purpose, and `CComPtr` has a public `p` class member. Предоставляя прямой доступ к базовому указателю, можно использовать интеллектуальный указатель для управления памятью в своем коде и по-прежнему передавать необработанный указатель коду, который не поддерживает интеллектуальные указатели.

[!code-cpp[smart_pointers_intro#4](codesnippet/CPP/smart-pointers-modern-cpp_4.cpp)]

## <a name="kinds-of-smart-pointers"></a>Kinds of smart pointers

В следующем разделе приведены различные виды интеллектуальных указателей, доступные в среде программирования Windows, и приводится описание их использования.

### <a name="c-standard-library-smart-pointers"></a>C++ Standard Library smart pointers

Используйте эти интеллектуальные указатели как основной вариант для инкапсуляции указателей на простые старые объекты C++ (POCO).

- `unique_ptr`<br/>
   Обеспечивает, чтобы у базового указателя был только один владелец. Используйте как вариант по умолчанию для POCO, кроме случая, когда вы точно знаете, что требуется `shared_ptr`. Может быть передан новому владельцу, но не может быть скопирован или сделан общим. Заменяет `auto_ptr`, использовать который не рекомендуется. Сравните с `boost::scoped_ptr`. `unique_ptr` is small and efficient; the size is one pointer and it supports rvalue references for fast insertion and retrieval from C++ Standard Library collections. Файл заголовка: `<memory>`. For more information, see [How to: Create and Use unique_ptr Instances](how-to-create-and-use-unique-ptr-instances.md) and [unique_ptr Class](../standard-library/unique-ptr-class.md).

- `shared_ptr`<br/>
   Интеллектуальный указатель с подсчитанными ссылками. Используйте, когда необходимо присвоить один необработанный указатель нескольким владельцам, например, когда копия указателя возвращается из контейнера, но требуется сохранить оригинал. Необработанный указатель не будет удален до тех пор, пока все владельцы `shared_ptr` не выйдут из области или не откажутся от владения. Размер — 2 указателя; один — для объекта и второй — для блока общего элемента управления, который содержит счетчик ссылок. Файл заголовка: `<memory>`. For more information, see [How to: Create and Use shared_ptr Instances](how-to-create-and-use-shared-ptr-instances.md) and [shared_ptr Class](../standard-library/shared-ptr-class.md).

- `weak_ptr`<br/>
    Интеллектуальный указатель для особых случаев использования с `shared_ptr`. `weak_ptr` предоставляет доступ к объекту, который принадлежит одному или нескольким экземплярам `shared_ptr`, но не участвует в подсчете ссылок. Используйте, когда требуется отслеживать объект, но не требуется, чтобы он оставался в активном состоянии. Требуется в некоторых случаях для разрыва циклических ссылок между экземплярами `shared_ptr`. Файл заголовка: `<memory>`. For more information, see [How to: Create and Use weak_ptr Instances](how-to-create-and-use-weak-ptr-instances.md) and [weak_ptr Class](../standard-library/weak-ptr-class.md).

### <a name="smart-pointers-for-com-objects-classic-windows-programming"></a>Smart pointers for COM objects (classic Windows programming)

При работе с COM-объектами создайте оболочку для указателей интерфейса в соответствующем типе интеллектуальных указателей. Библиотека шаблонных классов (ATL) определяет несколько интеллектуальных указателей для различных целей. Можно также использовать тип интеллектуального указателя `_com_ptr_t`, который компилятор использует при создании классов оболочки из файлов с расширением TLB. Это лучший вариант, если вы не хотите включать файлы заголовков ATL.

[Класс CComPtr](../atl/reference/ccomptr-class.md)<br/>
Используйте, если невозможно использовать ATL. Выполняет подсчет ссылок с помощью методов `AddRef` и `Release`. For more information, see [How to: Create and Use CComPtr and CComQIPtr Instances](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).

[Класс CComQIPtr](../atl/reference/ccomqiptr-class.md)<br/>
Похож на `CComPtr`, но также предоставляет упрощенный синтаксис для вызова `QueryInterface` COM-объекта. For more information, see [How to: Create and Use CComPtr and CComQIPtr Instances](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).

[Класс CComHeapPtr](../atl/reference/ccomheapptr-class.md)<br/>
Интеллектуальный указатель на объекты, которые используют `CoTaskMemFree` для освобождения памяти.

[Класс CComGITPtr](../atl/reference/ccomgitptr-class.md)<br/>
Интеллектуальный указатель для интерфейсов, получаемых из глобальной таблицы интерфейсов (GIT).

[Класс _com_ptr_t](com-ptr-t-class.md)<br/>
По функциональности аналогичен `CComQIPtr`, но не зависит от заголовков ATL.

### <a name="atl-smart-pointers-for-poco-objects"></a>ATL smart pointers for POCO objects

In addition to smart pointers for COM objects, ATL also defines smart pointers, and collections of smart pointers, for plain old C++ objects (POCO). In classic Windows programming, these types are useful alternatives to the C++ Standard Library collections, especially when code portability is not required or when you do not want to mix the programming models of the C++ Standard Library and ATL.

[Класс CAutoPtr](../atl/reference/cautoptr-class.md)<br/>
Интеллектуальный указатель, принудительно реализующий уникальное владение путем переноса владения на копию. Сравним с нерекомендуемым классом `std::auto_ptr`.

[Класс CHeapPtr](../atl/reference/cheapptr-class.md)<br/>
Smart pointer for objects that are allocated by using the C [malloc](../c-runtime-library/reference/malloc.md) function.

[Класс CAutoVectorPtr](../atl/reference/cautovectorptr-class.md)<br/>
Интеллектуальный указатель для массивов, память для которых выделяется с помощью `new[]`.

[Класс CAutoPtrArray](../atl/reference/cautoptrarray-class.md)<br/>
Класс, инкапсулирующий массив элементов `CAutoPtr`.

[Класс CAutoPtrList](../atl/reference/cautoptrlist-class.md)<br/>
Класс, инкапсулирующий методы для управления списком узлов `CAutoPtr`.

## <a name="see-also"></a>См. также

[Pointers](pointers-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)
