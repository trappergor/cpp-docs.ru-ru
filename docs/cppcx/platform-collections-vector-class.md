---
title: 'Класс Platform::Collections:: Vector | Документы Microsoft'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c7433ed3d1a81704180aa724424a39d39b193f15
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformcollectionsvector-class"></a>Класс Platform::Collections::Vector

Представляет упорядоченную коллекцию объектов с индивидуальным доступом, осуществляемым при помощи индекса.

## <a name="syntax"></a>Синтаксис

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>Параметры

*T*  
Тип элементов, содержащихся в объекте Vector.

*E*  
Определяет бинарный предикат для проверки равенства со значениями типа *T*. Значение по умолчанию — `std::equal_to<T>`.

### <a name="remarks"></a>Примечания

Допустимые типы:

1. целые числа

1. класс интерфейса ^

1. открытый ссылочный класс ^

1. структура значений

1. открытый класс перечисления

**Вектор** класс является конкретной реализацией C++ [Windows::Foundation::Collections::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_) интерфейса.

Если вы пытаетесь использовать **вектор** тип в качестве открытого возвращаемого значения или параметра, C3986 возникает ошибка компилятора. Вы можете исправить ошибку, изменив параметр или тип возвращаемого значения для [Windows::Foundation::Collections::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_). Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Vector::Vector](#ctor)|Инициализирует новый экземпляр класса Vector.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Vector::Append](#append)|Вставляет указанный элемент после последнего элемента текущего объекта Vector.|
|[Vector::Clear](#clear)|Удаляет все элементы текущего объекта Vector.|
|[Vector::First](#first)|Возвращает итератор, указывающий первый элемент объекта Vector.|
|[Vector::GetAt](#getat)|Извлекает элемент текущего объекта Vector, указанный заданным индексом.|
|[Vector::GetMany](#getmany)|Извлекает последовательность элементов из текущего объекта Vector, начиная с указанного индекса.|
|[Vector::GetView](#getview)|Возвращает доступное только для чтения представление объекта Vector, то есть [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md).|
|[Vector::IndexOf](#indexof)|Выполняет поиск указанного элемента в текущем объекте Vector и возвращает его индекс, если он найден.|
|[Vector::InsertAt](#insertat)|Вставляет указанный элемент в текущий объект Vector после элемента, указанного заданным индексом.|
|[Vector::ReplaceAll](#replaceall)|Удаляет элементы из текущего объекта Vector, а затем вставляет элементы из указанного массива.|
|[Vector::RemoveAt](#removeat)|Удаляет элемент, определенный заданным индексом из текущего объекта Vector.|
|[Vector::RemoveAtEnd](#removeatend)|Удаляет элемент в конце текущего объекта Vector.|
|[Vector::SetAt](#setat)|Присваивает указанное значение к элементу текущего объекта Vector, определяемому заданным индексом.|
|[Vector::Size](#size)|Возвращает количество элементов в текущем объекте Vector.|

### <a name="events"></a>События

|||
|-|-|
|name|Описание|
|событие [Windows::Foundation::Collection::VectorChangedEventHandler\<T > ^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Происходит при изменении объекта Vector.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Vector`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="append"></a>  Метод Vector::append

Вставляет указанный элемент после последнего элемента текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>Параметры

*Индекс*  
Элемент, который требуется вставить в объект Vector. Тип *элемент* определяется *T* typename.

## <a name="clear"></a>  Метод Vector::Clear

Удаляет все элементы текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="first"></a>  Vector::First-метод

Возвращает итератор, указывающий первый элемент объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент объекта Vector.

### <a name="remarks"></a>Примечания

Это удобный способ сохранения итератора, возвращаемого методом First(), — присвоить возвращаемое значение переменной, объявленной с **автоматически** ключевое слово выведения типа. Например, `auto x = myVector->First();`. Этому итератору известна длина коллекции.

При необходимости пару итераторов, передаваемые функции STL используйте свободные функции [Windows::Foundation:: Collections:: begin](../cppcx/begin-function.md) и [Windows::Foundation::Collections::end](../cppcx/end-function.md)

## <a name="getat"></a>  Vector::getat-метод

Извлекает элемент текущего объекта Vector, указанный заданным индексом.

### <a name="syntax"></a>Синтаксис

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>Параметры

*Индекс*  
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

### <a name="return-value"></a>Возвращаемое значение

Элемент с заданным *индекс* параметра. Тип элемента определяется *T* typename.

## <a name="getmany"></a>  Vector::getmany-метод

Извлекает последовательность элементов из текущего объекта Vector, начиная с определенного индекса, и копирует их в выделенный вызывающим объектом массив.

### <a name="syntax"></a>Синтаксис

```cpp
virtual unsigned int GetMany(
    unsigned int startIndex,
    Platform::WriteOnlyArray<T>^ dest);
```

### <a name="parameters"></a>Параметры

*startIndex*  
Отсчитываемый от нуля индекс начала элементов для извлечения.

*dest*  
Выделенный вызывающим объектом массив элементов начинается с элемента, заданного параметром *startIndex* и заканчивается последним элементом объекта Vector.

### <a name="return-value"></a>Возвращаемое значение

Количество извлеченных элементов.

### <a name="remarks"></a>Примечания

Эта функция не предназначена для прямого использования в клиентском коде. Используется внутренним образом в [функция to_vector](../cppcx/to-vector-function.md) , обеспечивая эффективное преобразование экземпляров Platform::Vector в экземпляры std::vector.

## <a name="getview"></a>  Vector::GetView-метод

Возвращает доступное только для чтения представление объекта Vector, то есть интерфейс IVectorView.

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект IVectorView.

## <a name="indexof"></a>  Vector::IndexOf-метод

Выполняет поиск указанного элемента в текущем объекте Vector и возвращает его индекс, если он найден.

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>Параметры

*значение*  
Элемент, который нужно найти.

*Индекс*  
Отсчитываемый от нуля индекс элемента, если параметр *значение* найден; в противном случае — 0.

*Индекс* имеет значение 0, если элемент является первым элементом вектора или элемент не найден. Если возвращаемое значение — `true`, элемент найден и является первым элементом; в противном случае элемент не найден.

### <a name="return-value"></a>Возвращаемое значение

Значение `true`, если указанный элемент найден; в противном случае — значение `false`.

### <a name="remarks"></a>Примечания

IndexOf использует std::find_if для поиска элемента. Таким образом, типы настраиваемых элементов должны перегрузить оператор == и != для включения сравнений на равенство, которое требуется для find_if.

##  <a name="insertat"></a>  Метод Vector::InsertAt

Вставляет указанный элемент в текущий объект Vector после элемента, указанного заданным индексом.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>Параметры

*Индекс*  
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

*Элемент*  
Элемент, вставляемый в объект Vector после элемента, заданного параметром *индекса*. Тип *элемент* определяется *T* typename.

## <a name="removeat"></a>  Метод Vector::RemoveAt

Удаляет элемент, определенный заданным индексом из текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>Параметры

*Индекс*  
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

## <a name="removeatend"></a>  Метод Vector::RemoveAtEnd

Удаляет элемент в конце текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void RemoveAtEnd();
```

## <a name="replaceall"></a>  Метод Vector::ReplaceAll

Удаляет элементы из текущего объекта Vector, а затем вставляет элементы из указанного массива.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>Параметры

*arr*  
Массив объектов, тип которого определяется *T* typename.

## <a name="setat"></a>  Метод Vector::SetAt

Присваивает указанное значение к элементу текущего объекта Vector, определяемому заданным индексом.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>Параметры

*Индекс*  
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

*Элемент*  
Значение, присваиваемое указанному элементу. Тип *элемент* определяется *T* typename.

## <a name="size"></a>  Метод Vector::size

Возвращает количество элементов в текущем объекте Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в текущем объекте Vector.

## <a name="ctor"></a>  Vector::Vector-конструктор

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

*a*  
Объект [std::array](../standard-library/array-class-stl.md) , будет использоваться для инициализации объекта Vector.

*arr*  
Объект [Platform::Array](../cppcx/platform-array-class.md) , будет использоваться для инициализации объекта Vector.

*InIt*  
Тип коллекции объектов, используемой для инициализации текущего объекта Vector.

*il*  
Объект [std::initializer_list](../standard-library/initializer-list-class.md) объектов типа *T* , будет использоваться для инициализации объекта Vector.

*N*  
Количество элементов в коллекции объектов, используемой для инициализации текущего объекта Vector.

*size*  
Количество элементов в объекте Vector.

*значение*  
Значение, используемое для инициализации каждого элемента в текущем объекте Vector.

*v*  
[Значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для [std::vector](../standard-library/vector-class.md) , используемый для инициализации текущего объекта Vector.

*ptr*  
Указатель на объект `std::vector`, используемый для инициализации текущего объекта Vector.

*Первый*  
Первый элемент в последовательности объектов, используемых для инициализации текущего объекта Vector. Тип *первый* передается с помощью параметра *точную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

*последний*  
Последний элемент в последовательности объектов, используемых для инициализации текущего объекта Vector. Тип *последний* передается с помощью параметра *точную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)  
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)  