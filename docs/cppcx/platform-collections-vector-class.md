---
title: Класс Platform::Collections::Vector
ms.date: 12/04/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Vector::Vector
- COLLECTION/Platform::Collections::Vector::Append
- COLLECTION/Platform::Collections::Vector::Clear
- COLLECTION/Platform::Collections::Vector::First
- COLLECTION/Platform::Collections::Vector::GetAt
- COLLECTION/Platform::Collections::Vector::GetMany
- COLLECTION/Platform::Collections::Vector::GetView
- COLLECTION/Platform::Collections::Vector::IndexOf
- COLLECTION/Platform::Collections::Vector::InsertAt
- COLLECTION/Platform::Collections::Vector::ReplaceAll
- COLLECTION/Platform::Collections::Vector::RemoveAt
- COLLECTION/Platform::Collections::Vector::RemoveAtEnd
- COLLECTION/Platform::Collections::Vector::SetAt
- COLLECTION/Platform::Collections::Vector::Size
- COLLECTION/Platform::Collections::Vector::VectorChanged
helpviewer_keywords:
- Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
ms.openlocfilehash: b2d08461b4ab57ed8479549c18c35c872d0eb9f1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354374"
---
# <a name="platformcollectionsvector-class"></a>Класс Platform::Collections::Vector

Представляет упорядоченную коллекцию объектов с индивидуальным доступом, осуществляемым при помощи индекса. Реализует [Windows::Foundation::: Коллекции::: IObservableVector](/uwp/api/Windows.Foundation.Collections.IObservableVector_T_) поможет с [связыванием данных](/windows/uwp/data-binding/data-binding-in-depth)XAML.

## <a name="syntax"></a>Синтаксис

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип элементов, содержащихся в объекте Vector.

*E*<br/>
Определяет двоичный предикат для тестирования равенства со значениями типа *T.* Значение по `std::equal_to<T>`умолчанию .

### <a name="remarks"></a>Remarks

Допустимые типы:

1. целые числа

1. интерфейс класса

1. открытый ссылочный класс ^

1. структура значений

1. открытый класс перечисления

Класс **«Вектор»** — это конкретная реализация [Windows:::: Коллекции::::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_) интерфейс.

