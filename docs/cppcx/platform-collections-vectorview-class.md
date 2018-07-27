---
title: 'Класс Platform::Collections:: vectorview | Документы Microsoft'
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 937342c340b085f2e2bdeef8ed7df21dae826152
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092914"
---
# <a name="platformcollectionsvectorview-class"></a>Класс Platform::Collections::VectorView
Представляет доступное только для чтения представление упорядоченной коллекции объектов, в которой возможен доступ к каждому отдельному объекту по его индексу. Тип каждого объекта в коллекции задается параметром шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип элементов, содержащихся в объекте `VectorView`.  
  
 `E`  
 Определяет бинарный предикат для проверки равенства со значениями типа `T`. Значение по умолчанию — `std::equal_to<T>`.  
  
### <a name="remarks"></a>Примечания  
 `VectorView` Класс реализует [Windows::Foundation::Collections::IVectorView\<T >](http://go.microsoft.com/fwlink/p/?LinkId=262411) интерфейс и поддержку итераторов библиотеки стандартных шаблонов.  
  
### <a name="members"></a>Члены  
  
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

## <a name="first"></a>  Vectorview::First-метод
Возвращает итератор, указывающий первый элемент объекта VectorView.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий первый элемент объекта VectorView.  
  
### <a name="remarks"></a>Примечания  
 Это удобный способ сохранения итератора, возвращаемого методом First(), — присвоить возвращаемое значение переменной, объявленной с **автоматически** ключевое слово выведения типа. Например, `auto x = myVectorView->First();`.  
  


## <a name="getat"></a>  Vectorview::getat-метод
Извлекает элемент текущего VectorView, указанный заданным индексом.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `index`  
 Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте VectorView.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, заданный параметром `index`. Тип элемента указан параметром шаблона VectorView *T*.  
  


## <a name="getmany"></a>  Vectorview::getmany-метод
Извлекает последовательность элементов из текущего объекта VectorView, начиная с указанного индекса.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `startIndex`  
 Отсчитываемый от нуля индекс начала элементов для извлечения.  
  
 `dest`  
 После завершения операции, массив элементов начинается с элемента, заданного параметром `startIndex` и заканчивается последним элементом объекта vectorview.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество извлеченных элементов.  
  


## <a name="indexof"></a>  Vectorview::IndexOf-метод
Выполняет поиск указанного элемента в текущем объекте VectorView и возвращает его индекс, если он найден.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `value`  
 Элемент, который нужно найти.  
  
 `index`  
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
  


## <a name="ctor"></a>  Vectorview::vectorview-конструктор
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
 `InIt`  
 Тип коллекции объектов, используемой для инициализации текущего объекта VectorView.  
  
 il  
 Объект [std::initializer_list](../standard-library/initializer-list-class.md) , элементы которого будут использоваться для инициализации объекта VectorView.  
  
 `N`  
 Количество элементов в коллекции объектов, используемой для инициализации текущего объекта VectorView.  
  
 `size`  
 Количество элементов в объекте VectorView.  
  
 `value`  
 Значение, используемое для инициализации каждого элемента в текущем объекте VectorView.  
  
 `v`  
 [Значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для [std::vector](../standard-library/vector-class.md) , используемый для инициализации текущего объекта VectorView.  
  
 `ptr`  
 Указатель на объект `std::vector`, используемый для инициализации текущего объекта VectorView.  
  
 `arr`  
 Объект [Platform::Array](../cppcx/platform-array-class.md) объект, используемый для инициализации текущего объекта VectorView.  
  
 `a`  
 Объект [std::array](../standard-library/array-class-stl.md) объект, используемый для инициализации текущего объекта VectorView.  
  
 `first`  
 Первый элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип `first` передается с помощью параметра *точную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Последний элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип `last` передается с помощью параметра *точную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  


  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](platform-namespace-c-cx.md)   
 [Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)