---
title: Класс Platform::Collections::UnorderedMap
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
ms.openlocfilehash: c6f702850f5bf84b8b1bc857c9d0a744728d0cbd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354420"
---
# <a name="platformcollectionsunorderedmap-class"></a>Класс Platform::Collections::UnorderedMap

Представляет неупорядоченное *сопоставление*, являющееся коллекцией пар "ключ-значение".

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename K,
   typename V,
   typename C = std::equal_to<K>
>
ref class Map sealed;
```

#### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключа в паре "ключ-значение".

*V*<br/>
Тип значения в паре "ключ-значение".

*C*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию, [\<std::equal_to K>](../standard-library/equal-to-struct.md).

### <a name="remarks"></a>Remarks

Допустимые типы:

- целые числа

- интерфейс класса

- открытый ссылочный класс ^

- структура значений

- открытый класс перечисления

**UnorderedMap** в основном является оберткой для [std::unordered_map,](../standard-library/unordered-map-class.md) которая поддерживает хранение типов Runtime Windows. Это конкретная реализация [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) и [IObservableMap,](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) которые передаются через общедоступные интерфейсы Windows Runtime. При попытке использования типа `Platform::Collections::UnorderedMap` в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Вы можете исправить ошибку, изменив тип параметра или возвращаемого значения на [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).

Для получения дополнительной информации [см.](../cppcx/collections-c-cx.md)

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Неупорядоченнаякарта:UnorderedMap](#ctor)|Инициализирует новый экземпляр класса Map.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Неупорядоченнаякарта::Ясно](#clear)|Удаляет все пары "ключ-значение" из текущего объекта Map.|
|[НеупорядоченнаяКарта::Первый](#first)|Возвращает итератор, указывающий первый элемент в сопоставлении.|
|[Неупорядоченнаякарта::GetView](#getview)|Возвращает доступное только для чтения представление текущего сопоставления, то есть класс Platform::Collections::UnorderedMapView.|
|[Неупорядоченнаякарта::HasKey](#haskey)|Определяет, содержит ли текущий объект Map указанный ключ.|
|[Неупорядоченнаякарта::Вставка](#insert)|Добавляет в текущий объект Map указанную пару "ключ-значение".|
|[Неупорядоченнаякарта::Поиск](#lookup)|Извлекает элемент по указанному ключу в текущем объекте Map.|
|[Неупорядоченнаякарта::Удалить](#remove)|Удаляет указанную пару "ключ-значение" из текущего объекта Map.|
|[Неупорядоченнаякарта::Размер](#size)|Возвращает количество элементов в текущем объекте Map.|

### <a name="events"></a>События

|||
|-|-|
|Имя|Описание|
|[Карта::MapChanged](#mapchanged) событие|Происходит при изменении объекта Map.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`UnorderedMap`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="unorderedmapclear-method"></a><a name="clear"></a>Неупорядоченнаякарта::Ясный метод

Удаляет все пары "ключ-значение" из текущего объекта UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="unorderedmapfirst-method"></a><a name="first"></a>UnorderedMap::Первый метод

Возвращает итератор, который определяет первую [Windows::::: Коллекции::\<IKeyValuePair K,>](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) элемент на неупорядоченной карте.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
   First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент на карте.

### <a name="remarks"></a>Remarks

Удобный способ удержания итератора, возвращенного First() заключается в присвоении значения возврата переменной, которая задекларирована с ключевым словом **автоматического** типа вычета. Например, `auto x = myUnorderedMap->First();`.

## <a name="unorderedmapgetview-method"></a><a name="getview"></a>Неупорядоченная карта::GetView Метод

Возвращает только для чтения представление текущего UnorderedMap; то есть, [Платформа::Коллекции::UnorderedMapView Класс,](../cppcx/platform-collections-unorderedmapview-class.md) который реализует "Windows::Фундамент::Коллекции::IMapView::IMapView::IMapView/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) интерфейс.

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `UnorderedMapView`.

## <a name="unorderedmaphaskey-method"></a><a name="haskey"></a>UnorderedMap::HasKey Метод

Определяет, содержит ли текущий объект UnorderedMap указанный ключ.

### <a name="syntax"></a>Синтаксис

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключ, используемый для поиска элемента UnorderedMap. Тип *ключа* typename *K*.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если ключ найден; в противном случае, **ложные**.

## <a name="unorderedmapinsert-method"></a><a name="insert"></a>Неупорядоченнаякарта::Вставить метод

Добавляет в текущий объект UnorderedMap указанную пару "ключ-значение".

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключ из пары "ключ-значение". Тип *ключа* typename *K*.

*value*<br/>
Значение из пары "ключ-значение". Тип *значения* — typename *V.*

### <a name="return-value"></a>Возвращаемое значение

**верно,** если ключ существующего элемента в текущей Карте соответствует *ключу,* и значение части этого элемента устанавливается *значение.* **ложный,** если существующий элемент в текущей карте не соответствует *ключу,* а параметры *ключа* и *значения* превращаются в пару ключей, а затем добавляются к текущей Неупорядоченной Map.

## <a name="unorderedmaplookup-method"></a><a name="lookup"></a>Неупорядоченнаякарта::Метод поиска

Возвращает значение типа V, связанное с указанным ключом типа K.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключ, используемый для поиска элемента в объекте UnorderedMap. Тип *ключа* typename *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, которое в паре с *ключом.* Тип значения возврата — typename *V.*

## <a name="unorderedmapmapchanged"></a><a name="mapchanged"></a>Неупорядоченнаякарта::КартаИзменена

Возникает, когда элемент вставляется в сопоставление или удаляется из него.

### <a name="syntax"></a>Синтаксис

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение

[КартаChangedEventHandler\<K,V>,](/uwp/api/windows.foundation.collections.mapchangedeventhandler) которая содержит информацию об объекте, который поднял событие, и вид изменений, которые произошли. Смотрите также [IMapChangedEventArgs\<K>](/uwp/api/Windows.Foundation.Collections.IMapChangedEventArgs_K_) и [CollectionChange Enumeration](/uwp/api/windows.foundation.collections.collectionchange).

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

Windows Runtime приложений, что нам Ск з или Visual Basic проекта IMap\<K,V> как IDictionary\<K,V>.

## <a name="unorderedmapremove-method"></a><a name="remove"></a>Неупорядоченная карта::Удалить метод

Удаляет указанную пару "ключ-значение" из текущего объекта UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключ из пары "ключ-значение". Тип *ключа* typename *K*.

## <a name="unorderedmapsize-method"></a><a name="size"></a>Неупорядоченнаякарта::Метод размера

Возвращает номер [Windows:::Источник::: Культура::\<IKeyValuePair K,>](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) элементов в unorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в объекте UnorderedMap.

## <a name="unorderedmapunorderedmap-constructor"></a><a name="ctor"></a>Неупорядоченнаякарта:Неупорядоченный конструктор Map

Инициализирует новый экземпляр класса UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
UnorderedMap();

explicit UnorderedMap(
    size_t n
    );

UnorderedMap(
    size_t n,
    const H& h
    );

UnorderedMap(
    size_t n,
    const H& h,
    const P& p
    );

explicit UnorderedMap(
    const std::unordered_map<K, V, H, P>& m
    );

explicit UnorderedMap(
    std::unordered_map<K, V, H, P>&& m
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p
    );
```

