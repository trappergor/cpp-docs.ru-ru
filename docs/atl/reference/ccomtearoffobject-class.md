---
title: Класс CComTearOffObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ecbf2b415b93526fe856e21411431eb1f20b4c42
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089584"
---
# <a name="ccomtearoffobject-class"></a>Класс CComTearOffObject

Этот класс реализует интерфейс перемещаемой.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Параметры

*Base*<br/>
Ваш перемещаемой класс, производный от `CComTearOffObjectBase` и интерфейсы объекта перемещаемой для поддержки.

ATL реализует его перемещаемые интерфейсы в два этапа — `CComTearOffObjectBase` методы обрабатывают счетчик ссылок и `QueryInterface`, хотя `CComTearOffObject` реализует [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Конструктор.|
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComTearOffObject::AddRef](#addref)|Увеличивает счетчик ссылок для `CComTearOffObject` объекта.|
|[CComTearOffObject::QueryInterface](#queryinterface)|Возвращает указатель на запрошенный интерфейс в классе перемещаемой или класс-владелец.|
|[CComTearOffObject::Release](#release)|Уменьшает счетчик ссылок для `CComTearOffObject` объекта и удаляет его.|

### <a name="ccomtearoffobjectbase-methods"></a>Методы CComTearOffObjectBase

|||
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Конструктор.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase данные-члены

|||
|-|-|
|[m_pOwner](#m_powner)|Указатель на `CComObject` производным от класса владельца.|

## <a name="remarks"></a>Примечания

`CComTearOffObject` реализует интерфейс перемещаемой как отдельный объект, экземпляр которого создается только в том случае, когда запрашиваются этот интерфейс. Перемещаемое удаляется, когда его счетчик становится равным нулю. Как правило можно создать интерфейс перемещаемой для интерфейса, который используется редко, так как с помощью перемещаемой сохраняет указатель vtable во всех экземплярах основного объекта.

Необходимо создать производный класс, реализующий перемещаемое из `CComTearOffObjectBase` и из любого интерфейсы должны объекта перемещаемой для поддержки. `CComTearOffObjectBase` шаблонизируется в классе владельца и потоковую модель. Класс-владелец является класс объекта, для которого перемещаемой реализуется. Если вы не укажете потоковую модель, модель потока по умолчанию будет использоваться.

Необходимо создать сопоставления COM для класса перемещаемой. Когда ATL создает экземпляр перемещаемой, он создаст `CComTearOffObject<CYourTearOffClass>` или `CComCachedTearOffObject<CYourTearOffClass>`.

Например, в Образец BEEPER `CBeeper2` класс является перемещаемой и `CBeeper` классом является класс владельца:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="addref"></a>  CComTearOffObject::AddRef

Увеличивает значение счетчика ссылок `CComTearOffObject` объекта на единицу.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

##  <a name="ccomtearoffobject"></a>  CComTearOffObject::CComTearOffObject

Конструктор.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
[in] Указатель, который будет преобразован в указатель на `CComObject<Owner>` объект.

### <a name="remarks"></a>Примечания

Увеличивает счетчик ссылок ее владельца на единицу.

##  <a name="dtor"></a>  CComTearOffObject:: ~ CComTearOffObject

Деструктор

```
~CComTearOffObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, вызывает модуль FinalRelease и уменьшает счетчик блокировки.

##  <a name="ccomtearoffobjectbase"></a>  CComTearOffObject::CComTearOffObjectBase

Конструктор.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Примечания

Инициализирует [m_pOwner](#m_powner) элемент NULL.

##  <a name="m_powner"></a>  CComTearOffObject::m_pOwner

Указатель на [CComObject](../../atl/reference/ccomobject-class.md) объект, производный от *владельца*.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Параметры

*Владелец*<br/>
[in] Класс, для которого перемещаемой реализуется.

### <a name="remarks"></a>Примечания

Указатель NULL инициализируется во время построения.

##  <a name="queryinterface"></a>  CComTearOffObject::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор IID интерфейса, запрашиваемый.

*ppvObject*<br/>
[out] Указатель на указатель интерфейса, идентифицируемый *iid*, или значение NULL, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Сначала запрашивает для интерфейсов в классе перемещаемой. Если интерфейс не установлен, запросы для интерфейса на объект владельца. Если запрошенный интерфейс `IUnknown`, возвращает `IUnknown` владельца.

##  <a name="release"></a>  CComTearOffObject::Release

Уменьшает счетчик ссылок на единицу и, если счетчик ссылок равен нулю, удаляет `CComTearOffObject`.

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Возвращаемое значение

В неотладочных сборках всегда возвращает ноль. В отладочных сборках возвращает значение, которое может быть полезно для диагностики или тестирования.

## <a name="see-also"></a>См. также

[Класс CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
