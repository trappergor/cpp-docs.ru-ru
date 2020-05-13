---
title: Класс Platform::Collections::Map
ms.date: 10/01/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
helpviewer_keywords:
- Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
ms.openlocfilehash: ff27f6c543a2326dd4318f66aae51b89092b28e2
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032451"
---
# <a name="platformcollectionsmap-class"></a>Класс Platform::Collections::Map

Представляет *сопоставление*, являющееся коллекцией пар "ключ-значение". Реализует [Windows::Foundation::: Коллекции::: IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) поможет с [связыванием данных](/windows/uwp/data-binding/data-binding-in-depth)XAML .

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключа в паре "ключ-значение".

*V*<br/>
Тип значения в паре "ключ-значение".

*C*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию, [\<std::менее K>](../standard-library/less-struct.md).

*__is_valid_winrt_type()* Функция компилятора, которая проверяет тип *K* и *V* и предоставляет дружественное сообщение об ошибке, если тип не может храниться на карте.

### <a name="remarks"></a>Remarks

Допустимые типы:

- целые числа

- интерфейс класса

- открытый ссылочный класс ^

- структура значений

- открытый класс перечисления

Карта — это, по сути, программа-оболочка для [std::map](../standard-library/map-class.md). Это конкретная реализация [Windows:::Foundation::Collections:::IMap<Windows:::Collections:::IKeyValuePair\<K, V>>](/uwp/api/windows.foundation.collections.imap-2) и [IObservableMap,](/uwp/api/windows.foundation.collections.iobservablemap-2) которые передаются через общедоступные интерфейсы Windows Runtime. При попытке использования типа `Platform::Collections::Map` в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Исправить ошибку можно, изменив тип параметра или возврат значения в [Windows::: Культура::: IMap\<K,>](/uwp/api/windows.foundation.collections.imap-2).

Для получения дополнительной информации [см.](../cppcx/collections-c-cx.md)

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Карта::Карта](#ctor)|Инициализирует новый экземпляр класса Map.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Карта::Очистить](#clear)|Удаляет все пары "ключ-значение" из текущего объекта Map.|
|[Карта::Первый](#first)|Возвращает итератор, указывающий первый элемент в сопоставлении.|
|[Карта::GetView](#getview)|Возвращает представление текущего объекта Map, доступное только для чтения (т. е. [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)).|
|[Карта::HasKey](#haskey)|Определяет, содержит ли текущий объект Map указанный ключ.|
|[Карта::Вставить](#insert)|Добавляет в текущий объект Map указанную пару "ключ-значение".|
|[Карта::Поиск](#lookup)|Извлекает элемент по указанному ключу в текущем объекте Map.|
|[Map::Remove](#remove)|Удаляет указанную пару "ключ-значение" из текущего объекта Map.|
|[Карта:Размер](#size)|Возвращает количество элементов в текущем объекте Map.|

### <a name="events"></a>События

|||
|-|-|
|Имя|Описание|
|[Карта::MapChanged](#mapchanged) событие|Происходит при изменении объекта Map.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Map`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="mapclear-method"></a><a name="clear"></a>Карта::Ясный метод

Удаляет все пары "ключ-значение" из текущего объекта Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="mapfirst-method"></a><a name="first"></a>Карта::Первый метод

Возвращает итератор, указывающий первый элемент в сопоставлении или `nullptr`, если сопоставление пусто.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент на карте.

### <a name="remarks"></a>Remarks

Удобный способ удержания итератора, возвращенного First() заключается в присвоении значения возврата переменной, которая задекларирована с ключевым словом **автоматического** типа вычета. Например, `auto x = myMap->First();`.

## <a name="mapgetview-method"></a><a name="getview"></a>Карта::GetView Метод

Возвращает вид только для чтения текущей Карты; то есть, [платформа::Коллекции::MapView класс](../cppcx/platform-collections-mapview-class.md), который реализует [Windows::Foundation::Collections::IMapView\<K,V>](/uwp/api/windows.foundation.collections.imapview-2) интерфейс.

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `MapView` .

## <a name="maphaskey-method"></a><a name="haskey"></a>Карта::Метод Хаски

Определяет, содержит ли текущий объект Map указанный ключ.

### <a name="syntax"></a>Синтаксис

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента Map. Тип *ключа* typename *K*.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если ключ найден; в противном случае, **ложные**.

## <a name="mapinsert-method"></a><a name="insert"></a>Карта::Вставить метод

Добавляет в текущий объект Map указанную пару "ключ-значение".

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключа* typename *K*.

*value*<br/>
Значение из пары "ключ-значение". Тип *значения* — typename *V.*

### <a name="return-value"></a>Возвращаемое значение

**верно,** если ключ существующего элемента в текущей Карте соответствует *ключу,* и значение части этого элемента устанавливается *значение.* **ложный,** если существующий элемент в текущей карте не соответствует *ключу,* а параметры *ключа* и *значения* превращаются в пару ключей, а затем добавляются к текущей карте.

## <a name="maplookup-method"></a><a name="lookup"></a>Карта::Метод поиска

Возвращает значение типа V, связанное с указанным ключом типа K, если ключ существует.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента на карте. Тип *ключа* typename *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, которое в паре с *ключом.* Тип значения возврата — typename *V.*

### <a name="remarks"></a>Remarks

Если ключа не существует, то [брошена платформа::OutOfBoundsException.](../cppcx/platform-outofboundsexception-class.md)

## <a name="mapmap-constructor"></a><a name="ctor"></a>Карта:Карта Конструктор

Инициализирует новый экземпляр класса Map.

### <a name="syntax"></a>Синтаксис

```cpp
explicit Map(const C& comp = C());
explicit Map(const StdMap& m);
explicit Map(StdMap&& m ;
template <typename InIt>
Map(
   InItfirst,
   InItlast,
   const C& comp = C());
```

### <a name="parameters"></a>Параметры

*Init*<br/>
Имя типа текущего объекта Map.

*Комп*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map.

*М*<br/>
Ссылка или [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) к `map Class` той, которая используется для инициализации текущей карты.

*Первый*<br/>
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта Map.

*Последний*<br/>
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта Map.

## <a name="mapmapchanged-event"></a><a name="mapchanged"></a>Карта::MapChanged Событие

Возникает, когда элемент вставляется в сопоставление или удаляется из него.

### <a name="syntax"></a>Синтаксис

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение

[КартаChangedEventHandler\<K,V>,](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) которая содержит информацию об объекте, который поднял событие, и вид изменений, которые произошли. Смотрите также [IMapChangedEventArgs\<K>](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) и [CollectionChange Enumeration](/uwp/api/windows.foundation.collections.collectionchange).

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

Windows Runtime приложений, которые используют C\<или Visual Basic проекта\<IMap K,V> как IDictionary K, V>.

## <a name="mapremove-method"></a><a name="remove"></a>Карта::Удалить метод

Удаляет указанную пару "ключ-значение" из текущего объекта Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключа* typename *K*.

## <a name="mapsize-method"></a><a name="size"></a>Карта::Метод размера

Возвращает номер [Windows:::Источник::: Культура::\<IKeyValuePair K,>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) элементов на карте.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в объекте Map.

## <a name="see-also"></a>См. также раздел

[Коллекции (КЗ/CX)](collections-c-cx.md)<br/>
[Название платформы](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
