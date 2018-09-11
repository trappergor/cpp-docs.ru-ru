---
title: 'Класс Platform::Collections:: vectorview | Документация Майкрософт'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
dev_langs:
- C++
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe3c516881115dd96337f950d83de2d30c57161b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102516"
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
Определяет бинарный предикат для проверки равенства со значениями типа `T`. Значение по умолчанию — `std::equal_to<T>`.

### <a name="remarks"></a>Примечания

`VectorView` Класс реализует [Windows::Foundation::Collections::IVectorView\<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_) интерфейс, а также поддержку итераторов библиотеки стандартных шаблонов.

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[VectorView::VectorView](#ctor)|Инициализирует новый экземпляр класса VectorView.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[VectorView::First](#first)|Возвращает итератор, указывающий первый элемент объекта VectorView.|
|[VectorView::GetAt](#getat)|Извлекает элемент текущего VectorView, указанный заданным индексом.|
|[VectorView::GetMany](#getmany)|Извлекает последовательность элементов из текущего объекта VectorView, начиная с указанного индекса.|
|[VectorView::IndexOf](#indexof)|Выполняет поиск указанного элемента в текущем объекте VectorView и возвращает его индекс, если он найден.|
|[VectorView::Size](#size)|Возвращает количество элементов в текущем объекте VectorView.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VectorView`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="first"></a>  Метод VectorView::First

Возвращает итератор, указывающий первый элемент объекта VectorView.

### <a name="syntax"></a>Синтаксис

```

virtual Windows::Foundation::Collections::IIterator<T>^
   First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент объекта VectorView.

### <a name="remarks"></a>Примечания

Удобный способ сохранения итератора, возвращаемого методом First() — присвоить возвращаемое значение переменной, объявленной с **автоматически** ключевым словом вывода типа. Например, `auto x = myVectorView->First();`.

## <a name="getat"></a>  Метод VectorView::GetAt

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

## <a name="getmany"></a>  Метод VectorView::GetMany

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
После завершения операции, массив элементов начинается с элемента, указанного `startIndex` и заканчивается последним элементом объекта vectorview.

### <a name="return-value"></a>Возвращаемое значение

Количество извлеченных элементов.

## <a name="indexof"></a>  Метод VectorView::IndexOf

Выполняет поиск указанного элемента в текущем объекте VectorView и возвращает его индекс, если он найден.

### <a name="syntax"></a>Синтаксис

```

virtual bool IndexOf(
   T value,
   unsigned int* index
);
```

### <a name="parameters"></a>Параметры

*значение*<br/>
Элемент, который нужно найти.

*Индекс*<br/>
Отсчитываемый от нуля индекс элемента, если параметр `value` найден; в противном случае — 0.

Параметр `index` имеет значение 0, если элемент является первым элементом объекта VectorView или элемент не найден. Если возвращаемое значение — `true`, элемент найден и является первым элементом; в противном случае элемент не найден.

### <a name="return-value"></a>Возвращаемое значение

Значение `true`, если указанный элемент найден; в противном случае — значение `false`.

## <a name="size"></a>  Метод VectorView::Size

Возвращает количество элементов в текущем объекте VectorView.

### <a name="syntax"></a>Синтаксис

```

virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в текущем объекте VectorView.

## <a name="ctor"></a>  Конструктор VectorView::VectorView

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

*InIt*<br/>
Тип коллекции объектов, используемой для инициализации текущего объекта VectorView.

*il*<br/>
Объект [std::initializer_list](../standard-library/initializer-list-class.md) , элементы которого будут использоваться для инициализации объекта VectorView.

*N*<br/>
Количество элементов в коллекции объектов, используемой для инициализации текущего объекта VectorView.

*size*<br/>
Количество элементов в объекте VectorView.

*значение*<br/>
Значение, используемое для инициализации каждого элемента в текущем объекте VectorView.

*v*<br/>
[Значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для [std::vector](../standard-library/vector-class.md) , используемый для инициализации текущего объекта VectorView.

*ptr*<br/>
Указатель на объект `std::vector`, используемый для инициализации текущего объекта VectorView.

*arr*<br/>
Объект [Platform::Array](../cppcx/platform-array-class.md) объект, используемый для инициализации текущего объекта VectorView.

*a*<br/>
Объект [std::array](../standard-library/array-class-stl.md) объект, используемый для инициализации текущего объекта VectorView.

*Первый*<br/>
Первый элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип `first` передается с помощью параметра *точную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

*последний*<br/>
Последний элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип `last` передается с помощью параметра *точную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)