---
title: Класс ICollectionOnSTLImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
dev_langs:
- C++
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6bbfb34d34f6bd920744621042f5f3e09143e896
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751323"
---
# <a name="icollectiononstlimpl-class"></a>Класс ICollectionOnSTLImpl

Этот класс предоставляет методы, используемые классом коллекции.

## <a name="syntax"></a>Синтаксис

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>  
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>Параметры

*T*  
COM-интерфейс коллекции.

*CollType*  
Класс контейнера стандартной библиотеки C++.

*ItemType*  
Тип элемента, предоставляемых интерфейсом контейнера.

*CopyItem*  
Объект [скопируйте класс политики](../../atl/atl-copy-policy-classes.md).

*EnumType*  
Объект [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)-класс совместимой перечислителя.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ICollectionOnSTLImpl::get__NewEnum](#newenum)|Возвращает объект перечислителя для коллекции.|
|[ICollectionOnSTLImpl::getcount](#get_count)|Возвращает количество элементов в коллекции.|
|[ICollectionOnSTLImpl::get_Item](#get_item)|Возвращает запрашиваемый элемент из коллекции.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ICollectionOnSTLImpl::m_coll](#m_coll)|Коллекция.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет реализацию для трех методов интерфейса коллекции: [getcount](#get_count), [get_Item](#get_item), и [метод get__NewEnum](#newenum).

Чтобы использовать этот класс:

- Определить (или заимствуйте), которую необходимо реализовать интерфейс коллекций.

- Создайте класс, производный от специализации `ICollectionOnSTLImpl` на основе интерфейса этой коллекции.

- Используйте производный класс для реализации методы из интерфейса коллекции, не обрабатываются `ICollectionOnSTLImpl`.

> [!NOTE]
>  Если интерфейс коллекции сдвоенный интерфейс, являются производными от класса [IDispatchImpl](../../atl/reference/idispatchimpl-class.md), передав `ICollectionOnSTLImpl` специализации как первый параметр шаблона, если вы хотите ATL для реализации метода `IDispatch` методы.

- Добавить элементы в [m_coll](#m_coll) член для заполнения коллекции.

Дополнительные сведения и примеры см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="get_count"></a>  ICollectionOnSTLImpl::getcount

Этот метод возвращает число элементов в коллекции.

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>Параметры

*pcount*  
[out] Число элементов в коллекции.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="get_item"></a>  ICollectionOnSTLImpl::get_Item

Этот метод возвращает указанный элемент из коллекции.

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>Параметры

*Index*  
[in] Отсчитываемый от единицы индекс элемента в коллекции.

*pvar*  
[out] Элемент, соответствующий параметру *индекс*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Элемент получается путем копирования данных в указанной позиции в [m_coll](#m_coll) метод копирования [скопируйте класс политики](../../atl/atl-copy-policy-classes.md) передается как аргумент шаблона в `ICollectionOnSTLImpl` специализации.

##  <a name="newenum"></a>  ICollectionOnSTLImpl::get__NewEnum

Возвращает объект перечислителя для коллекции.

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>Параметры

*ppUnk*  
[out] **IUnknown** указатель объекта только что созданный перечислитель.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Итератор, указывающий на исходной коллекции, поддерживает только что созданный перечислитель `m_coll`, (поэтому копия не создается) и сохраняет ссылку COM в объекте коллекции, чтобы убедиться, что коллекция остается активным, несмотря на наличие ожидающих перечислителей.

##  <a name="m_coll"></a>  ICollectionOnSTLImpl::m_coll

Этот элемент содержит элементов, представленных в коллекции.

```
CollType m_coll;
```

## <a name="see-also"></a>См. также

[Пример ATLCollections](../../visual-cpp-samples.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
