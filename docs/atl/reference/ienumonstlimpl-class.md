---
title: Класс IEnumOnSTLImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f2e448d5fa73c64e9abb66ef70e513bc9fa0728
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759250"
---
# <a name="ienumonstlimpl-class"></a>Класс IEnumOnSTLImpl

Этот класс определяет перечислитель интерфейс на основе коллекции стандартной библиотеки C++.

## <a name="syntax"></a>Синтаксис

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>  
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>Параметры

*Base*  
COM-перечислитель. См. в разделе [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) пример.

*piid*  
Указатель на идентификатор интерфейса интерфейса перечислителя.

*T*  
Тип элемента, доступные в интерфейсе перечислителя.

*Копировать*  
Объект [скопируйте класс политики](../../atl/atl-copy-policy-classes.md).

*CollType*  
Класс контейнера стандартной библиотеки C++.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IEnumOnSTLImpl::Clone](#clone)|Реализация **клона**.|
|[IEnumOnSTLImpl::Init](#init)|Инициализирует перечислитель.|
|[IEnumOnSTLImpl::Next](#next)|Реализация **Далее**.|
|[IEnumOnSTLImpl::Reset](#reset)|Реализация **сбросить**.|
|[IEnumOnSTLImpl::Skip](#skip)|Реализация **Skip**.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[IEnumOnSTLImpl::m_iter](#m_iter)|Итератор, который представляет текущей позиции перечислителя в коллекции.|
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|Указатель на контейнера стандартной библиотеки C++, содержащего элементы, которые необходимо перечислить.|
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|`IUnknown` Указатель объекта, указав в коллекцию.|

## <a name="remarks"></a>Примечания

`IEnumOnSTLImpl` предоставляет реализацию для интерфейса перечислителя COM, где перечисляемые элементы хранятся в контейнере совместимые библиотеки C++ Standard. Этот класс является аналогом [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) класс, который предоставляет реализацию для интерфейса перечислителя на основе массива.

> [!NOTE]
>  См. в разделе [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) Дополнительные сведения о дальнейшей различия между `CComEnumImpl` и `IEnumOnSTLImpl`.

Как правило, вы будете *не* нужно создать свой собственный класс перечислителя путем наследования от реализации этого интерфейса. Если вы хотите использовать перечислитель предоставляемую ATL, основанное на контейнере стандартной библиотеки C++, очень часто для создания экземпляра [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), или для создания класса коллекции, который возвращает перечислитель, путем наследования от [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).

Тем не менее если требуется для предоставления пользовательского перечислителя (например, по одному, предоставляет интерфейсы, а также интерфейс перечислителя), могут наследовать этот класс. В этом случае вполне вероятно, что вам потребуется переопределить [клона](#clone) метод, чтобы предоставить свою собственную реализацию.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="init"></a>  IEnumOnSTLImpl::Init

Инициализирует перечислитель.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>Параметры

*pUnkForRelease*  
[in] `IUnknown` Указатель на объект, который должен поддерживаться в течение времени существования перечислителя. Передайте значение NULL, если объект не существует.

*коллекция*  
Ссылка на контейнер стандартной библиотеки C++, который содержит элементы, которые необходимо перечислить.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если передать `Init` ссылку на коллекцию, хранящиеся в другом объекте, можно использовать *pUnkForRelease* параметр убедитесь, что объект, а также коллекцию, он удерживает, доступных для до тех пор, пока она нужна перечислитель.

Этот метод необходимо вызвать перед тем как передать указатель на интерфейс перечисления любой клиентам.

##  <a name="clone"></a>  IEnumOnSTLImpl::Clone

Этот метод предоставляет реализацию **клона** метод путем создания объекта типа `CComEnumOnSTL`, инициализировав его с одной и той же коллекции и итератор, используемый текущим объектом и возврат интерфейса на вновь созданный объект.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Параметры

*ppEnum*  
[out] Интерфейс перечислителя для вновь созданного объекта, клонированный из текущего перечислителя.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="m_spunk"></a>  IEnumOnSTLImpl::m_spUnk

`IUnknown` Указатель объекта, указав в коллекцию.

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>Примечания

Этого интеллектуального указателя содержит ссылку на объект, передаваемый в [IEnumOnSTLImpl::Init](#init), гарантируя, что он остается активным в течение времени существования перечислителя.

##  <a name="m_pcollection"></a>  IEnumOnSTLImpl::m_pcollection

Этот элемент указывает на коллекцию, которая выдает данные, представленные реализацию интерфейса перечислителя.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>Примечания

Этот член инициализируется путем вызова [IEnumOnSTLImpl::Init](#init).

##  <a name="m_iter"></a>  IEnumOnSTLImpl::m_iter

Этот элемент содержит итератор, который используется для маркировки текущую позицию в коллекции и перехода на последующие элементы.

```
CollType::iterator m_iter;
```

##  <a name="next"></a>  IEnumOnSTLImpl::Next

Этот метод предоставляет реализацию **Далее** метод.

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>Параметры

*celt*  
[in] Количество запрошенных элементов.

*rgelt*  
[out] Массив, заполненный элементы.

*pceltFetched*  
[out] Число элементов, фактически возвращенных в *rgelt*. Это может быть меньше, чем *celt* если меньше, чем *celt* элементы остаются в списке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="reset"></a>  IEnumOnSTLImpl::Reset

Этот метод предоставляет реализацию **Сброс** метод.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="skip"></a>  IEnumOnSTLImpl::Skip

Этот метод предоставляет реализацию **Skip** метод.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Параметры

*celt*  
[in] Количество пропускаемых элементов.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