При попытке использования типа **Vector** в значении или параметре общедоступного возврата повышается ошибка компилятора C3986. Вы можете исправить ошибку, изменив тип параметра или возвращаемого значения на [Windows::Foundation::Collections::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_). Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Вектор::Вектор](#ctor)|Инициализирует новый экземпляр класса Vector.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Vector::Append](#append)|Вставляет указанный элемент после последнего элемента текущего объекта Vector.|
|[Вектор::Ясно](#clear)|Удаляет все элементы текущего объекта Vector.|
|[Вектор::Первый](#first)|Возвращает итератор, указывающий первый элемент объекта Vector.|
|[Вектор::GetAt](#getat)|Извлекает элемент текущего объекта Vector, указанный заданным индексом.|
|[Вектор::GetMany](#getmany)|Извлекает последовательность элементов из текущего объекта Vector, начиная с указанного индекса.|
|[Вектор::GetView](#getview)|Возвращает доступное только для чтения представление объекта Vector, то есть [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md).|
|[Вектор::Индекс](#indexof)|Выполняет поиск указанного элемента в текущем объекте Vector и возвращает его индекс, если он найден.|
|[Vector::InsertAt](#insertat)|Вставляет указанный элемент в текущий вектор в элементе, определенном указанным индексом.|
|[Vector::ReplaceAll](#replaceall)|Удаляет элементы из текущего объекта Vector, а затем вставляет элементы из указанного массива.|
|[Vector::RemoveAt](#removeat)|Удаляет элемент, определенный заданным индексом из текущего объекта Vector.|
|[Vector::RemoveAtEnd](#removeatend)|Удаляет элемент в конце текущего объекта Vector.|
|[Vector::SetAt](#setat)|Присваивает указанное значение к элементу текущего объекта Vector, определяемому заданным индексом.|
|[Вектор::Размер](#size)|Возвращает количество элементов в текущем объекте Vector.|

### <a name="events"></a>События

|||
|-|-|
|Имя|Описание|
|Событие [Windows::Фундамент::Коллекция::VectorChangedEventHandler\<T>](/uwp/api/windows.foundation.collections.vectorchangedeventhandler)|Происходит при изменении объекта Vector.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Vector`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="vectorappend-method"></a><a name="append"></a>Вектор::Метод аппенда

Вставляет указанный элемент после последнего элемента текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Элемент, который требуется вставить в объект Vector. Тип *элемента* определяется тизами *T.*

## <a name="vectorclear-method"></a><a name="clear"></a>Вектор::Ясный метод

Удаляет все элементы текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="vectorfirst-method"></a><a name="first"></a>Вектор::Первый метод

Возвращает итератор, указывающий первый элемент объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент объекта Vector.

### <a name="remarks"></a>Remarks

Удобный способ удержания итератора, возвращенного First() заключается в присвоении значения возврата переменной, которая задекларирована с ключевым словом **автоматического** типа вычета. Например, `auto x = myVector->First();`. Этому итератору известна длина коллекции.

Когда вам нужна пара итераторов, чтобы перейти к функции STL, используйте бесплатные функции [Windows::Foundation::Collections::: Начало](../cppcx/begin-function.md) и [Windows::: Коллекции:::Конец](../cppcx/end-function.md)

## <a name="vectorgetat-method"></a><a name="getat"></a>Вектор::Метод GetAt

Извлекает элемент текущего объекта Vector, указанный заданным индексом.

### <a name="syntax"></a>Синтаксис

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

### <a name="return-value"></a>Возвращаемое значение

Элемент, указанный параметром *индекса.* Тип элемента определяется тизацией *T.*

## <a name="vectorgetmany-method"></a><a name="getmany"></a>Вектор::GetMany Метод

Извлекает последовательность элементов из текущего объекта Vector, начиная с определенного индекса, и копирует их в выделенный вызывающим объектом массив.

### <a name="syntax"></a>Синтаксис

```cpp
virtual unsigned int GetMany(
    unsigned int startIndex,
    Platform::WriteOnlyArray<T>^ dest);
```

### <a name="parameters"></a>Параметры

*startIndex*<br/>
Отсчитываемый от нуля индекс начала элементов для извлечения.

*dest*<br/>
Выделенный абонентом массив элементов, которые начинаются с элемента, указанного *startIndex* и заканчиваются в последнем элементе в векторе.

### <a name="return-value"></a>Возвращаемое значение

Количество извлеченных элементов.

### <a name="remarks"></a>Remarks

Эта функция не предназначена для прямого использования в клиентском коде. Он используется внутренне в [to_vector функции](../cppcx/to-vector-function.md) для обеспечения эффективного преобразования платформы::Vector intances к std::vector instances.

## <a name="vectorgetview-method"></a><a name="getview"></a>Вектор::GetView Метод

Возвращает доступное только для чтения представление объекта Vector, то есть интерфейс IVectorView.

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект IVectorView.

## <a name="vectorindexof-method"></a><a name="indexof"></a>Вектор::Индексоф Метод

Выполняет поиск указанного элемента в текущем объекте Vector и возвращает его индекс, если он найден.

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Элемент, который нужно найти.

*Индекс*<br/>
Нулевой индекс элемента при обнаружении *значения* параметра; в противном случае, 0.

Параметр *индекса* растеряет 0, если элемент является первым элементом вектора или не найден. Если значение возврата **верно,** элемент был найден, и это первый элемент; в противном случае товар не найден.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если указанный элемент найден; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

IndexOf использует std::find_if для поиска элемента. Таким образом, типы настраиваемых элементов должны перегрузить оператор == и != для включения сравнений на равенство, которое требуется для find_if.

## <a name="vectorinsertat-method"></a><a name="insertat"></a>Вектор::Вставка метод

Вставляет указанный элемент в текущий вектор в элементе, определенном указанным индексом.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

*item*<br/>
Элемент для вставки в вектор в элементе, указанном *индексом.* Тип *элемента* определяется тизами *T.*

## <a name="vectorremoveat-method"></a><a name="removeat"></a>Вектор::Удаление метода

Удаляет элемент, определенный заданным индексом из текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

## <a name="vectorremoveatend-method"></a><a name="removeatend"></a>Вектор::Метод удаления

Удаляет элемент в конце текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void RemoveAtEnd();
```

## <a name="vectorreplaceall-method"></a><a name="replaceall"></a>Вектор::Заменитьвсе метод

Удаляет элементы из текущего объекта Vector, а затем вставляет элементы из указанного массива.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>Параметры

*Arr*<br/>
Массив объектов, тип которых определяется тиной *T.*

## <a name="vectorsetat-method"></a><a name="setat"></a>Вектор::Метод SetAt

Присваивает указанное значение к элементу текущего объекта Vector, определяемому заданным индексом.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

*item*<br/>
Значение, присваиваемое указанному элементу. Тип *элемента* определяется тизами *T.*

## <a name="vectorsize-method"></a><a name="size"></a>Вектор::Метод размера

Возвращает количество элементов в текущем объекте Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в текущем объекте Vector.

## <a name="vectorvector-constructor"></a><a name="ctor"></a>Вектор::Векторный конструктор

Инициализирует новый экземпляр класса Vector.

### <a name="syntax"></a>Синтаксис

```cpp
Vector();

explicit Vector(unsigned int size);
Vector( unsigned int size, T value);
template <typename U> explicit Vector( const ::std::vector<U>& v);
template <typename U> explicit Vector( std::vector<U>&& v);

Vector( const T * ptr, unsigned int size);
template <size_t N> explicit Vector(const T(&arr)[N]);
template <size_t N> explicit Vector(const std::array<T, N>& a);
explicit Vector(const Array<T>^ arr);

template <typename InIt> Vector(InIt first, InIt last);
Vector(std::initializer_list<T> il);
```

### <a name="parameters"></a>Параметры

*a*<br/>
[Std::array,](../standard-library/array-class-stl.md) который будет использоваться для инициализации Вектор.

*Arr*<br/>
[Платформа::Array,](../cppcx/platform-array-class.md) который будет использоваться для инициализации Вектор.

*Init*<br/>
Тип коллекции объектов, используемой для инициализации текущего объекта Vector.

*Il*<br/>
[Std::initializer_list](../standard-library/initializer-list-class.md) объектов типа *T,* которые будут использоваться для инициализации Вектор.

*N*<br/>
Количество элементов в коллекции объектов, используемой для инициализации текущего объекта Vector.

*Размер*<br/>
Количество элементов в объекте Vector.

*value*<br/>
Значение, используемое для инициализации каждого элемента в текущем объекте Vector.

*V*<br/>
[Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) к [std::vector,](../standard-library/vector-class.md) который используется для инициализации текущего вектор.

*Ptr*<br/>
Указатель на объект `std::vector`, используемый для инициализации текущего объекта Vector.

*Первый*<br/>
Первый элемент в последовательности объектов, используемых для инициализации текущего объекта Vector. Тип *первого* передается с помощью *идеальной пересылки.* Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

*Последний*<br/>
Последний элемент в последовательности объектов, используемых для инициализации текущего объекта Vector. Тип *последнего* передается с помощью *идеальной пересылки.* Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>См. также раздел

[Коллекции (КЗ/CX)](collections-c-cx.md)<br/>
[Название платформы](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
