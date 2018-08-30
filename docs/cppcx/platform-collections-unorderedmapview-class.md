---
title: 'Класс Platform::Collections:: unorderedmapview | Документация Майкрософт'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c463dbcb68b5a4b875dbb109eedc07a3b4b27c86
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203032"
---
# <a name="platformcollectionsunorderedmapview-class"></a>Класс Platform::Collections::UnorderedMapView
Представляет доступное только для чтения представление на *карте*, которое является коллекцией пар "ключ-значение".  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = ::std::equal_to<K>>  
ref class UnorderedMapView sealed;  
```  
  
#### <a name="parameters"></a>Параметры  
 `K`  
 Тип ключа в паре "ключ-значение".  
  
 `V`  
 Тип значения в паре "ключ-значение".  
  
 `C`  
 Тип, предоставляющий объект функции, который может сравнивать два ключевых значения для определения равенства. По умолчанию [std::equal_to\<K >](../standard-library/equal-to-struct.md)  
  
### <a name="remarks"></a>Примечания  
 UnorderedMapView — это конкретная реализация C++ [Windows::Foundation::Collections::IMapView\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262409) интерфейс, который передается через двоичный интерфейс приложений (ABI). Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[UnorderedMapView::UnorderedMapView](#ctor)|Инициализирует новый экземпляр класса UnorderedMapView.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[UnorderedMapView::First](#first)|Возвращает итератор, который инициализируется первым элементом в представлении карты.|  
|[UnorderedMapView::HasKey](#haskey)|Определяет, содержит ли текущий объект UnorderedMapView указанный ключ.|  
|[UnorderedMapView::Lookup](#lookup)|Извлекает элемент по указанному ключу в текущем объекте UnorderedMapView.|  
|[UnorderedMapView::Size](#size)|Возвращает количество элементов в текущем объекте UnorderedMapView.|  
|[UnorderedMapView::Split](#split)|Разделяет исходный объект UnorderedMapView на два объекта UnorderedMapView.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `UnorderedMapView`  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  

## <a name="first"></a>  Метод UnorderedMapView::First
Возвращает итератор, задающий первый [Windows::Foundation::Collections::IKeyValuePair\<K, V >](https://msdn.microsoft.com/library/windows/apps/br226031.aspx) элемент в неупорядоченном сопоставлении.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp   
virtual Windows::Foundation::Collections::IIterator<  
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
    First();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий первый элемент в представлении сопоставления.  
  
### <a name="remarks"></a>Примечания  
 Удобный способ сохранения итератора, возвращаемого методом First() — присвоить возвращаемое значение переменной, объявленной с **автоматически** ключевым словом вывода типа. Например, `auto x = myMapView->First();`.  
  


## <a name="haskey"></a>  Метод UnorderedMapView::HasKey
Определяет, содержит ли текущий объект UnorderedMap указанный ключ.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp    
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ, используемый для поиска элемента. Тип `key` является именем типа *K*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если ключ найден; в противном случае — значение `false`.  
  


## <a name="lookup"></a>  Метод UnorderedMapView::Lookup
Возвращает значение типа V, связанное с указанным ключом типа K.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ, используемый для поиска элемента в объекте UnorderedMapView. Тип `key` является именем типа *K*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, связанное с ключом `key`. Тип возвращаемого значения является именем типа *V*.  
  


## <a name="size"></a>  Метод UnorderedMapView::Size
Возвращает количество [Windows::Foundation::Collections::IKeyValuePair\<K, V >](https://msdn.microsoft.com/library/windows/apps/br226031.aspx) элементов в UnorderedMapView.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов в Unordered MapView.  
  


## <a name="split"></a>  Метод UnorderedMapView::Split
Разделяет текущий объект UnorderedMapView на два объекта UnorderedMapView. Этот метод не выполняет никаких действий.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,V>^ * secondPartition);  
```  
  
### <a name="parameters"></a>Параметры  
 `firstPartition`  
 Первая часть исходного объекта UnorderedMapView.  
  
 `secondPartition`  
 Вторая часть исходного объекта UnorderedMapView.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняет никаких действий.  
  


## <a name="ctor"></a>  Конструктор UnorderedMapView::UnorderedMapView
Инициализирует новый экземпляр класса UnorderedMapView.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
UnorderedMapView();    
explicit UnorderedMapView(size_t n);   
UnorderedMapView(size_t n, const H& h);   
UnorderedMapView(size_t n, const H& h, const P& p);  
  
explicit UnorderedMapView(  
    const std::unordered_map<K, V, H, P>& m);  
explicit UnorderedMapView(  
    std::unordered_map<K, V, H, P>&& m);  
  
template <typename InIt> UnorderedMapView(InIt first, InIt last );  
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h,  
    const P& p );  
  
UnorderedMapView(std::initializer_list<std::pair<const K, V>);  
  
UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n   
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h);  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h,  
    const P& p );  
```  
  
### <a name="parameters"></a>Параметры  
 n  
 Число элементов, для которых необходимо заранее выделить пространство.  
  
 `InIt`  
 Имя типа UnorderedMapView.  
  
 `H`  
 Объект функции, который может создать хэш-значение для ключа. По умолчанию используется [std::hash\<K >](https://msdn.microsoft.com/54f67435-af9d-4217-a29d-fa4d2491a104) для типов, `std::hash` поддерживает.  
  
 `P`  
 Тип, предоставляющий объект функции, который может сравнивать два ключа с целью установления их равенства. По умолчанию используется [std::equal_to\<K >](../standard-library/equal-to-struct.md).  
  
 `m`  
 Ссылка или [значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для [std::unordered_map](../standard-library/unordered-map-class.md) , используемый для инициализации UnorderedMapView.  
  
 `first`  
 Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации UnorderedMapView.  
  
 `last`  
 Итератор ввода первого элемента после диапазона элементов, используемый для инициализации UnorderedMapView.  
   
## <a name="see-also"></a>См. также  
 [Пространство имен Platform::Collections](../cppcx/platform-collections-namespace.md)   
 [Windows::Foundation::IMapView](http://go.microsoft.com/fwlink/p/?LinkId=262409)