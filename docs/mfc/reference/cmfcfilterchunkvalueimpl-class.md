---
title: Класс CMFCFilterChunkValueImpl
ms.date: 11/04/2016
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
ms.openlocfilehash: b883d442342dd9fbbd074d9f8fcab76f81ef9864
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237562"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>Класс CMFCFilterChunkValueImpl

Это класс, который упрощает логику пар значений блок-свойство.

## <a name="syntax"></a>Синтаксис

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Разрушается объекта.|
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Создает объект.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::Clear](#clear)|Очищает ChunkValue.|
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Копирует структуру, определяющих характеристики фрагмент этого блока.|
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Инициализирует это значение фрагмента данных из другого значения.|
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Извлекает идентификатор GUID фрагмента данных.|
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Извлекает Идентификаторы свойство фрагмента данных.|
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Получает Фрагментирование типа.|
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Получает строковое значение.|
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Получает значение в виде выделенных propvariant.|
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Возвращает не выделено (внутреннее значение) значение.|
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Проверяет, является ли значение этого свойства допустимым.|
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Перегружен. Задает свойство, ключом которого является логическое значение.|
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Задает свойство по ключу на значение типа DWORD.|
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Задает свойство по ключу для filetime.|
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Задает свойство по ключу в значение типа int64.|
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Задает свойство по ключу в тип int.|
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Задает свойство по ключу для типа LONG.|
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Задает свойство по ключу в SystemTime.|
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Задает свойство по ключу в строку Юникода.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Вспомогательная функция, которая задает общие свойства фрагмента данных.|

## <a name="remarks"></a>Примечания

Чтобы использовать, просто создайте класс CMFCFilterChunkValueImpl правильный тип

Пример

CMFCFilterChunkValueImpl блоков;

hr = фрагмента данных. SetBoolValue(PKEY_IsAttachment, true);

или

hr = chunk.SetFileTimeValue(PKEY_ItemDate, ftLastModified);

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ATL::IFilterChunkValue`

[CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="clear"></a>  CMFCFilterChunkValueImpl::Clear

Очищает ChunkValue.

```
void Clear();
```

### <a name="remarks"></a>Примечания

##  <a name="cmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl

Создает объект.

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Примечания

##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl

Разрушается объекта.

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Примечания

##  <a name="copychunk"></a>  CMFCFilterChunkValueImpl::CopyChunk

Копирует структуру, определяющих характеристики фрагмент этого блока.

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>Параметры

*pStatChunk*<br/>
Указатель на значение назначения, определяющих характеристики фрагмента данных.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="copyfrom"></a>  CMFCFilterChunkValueImpl::CopyFrom

Инициализирует это значение фрагмента данных из другого значения.

```
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Указывает значение для копирования из источника.

### <a name="remarks"></a>Примечания

##  <a name="getchunkguid"></a>  CMFCFilterChunkValueImpl::GetChunkGUID

Извлекает идентификатор GUID фрагмента данных.

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на идентификатор GUID, указывающий фрагмента данных.

### <a name="remarks"></a>Примечания

##  <a name="getchunkpid"></a>  CMFCFilterChunkValueImpl::GetChunkPID

Извлекает Идентификаторы свойство фрагмента данных.

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение типа DWORD, содержащее идентификатор свойства.

### <a name="remarks"></a>Примечания

##  <a name="getchunktype"></a>  CMFCFilterChunkValueImpl::GetChunkType

Возвращает тип фрагмента данных.

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение перечисления CHUNKSTATE, которое указывает, является ли текущий фрагмент текстовые свойство или свойство тип значения.

### <a name="remarks"></a>Примечания

##  <a name="getstring"></a>  CMFCFilterChunkValueImpl::GetString

Получает строковое значение.

```
CString &GetString();
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая значение фрагмента данных.

### <a name="remarks"></a>Примечания

##  <a name="getvalue"></a>  CMFCFilterChunkValueImpl::GetValue

Получает значение в виде выделенных propvariant.

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>Параметры

*ppPropVariant*<br/>
Когда функция возвращает значение, данный параметр содержит значение фрагмента данных.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если PROPVARIANT был выделен успешно и значение фрагмента данных успешно скопирована в *ppPropVariant*; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="getvaluenoalloc"></a>  CMFCFilterChunkValueImpl::GetValueNoAlloc

Возвращает значение-выделенных (внутреннее значение).

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущее значение фрагмента данных.

### <a name="remarks"></a>Примечания

##  <a name="isvalid"></a>  CMFCFilterChunkValueImpl::IsValid

Проверяет, является ли значение этого свойства допустимым.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущее значение фрагмента данных является допустимым; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="setboolvalue"></a>  CMFCFilterChunkValueImpl::SetBoolValue

Перегружен. Задает свойство, ключом которого является логическое значение.

```
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    VARIANT_BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*PKEY*<br/>
Указывает ключ свойства.

*bVal*<br/>
Указывает задаваемое значение фрагмента данных.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент текста type или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.

*locale*<br/>
Язык, связанный с фрагмент текста. Языковой стандарт блоков используется индексаторы документов для выполнения правильной разбиение по словам текста. Если фрагмента данных является типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, ни тип текста, это поле учитывается.

*cwcLenSource*<br/>
Длина в символах исходного текста, из которого получена текущий фрагмент. Нулевое значение означает символ за символом соответствие исходного текста производном текст. Ненулевое значение означает, что существует такое прямое соответствие.

*cwcStartSource*<br/>
Смещение, из которого исходного текста для производного фрагмента начинается в блоке источника.

*chunkBreakType*<br/>
Тип разрыва, разделяющий предыдущего фрагмента данных в текущем блоке. Значения получены из перечисления CHUNK_BREAKTYPE.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="setchunk"></a>  CMFCFilterChunkValueImpl::SetChunk

Вспомогательная функция, которая задает общие свойства фрагмента данных.

```
HRESULT SetChunk(
    REFPROPERTYKEY pkey,
    CHUNKSTATE chunkType=CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*PKEY*<br/>
Указывает ключ свойства.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент текста type или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.

*locale*<br/>
Язык, связанный с фрагмент текста. Языковой стандарт блоков используется индексаторы документов для выполнения правильной разбиение по словам текста. Если фрагмента данных является типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, ни тип текста, это поле учитывается.

*cwcLenSource*<br/>
Длина в символах исходного текста, из которого получена текущий фрагмент. Нулевое значение означает символ за символом соответствие исходного текста производном текст. Ненулевое значение означает, что существует такое прямое соответствие.

*cwcStartSource*<br/>
Смещение, из которого исходного текста для производного фрагмента начинается в блоке источника.

*chunkBreakType*<br/>
Тип разрыва, разделяющий предыдущего фрагмента данных в текущем блоке. Значения получены из перечисления CHUNK_BREAKTYPE.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="setdwordvalue"></a>  CMFCFilterChunkValueImpl::SetDwordValue

Свойства по ключу на значение типа DWORD.

```
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,
    DWORD dwVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*PKEY*<br/>
Указывает ключ свойства.

*dwVal*<br/>
Указывает задаваемое значение фрагмента данных.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент текста type или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.

*locale*<br/>
Язык, связанный с фрагмент текста. Языковой стандарт блоков используется индексаторы документов для выполнения правильной разбиение по словам текста. Если фрагмента данных является типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, ни тип текста, это поле учитывается.

*cwcLenSource*<br/>
Длина в символах исходного текста, из которого получена текущий фрагмент. Нулевое значение означает символ за символом соответствие исходного текста производном текст. Ненулевое значение означает, что существует такое прямое соответствие.

*cwcStartSource*<br/>
Смещение, из которого исходного текста для производного фрагмента начинается в блоке источника.

*chunkBreakType*<br/>
Тип разрыва, разделяющий предыдущего фрагмента данных в текущем блоке. Значения получены из перечисления CHUNK_BREAKTYPE.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="setfiletimevalue"></a>  CMFCFilterChunkValueImpl::SetFileTimeValue

Свойства по ключу для filetime.

```
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,
    FILETIME dtVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*PKEY*<br/>
Указывает ключ свойства.

*dtVal*<br/>
Указывает задаваемое значение фрагмента данных.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент текста type или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.

*locale*<br/>
Язык, связанный с фрагмент текста. Языковой стандарт блоков используется индексаторы документов для выполнения правильной разбиение по словам текста. Если фрагмента данных является типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, ни тип текста, это поле учитывается.

*cwcLenSource*<br/>
Длина в символах исходного текста, из которого получена текущий фрагмент. Нулевое значение означает символ за символом соответствие исходного текста производном текст. Ненулевое значение означает, что существует такое прямое соответствие.

*cwcStartSource*<br/>
Смещение, из которого исходного текста для производного фрагмента начинается в блоке источника.

*chunkBreakType*<br/>
Тип разрыва, разделяющий предыдущего фрагмента данных в текущем блоке. Значения получены из перечисления CHUNK_BREAKTYPE.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="setint64value"></a>  CMFCFilterChunkValueImpl::SetInt64Value

Свойства по ключу в значение типа int64.

```
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,
    __int64 nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*PKEY*<br/>
Указывает ключ свойства.

*nval, полученное средством*<br/>
Указывает задаваемое значение фрагмента данных.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент текста type или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.

*locale*<br/>
Язык, связанный с фрагмент текста. Языковой стандарт блоков используется индексаторы документов для выполнения правильной разбиение по словам текста. Если фрагмента данных является типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, ни тип текста, это поле учитывается.

*cwcLenSource*<br/>
Длина в символах исходного текста, из которого получена текущий фрагмент. Нулевое значение означает символ за символом соответствие исходного текста производном текст. Ненулевое значение означает, что существует такое прямое соответствие.

*cwcStartSource*<br/>
Смещение, из которого исходного текста для производного фрагмента начинается в блоке источника.

*chunkBreakType*<br/>
Тип разрыва, разделяющий предыдущего фрагмента данных в текущем блоке. Значения получены из перечисления CHUNK_BREAKTYPE.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="setintvalue"></a>  CMFCFilterChunkValueImpl::SetIntValue

Установите для свойства по ключу в тип int.

```
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,
    int nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*PKEY*<br/>
Указывает ключ свойства.

*nval, полученное средством*<br/>
Указывает задаваемое значение фрагмента данных.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент текста type или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.

*locale*<br/>
Язык, связанный с фрагмент текста. Языковой стандарт блоков используется индексаторы документов для выполнения правильной разбиение по словам текста. Если фрагмента данных является типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, ни тип текста, это поле учитывается.

*cwcLenSource*<br/>
Длина в символах исходного текста, из которого получена текущий фрагмент. Нулевое значение означает символ за символом соответствие исходного текста производном текст. Ненулевое значение означает, что существует такое прямое соответствие.

*cwcStartSource*<br/>
Смещение, из которого исходного текста для производного фрагмента начинается в блоке источника.

*chunkBreakType*<br/>
Тип разрыва, разделяющий предыдущего фрагмента данных в текущем блоке. Значения получены из перечисления CHUNK_BREAKTYPE.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="setlongvalue"></a>  CMFCFilterChunkValueImpl::SetLongValue

Свойства по ключу для типа LONG.

```
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,
    long lVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*PKEY*<br/>
Указывает ключ свойства.

*lVal*<br/>
Указывает задаваемое значение фрагмента данных.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент текста type или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.

*locale*<br/>
Язык, связанный с фрагмент текста. Языковой стандарт блоков используется индексаторы документов для выполнения правильной разбиение по словам текста. Если фрагмента данных является типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, ни тип текста, это поле учитывается.

*cwcLenSource*<br/>
Длина в символах исходного текста, из которого получена текущий фрагмент. Нулевое значение означает символ за символом соответствие исходного текста производном текст. Ненулевое значение означает, что существует такое прямое соответствие.

*cwcStartSource*<br/>
Смещение, из которого исходного текста для производного фрагмента начинается в блоке источника.

*chunkBreakType*<br/>
Тип разрыва, разделяющий предыдущего фрагмента данных в текущем блоке. Значения получены из перечисления CHUNK_BREAKTYPE.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="setsystemtimevalue"></a>  CMFCFilterChunkValueImpl::SetSystemTimeValue

Задает свойство по ключу в SystemTime.

```
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,
    const SYSTEMTIME& systemTime,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*PKEY*<br/>
Указывает ключ свойства.

*systemTime*<br/>
Указывает задаваемое значение фрагмента данных.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент текста type или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.

*locale*<br/>
Язык, связанный с фрагмент текста. Языковой стандарт блоков используется индексаторы документов для выполнения правильной разбиение по словам текста. Если фрагмента данных является типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, ни тип текста, это поле учитывается.

*cwcLenSource*<br/>
Длина в символах исходного текста, из которого получена текущий фрагмент. Нулевое значение означает символ за символом соответствие исходного текста производном текст. Ненулевое значение означает, что существует такое прямое соответствие.

*cwcStartSource*<br/>
Смещение, из которого исходного текста для производного фрагмента начинается в блоке источника.

*chunkBreakType*<br/>
Тип разрыва, разделяющий предыдущего фрагмента данных в текущем блоке. Значения получены из перечисления CHUNK_BREAKTYPE.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="settextvalue"></a>  CMFCFilterChunkValueImpl::SetTextValue

Задает свойство по ключу в строку Юникода.

```
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,
    LPCTSTR pszValue,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*PKEY*<br/>
Указывает ключ свойства.

*pszValue*<br/>
Указывает задаваемое значение фрагмента данных.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент текста type или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.

*locale*<br/>
Язык, связанный с фрагмент текста. Языковой стандарт блоков используется индексаторы документов для выполнения правильной разбиение по словам текста. Если фрагмента данных является типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, ни тип текста, это поле учитывается.

*cwcLenSource*<br/>
Длина в символах исходного текста, из которого получена текущий фрагмент. Нулевое значение означает символ за символом соответствие исходного текста производном текст. Ненулевое значение означает, что существует такое прямое соответствие.

*cwcStartSource*<br/>
Смещение, из которого исходного текста для производного фрагмента начинается в блоке источника.

*chunkBreakType*<br/>
Тип разрыва, разделяющий предыдущего фрагмента данных в текущем блоке. Значения получены из перечисления CHUNK_BREAKTYPE.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
