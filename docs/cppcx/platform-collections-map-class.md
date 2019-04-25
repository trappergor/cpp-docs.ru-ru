---
title: Класс Platform::Collections::Map
ms.date: 03/27/2019
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
ms.openlocfilehash: ce50290217c7c06e26f26fc50564d3e37c873157
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161762"
---
# <a name="platformcollectionsmap-class"></a>Класс Platform::Collections::Map

Представляет *сопоставление*, являющееся коллекцией пар "ключ-значение".

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
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию [std::less\<K >](../standard-library/less-struct.md).

*__is_valid_winrt_type()* созданная компилятором функция, которая проверяет тип *K* и *V* и предоставляет понятное сообщение об ошибке, если тип не может храниться в сопоставлении.

### <a name="remarks"></a>Примечания

Допустимые типы:

- целые числа

- класс интерфейса ^

- открытый ссылочный класс ^

- структура значений

- открытый класс перечисления

Карта — это, по сути, программа-оболочка для [std::map](../standard-library/map-class.md). Это конкретная реализация в C++ из [Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) и [IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) типы, передаваемые через открытые интерфейсы среды выполнения Windows. При попытке использования типа `Platform::Collections::Map` в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Вы можете исправить ошибку, изменив тип параметра или возвращаемого значения на [Windows::Foundation::Collections::IMap\<K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).

Дополнительные сведения см. в разделе [коллекций](../cppcx/collections-c-cx.md).

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[MAP::MAP](#ctor)|Инициализирует новый экземпляр класса Map.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Map::Clear](#clear)|Удаляет все пары "ключ-значение" из текущего объекта Map.|
|[MAP::First](#first)|Возвращает итератор, указывающий первый элемент в сопоставлении.|
|[Map::GetView](#getview)|Возвращает представление текущего объекта Map, доступное только для чтения (т. е. [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)).|
|[MAP::HasKey](#haskey)|Определяет, содержит ли текущий объект Map указанный ключ.|
|[Map::Insert](#insert)|Добавляет в текущий объект Map указанную пару "ключ-значение".|
|[Map::Lookup](#lookup)|Извлекает элемент по указанному ключу в текущем объекте Map.|
|[Map::Remove](#remove)|Удаляет указанную пару "ключ-значение" из текущего объекта Map.|
|[Map::Size](#size)|Возвращает количество элементов в текущем объекте Map.|

### <a name="events"></a>События

|||
|-|-|
|name|Описание|
|[MAP::MapChanged](#mapchanged) событий|Происходит при изменении объекта Map.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Map`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="clear"></a>  Метод MAP::Clear

Удаляет все пары "ключ-значение" из текущего объекта Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="first"></a>  Метод MAP::First

Возвращает итератор, указывающий первый элемент в сопоставлении или `nullptr`, если сопоставление пусто.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент на карте.

### <a name="remarks"></a>Примечания

Удобный способ сохранения итератора, возвращаемого методом First() — присвоить возвращаемое значение переменной, объявленной с **автоматически** ключевым словом вывода типа. Например, `auto x = myMap->First();`.

## <a name="getview"></a>  Метод MAP::GetView

Возвращает доступное только для чтения представление текущего сопоставления; то есть [класс Platform::Collections:: mapview](../cppcx/platform-collections-mapview-class.md), который реализует [Windows::Foundation::Collections::IMapView\<K, V >] / uwp/api/Windows.Foundation.Collections.IMapView_K_V_) интерфейса.

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `MapView`.

## <a name="haskey"></a>  Метод MAP::HasKey

Определяет, содержит ли текущий объект Map указанный ключ.

### <a name="syntax"></a>Синтаксис

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента Map. Тип *ключ* является именем типа *K*.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если ключ найден; в противном случае — значение **false**.

## <a name="insert"></a>  Метод MAP::INSERT

Добавляет в текущий объект Map указанную пару "ключ-значение".

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключ* является именем типа *K*.

*value*<br/>
Значение из пары "ключ-значение". Тип *значение* является именем типа *V*.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если ключ существующего элемента в текущем объекте Map совпадает с *ключ* и часть, представляющая значение этого элемента имеет значение *значение*. **false** совпадает ни один существующий элемент в текущем объекте Map *ключ* и *ключ* и *значение* параметров, внесенные в пару ключ значение и затем добавляются в текущий объект Map.

## <a name="lookup"></a>  Метод MAP::Lookup

Возвращает значение типа V, связанное с указанным ключом типа K, если ключ существует.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента на карте. Тип *ключ* является именем типа *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, с которым сопоставляется *ключ*. Тип возвращаемого значения является именем типа *V*.

### <a name="remarks"></a>Примечания

Если ключ не существует, то [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) возникает исключение.

## <a name="ctor"></a>  Конструктор MAP::MAP

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

*InIt*<br/>
Имя типа текущего объекта Map.

*Зап.*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map.

*m*<br/>
Ссылка или [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для `map Class` , используемый для инициализации текущего объекта Map.

*Первый*<br/>
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта Map.

*последний*<br/>
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта Map.

## <a name="mapchanged"></a>  Событие MAP::MapChanged

Возникает, когда элемент вставляется в сопоставление или удаляется из него.

### <a name="syntax"></a>Синтаксис

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Объект [MapChangedEventHandler\<K, V >](/uwp/api/windows.foundation.collections.mapchangedeventhandler) , содержащий сведения об объекте, который вызвал событие и типе произошедшего изменения. См. также [IMapChangedEventArgs\<K >](/uwp/api/Windows.Foundation.Collections.IMapChangedEventArgs_K_) и [CollectionChange Enumeration](/uwp/api/windows.foundation.collections.collectionchange).

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

Приложения для среды выполнения Windows, использующих C# или Visual Basic проект IMap\<K, V > в качестве IDictionary\<K, V >.

## <a name="remove"></a>  Метод MAP::Remove

Удаляет указанную пару "ключ-значение" из текущего объекта Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключ* является именем типа *K*.

## <a name="size"></a>  Метод MAP::size

Возвращает количество [Windows::Foundation::Collections::IKeyValuePair\<K, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) элементов в сопоставлении.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в объекте Map.

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