### <a name="parameters"></a>Параметры

*Init*<br/>
Имя типа текущего объекта UnorderedMap.

*P*<br/>
Объект функции, который может сравнивать два ключа с целью определения их равенства. Этот параметр по умолчанию [\<std::equal_to K>](../standard-library/equal-to-struct.md).

*H*<br/>
Объект функции, создающий хэш-значения для ключей. Этот параметр по умолчанию влияет на [хэш-класс 1](../standard-library/hash-class.md) для ключевых типов, поддерживающих класс.

*М*<br/>
Ссылка или [Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) к [std::unordered_map,](../standard-library/unordered-map-class.md) которая используется для инициализации текущего UnorderedMap.

*Il*<br/>
[Std::initializer_list](../standard-library/initializer-list-class.md) [из объектов std::pair,](../standard-library/pair-structure.md) которые используются для инициализации карты.

*Первый*<br/>
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта UnorderedMap.

*Последний*<br/>
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта UnorderedMap.

## <a name="see-also"></a>См. также раздел

[Название платформы](platform-namespace-c-cx.md)<br/>
[Платформа:Название коллекций](../cppcx/platform-collections-namespace.md)<br/>
[Платформа:Коллекции::Карта класса](../cppcx/platform-collections-map-class.md)<br/>
[Класс Platform::Collections::UnorderedMapView](../cppcx/platform-collections-unorderedmapview-class.md)<br/>
[Коллекции](../cppcx/collections-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
