---
title: Класс Platform::Collections::MapView
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::MapView::MapView
- COLLECTION/Platform::Collections::MapView::First
- COLLECTION/Platform::Collections::MapView::HasKey
- COLLECTION/Platform::Collections::MapView::Lookup
- COLLECTION/Platform::Collections::MapView::Size
- COLLECTION/Platform::Collections::MapView::Split
helpviewer_keywords:
- MapView Class
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
ms.openlocfilehash: a770b318d893b9e81bdf11a75c2b0b05c0a9979f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750614"
---
# <a name="platformcollectionsmapview-class"></a>Класс Platform::Collections::MapView

Представляет доступное только для чтения представление на *карте*, которое является коллекцией пар "ключ-значение".

## <a name="syntax"></a>Синтаксис

```
template <
   typename K,
   typename V,
   typename C = ::std::less<K>>
ref class MapView sealed;
```

#### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключа в паре "ключ-значение".

*V*<br/>
Тип значения в паре "ключ-значение".

*C*<br/>
Тип, предоставляющий объект функции, который может сравнить значения двух элементов как ключи сортировки, чтобы определить их относительный порядок в объекте MapView. По умолчанию, [\<std::менее K>](../standard-library/less-struct.md).

### <a name="remarks"></a>Remarks

MapView — это конкретная реализация [Windows:::Основа::Коллекции::IMapView \<K, V>](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) интерфейс, который передается через двоичный интерфейс приложения (ABI). Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[MapView::MapView](#ctor)|Инициализирует новый экземпляр класса MapView.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[MapView::Первый](#first)|Возвращает итератор, который инициализируется первым элементом в представлении карты.|
|[MapView::HasKey](#haskey)|Определяет, содержит ли текущий объект MapView указанный ключ.|
|[MapView::Lookup](#lookup)|Извлекает элемент по указанному ключу в текущем объекте MapView.|
|[MapView::Size](#size)|Возвращает количество элементов в текущем объекте MapView.|
|[MapView::Split](#split)|Разделяет исходный объект MapView на два объекта MapView.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`MapView`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="mapviewfirst-method"></a><a name="first"></a>MapView::Первый метод

Возвращает итератор, указывающий первый элемент в представлении сопоставления.

### <a name="syntax"></a>Синтаксис

```
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент в представлении сопоставления.

### <a name="remarks"></a>Remarks

Удобный способ удержания итератора, возвращенного First() заключается в присвоении значения возврата переменной, которая задекларирована с ключевым словом **автоматического** типа вычета. Например, `auto x = myMapView->First();`.

## <a name="mapviewhaskey-method"></a><a name="haskey"></a>MapView::HasKey метод

Определяет, содержит ли текущий объект MapView указанный ключ.

### <a name="syntax"></a>Синтаксис

```

bool HasKey(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента MapView. Тип *ключа* typename *K*.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если ключ найден; в противном случае, **ложные**.

## <a name="mapviewlookup-method"></a><a name="lookup"></a>MapView::Метод поиска

Возвращает значение типа V, связанное с указанным ключом типа K.

### <a name="syntax"></a>Синтаксис

```
V Lookup(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента в объекте MapView. Тип `key` typename *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с ключом `key`. Тип значения возврата — typename *V.*

## <a name="mapviewmapview-constructor"></a><a name="ctor"></a>MapView:MapView Конструктор

Инициализирует новый экземпляр класса MapView.

### <a name="syntax"></a>Синтаксис

```cpp
explicit MapView(const C& comp = C());

explicit MapView(const ::std::map<K, V, C>& m);

explicit MapView(std::map<K, V, C>&& m);

template <typename InIt> MapView(
    InIt first,
    InIt last,
    const C& comp = C());

MapView(
    ::std::initializer_list<std::pair<const K, V>> il,
    const C& comp = C());
```

### <a name="parameters"></a>Параметры

*Init*<br/>
Имя типа текущего объекта MapView.

*Комп*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элементов в качестве ключей сортировки для определения их относительного порядка в объекте MapView.

*М*<br/>
Ссылка или [Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) к `map Class` тому, который используется для инициализации текущего MapView.

*Первый*<br/>
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта MapView.

*Последний*<br/>
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта MapView.

*Il*<br/>
[Std::initializer_list<std::pair\<K,V>>](../standard-library/initializer-list-class.md) элементы которого будут вставлены в MapView.

## <a name="mapviewsize-method"></a><a name="size"></a>MapView::Метод размера

Возвращает количество элементов в текущем объекте MapView.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в текущем объекте MapView.

## <a name="mapviewsplit-method"></a><a name="split"></a>MapView::Метод разделения

Разделяет текущий объект MapView на два объекта MapView. Этот метод не выполняет никаких действий.

### <a name="syntax"></a>Синтаксис

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * secondPartition);
```

### <a name="parameters"></a>Параметры

*перваяПартия*<br/>
Первая часть исходного объекта MapView.

*второйЧасти*<br/>
Вторая часть исходного объекта MapView.

### <a name="remarks"></a>Remarks

Этот метод не выполняет никаких действий.

## <a name="see-also"></a>См. также раздел

[Название платформы](platform-namespace-c-cx.md)
