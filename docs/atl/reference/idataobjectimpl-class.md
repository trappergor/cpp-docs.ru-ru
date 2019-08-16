---
title: Класс Идатаобжектимпл
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
ms.openlocfilehash: 8e3369edd0731ede0892a405ef3de4e7b4cfdef1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495944"
---
# <a name="idataobjectimpl-class"></a>Класс Идатаобжектимпл

Этот класс предоставляет методы для поддержки универсальных Передача данных и управления соединениями.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IDataObjectImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Идатаобжектимпл::D advise](#dadvise)|Устанавливает соединение между объектом данных и приемником уведомлений. Это позволяет приемнику уведомлений получать уведомления об изменениях в объекте.|
|[Идатаобжектимпл::D unadvise](#dunadvise)|Завершает соединение, установленное ранее с `DAdvise`помощью.|
|[Идатаобжектимпл:: Енумдадвисе](#enumdadvise)|Создает перечислитель для прохода по текущим вспомогательным соединениям.|
|[Идатаобжектимпл:: Енумформатетк](#enumformatetc)|Создает перечислитель для прохода по `FORMATETC` структурам, поддерживаемым объектом данных. Реализация ATL возвращает значение E_NOTIMPL.|
|[Идатаобжектимпл:: Фиредатачанже](#firedatachange)|Отправляет уведомление об изменении обратно в каждый приемник уведомлений.|
|[Идатаобжектимпл:: Жетканоникалформатетк](#getcanonicalformatetc)|Извлекает логически эквивалентную `FORMATETC` структуру более сложной. Реализация ATL возвращает значение E_NOTIMPL.|
|[Идатаобжектимпл:: GetData](#getdata)|Передает данные из объекта данных клиенту. Данные описываются в `FORMATETC` структуре и передаются `STGMEDIUM` через структуру.|
|[Идатаобжектимпл:: Жетдатахере](#getdatahere)|Аналогично `STGMEDIUM` , за исключением того, что клиент должен выделить структуру. `GetData` Реализация ATL возвращает значение E_NOTIMPL.|
|[Идатаобжектимпл:: Куерижетдата](#querygetdata)|Определяет, поддерживает ли объект данных определенную `FORMATETC` структуру для передачи данных. Реализация ATL возвращает значение E_NOTIMPL.|
|[Идатаобжектимпл:: SetData](#setdata)|Передает данные из клиента в объект данных. Реализация ATL возвращает значение E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Интерфейс [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) предоставляет методы для поддержки однородных передача данных. `IDataObject`использует стандартные структуры формата [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) и [стгмедиум](/windows/win32/api/objidl/ns-objidl-stgmedium) для получения и хранения данных.

`IDataObject`также управляет подключениями к приемникам уведомлений, которые обрабатывали уведомления об изменении данных. Чтобы клиент получал уведомления об изменении данных из объекта данных, клиент должен реализовать интерфейс [иадвисесинк](/windows/win32/api/objidl/nn-objidl-iadvisesink) для объекта, который называется приемником уведомлений. Когда клиент вызывает `IDataObject::DAdvise`, устанавливается соединение между объектом данных и приемником уведомлений.

Класс `IDataObjectImpl` `IUnknown` предоставляет`IDataObject` реализацию по умолчанию и реализует, отправляя сведения в устройство дампа в отладочных сборках.

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="dadvise"></a>Идатаобжектимпл::D advise

Устанавливает соединение между объектом данных и приемником уведомлений.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Примечания

Это позволяет приемнику уведомлений получать уведомления об изменениях в объекте.

Чтобы завершить подключение, вызовите [дунадвисе](#dunadvise).

См. раздел [IDataObject::D advise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) в Windows SDK.

##  <a name="dunadvise"></a>Идатаобжектимпл::D unadvise

Прерывает подключение, установленное ранее с помощью [дадвисе](#dadvise).

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>Примечания

См. раздел [IDataObject::D unadvise](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) в Windows SDK.

##  <a name="enumdadvise"></a>Идатаобжектимпл:: Енумдадвисе

Создает перечислитель для прохода по текущим вспомогательным соединениям.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Примечания

См. раздел [IDataObject:: енумдадвисе](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise) в Windows SDK.

##  <a name="enumformatetc"></a>Идатаобжектимпл:: Енумформатетк

Создает перечислитель для прохода по `FORMATETC` структурам, поддерживаемым объектом данных.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>Примечания

См. раздел [IDataObject:: енумформатетк](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

##  <a name="firedatachange"></a>Идатаобжектимпл:: Фиредатачанже

Отправляет уведомление об изменении в каждый приемник уведомлений, управляемый в данный момент.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="getcanonicalformatetc"></a>Идатаобжектимпл:: Жетканоникалформатетк

Извлекает логически эквивалентную `FORMATETC` структуру более сложной.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [IDataObject:: жетканоникалформатетк](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) в Windows SDK.

##  <a name="getdata"></a>Идатаобжектимпл:: GetData

Передает данные из объекта данных клиенту.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>Примечания

Параметр *пформатетЦин* должен указывать тип среды хранения TYMED_MFPICT.

См. раздел [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в Windows SDK.

##  <a name="getdatahere"></a>Идатаобжектимпл:: Жетдатахере

Аналогично `STGMEDIUM` , за исключением того, что клиент должен выделить структуру. `GetData`

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [IDataObject:: жетдатахере](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere) в Windows SDK.

##  <a name="querygetdata"></a>Идатаобжектимпл:: Куерижетдата

Определяет, поддерживает ли объект данных определенную `FORMATETC` структуру для передачи данных.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [IDataObject:: куерижетдата](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) в Windows SDK.

##  <a name="setdata"></a>Идатаобжектимпл:: SetData

Передает данные из клиента в объект данных.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [IDataObject:: SetData](/windows/win32/api/objidl/nf-objidl-idataobject-setdata) в Windows SDK.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
