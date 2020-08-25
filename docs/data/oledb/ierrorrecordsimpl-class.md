---
title: Класс IErrorRecordsImpl
ms.date: 11/04/2016
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
- GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpContext
- IErrorRecordsImpl.GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpFile
- GetErrorHelpFile
- IErrorRecordsImpl.GetErrorHelpFile
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
- IErrorRecordsImpl.AddErrorRecord
- AddErrorRecord
- IErrorRecordsImpl::AddErrorRecord
- ATL::IErrorRecordsImpl::GetBasicErrorInfo
- IErrorRecordsImpl::GetBasicErrorInfo
- GetBasicErrorInfo
- ATL.IErrorRecordsImpl.GetBasicErrorInfo
- IErrorRecordsImpl.GetBasicErrorInfo
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetErrorInfo
- IErrorRecordsImpl::GetErrorInfo
- IErrorRecordsImpl::GetErrorParameters
- ATL.IErrorRecordsImpl.GetErrorParameters
- IErrorRecordsImpl.GetErrorParameters
- GetErrorParameters
- ATL::IErrorRecordsImpl::GetErrorParameters
- IErrorRecordsImpl::GetRecordCount
- ATL::IErrorRecordsImpl::GetRecordCount
- IErrorRecordsImpl.GetRecordCount
- ATL.IErrorRecordsImpl.GetRecordCount
- IErrorRecordsImpl::m_rgErrors
- IErrorRecordsImpl.m_rgErrors
- ATL.IErrorRecordsImpl.m_rgErrors
- m_rgErrors
- ATL::IErrorRecordsImpl::m_rgErrors
helpviewer_keywords:
- IErrorRecordsImpl class
- GetErrorDescriptionString method
- GetErrorGUID method
- GetErrorHelpContext method
- GetErrorHelpFile method
- GetErrorSource method
- AddErrorRecord method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetRecordCount method
- m_rgErrors
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
ms.openlocfilehash: 189f97e72f1cb87de7e4c4a388128c2a76c42961
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832442"
---
# <a name="ierrorrecordsimpl-class"></a>Класс IErrorRecordsImpl

