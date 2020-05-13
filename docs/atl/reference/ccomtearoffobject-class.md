---
title: Класс CComTearOffObject
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: de7528d3972991c233ee4b9037f609b89d0f7434
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327311"
---
# <a name="ccomtearoffobject-class"></a>Класс CComTearOffObject

Этот класс реализует отрывной интерфейс.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Параметры

*Базы*<br/>
Ваш класс отрыва, полученный из `CComTearOffObjectBase` интерфейсов, которые вы хотите, чтобы ваш объект отрыва в поддержку.

ATL реализует свои отрыва явные интерфейсы `CComTearOffObjectBase` в два этапа `QueryInterface`- `CComTearOffObject` методы обрабатывать подсчет ссылок и , в то время как реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComTearOffObject::CcomtearoffObject](#ccomtearoffobject)|Конструктор.|
|[CComTearOffObject:::CComTearoffObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComTearOffObject:AddRef](#addref)|Приращения отсчета `CComTearOffObject` ссылки на объект.|
|[CComTearOffObject::QueryInterface](#queryinterface)|Возвращает указатель на запрашиваемый интерфейс либо на класс отрыва, либо на класс владельца.|
|[CComTearOffObject::Release](#release)|Декретирует значение ссылки `CComTearOffObject` на объект и уничтожает его.|

### <a name="ccomtearoffobjectbase-methods"></a>Методы CComTearOffObjectBase

|||
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Конструктор.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase данных членов

|||
|-|-|
|[m_pOwner](#m_powner)|Указатель на `CComObject` производные от класса владельца.|

## <a name="remarks"></a>Remarks

`CComTearOffObject`реализует интерфейс отрыва в виде отдельного объекта, который мгновенно выполняется только тогда, когда этот интерфейс запрашивается. Разрыв удаляется, когда количество ссылок становится нулевым. Как правило, вы создаете интерфейс отрыва для интерфейса, который используется редко, так как использование отрыва сохраняет указатель vtable во всех экземплярах вашего основного объекта.

Вы должны получить класс реализации отрыва от `CComTearOffObjectBase` и от того, какие интерфейсы вы хотите, чтобы ваш объект отрыва для поддержки. `CComTearOffObjectBase`шаблонируется на классе владельца и модели потока. Класс владельца — это класс объекта, для которого осуществляется разрыв. Если не указано модель потока, используется модель потока по умолчанию.

Вы должны создать карту COM для вашего класса отрыва. Когда ATL мгновенно отрыв, он будет создавать `CComTearOffObject<CYourTearOffClass>` `CComCachedTearOffObject<CYourTearOffClass>`или .

Например, в образце BEEPER `CBeeper2` класс является классом `CBeeper` отрыва, а класс — классом владельца:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomtearoffobjectaddref"></a><a name="addref"></a>CComTearOffObject:AddRef

Приращения отсчета `CComTearOffObject` ссылки объекта по одному.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="ccomtearoffobject"></a>CComTearOffObject::CcomtearoffObject

Конструктор.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
(в) Указатель, который будет преобразован в `CComObject<Owner>` указатель на объект.

### <a name="remarks"></a>Remarks

Приращения счета ссылки владельца на один.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="dtor"></a>CComTearOffObject:::CComTearoffObject

Деструктор

```
~CComTearOffObject();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы, вызывает FinalRelease и высчитывает количество блокировки модуля.

## <a name="ccomtearoffobjectccomtearoffobjectbase"></a><a name="ccomtearoffobjectbase"></a>CComTearOffObject::CcomtearoffObjectBase

Конструктор.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Remarks

Инициализирует [m_pOwner](#m_powner) член NULL.

## <a name="ccomtearoffobjectm_powner"></a><a name="m_powner"></a>CComTearOffObject:::m_pOwner

Указатель на объект [CComObject,](../../atl/reference/ccomobject-class.md) полученный от *владельца.*

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Параметры

*Владелец*<br/>
(в) Класс, для которого осуществляется разрыв.

### <a name="remarks"></a>Remarks

Указатель инициализирован до NULL во время строительства.

## <a name="ccomtearoffobjectqueryinterface"></a><a name="queryinterface"></a>CComTearOffObject::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) IID запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *iid,* или NULL, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Запросы сначала для интерфейсов на вашем отрыв-офф класса. Если интерфейса нет, запросы для интерфейса на объекте владельца. Если запрашиваемый `IUnknown`интерфейс, `IUnknown` возвращает владельца.

## <a name="ccomtearoffobjectrelease"></a><a name="release"></a>CComTearOffObject::Release

Декретирует количество ссылок на один и, если количество `CComTearOffObject`ссылок равно нулю, удаляет .

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Возвращаемое значение

В неотлибуговых сборках всегда возвращается ноль. В сборках отладок возвращается значение, которое может быть полезно для диагностики или тестирования.

## <a name="see-also"></a>См. также раздел

[Класс CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
