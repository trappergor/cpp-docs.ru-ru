---
title: IDataObjectImpl класс
ms.date: 11/04/2016
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
ms.openlocfilehash: 618f8248a03297120ae2504bcb30ba8f080b184d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329842"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl класс

Этот класс предоставляет методы поддержки единообразной передачи данных и управления соединениями.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IDataObjectImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IDataObjectImpl::DAdvise](#dadvise)|Устанавливает связь между объектом данных и раковиной рекомендации. Это позволяет advise sink получать уведомления об изменениях в объекте.|
|[IDataObjectImpl::DНесовет](#dunadvise)|Прекращает подключение, ранее `DAdvise`установленное через .|
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Создает перечислитель для итерации по текущим вспомогательным соединениям.|
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Создает перечислитель для итерации по структурам `FORMATETC`, поддерживаемым объектом данных. Реализация ATL возвращает E_NOTIMPL.|
|[IDataObjectImpl::FireDataChange](#firedatachange)|Отправляет уведомление об изменении обратно к каждому совету раковине.|
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Извлекает логически эквивалентную `FORMATETC` структуру более сложной. Реализация ATL возвращает E_NOTIMPL.|
|[IDataObjectImpl::GetData](#getdata)|Передает данные из объекта данных клиенту. Данные описываются `FORMATETC` в структуре и `STGMEDIUM` передаются через структуру.|
|[IDataObjectImpl::GetDataHere](#getdatahere)|`GetData`Подобно, кроме клиента должна `STGMEDIUM` выделить структуру. Реализация ATL возвращает E_NOTIMPL.|
|[IDataObjectImpl::QueryGetData](#querygetdata)|Определяет, поддерживает ли объект данных указанную структуру `FORMATETC` для передачи данных. Реализация ATL возвращает E_NOTIMPL.|
|[IDataObjectImpl::SetData](#setdata)|Передает данные от клиента в объект данных. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Remarks

Интерфейс [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) предоставляет методы поддержки единообразной передачи данных. `IDataObject`использует стандартные структуры [формата FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) и [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) для извлечения и хранения данных.

`IDataObject`также управляет соединениями для консультирования раковин для обработки уведомлений об изменении данных. Для того, чтобы клиент получил уведомления об изменении данных от объекта данных, клиент должен реализовать интерфейс [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) на объекте, называемом раковиной рекомендаций. Когда клиент звонит, `IDataObject::DAdvise`устанавливается соединение между объектом данных и раковиной advise.

Класс `IDataObjectImpl` обеспечивает реализацию `IDataObject` и реализацию `IUnknown` по умолчанию, отправляя информацию на устройство сброса в сборках отладок.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="idataobjectimpldadvise"></a><a name="dadvise"></a>IDataObjectImpl::DAdvise

Устанавливает связь между объектом данных и раковиной рекомендации.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Remarks

Это позволяет advise sink получать уведомления об изменениях в объекте.

Чтобы прекратить подключение, позвоните [в DUnadvise](#dunadvise).

Смотрите [IDataObject::DAdvise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) в Windows SDK.

## <a name="idataobjectimpldunadvise"></a><a name="dunadvise"></a>IDataObjectImpl::DНесовет

Прекращает подключение, ранее установленное через [DAdvise.](#dadvise)

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>Remarks

Смотрите [IDataObject::DНесоветчив](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) в Windows SDK.

## <a name="idataobjectimplenumdadvise"></a><a name="enumdadvise"></a>IDataObjectImpl::EnumDAdvise

Создает перечислитель для итерации по текущим вспомогательным соединениям.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Remarks

Смотрите [IDataObject::EnumDAdvise](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise) в Windows SDK.

## <a name="idataobjectimplenumformatetc"></a><a name="enumformatetc"></a>IDataObjectImpl::EnumFormatEtc

Создает перечислитель для итерации по структурам `FORMATETC`, поддерживаемым объектом данных.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>Remarks

Смотрите [IDataObject::EnumFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

## <a name="idataobjectimplfiredatachange"></a><a name="firedatachange"></a>IDataObjectImpl::FireDataChange

Отправляет уведомление об изменении обратно к каждому совету раковине, которая в настоящее время управляется.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="idataobjectimplgetcanonicalformatetc"></a><a name="getcanonicalformatetc"></a>IDataObjectImpl::GetCanonicalFormatEtc

Извлекает логически эквивалентную `FORMATETC` структуру более сложной.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Смотрите [IDataObject::GetCanonicalFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) в Windows SDK.

## <a name="idataobjectimplgetdata"></a><a name="getdata"></a>IDataObjectImpl::GetData

Передает данные из объекта данных клиенту.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>Remarks

Параметр *pformatetcIn* должен указывать средний тип TYMED_MFPICT.

Смотрите [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в Windows SDK.

## <a name="idataobjectimplgetdatahere"></a><a name="getdatahere"></a>IDataObjectImpl::GetDataHere

`GetData`Подобно, кроме клиента должна `STGMEDIUM` выделить структуру.

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Смотрите [IDataObject::GetDataHere](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere) в Windows SDK.

## <a name="idataobjectimplquerygetdata"></a><a name="querygetdata"></a>IDataObjectImpl::QueryGetData

Определяет, поддерживает ли объект данных указанную структуру `FORMATETC` для передачи данных.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Смотрите [IDataObject::QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) в SDK Windows.

## <a name="idataobjectimplsetdata"></a><a name="setdata"></a>IDataObjectImpl::SetData

Передает данные от клиента в объект данных.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Смотрите [IDataObject::SetData](/windows/win32/api/objidl/nf-objidl-idataobject-setdata) в SDK Windows.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
