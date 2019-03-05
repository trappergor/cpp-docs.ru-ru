---
title: Макросы сопоставления служб
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
ms.openlocfilehash: ab130b2401dc9885f82fd5668a2d722a96dd289b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290538"
---
# <a name="service-map-macros"></a>Макросы сопоставления служб

Эти макросы определяют схемы услуг и записи.

|||
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|Помечает начало ATL схемы услуги.|
|[END_SERVICE_MAP](#end_service_map)|Помечает конец ATL схемы услуги.|
|[SERVICE_ENTRY](#service_entry)|Указывает, что объект поддерживает с идентификатором конкретной службы.|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Указывает, что [IServiceProviderImpl::QueryService](#queryservice) цепочку в указанный объект.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="begin_service_map"></a>  BEGIN_SERVICE_MAP

Помечает начало схемы услуги.

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
[in] Указывает класс, содержащий схемы услуги.

### <a name="remarks"></a>Примечания

Используйте схемы услуги, чтобы реализовать функциональные возможности поставщика службы на COM-объект. Во-первых, должен быть производным от класса [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md). Существует два типа операций:

- [SERVICE_ENTRY](#service_entry) указывает поддержку для указанной службы идентификатора (SID).

- [SERVICE_ENTRY_CHAIN](#service_entry_chain) Instructs [IServiceProviderImpl::QueryService](#queryservice) цепь на другой, указанный объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

##  <a name="end_service_map"></a>  END_SERVICE_MAP

Помечает конец схемы услуги.

```
END_SERVICE_MAP()
```

### <a name="example"></a>Пример

См. в примере [BEGIN_SERVICE_MAP](#begin_service_map).

##  <a name="service_entry"></a>  SERVICE_ENTRY

Указывает, что объект поддерживает идентификатор службы, заданные *SID*.

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>Параметры

*ИД БЕЗОПАСНОСТИ*<br/>
Идентификатор службы.

### <a name="example"></a>Пример

См. в примере [BEGIN_SERVICE_MAP](#begin_service_map).

##  <a name="service_entry_chain"></a>  SERVICE_ENTRY_CHAIN

Указывает, что [IServiceProviderImpl::QueryService](#queryservice) в цепочке для объекта, заданного параметром *punk*.

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
Указатель на **IUnknown** интерфейс, к которому цепочки.

### <a name="example"></a>Пример

См. в примере [BEGIN_SERVICE_MAP](#begin_service_map).

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

[Макросы](../../atl/reference/atl-macros.md)
