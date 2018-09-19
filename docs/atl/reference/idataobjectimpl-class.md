---
title: Класс IDataObjectImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7444cfe152d964318ea9786f4e4f7718e11d71cb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069811"
---
# <a name="idataobjectimpl-class"></a>Класс IDataObjectImpl

Этот класс предоставляет методы для поддержки унифицированная передача данных и управление подключениями.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IDataObjectImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IDataObjectImpl::DAdvise](#dadvise)|Устанавливает соединение между объектом данных и приемника уведомлений. Это позволяет в приемник получать уведомления об изменениях в объекте.|
|[IDataObjectImpl::DUnadvise](#dunadvise)|Завершает соединение, установленное ранее при помощи `DAdvise`.|
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Создает перечислитель для итерации по текущим вспомогательным соединениям.|
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Создает перечислитель для перебора `FORMATETC` структуры, поддерживаемые объектом данных. Реализация ATL возвращает E_NOTIMPL.|
|[IDataObjectImpl::FireDataChange](#firedatachange)|Отправляет уведомление об изменениях каждый приемник.|
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Извлекает логически эквивалентного `FORMATETC` структуры, который является более сложным. Реализация ATL возвращает E_NOTIMPL.|
|[IDataObjectImpl::GetData](#getdata)|Передает данные из объекта данных клиенту. Данные описываются в `FORMATETC` структурировать и передается через `STGMEDIUM` структуры.|
|[IDataObjectImpl::GetDataHere](#getdatahere)|Аналогичную `GetData`, за исключением, что клиент должен выделить `STGMEDIUM` структуры. Реализация ATL возвращает E_NOTIMPL.|
|[IDataObjectImpl::QueryGetData](#querygetdata)|Определяет, поддерживает ли объект данных определенного `FORMATETC` структуры для передачи данных. Реализация ATL возвращает E_NOTIMPL.|
|[IDataObjectImpl::SetData](#setdata)|Передает данные от клиента к объекту данных. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Примечания

[IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) интерфейс предоставляет методы для поддержки унифицированная передача данных. `IDataObject` использует стандартный формат структуры [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) и [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) для получения и хранения данных.

`IDataObject` также управляет соединениями с вспомогательными приемникам обрабатывать уведомления об изменении данных. Чтобы клиенту получать уведомления об изменении данных из объекта данных, должен реализовать клиент, [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) интерфейса на объект с именем приемника уведомлений. Когда клиент вызывает метод `IDataObject::DAdvise`, установить соединение между объектом данных и приемником уведомлений.

Класс `IDataObjectImpl` предоставляет реализацию по умолчанию `IDataObject` и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="dadvise"></a>  IDataObjectImpl::DAdvise

Устанавливает соединение между объектом данных и приемника уведомлений.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Примечания

Это позволяет в приемник получать уведомления об изменениях в объекте.

Чтобы разорвать соединение, вызовите [DUnadvise](#dunadvise).

См. в разделе [IDataObject::DAdvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dadvise) в Windows SDK.

##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise

Завершает соединение, установленное ранее при помощи [DAdvise](#dadvise).

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>Примечания

См. в разделе [IDataObject::DUnadvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dunadvise) в Windows SDK.

##  <a name="enumdadvise"></a>  IDataObjectImpl::EnumDAdvise

Создает перечислитель для итерации по текущим вспомогательным соединениям.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Примечания

См. в разделе [IDataObject::EnumDAdvise](/windows/desktop/api/objidl/nf-objidl-idataobject-enumdadvise) в Windows SDK.

##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc

Создает перечислитель для перебора `FORMATETC` структуры, поддерживаемые объектом данных.

```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>Примечания

См. в разделе [IDataObject::EnumFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-enumformatetc) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange

Отправляет уведомление об изменениях каждый приемник, управляемого в данный момент выполняется.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc

Извлекает логически эквивалентного `FORMATETC` структуры, который является более сложным.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. в разделе [IDataObject::GetCanonicalFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) в Windows SDK.

##  <a name="getdata"></a>  IDataObjectImpl::GetData

Передает данные из объекта данных клиенту.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>Примечания

*PformatetcIn* параметра необходимо указать тип среды хранения TYMED_MFPICT.

См. в разделе [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) в Windows SDK.

##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere

Аналогичную `GetData`, за исключением, что клиент должен выделить `STGMEDIUM` структуры.

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. в разделе [IDataObject::GetDataHere](/windows/desktop/api/objidl/nf-objidl-idataobject-getdatahere) в Windows SDK.

##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData

Определяет, поддерживает ли объект данных определенного `FORMATETC` структуры для передачи данных.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. в разделе [IDataObject::QueryGetData](/windows/desktop/api/objidl/nf-objidl-idataobject-querygetdata) в Windows SDK.

##  <a name="setdata"></a>  IDataObjectImpl::SetData

Передает данные от клиента к объекту данных.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. в разделе [IDataObject::SetData](/windows/desktop/api/objidl/nf-objidl-idataobject-setdata) в Windows SDK.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
