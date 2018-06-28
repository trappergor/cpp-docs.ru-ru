---
title: Класс CMFCFilterChunkValueImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1f2fcdedb6b01025b06e4384ec2c32e95d08b6e
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040133"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>Класс CMFCFilterChunkValueImpl
Это класс, который упрощает логику пар значений блок-свойство.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Разрушается объекта.|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Создает объект.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](#clear)|Очищает ChunkValue.|  
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Копирует структуру, определяющих характеристики фрагмента этот фрагмент.|  
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Инициализирует этого фрагмента значения из другого значения.|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Извлекает идентификатор GUID фрагмента данных.|  
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Считывает фрагмент PID (идентификатор свойства).|  
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Возвращает фрагмент типа.|  
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Извлекает строковое значение.|  
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Получает значение как выделенный propvariant.|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Возвращает без выделенной (внутреннее значение) значение.|  
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Проверяет, является ли значение данного свойства допустимым.|  
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Перегружен. Задает свойство, ключом которого является логическое значение.|  
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Задает свойство по ключу на значение DWORD.|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Задает свойство ключом для filetime.|  
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Задает свойство ключом для переменной типа int64.|  
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Задает свойство ключом для значения типа int.|  
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Задает свойство ключом для типа LONG.|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Задает свойство ключом в SystemTime.|  
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Задает свойство ключом в строку Юникода.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Вспомогательная функция, которая задает общие свойства фрагмента данных.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать, просто создайте класс CMFCFilterChunkValueImpl правильный тип  
  
 Пример  
  
 CMFCFilterChunkValueImpl блока;  
  
 hr = фрагмента данных. SetBoolValue(PKEY_IsAttachment, true);  
  
 или  
  
 hr = фрагмента данных. SetFileTimeValue (PKEY_ItemDate ftLastModified);  
  
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
 Копирует структуру, определяющих характеристики фрагмента этот фрагмент.  
  
```  
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```  
  
### <a name="parameters"></a>Параметры  
 *pStatChunk*  
 Указатель на целевое значение, определяющих характеристики фрагмента данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="copyfrom"></a>  CMFCFilterChunkValueImpl::CopyFrom  
 Инициализирует этого фрагмента значения из другого значения.  
  
```  
void CopyFrom (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Параметры  
 *pValue*  
 Указывает значение для копирования из источника.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getchunkguid"></a>  CMFCFilterChunkValueImpl::GetChunkGUID  
 Извлекает идентификатор GUID фрагмента данных.  
  
```  
REFGUID GetChunkGUID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на идентификатор GUID, определяющий фрагмента данных.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getchunkpid"></a>  CMFCFilterChunkValueImpl::GetChunkPID  
 Считывает фрагмент PID (идентификатор свойства).  
  
```  
DWORD GetChunkPID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение DWORD, содержащее идентификатор свойства.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getchunktype"></a>  CMFCFilterChunkValueImpl::GetChunkType  
 Получает тип блока.  
  
```  
CHUNKSTATE GetChunkType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение перечисления CHUNKSTATE, которое указывает, является ли текущий блок свойство типа text или тип значения свойства.  
  
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
 Получает значение как выделенный propvariant.  
  
```  
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```  
  
### <a name="parameters"></a>Параметры  
 *ppPropVariant*  
 Когда функция возвращает значение, этот параметр содержит значение фрагмента данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если PROPVARIANT был выделен успешно и значение фрагмента данных успешно скопирована в *ppPropVariant*; в противном случае код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getvaluenoalloc"></a>  CMFCFilterChunkValueImpl::GetValueNoAlloc  
 Возвращает значение без выделенной (внутреннее значение).  
  
```  
PROPVARIANT GetValueNoAlloc ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее значение фрагмента данных.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isvalid"></a>  CMFCFilterChunkValueImpl::IsValid  
 Проверяет, является ли значение данного свойства допустимым.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если текущее значение фрагмента данных допустима; в противном случае `FALSE`.  
  
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
 *PKEY*  
 Указывает ключ свойства.  
  
 *bVal*  
 Указывает значение фрагмента данных для установки.  
  
 *chunkType*  
 Флаги указывают, является ли этот фрагмент содержит текстового типа или типа значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 *locale*  
 Язык, связанный с блок текста. Языковой стандарт блоков используется индексаторов документа для выполнения правильной разбиения текста. Если фрагмента данных типа text, ни типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле учитывается.  
  
 *cwcLenSource*  
 Длина в символах исходного текста, производными от которого текущего фрагмента. Нулевое значение означает символ за символом соответствие между исходного текста и производных текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 *cwcStartSource*  
 Смещение, из которого исходный текст для всех блоков, производном начинается в блоке исходного.  
  
 *chunkBreakType*  
 Тип паузы, разделяющий предыдущего фрагмента данных из текущего фрагмента. Значения: от CHUNK_BREAKTYPE перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
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
 *PKEY*  
 Указывает ключ свойства.  
  
 *chunkType*  
 Флаги указывают, является ли этот фрагмент содержит текстового типа или типа значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 *locale*  
 Язык, связанный с блок текста. Языковой стандарт блоков используется индексаторов документа для выполнения правильной разбиения текста. Если фрагмента данных типа text, ни типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле учитывается.  
  
 *cwcLenSource*  
 Длина в символах исходного текста, производными от которого текущего фрагмента. Нулевое значение означает символ за символом соответствие между исходного текста и производных текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 *cwcStartSource*  
 Смещение, из которого исходный текст для всех блоков, производном начинается в блоке исходного.  
  
 *chunkBreakType*  
 Тип паузы, разделяющий предыдущего фрагмента данных из текущего фрагмента. Значения: от CHUNK_BREAKTYPE перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdwordvalue"></a>  CMFCFilterChunkValueImpl::SetDwordValue  
 Задайте для свойства по ключу на значение DWORD.  
  
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
 *PKEY*  
 Указывает ключ свойства.  
  
 *dwVal*  
 Указывает значение фрагмента данных для установки.  
  
 *chunkType*  
 Флаги указывают, является ли этот фрагмент содержит текстового типа или типа значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 *locale*  
 Язык, связанный с блок текста. Языковой стандарт блоков используется индексаторов документа для выполнения правильной разбиения текста. Если фрагмента данных типа text, ни типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле учитывается.  
  
 *cwcLenSource*  
 Длина в символах исходного текста, производными от которого текущего фрагмента. Нулевое значение означает символ за символом соответствие между исходного текста и производных текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 *cwcStartSource*  
 Смещение, из которого исходный текст для всех блоков, производном начинается в блоке исходного.  
  
 *chunkBreakType*  
 Тип паузы, разделяющий предыдущего фрагмента данных из текущего фрагмента. Значения: от CHUNK_BREAKTYPE перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setfiletimevalue"></a>  CMFCFilterChunkValueImpl::SetFileTimeValue  
 Задайте свойство ключом для filetime.  
  
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
 *PKEY*  
 Указывает ключ свойства.  
  
 *dtVal*  
 Указывает значение фрагмента данных для установки.  
  
 *chunkType*  
 Флаги указывают, является ли этот фрагмент содержит текстового типа или типа значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 *locale*  
 Язык, связанный с блок текста. Языковой стандарт блоков используется индексаторов документа для выполнения правильной разбиения текста. Если фрагмента данных типа text, ни типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле учитывается.  
  
 *cwcLenSource*  
 Длина в символах исходного текста, производными от которого текущего фрагмента. Нулевое значение означает символ за символом соответствие между исходного текста и производных текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 *cwcStartSource*  
 Смещение, из которого исходный текст для всех блоков, производном начинается в блоке исходного.  
  
 *chunkBreakType*  
 Тип паузы, разделяющий предыдущего фрагмента данных из текущего фрагмента. Значения: от CHUNK_BREAKTYPE перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setint64value"></a>  CMFCFilterChunkValueImpl::SetInt64Value  
 Задайте свойство ключом для переменной типа int64.  
  
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
 *PKEY*  
 Указывает ключ свойства.  
  
 *nVal*  
 Указывает значение фрагмента данных для установки.  
  
 *chunkType*  
 Флаги указывают, является ли этот фрагмент содержит текстового типа или типа значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 *locale*  
 Язык, связанный с блок текста. Языковой стандарт блоков используется индексаторов документа для выполнения правильной разбиения текста. Если фрагмента данных типа text, ни типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле учитывается.  
  
 *cwcLenSource*  
 Длина в символах исходного текста, производными от которого текущего фрагмента. Нулевое значение означает символ за символом соответствие между исходного текста и производных текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 *cwcStartSource*  
 Смещение, из которого исходный текст для всех блоков, производном начинается в блоке исходного.  
  
 *chunkBreakType*  
 Тип паузы, разделяющий предыдущего фрагмента данных из текущего фрагмента. Значения: от CHUNK_BREAKTYPE перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setintvalue"></a>  CMFCFilterChunkValueImpl::SetIntValue  
 Задать значение свойства ключа в тип int.  
  
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
 *PKEY*  
 Указывает ключ свойства.  
  
 *nVal*  
 Указывает значение фрагмента данных для установки.  
  
 *chunkType*  
 Флаги указывают, является ли этот фрагмент содержит текстового типа или типа значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 *locale*  
 Язык, связанный с блок текста. Языковой стандарт блоков используется индексаторов документа для выполнения правильной разбиения текста. Если фрагмента данных типа text, ни типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле учитывается.  
  
 *cwcLenSource*  
 Длина в символах исходного текста, производными от которого текущего фрагмента. Нулевое значение означает символ за символом соответствие между исходного текста и производных текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 *cwcStartSource*  
 Смещение, из которого исходный текст для всех блоков, производном начинается в блоке исходного.  
  
 *chunkBreakType*  
 Тип паузы, разделяющий предыдущего фрагмента данных из текущего фрагмента. Значения: от CHUNK_BREAKTYPE перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setlongvalue"></a>  CMFCFilterChunkValueImpl::SetLongValue  
 Задайте свойство ключом для типа LONG.  
  
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
 *PKEY*  
 Указывает ключ свойства.  
  
 *lVal*  
 Указывает значение фрагмента данных для установки.  
  
 *chunkType*  
 Флаги указывают, является ли этот фрагмент содержит текстового типа или типа значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 *locale*  
 Язык, связанный с блок текста. Языковой стандарт блоков используется индексаторов документа для выполнения правильной разбиения текста. Если фрагмента данных типа text, ни типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле учитывается.  
  
 *cwcLenSource*  
 Длина в символах исходного текста, производными от которого текущего фрагмента. Нулевое значение означает символ за символом соответствие между исходного текста и производных текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 *cwcStartSource*  
 Смещение, из которого исходный текст для всех блоков, производном начинается в блоке исходного.  
  
 *chunkBreakType*  
 Тип паузы, разделяющий предыдущего фрагмента данных из текущего фрагмента. Значения: от CHUNK_BREAKTYPE перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setsystemtimevalue"></a>  CMFCFilterChunkValueImpl::SetSystemTimeValue  
 Задает свойство ключом в SystemTime.  
  
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
 *PKEY*  
 Указывает ключ свойства.  
  
 *systemTime*  
 Указывает значение фрагмента данных для установки.  
  
 *chunkType*  
 Флаги указывают, является ли этот фрагмент содержит текстового типа или типа значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 *locale*  
 Язык, связанный с блок текста. Языковой стандарт блоков используется индексаторов документа для выполнения правильной разбиения текста. Если фрагмента данных типа text, ни типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле учитывается.  
  
 *cwcLenSource*  
 Длина в символах исходного текста, производными от которого текущего фрагмента. Нулевое значение означает символ за символом соответствие между исходного текста и производных текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 *cwcStartSource*  
 Смещение, из которого исходный текст для всех блоков, производном начинается в блоке исходного.  
  
 *chunkBreakType*  
 Тип паузы, разделяющий предыдущего фрагмента данных из текущего фрагмента. Значения: от CHUNK_BREAKTYPE перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settextvalue"></a>  CMFCFilterChunkValueImpl::SetTextValue  
 Задает свойство ключом в строку Юникода.  
  
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
 *PKEY*  
 Указывает ключ свойства.  
  
 *размер pszValue*  
 Указывает значение фрагмента данных для установки.  
  
 *chunkType*  
 Флаги указывают, является ли этот фрагмент содержит текстового типа или типа значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 *locale*  
 Язык, связанный с блок текста. Языковой стандарт блоков используется индексаторов документа для выполнения правильной разбиения текста. Если фрагмента данных типа text, ни типом значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле учитывается.  
  
 *cwcLenSource*  
 Длина в символах исходного текста, производными от которого текущего фрагмента. Нулевое значение означает символ за символом соответствие между исходного текста и производных текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 *cwcStartSource*  
 Смещение, из которого исходный текст для всех блоков, производном начинается в блоке исходного.  
  
 *chunkBreakType*  
 Тип паузы, разделяющий предыдущего фрагмента данных из текущего фрагмента. Значения: от CHUNK_BREAKTYPE перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
