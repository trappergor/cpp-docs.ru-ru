---
title: 'Класс Platform::Collections:: MAP | Документы Microsoft'
ms.custom: ''
ms.date: 01/18/2018
ms.technology: cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6580ccb9ca19a575bac6a9fedbb4e8f16c7060ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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

*K*  
 Тип ключа в паре "ключ-значение".

*V*  
Тип значения в паре "ключ-значение".

*C*  
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию [std::less\<K >](../standard-library/less-struct.md).

*__is_valid_winrt_type()*  
Созданные компилятором функцию, которая проверяет тип *K* и *V* и предоставляет понятное сообщение об ошибке, если тип не может храниться в схеме.

### <a name="remarks"></a>Примечания

Допустимые типы:

- целые числа

- класс интерфейса ^

- открытый ссылочный класс ^

- структура значений

- открытый класс перечисления

Карта — это, по сути, программа-оболочка для [std::map](../standard-library/map-class.md). Это конкретная реализация C++ типов [Windows::Foundation:: Collections:: < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](http://go.microsoft.com/fwlink/p/?LinkId=262408) и [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) типы, которые передаются через открытые интерфейсы среды выполнения Windows. При попытке использования типа `Platform::Collections::Map` в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Вы можете исправить ошибку, изменив тип параметра или возвращаемого значения для [Windows::Foundation:: Collections::\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262408).

Дополнительные сведения см. в разделе [коллекции](../cppcx/collections-c-cx.md).

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[MAP::MAP](#ctor)|Инициализирует новый экземпляр класса Map.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
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
|[MAP::MapChanged](#mapchanged-event.md) `event`|Происходит при изменении объекта Map.|

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

Это удобный способ сохранения итератора, возвращаемого методом First(), — присвоить возвращаемое значение переменной, объявленной с **автоматически** ключевое слово выведения типа. Например, `auto x = myMap->First();`.

## <a name="getview"></a>  Метод MAP::GetView

Возвращает только для чтения представление текущего сопоставления; то есть [класс Platform::Collections:: mapview](../cppcx/platform-collections-mapview-class.md), который реализует [Windows::Foundation:: Collections::\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) интерфейса.

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

*key*  
Ключ, используемый для поиска элемента Map. Тип *ключ* является именем типа *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение `true`, если ключ найден; в противном случае — значение `false`.

## <a name="insert"></a>  Метод MAP::INSERT

Добавляет в текущий объект Map указанную пару "ключ-значение".

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Параметры

*key*  
Ключ из пары "ключ-значение". Тип *ключ* является именем типа *K*.

*значение*  
Значение из пары "ключ-значение". Тип *значение* является именем типа *V*.

### <a name="return-value"></a>Возвращаемое значение

`true` Если ключ существующего элемента в текущем объекте Map совпадает *ключ* части значения этому элементу задано значение *значение*. `false` Если в текущем объекте Map нет элемента, соответствующего *ключ* и *ключ* и *значение* параметров, внесенные в виде пары ключ значение и затем добавляются в текущей карты.

## <a name="lookup"></a>  Метод MAP::Lookup

Возвращает значение типа V, связанное с указанным ключом типа K, если ключ существует.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Параметры

*key*  
Ключ, используемый для поиска элемента в сопоставлении. Тип *ключ* является именем типа *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с *ключ*. Тип возвращаемого значения является именем типа *V*.

### <a name="remarks"></a>Примечания

Если ключ не существует, то [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) возникает исключение.

## <a name="ctor"></a>  MAP::MAP-конструктор

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

*InIt*  
Имя типа текущего объекта Map.

*comp*  
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map.

*m*  
Ссылка или [значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для `map Class` , используемый для инициализации текущего объекта Map.

*Первый*  
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта Map.

*последний*  
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта Map.

## <a name="mapchanged"></a>  Событие MAP::MapChanged

Возникает, когда элемент вставляется в сопоставление или удаляется из него.

### <a name="syntax"></a>Синтаксис

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Объект [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) , содержащий сведения о объект, создавший событие и типе произошедшего изменения. См. также [IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) и [перечисление CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

Проект приложения для среды выполнения Windows, использующие C# или Visual Basic IMap\<K, V > в качестве IDictionary\<K, V >.

## <a name="remove"></a>  Метод MAP::Remove

Удаляет указанную пару "ключ-значение" из текущего объекта Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Параметры

*key*  
Ключ из пары "ключ-значение". Тип *ключ* является именем типа *K*.

## <a name="size"></a>  Метод MAP::size

Возвращает число [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) элементов в объекте Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в объекте Map.

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)  
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)  
