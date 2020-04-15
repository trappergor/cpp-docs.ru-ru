---
title: Класс Platform::Collections::UnorderedMapView
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
ms.openlocfilehash: 8f8bc3490fba28232cdab3ea189dd9cfcc8d0650
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354396"
---
# <a name="platformcollectionsunorderedmapview-class"></a>Класс Platform::Collections::UnorderedMapView

Представляет доступное только для чтения представление на *карте*, которое является коллекцией пар "ключ-значение".

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename K,
   typename V,
   typename C = ::std::equal_to<K>>
ref class UnorderedMapView sealed;
```

#### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключа в паре "ключ-значение".

*V*<br/>
Тип значения в паре "ключ-значение".

*C*<br/>
Тип, предоставляющий объект функции, который может сравнивать два ключевых значения для определения равенства. По умолчанию, [\<std::equal_to K>](../standard-library/equal-to-struct.md)

### <a name="remarks"></a>Remarks

UnorderedMapView — это конкретная реализация [Windows::Foundation::Collections::IMapView\<K, V>](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) интерфейс, который передается через двоичный интерфейс приложения (ABI). Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[НеупорядоченноеMapViewView::UnorderedMapView](#ctor)|Инициализирует новый экземпляр класса UnorderedMapView.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[НеупорядоченныйMapView::Первый](#first)|Возвращает итератор, который инициализируется первым элементом в представлении карты.|
|[UnorderedMapView::HasKey](#haskey)|Определяет, содержит ли текущий объект UnorderedMapView указанный ключ.|
|[НеупорядоченныйMapView::Поиск](#lookup)|Извлекает элемент по указанному ключу в текущем объекте UnorderedMapView.|
|[НеупорядоченныйMapView::Размер](#size)|Возвращает количество элементов в текущем объекте UnorderedMapView.|
|[НеупорядоченноеMapViewView::Сплит](#split)|Разделяет исходный объект UnorderedMapView на два объекта UnorderedMapView.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`UnorderedMapView`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="unorderedmapviewfirst-method"></a><a name="first"></a>UnorderedMapViewView::Первый метод

Возвращает итератор, который определяет первую [Windows::::: Коллекции::\<IKeyValuePair K,>](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) элемент на неупорядоченной карте.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator<
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
    First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент в представлении сопоставления.

### <a name="remarks"></a>Remarks

Удобный способ удержания итератора, возвращенного First() заключается в присвоении значения возврата переменной, которая задекларирована с ключевым словом **автоматического** типа вычета. Например, `auto x = myMapView->First();`.

## <a name="unorderedmapviewhaskey-method"></a><a name="haskey"></a>UnorderedMapView::HasKey Метод

Определяет, содержит ли текущий объект UnorderedMap указанный ключ.

### <a name="syntax"></a>Синтаксис

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключ, используемый для поиска элемента. Тип `key` typename *K*.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если ключ найден; в противном случае, **ложные**.

## <a name="unorderedmapviewlookup-method"></a><a name="lookup"></a>НеупорядоченноеMapViewView::Метод поиска

Возвращает значение типа V, связанное с указанным ключом типа K.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключ, используемый для поиска элемента в объекте UnorderedMapView. Тип `key` typename *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с ключом `key`. Тип значения возврата — typename *V.*

## <a name="unorderedmapviewsize-method"></a><a name="size"></a>UnorderedMapView::Метод размера

Возвращает номер [Windows:::Источник:::: Культура::\<IKeyValuePair K,v>](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) элементов в UnorderedMapView.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в Unordered MapView.

## <a name="unorderedmapviewsplit-method"></a><a name="split"></a>UnorderedMapView::Метод разделения

Разделяет текущий объект UnorderedMapView на два объекта UnorderedMapView. Этот метод не выполняет никаких действий.

### <a name="syntax"></a>Синтаксис

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * secondPartition);
```

### <a name="parameters"></a>Параметры

*перваяПартия*<br/>
Первая часть исходного объекта UnorderedMapView.

*второйЧасти*<br/>
Вторая часть исходного объекта UnorderedMapView.

### <a name="remarks"></a>Remarks

Этот метод не выполняет никаких действий.

## <a name="unorderedmapviewunorderedmapview-constructor"></a><a name="ctor"></a>НеупорядоченныйMapView::НеупорядоченныйКонструкторMapView

Инициализирует новый экземпляр класса UnorderedMapView.

### <a name="syntax"></a>Синтаксис

```cpp
UnorderedMapView();
explicit UnorderedMapView(size_t n);
UnorderedMapView(size_t n, const H& h);
UnorderedMapView(size_t n, const H& h, const P& p);

explicit UnorderedMapView(
    const std::unordered_map<K, V, H, P>& m);
explicit UnorderedMapView(
    std::unordered_map<K, V, H, P>&& m);

template <typename InIt> UnorderedMapView(InIt first, InIt last );
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p );

UnorderedMapView(std::initializer_list<std::pair<const K, V>);

UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h);

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p );
```

### <a name="parameters"></a>Параметры

*n*<br/>
Число элементов, для которых необходимо заранее выделить пространство.

*Init*<br/>
Имя типа UnorderedMapView.

*H*<br/>
Объект функции, который может создать хэш-значение для ключа. По умолчанию [для\<std::хэш K>](../standard-library/hash-class.md) для типов, которые `std::hash` поддерживают.

*P*<br/>
Тип, предоставляющий объект функции, который может сравнивать два ключа с целью установления их равенства. По умолчанию к [\<std::equal_to K>](../standard-library/equal-to-struct.md).

*М*<br/>
Ссылка или [Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) к [std::unordered_map,](../standard-library/unordered-map-class.md) которая используется для инициализации UnorderedMapView.

*Первый*<br/>
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации UnorderedMapView.

*Последний*<br/>
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации UnorderedMapView.

## <a name="see-also"></a>См. также раздел

[Платформа:Название коллекций](../cppcx/platform-collections-namespace.md)<br/>
[Windows::Foundation::IMapView](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_)