Реализует интерфейс OLE DB [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) , добавляя записи и получая записи из элемента данных ([M_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) типа **CAtlArray<** `RecordClass` **>** .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class RecordClass = ATLERRORINFO>
class IErrorRecordsImpl : public IErrorRecords
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IErrorRecordsImpl` .

*рекордкласс*<br/>
Класс, представляющий объект OLE DB ошибки.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[жетеррордескриптионстринг](#geterrordescriptionstring)|Возвращает строку описания ошибки из записи об ошибке.|
|[жетерроргуид](#geterrorguid)|Возвращает идентификатор GUID ошибки из записи об ошибке.|
|[жетеррорхелпконтекст](#geterrorhelpcontext)|Возвращает идентификатор контекста справки из записи об ошибке.|
|[жетеррорхелпфиле](#geterrorhelpfile)|Возвращает полный путь к файлу справки из записи об ошибке.|
|[жетеррорсаурце](#geterrorsource)|Возвращает исходный код ошибки из записи об ошибке.|

### <a name="interface-methods"></a>Методы интерфейса

| Имя | Описание |
|-|-|
|[аддерроррекорд](#adderrorrecord)|Добавляет запись в объект OLE DB Error.|
|[GetBasicErrorInfo](#getbasicerrorinfo)|Возвращает основные сведения об ошибке, например код возврата и номер ошибки, зависящий от поставщика.|
|[GetCustomErrorObject](#getcustomerrorobject)|Возвращает указатель на интерфейс для пользовательского объекта ошибки.|
|[GetErrorInfo](#geterrorinfo)|Возвращает указатель интерфейса [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) для указанной записи.|
|[GetErrorParameters](#geterrorparameters)|Возвращает параметры ошибки.|
|[GetRecordCount](#getrecordcount)|Возвращает количество записей в объекте записи OLE DB.|

### <a name="data-members"></a>Элементы данных

| Имя | Описание |
|-|-|
|[m_rgErrors](#rgerrors)|Массив записей об ошибках.|

## <a name="ierrorrecordsimplgeterrordescriptionstring"></a><a name="geterrordescriptionstring"></a> IErrorRecordsImpl:: Жетеррордескриптионстринг

Возвращает строку описания ошибки из записи об ошибке.

### <a name="syntax"></a>Синтаксис

```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Параметры

*ркуреррор*<br/>
`ERRORINFO`Запись в `IErrorInfo` интерфейсе.

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, описывающую ошибку.

## <a name="ierrorrecordsimplgeterrorguid"></a><a name="geterrorguid"></a> IErrorRecordsImpl:: Жетерроргуид

Возвращает идентификатор GUID ошибки из записи об ошибке.

### <a name="syntax"></a>Синтаксис

```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Параметры

*ркуреррор*<br/>
`ERRORINFO`Запись в `IErrorInfo` интерфейсе.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на идентификатор GUID для ошибки.

## <a name="ierrorrecordsimplgeterrorhelpcontext"></a><a name="geterrorhelpcontext"></a> IErrorRecordsImpl:: Жетеррорхелпконтекст

Возвращает идентификатор контекста справки из записи об ошибке.

### <a name="syntax"></a>Синтаксис

```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Параметры

*ркуреррор*<br/>
`ERRORINFO`Запись в `IErrorInfo` интерфейсе.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор контекста справки для ошибки.

## <a name="ierrorrecordsimplgeterrorhelpfile"></a><a name="geterrorhelpfile"></a> IErrorRecordsImpl:: Жетеррорхелпфиле

Возвращает путь к файлу справки из записи об ошибке.

### <a name="syntax"></a>Синтаксис

```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Параметры

*ркуреррор*<br/>
`ERRORINFO`Запись в `IErrorInfo` интерфейсе.

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, содержащую путь к файлу справки для ошибки.

## <a name="ierrorrecordsimplgeterrorsource"></a><a name="geterrorsource"></a> IErrorRecordsImpl:: Жетеррорсаурце

Возвращает исходный код, который привел к ошибке из записи об ошибке.

### <a name="syntax"></a>Синтаксис

```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Параметры

*ркуреррор*<br/>
`ERRORINFO`Запись в `IErrorInfo` интерфейсе.

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, содержащую исходный код ошибки.

## <a name="ierrorrecordsimpladderrorrecord"></a><a name="adderrorrecord"></a> IErrorRecordsImpl:: Аддерроррекорд

Добавляет запись в объект OLE DB Error.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,
   DWORD dwLookupID,
   DISPPARAMS *pdispparams,
   IUnknown *punkCustomError,
   DWORD dwDynamicErrorID);
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: аддерроррекорд](/previous-versions/windows/desktop/ms725362(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="ierrorrecordsimplgetbasicerrorinfo"></a><a name="getbasicerrorinfo"></a> IErrorRecordsImpl:: Жетбасицерроринфо

Возвращает основные сведения об ошибке, например код возврата и номер ошибки, зависящий от поставщика.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,
   ERRORINFO *pErrorInfo);
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: жетбасицерроринфо](/previous-versions/windows/desktop/ms723907(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="ierrorrecordsimplgetcustomerrorobject"></a><a name="getcustomerrorobject"></a> IErrorRecordsImpl:: Жеткустомерроробжект

Возвращает указатель на интерфейс для пользовательского объекта ошибки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,
   REFIID riid,
   IUnknown **ppObject);
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: жеткустомерроробжект](/previous-versions/windows/desktop/ms725417(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="ierrorrecordsimplgeterrorinfo"></a><a name="geterrorinfo"></a> IErrorRecordsImpl:: Жетерроринфо

Возвращает указатель интерфейса [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) для указанной записи.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,
   LCID lcid,
   IErrorInfo **ppErrorInfo);
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: жетерроринфо](/previous-versions/windows/desktop/ms711230(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="ierrorrecordsimplgeterrorparameters"></a><a name="geterrorparameters"></a> IErrorRecordsImpl:: Жетеррорпараметерс

Возвращает параметры ошибки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,
   DISPPARAMS *pdispparams);
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: жетеррорпараметерс](/previous-versions/windows/desktop/ms715793(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="ierrorrecordsimplgetrecordcount"></a><a name="getrecordcount"></a> IErrorRecordsImpl:: Жетрекордкаунт

Возвращает количество записей в объекте записи OLE DB.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);
```

#### <a name="parameters"></a>Параметры

См. раздел [IErrorRecords:: жетрекордкаунт](/previous-versions/windows/desktop/ms722724(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="ierrorrecordsimplm_rgerrors"></a><a name="rgerrors"></a> IErrorRecordsImpl:: m_rgErrors

Массив записей об ошибках.

### <a name="syntax"></a>Синтаксис

```cpp
CAtlArray< RecordClass > m_rgErrors;
```

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
