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
ms.openlocfilehash: 81721d719a424250beed89f4a5656b3f2fc27922
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816299"
---
# <a name="platformcollectionsmap-class"></a>Класс Platform::Collections::Map

Представляет *сопоставление*, являющееся коллекцией пар "ключ-значение". Реализует [Windows:: Foundation:: Collections:: IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap_k_v_) для помощи с [привязкой данных](/windows/uwp/data-binding/data-binding-in-depth)XAML.

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
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию [std:: less @ no__t-1000 >](../standard-library/less-struct.md).

*__is_valid_winrt_type ()* Созданная компилятором функция, которая проверяет тип *K* и *V* и предоставляет понятное сообщение об ошибке, если тип не может быть сохранен на карте.

### <a name="remarks"></a>Примечания

Допустимые типы:

- целые числа

- класс интерфейса ^

- открытый ссылочный класс ^

- структура значений

- открытый класс перечисления

Карта — это, по сути, программа-оболочка для [std::map](../standard-library/map-class.md). Это C++ конкретная реализация типов [Windows:: Foundation:: Collections:: IMAP < Windows:: Foundation:: Collections:: IKeyValuePair @ no__t-2000, V > >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) и [IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) , которые передаются в общедоступных окнах. Интерфейсы среды выполнения. При попытке использования типа `Platform::Collections::Map` в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Эту ошибку можно исправить, изменив тип параметра или возвращаемого значения на [Windows:: Foundation:: Collections:: IMAP @ no__t-1000, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).

Дополнительные сведения см. в разделе [коллекции](../cppcx/collections-c-cx.md).

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Map:: Map](#ctor)|Инициализирует новый экземпляр класса Map.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Map::Clear](#clear)|Удаляет все пары "ключ-значение" из текущего объекта Map.|
|[Map:: First](#first)|Возвращает итератор, указывающий первый элемент в сопоставлении.|
|[Map::GetView](#getview)|Возвращает представление текущего объекта Map, доступное только для чтения (т. е. [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)).|
|[Map:: HasKey](#haskey)|Определяет, содержит ли текущий объект Map указанный ключ.|
|[Map::Insert](#insert)|Добавляет в текущий объект Map указанную пару "ключ-значение".|
|[Map::Lookup](#lookup)|Извлекает элемент по указанному ключу в текущем объекте Map.|
|[Map::Remove](#remove)|Удаляет указанную пару "ключ-значение" из текущего объекта Map.|
|[Map::Size](#size)|Возвращает количество элементов в текущем объекте Map.|

### <a name="events"></a>События

|||
|-|-|
|name|Описание|
|Событие [Map:: мапчанжед](#mapchanged)|Происходит при изменении объекта Map.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Map`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="clear"></a>Метод Map:: Clear

Удаляет все пары "ключ-значение" из текущего объекта Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="first"></a>Метод Map:: First

Возвращает итератор, указывающий первый элемент в сопоставлении или `nullptr`, если сопоставление пусто.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент на карте.

### <a name="remarks"></a>Примечания

Удобным способом удержания итератора, возвращенного первым (), является присвоение возвращаемого значения переменной, объявленной с ключевым словом **автоматического** выведения типа. Например, `auto x = myMap->First();`.

## <a name="getview"></a>Метод Map:: onview

Возвращает доступное только для чтения представление текущей схемы. то есть [класс Platform:: Collections:: MapView](../cppcx/platform-collections-mapview-class.md), реализующий интерфейс [Windows:: Foundation:: Collections:: IMapView @ No__t-1000, V >]/UWP/API/Windows.Foundation.Collections.IMapView_K_V_).

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `MapView`.

## <a name="haskey"></a>Метод Map:: HasKey

Определяет, содержит ли текущий объект Map указанный ключ.

### <a name="syntax"></a>Синтаксис

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента Map. Тип *ключа* — TypeName *K*.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если ключ найден; в противном случае — **значение false**.

## <a name="insert"></a>Метод Map:: INSERT

Добавляет в текущий объект Map указанную пару "ключ-значение".

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключа* — TypeName *K*.

*value*<br/>
Значение из пары "ключ-значение". Тип *значения* — TypeName *V*.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если ключ существующего элемента в текущей карте соответствует *ключу* , а значение этого элемента равно *значению*. **значение false** , если существующий элемент в текущем *ключе* сопоставления не совпадает, а параметры *ключа* и *значения* вносятся в пару "ключ-значение", а затем добавляются в текущую карту.

## <a name="lookup"></a>Метод Map:: Lookup

Возвращает значение типа V, связанное с указанным ключом типа K, если ключ существует.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента на карте. Тип *ключа* — TypeName *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с *ключом*. Тип возвращаемого значения — TypeName *V*.

### <a name="remarks"></a>Примечания

Если ключ не существует, создается исключение [Platform:: OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) .

## <a name="ctor"></a>Конструктор Map:: Map

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

*Ini*<br/>
Имя типа текущего объекта Map.

*соответствовал*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map.

*m*<br/>
Ссылка или [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) на `map Class`, используемый для инициализации текущей схемы.

*началь*<br/>
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта Map.

*Последняя*<br/>
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта Map.

## <a name="mapchanged"></a>Событие Map:: Мапчанжед

Возникает, когда элемент вставляется в сопоставление или удаляется из него.

### <a name="syntax"></a>Синтаксис

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

[Мапчанжедевенсандлер @ no__t-1000, V >](/uwp/api/windows.foundation.collections.mapchangedeventhandler) , содержащий сведения об объекте, вызвавшем событие, и типе произошедшего изменения. См. также [перечисление](/uwp/api/windows.foundation.collections.collectionchange) [имапчанжедевентаргс @ no__t-1000 >](/uwp/api/Windows.Foundation.Collections.IMapChangedEventArgs_K_) и коллектиончанже.

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

Среда выполнения Windows приложения, которые C# используют или Visual Basic Project IMAP @ No__t-1000, v > как IDictionary @ No__t-2000, v >.

## <a name="remove"></a>Метод Map:: Remove

Удаляет указанную пару "ключ-значение" из текущего объекта Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключа* — TypeName *K*.

## <a name="size"></a>Метод Map:: size

Возвращает число элементов [Windows:: Foundation:: Collections:: IKeyValuePair @ no__t-1000, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) на карте.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в объекте Map.

## <a name="see-also"></a>См. также

[Коллекции (C++/CX)](collections-c-cx.md)<br/>
[Пространство имен платформы](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
