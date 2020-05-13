---
title: СервисКарта Макрос
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
ms.openlocfilehash: eb2fe41c79135a7ac2ced9bc3242b070170716b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325943"
---
# <a name="service-map-macros"></a>СервисКарта Макрос

Эти макросы определяют карты служб и записи.

|||
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|Отмечает начало карты обслуживания ATL.|
|[END_SERVICE_MAP](#end_service_map)|Отметка окончания карты обслуживания ATL.|
|[SERVICE_ENTRY](#service_entry)|Означает, что объект поддерживает определенный идентификатор службы.|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Инструктирует [IServiceProviderImpl::QueryService](#queryservice) цепочку к указанному объекту.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="begin_service_map"></a><a name="begin_service_map"></a>BEGIN_SERVICE_MAP

Отмечает начало карты обслуживания.

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
(в) Опображаем класс, содержащий карту обслуживания.

### <a name="remarks"></a>Remarks

Используйте карту обслуживания для реализации функциональности поставщика услуг на объекте COM. Во-первых, вы должны получить свой класс от [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md). Существует два типа записей:

- [SERVICE_ENTRY](#service_entry)   Указывает поддержку указанного идентификатора обслуживания (SID).

- [SERVICE_ENTRY_CHAIN](#service_entry_chain)   Инструктирует [IServiceProviderImpl::QueryService](#queryservice) приковать цепь к другому указанному объекту.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

## <a name="end_service_map"></a><a name="end_service_map"></a>END_SERVICE_MAP

Отметка конца карты обслуживания.

```
END_SERVICE_MAP()
```

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_SERVICE_MAP](#begin_service_map).

## <a name="service_entry"></a><a name="service_entry"></a>SERVICE_ENTRY

Означает, что объект поддерживает идентификатор службы, указанный *SID.*

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>Параметры

*Sid*<br/>
Идентификатор службы.

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_SERVICE_MAP](#begin_service_map).

## <a name="service_entry_chain"></a><a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN

Инструктирует [IServiceProviderImpl::QueryService](#queryservice) приковать к объекту, указанному *панком.*

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
Указатель на интерфейс **IUnknown,** к которому цепочка.

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_SERVICE_MAP](#begin_service_map).

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a>IServiceProviderImpl:::КвиСервис

Создает или получает доступ к указанной службе и возвращает указатель интерфейса в указанный интерфейс службы.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*guidService*<br/>
(в) Указатель на идентификатор службы (SID).

*riid*<br/>
(в) Идентификатор интерфейса, к которому абонент должен получить доступ.

*ppvObj*<br/>
(ваут) Косвенный указатель на запрашиваемый интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращается значение HRESULT является одним из следующих:

|Возвращаемое значение|Значение|
|------------------|-------------|
|S_OK|Служба была успешно создана или извлечена.|
|E_INVALIDARG|Один или несколько аргументов являются недопустимыми.|
|E_OUTOFMEMORY|Памяти недостаточно для создания службы.|
|E_UNEXPECTED|Произошла неизвестная ошибка.|
|E_NOINTERFACE|Запрашиваемый интерфейс не является частью этой службы, или служба неизвестна.|

### <a name="remarks"></a>Remarks

`QueryService`возвращает непрямой указатель на запрашиваемый интерфейс в указанной службе. Звонящее отвечает за освобождение этого указателя, когда он больше не требуется.

При звонке `QueryService`вы проходите как идентификатор службы *(guidService),* так и идентификатор интерфейса *(riid).* *Служба guidService* определяет службу, к которой вы хотите получить доступ, а *риид* определяет интерфейс, который является частью службы. Взамен вы получаете непрямой указатель на интерфейс.

Объект, реализуемый в интерфейсе, может также реализовать интерфейсы, которые являются частью других служб. Рассмотрим следующее:

- Некоторые из этих интерфейсов могут быть необязательными. Не все интерфейсы, определенные в описании службы, обязательно присутствуют на каждой реализации службы или на каждом возвращенном объекте.

- В отличие `QueryInterface`от вызовов, передача другого идентификатора службы не обязательно означает, что возвращается другой объект компонентной модели (COM).

- Возвращаемый объект может иметь дополнительные интерфейсы, которые не являются частью определения службы.

Две разные службы, такие как SID_SMyService и SID_SYourService, могут указать использование одного и того же интерфейса, даже если реализация интерфейса может не иметь ничего общего между этими двумя службами. Это работает, потому `QueryService` что вызов (SID_SMyService, IID_IDispatch) `QueryService` может вернуть другой объект, чем (SID_SYourService, IID_IDispatch). Идентификация объекта не предполагается при указании другого идентификатора службы.

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
