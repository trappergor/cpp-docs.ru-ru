---
title: Класс IServiceProviderImpl
ms.date: 11/04/2016
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
ms.openlocfilehash: e52c28d528e187713d2d0925fed23bd8cd4493d5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298676"
---
# <a name="iserviceproviderimpl-class"></a>Класс IServiceProviderImpl

Этот класс предоставляет реализацию по умолчанию `IServiceProvider` интерфейс.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IServiceProviderImpl`.

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[IServiceProviderImpl::QueryService](#queryservice)|Создает или получает доступ к указанной службы и возвращает указатель интерфейса на указанный интерфейс для службы.|

## <a name="remarks"></a>Примечания

`IServiceProvider` Интерфейс находит службу, указанного по его идентификатору GUID и возвращает указатель интерфейса для запрошенного интерфейса в службе. Класс `IServiceProviderImpl` предоставляет стандартную реализацию этого интерфейса.

`IServiceProviderImpl` Указывает один из методов: [QueryService](#queryservice), который создает или получает доступ к указанной службы и возвращает указатель интерфейса на указанный интерфейс для службы.

`IServiceProviderImpl` использует схемы услуг, начиная с [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) и заканчивая [END_SERVICE_MAP](service-map-macros.md#end_service_map).

Схема услуги содержит две записи: [SERVICE_ENTRY](service-map-macros.md#service_entry), который указывает идентификатор указанной службы (SID), поддерживаемых этим объектом, и [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain), который вызывает `QueryService` цепочке с другим объектом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="queryservice"></a>  IServiceProviderImpl::QueryService

Создает или получает доступ к указанной службы и возвращает указатель интерфейса на указанный интерфейс для службы.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*guidService*<br/>
[in] Указатель на идентификатор службы (SID).

*riid*<br/>
[in] Идентификатор интерфейса, к которому вызывающий объект для получения доступа.

*ppvObj*<br/>
[out] Косвенный указатель на запрашиваемый интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение HRESULT является одним из следующих:

|Возвращаемое значение|Значение|
|------------------|-------------|
|S_OK|Служба успешно создана или извлечь.|
|E_INVALIDARG|Один или несколько аргументов являются недопустимыми.|
|E_OUTOFMEMORY|Не хватает памяти для создания службы.|
|E_UNEXPECTED|Произошла неизвестная ошибка.|
|E_NOINTERFACE|Запрошенный интерфейс не является частью этой службы или службы неизвестно.|

### <a name="remarks"></a>Примечания

`QueryService` Возвращает косвенный указатель на запрошенный интерфейс в указанную службу. Вызывающий объект несет ответственность за освобождение этого указателя, когда он больше не требуется.

При вызове `QueryService`, передайте идентификатор службы (*guidService*) и идентификатор интерфейса (*riid*). *GuidService* указывает службу, к которому вы хотите получить доступ, и *riid* определяет интерфейс, который является частью службы. В ответ вы получите косвенный указатель на интерфейс.

Объект, реализующий интерфейс может также реализовывать интерфейсы, которые являются частью других служб. Рассмотрим следующий пример.

- Некоторые из этих интерфейсов может быть необязательным. Не все интерфейсы, определенные в описании службы всегда присутствуют в каждой реализации службы или на каждый возвращаемый объект.

- В отличие от вызовов `QueryInterface`, передав идентификатор другой службе не обязательно означает, что возвращается объект компонента объекта модели (COM).

- Возвращаемый объект может иметь дополнительные интерфейсы, которые не являются частью определения службы.

Два различных служб, таких как SID_SMyService и SID_SYourService, можно оба указывают на использование один и тот же интерфейс, несмотря на то, что реализация интерфейса может иметь ничего общего между двумя службами. Это работает, так как вызов `QueryService` (SID_SMyService, IID_IDispatch) могут возвращать объектом, отличным от `QueryService` (SID_SYourService, IID_IDispatch). Удостоверение объекта не подразумевается при указании идентификатора разные службы.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
