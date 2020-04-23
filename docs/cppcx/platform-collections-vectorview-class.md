---
title: Класс Platform::Collections::VectorView
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
ms.openlocfilehash: 7f12c7b926cd8d3d8fc892cff6f2245e7c216219
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032230"
---
# <a name="platformcollectionsvectorview-class"></a>Класс Platform::Collections::VectorView

Представляет доступное только для чтения представление упорядоченной коллекции объектов, в которой возможен доступ к каждому отдельному объекту по его индексу. Тип каждого объекта в коллекции задается параметром шаблона.

## <a name="syntax"></a>Синтаксис

```
template <typename T, typename E>
   ref class VectorView sealed;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип элементов, содержащихся в объекте `VectorView` .

*E*<br/>
Определяет бинарный предикат для проверки равенства со значениями типа `T`. Значение по умолчанию — `std::equal_to<T>`.

### <a name="remarks"></a>Remarks

Класс `VectorView` реализует [Windows::Foundation::Collections:::IVectorView\<T>](/uwp/api/windows.foundation.collections.ivectorview-1) интерфейс и поддержку итераторов библиотеки Standard Template.

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Векторвид::ВекторВьюй](#ctor)|Инициализирует новый экземпляр класса VectorView.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ВекторВид::Первый](#first)|Возвращает итератор, указывающий первый элемент объекта VectorView.|
|[Векторвид::GetAt](#getat)|Извлекает элемент текущего VectorView, указанный заданным индексом.|
|[ВекторВид::GetMany](#getmany)|Извлекает последовательность элементов из текущего объекта VectorView, начиная с указанного индекса.|
|[Векторвид:Индекс](#indexof)|Выполняет поиск указанного элемента в текущем объекте VectorView и возвращает его индекс, если он найден.|
|[VectorView::Size](#size)|Возвращает количество элементов в текущем объекте VectorView.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VectorView`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="vectorviewfirst-method"></a><a name="first"></a>VectorView::Первый метод

Возвращает итератор, указывающий первый элемент объекта VectorView.

### <a name="syntax"></a>Синтаксис

```

virtual Windows::Foundation::Collections::IIterator<T>^
   First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент объекта VectorView.

### <a name="remarks"></a>Remarks

Удобный способ удержания итератора, возвращенного First() заключается в присвоении значения возврата переменной, которая задекларирована с ключевым словом **автоматического** типа вычета. Например, `auto x = myVectorView->First();`.

## <a name="vectorviewgetat-method"></a><a name="getat"></a>Векторвид::Метод GetAt

Извлекает элемент текущего VectorView, указанный заданным индексом.

### <a name="syntax"></a>Синтаксис

```

T GetAt(
   UInt32 index
);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте VectorView.

### <a name="return-value"></a>Возвращаемое значение

Элемент, заданный параметром `index`. Тип элемента указан параметром шаблона VectorView, *T*.

## <a name="vectorviewgetmany-method"></a><a name="getmany"></a>VectorView::GetMany Метод

Извлекает последовательность элементов из текущего объекта VectorView, начиная с указанного индекса.

### <a name="syntax"></a>Синтаксис

```

virtual unsigned int GetMany(
   unsigned int startIndex,
   ::Platform::WriteOnlyArray<T>^ dest
);
```

### <a name="parameters"></a>Параметры

*startIndex*<br/>
Отсчитываемый от нуля индекс начала элементов для извлечения.

*dest*<br/>
Когда эта операция завершается, массив элементов начинается с элемента, заданного `startIndex`, и заканчивается последним элементом объекта VectorView.

### <a name="return-value"></a>Возвращаемое значение

Количество извлеченных элементов.

## <a name="vectorviewindexof-method"></a><a name="indexof"></a>Векторвид::Индексметод

Выполняет поиск указанного элемента в текущем объекте VectorView и возвращает его индекс, если он найден.

### <a name="syntax"></a>Синтаксис

```

virtual bool IndexOf(
   T value,
   unsigned int* index
);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Элемент, который нужно найти.

*Индекс*<br/>
Отсчитываемый от нуля индекс элемента, если параметр `value` найден; в противном случае — 0.

Параметр *индекса* растеряет 0, если `VectorView` элемент является первым элементом или не найден элемент. Если значение возврата **верно,** элемент был найден, и это первый элемент; в противном случае товар не найден.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если указанный элемент найден; в противном случае, **ложные**.

## <a name="vectorviewsize-method"></a><a name="size"></a>VectorView::Метод размера

Возвращает количество элементов в текущем объекте VectorView.

### <a name="syntax"></a>Синтаксис

```

virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в текущем объекте VectorView.

## <a name="vectorviewvectorview-constructor"></a><a name="ctor"></a>Векторвид::ВекторВид Конструктор

Инициализирует новый экземпляр класса VectorView.

### <a name="syntax"></a>Синтаксис

```
VectorView();
explicit VectorView(
   UInt32 size
);
VectorView(
   UInt32 size,
   T value
);
explicit VectorView(
   const ::std::vector<T>& v
);
explicit VectorView(
   ::std::vector<T>&& v
);
VectorView(
   const T * ptr,
   UInt32 size
);

template <
   size_t N
>
explicit VectorView(
   const T (&arr)[N]
);

template <
   size_t N
>
explicit VectorView(
   const ::std::array<T,
   N>& a
);

explicit VectorView(
   const ::Platform::Array<T>^ arr
);

template <
   typename InIt
>
VectorView(
   InItfirst,
   InItlast
);

VectorView(
   std::initializer_list<T> il
);
```

### <a name="parameters"></a>Параметры

*Init*<br/>
Тип коллекции объектов, используемой для инициализации текущего объекта VectorView.

*Il*<br/>
[Std::initializer_list](../standard-library/initializer-list-class.md) чьи элементы будут использованы для инициализации VectorView.

*Нет*<br/>
Количество элементов в коллекции объектов, используемой для инициализации текущего объекта VectorView.

*size*<br/>
Количество элементов в объекте VectorView.

*value*<br/>
Значение, используемое для инициализации каждого элемента в текущем объекте VectorView.

*V*<br/>
[Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) к [std::vector,](../standard-library/vector-class.md) который используется для инициализации текущего VectorView.

*Ptr*<br/>
Указатель на объект `std::vector`, используемый для инициализации текущего объекта VectorView.

*Arr*<br/>
[Платформа::Объект Array,](../cppcx/platform-array-class.md) который используется для инициализации текущего VectorView.

*a*<br/>
[Std::array](../standard-library/array-class-stl.md) объект, который используется для инициализации текущего VectorView.

*Первый*<br/>
Первый элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип `first` передается с помощью *идеальной пересылки.* Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

*Последний*<br/>
Последний элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип `last` передается с помощью *идеальной пересылки.* Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>См. также раздел

[Название платформы](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
