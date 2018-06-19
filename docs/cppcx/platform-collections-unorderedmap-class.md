---
title: 'Класс Platform::Collections:: unorderedmap | Документы Microsoft'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fbc1905023f64c4983cf041eda244b28ce507abc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092335"
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

*K*  
Тип ключа в паре "ключ-значение".

*V*  
Тип значения в паре "ключ-значение".

*C*  
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию [std::equal_to\<K >](../standard-library/equal-to-struct.md).

### <a name="remarks"></a>Примечания

Допустимые типы:

- целые числа

- класс интерфейса ^

- открытый ссылочный класс ^

- структура значений

- открытый класс перечисления

**UnorderedMap** по сути является оболочкой для [std::unordered_map](../standard-library/unordered-map-class.md) , поддерживает хранение типов среды выполнения Windows. Это конкретная реализация типов [Windows::Foundation:: Collections::](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) и [IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) , передаваемых через открытые интерфейсы среды выполнения Windows. При попытке использования типа `Platform::Collections::UnorderedMap` в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Вы можете исправить ошибку, изменив тип параметра или возвращаемого значения для [Windows::Foundation:: Collections::](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).

Дополнительные сведения см. в разделе [коллекции](../cppcx/collections-c-cx.md).

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[UnorderedMap::UnorderedMap](#ctor)|Инициализирует новый экземпляр класса Map.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[UnorderedMap::Clear](#clear)|Удаляет все пары "ключ-значение" из текущего объекта Map.|
|[UnorderedMap::First](#first)|Возвращает итератор, указывающий первый элемент в сопоставлении.|
|[UnorderedMap::GetView](#getview)|Возвращает доступное только для чтения представление текущего сопоставления, то есть класс Platform::Collections::UnorderedMapView.|
|[UnorderedMap::HasKey](#haskey)|Определяет, содержит ли текущий объект Map указанный ключ.|
|[UnorderedMap::Insert](#insert)|Добавляет в текущий объект Map указанную пару "ключ-значение".|
|[UnorderedMap::Lookup](#lookup)|Извлекает элемент по указанному ключу в текущем объекте Map.|
|[UnorderedMap::Remove](#remove)|Удаляет указанную пару "ключ-значение" из текущего объекта Map.|
|[UnorderedMap::Size](#size)|Возвращает количество элементов в текущем объекте Map.|

### <a name="events"></a>События

|||
|-|-|
|name|Описание|
|[MAP::MapChanged](#mapchanged) событий|Происходит при изменении объекта Map.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`UnorderedMap`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="clear"></a>  Метод UnorderedMap::Clear

Удаляет все пары "ключ-значение" из текущего объекта UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="first"></a>  Метод UnorderedMap::First

Возвращает итератор, задающий первый [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) элемент в неупорядоченном сопоставлении.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ 
   First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент на карте.

### <a name="remarks"></a>Примечания

Это удобный способ сохранения итератора, возвращаемого методом First(), — присвоить возвращаемое значение переменной, объявленной с **автоматически** ключевое слово выведения типа. Например, `auto x = myUnorderedMap->First();`.

## <a name="getview"></a>  Метод UnorderedMap::GetView

Возвращает доступное только для чтения представление текущего объекта unorderedmap; то есть [класс Platform::Collections:: unorderedmapview](../cppcx/platform-collections-unorderedmapview-class.md) , реализующий [Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) интерфейса.

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `UnorderedMapView`.

## <a name="haskey"></a>  Метод UnorderedMap::HasKey

Определяет, содержит ли текущий объект UnorderedMap указанный ключ.

### <a name="syntax"></a>Синтаксис

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>Параметры

*key*  
Ключ, используемый для поиска элемента UnorderedMap. Тип *ключ* является именем типа *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение `true`, если ключ найден; в противном случае — значение `false`.

## <a name="insert"></a>  UnorderedMap::Insert Method

Добавляет в текущий объект UnorderedMap указанную пару "ключ-значение".

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>Параметры

*key*  
Ключ из пары "ключ-значение". Тип *ключ* является именем типа *K*.

*значение*  
Значение из пары "ключ-значение". Тип *значение* является именем типа *V*.

### <a name="return-value"></a>Возвращаемое значение

`true` Если ключ существующего элемента в текущем объекте Map совпадает *ключ* части значения этому элементу задано значение *значение*. `false` Если в текущем объекте Map нет элемента, соответствующего *ключ* и *ключ* и *значение* параметров, внесенные в виде пары ключ значение и затем добавляются в текущий объект UnorderedMap.

## <a name="lookup"></a>  Метод UnorderedMap::Lookup

Возвращает значение типа V, связанное с указанным ключом типа K.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>Параметры

*key*  
Ключ, используемый для поиска элемента в объекте UnorderedMap. Тип *ключ* является именем типа *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с *ключ*. Тип возвращаемого значения является именем типа *V*.

## <a name="mapchanged"></a>  UnorderedMap::MapChanged

Возникает, когда элемент вставляется в сопоставление или удаляется из него.

### <a name="syntax"></a>Синтаксис

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Объект [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) , содержащий сведения о объект, создавший событие и типе произошедшего изменения. См. также [IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) и [перечисление CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

Приложения для среды выполнения Windows, нам C# или Visual Basic проект IMap\<K, V > в качестве IDictionary\<K, V >.

## <a name="remove"></a>  Метод UnorderedMap::Remove

Удаляет указанную пару "ключ-значение" из текущего объекта UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>Параметры

*key*  
Ключ из пары "ключ-значение". Тип *ключ* является именем типа *K*.

## <a name="size"></a>  Метод UnorderedMap::Size

Возвращает число [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) элементов в объекте UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в объекте UnorderedMap.

## <a name="ctor"></a>  Конструктор UnorderedMap::UnorderedMap

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

*InIt*  
Имя типа текущего объекта UnorderedMap.

*P*  
Объект функции, который может сравнивать два ключа с целью определения их равенства. Этот параметр по умолчанию [std::equal_to\<K >](../standard-library/equal-to-struct.md).

*H*  
Объект функции, создающий хэш-значения для ключей. Этот параметр по умолчанию [хэша 1 класс](../standard-library/hash-class.md) для ключевых типов, поддерживаемых этим классом.

*m*  
Ссылка или [значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для [std::unordered_map](../standard-library/unordered-map-class.md) , используемый для инициализации текущего объекта UnorderedMap.

*IL* A [std::initializer_list](../standard-library/initializer-list-class.md) из [std::pair](../standard-library/pair-structure.md) объекты, которые используются для инициализации сопоставления.

*Первый*  
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта UnorderedMap.

*последний*  
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта UnorderedMap.

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)  
[Пространство имен Platform::Collections](../cppcx/platform-collections-namespace.md)  
[Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)  
[Класс Platform::Collections::UnorderedMapView](../cppcx/platform-collections-unorderedmapview-class.md)  
[Коллекции](../cppcx/collections-c-cx.md)  
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)  
