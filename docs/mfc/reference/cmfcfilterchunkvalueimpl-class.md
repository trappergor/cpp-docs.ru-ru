---
title: "Класс CMFCFilterChunkValueImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCFilterChunkValueImpl class
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8de3cba19a60b8022df96a9edafd13677fa3fecb
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfilterchunkvalueimpl-class"></a>Класс CMFCFilterChunkValueImpl
Это класс, который упрощает логику пар значений блок-свойство.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Разрушается объекта.|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Создает объект.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](#clear)|Очищает ChunkValue.|  
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Копирует структуру, определяющих характеристики фрагмента этот фрагмент.|  
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Инициализирует этот фрагмент значение из другого значения.|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Получает GUID фрагмента данных.|  
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Извлекает Идентификаторы свойств фрагмента данных.|  
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Возвращает тип по блокам.|  
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Извлекает строковое значение.|  
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Получает значение как выделенный propvariant.|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Значение не выделенный возвращает (внутреннее значение).|  
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Проверяет, является ли значение данного свойства допустимым.|  
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Перегружен. Задает свойство, ключом которого является логическое значение.|  
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Задает свойство ключом на значение DWORD.|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Задает свойство ключом для filetime.|  
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Задает свойство ключом для переменной типа int64.|  
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Задает свойство по ключу в тип int.|  
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Задает свойство ключом для типа LONG.|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Задает свойство ключом в SystemTime.|  
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Задает свойство ключом в строку Юникода.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Вспомогательная функция, которая устанавливает общие свойства фрагмента.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать, просто создайте класс CMFCFilterChunkValueImpl правильный тип  
  
 Пример  
  
 Фрагмент CMFCFilterChunkValueImpl;  
  
 hr = фрагмента данных. SetBoolValue(PKEY_IsAttachment, true);  
  
 или  
  
 hr = фрагмента данных. SetFileTimeValue (PKEY_ItemDate ftLastModified);  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ATL::IFilterChunkValue`  
  
 [CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="clear"></a>CMFCFilterChunkValueImpl::Clear  
 Очищает ChunkValue.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="cmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl  
 Создает объект.  
  
```  
CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl  
 Разрушается объекта.  
  
```  
virtual ~CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="copychunk"></a>CMFCFilterChunkValueImpl::CopyChunk  
 Копирует структуру, определяющих характеристики фрагмента этот фрагмент.  
  
```  
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```  
  
### <a name="parameters"></a>Параметры  
 `pStatChunk`  
 Указатель на целевое значение, определяющих характеристики фрагмента данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="copyfrom"></a>CMFCFilterChunkValueImpl::CopyFrom  
 Инициализирует этот фрагмент значение из другого значения.  
  
```  
void CopyFrom (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Параметры  
 `pValue`  
 Указывает значение для копирования из источника.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getchunkguid"></a>CMFCFilterChunkValueImpl::GetChunkGUID  
 Получает GUID фрагмента данных.  
  
```  
REFGUID GetChunkGUID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на идентификатор GUID, определяющий фрагмента данных.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getchunkpid"></a>CMFCFilterChunkValueImpl::GetChunkPID  
 Извлекает Идентификаторы свойств фрагмента данных.  
  
```  
DWORD GetChunkPID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение типа DWORD, содержащее идентификатор свойства.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getchunktype"></a>CMFCFilterChunkValueImpl::GetChunkType  
 Получает тип фрагмента данных.  
  
```  
CHUNKSTATE GetChunkType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение перечисления CHUNKSTATE, которое указывает, является ли текущий фрагмент свойство text тип или тип значения свойства.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getstring"></a>CMFCFilterChunkValueImpl::GetString  
 Получает строковое значение.  
  
```  
CString &GetString();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая значение фрагмента данных.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getvalue"></a>CMFCFilterChunkValueImpl::GetValue  
 Получает значение как выделенный propvariant.  
  
```  
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```  
  
### <a name="parameters"></a>Параметры  
 `ppPropVariant`  
 Если функция возвращает значение, этот параметр содержит значение фрагмента данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если PROPVARIANT был выделен успешно и значение фрагмента успешно скопирована в `ppPropVariant`; в противном случае код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getvaluenoalloc"></a>CMFCFilterChunkValueImpl::GetValueNoAlloc  
 Возвращает значение, не выделенные (внутреннее значение).  
  
```  
PROPVARIANT GetValueNoAlloc ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение текущего фрагмента данных.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isvalid"></a>CMFCFilterChunkValueImpl::IsValid  
 Проверяет, является ли значение данного свойства допустимым.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если текущее значение фрагмент является допустимым; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setboolvalue"></a>CMFCFilterChunkValueImpl::SetBoolValue  
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
 `pkey`  
 Задает ключ свойства.  
  
 `bVal`  
 Указывает значение фрагмента данных.  
  
 `chunkType`  
 Флаги указывают, содержит ли этот фрагмент текста тип или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 `locale`  
 Язык, связанный с фрагмента текста. Фрагмент языка используется индексаторов документа для выполнения правильной разбиение по словам текста. Если фрагмент не является ни тип текста, ни тип значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле обрабатывается.  
  
 `cwcLenSource`  
 Длина в символах, производными от которого текущий фрагмент исходного текста. Нулевое значение означает символ за символом соответствие между исходного текста и производные текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 `cwcStartSource`  
 Смещение, из которого исходный текст для производных фрагмента запускает в блоке исходного.  
  
 `chunkBreakType`  
 Тип разрыва, разделяющий предыдущего фрагмента в текущем блоке. Значения из перечисления CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setchunk"></a>CMFCFilterChunkValueImpl::SetChunk  
 Вспомогательная функция, которая устанавливает общие свойства фрагмента.  
  
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
 `pkey`  
 Задает ключ свойства.  
  
 `chunkType`  
 Флаги указывают, содержит ли этот фрагмент текста тип или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 `locale`  
 Язык, связанный с фрагмента текста. Фрагмент языка используется индексаторов документа для выполнения правильной разбиение по словам текста. Если фрагмент не является ни тип текста, ни тип значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле обрабатывается.  
  
 `cwcLenSource`  
 Длина в символах, производными от которого текущий фрагмент исходного текста. Нулевое значение означает символ за символом соответствие между исходного текста и производные текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 `cwcStartSource`  
 Смещение, из которого исходный текст для производных фрагмента запускает в блоке исходного.  
  
 `chunkBreakType`  
 Тип разрыва, разделяющий предыдущего фрагмента в текущем блоке. Значения из перечисления CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdwordvalue"></a>CMFCFilterChunkValueImpl::SetDwordValue  
 Задайте для свойства ключом на значение DWORD.  
  
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
 `pkey`  
 Задает ключ свойства.  
  
 `dwVal`  
 Указывает значение фрагмента данных.  
  
 `chunkType`  
 Флаги указывают, содержит ли этот фрагмент текста тип или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 `locale`  
 Язык, связанный с фрагмента текста. Фрагмент языка используется индексаторов документа для выполнения правильной разбиение по словам текста. Если фрагмент не является ни тип текста, ни тип значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле обрабатывается.  
  
 `cwcLenSource`  
 Длина в символах, производными от которого текущий фрагмент исходного текста. Нулевое значение означает символ за символом соответствие между исходного текста и производные текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 `cwcStartSource`  
 Смещение, из которого исходный текст для производных фрагмента запускает в блоке исходного.  
  
 `chunkBreakType`  
 Тип разрыва, разделяющий предыдущего фрагмента в текущем блоке. Значения из перечисления CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setfiletimevalue"></a>CMFCFilterChunkValueImpl::SetFileTimeValue  
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
 `pkey`  
 Задает ключ свойства.  
  
 `dtVal`  
 Указывает значение фрагмента данных.  
  
 `chunkType`  
 Флаги указывают, содержит ли этот фрагмент текста тип или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 `locale`  
 Язык, связанный с фрагмента текста. Фрагмент языка используется индексаторов документа для выполнения правильной разбиение по словам текста. Если фрагмент не является ни тип текста, ни тип значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле обрабатывается.  
  
 `cwcLenSource`  
 Длина в символах, производными от которого текущий фрагмент исходного текста. Нулевое значение означает символ за символом соответствие между исходного текста и производные текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 `cwcStartSource`  
 Смещение, из которого исходный текст для производных фрагмента запускает в блоке исходного.  
  
 `chunkBreakType`  
 Тип разрыва, разделяющий предыдущего фрагмента в текущем блоке. Значения из перечисления CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setint64value"></a>CMFCFilterChunkValueImpl::SetInt64Value  
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
 `pkey`  
 Задает ключ свойства.  
  
 `nVal`  
 Указывает значение фрагмента данных.  
  
 `chunkType`  
 Флаги указывают, содержит ли этот фрагмент текста тип или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 `locale`  
 Язык, связанный с фрагмента текста. Фрагмент языка используется индексаторов документа для выполнения правильной разбиение по словам текста. Если фрагмент не является ни тип текста, ни тип значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле обрабатывается.  
  
 `cwcLenSource`  
 Длина в символах, производными от которого текущий фрагмент исходного текста. Нулевое значение означает символ за символом соответствие между исходного текста и производные текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 `cwcStartSource`  
 Смещение, из которого исходный текст для производных фрагмента запускает в блоке исходного.  
  
 `chunkBreakType`  
 Тип разрыва, разделяющий предыдущего фрагмента в текущем блоке. Значения из перечисления CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setintvalue"></a>CMFCFilterChunkValueImpl::SetIntValue  
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
 `pkey`  
 Задает ключ свойства.  
  
 `nVal`  
 Указывает значение фрагмента данных.  
  
 `chunkType`  
 Флаги указывают, содержит ли этот фрагмент текста тип или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 `locale`  
 Язык, связанный с фрагмента текста. Фрагмент языка используется индексаторов документа для выполнения правильной разбиение по словам текста. Если фрагмент не является ни тип текста, ни тип значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле обрабатывается.  
  
 `cwcLenSource`  
 Длина в символах, производными от которого текущий фрагмент исходного текста. Нулевое значение означает символ за символом соответствие между исходного текста и производные текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 `cwcStartSource`  
 Смещение, из которого исходный текст для производных фрагмента запускает в блоке исходного.  
  
 `chunkBreakType`  
 Тип разрыва, разделяющий предыдущего фрагмента в текущем блоке. Значения из перечисления CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setlongvalue"></a>CMFCFilterChunkValueImpl::SetLongValue  
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
 `pkey`  
 Задает ключ свойства.  
  
 `lVal`  
 Указывает значение фрагмента данных.  
  
 `chunkType`  
 Флаги указывают, содержит ли этот фрагмент текста тип или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 `locale`  
 Язык, связанный с фрагмента текста. Фрагмент языка используется индексаторов документа для выполнения правильной разбиение по словам текста. Если фрагмент не является ни тип текста, ни тип значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле обрабатывается.  
  
 `cwcLenSource`  
 Длина в символах, производными от которого текущий фрагмент исходного текста. Нулевое значение означает символ за символом соответствие между исходного текста и производные текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 `cwcStartSource`  
 Смещение, из которого исходный текст для производных фрагмента запускает в блоке исходного.  
  
 `chunkBreakType`  
 Тип разрыва, разделяющий предыдущего фрагмента в текущем блоке. Значения из перечисления CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setsystemtimevalue"></a>CMFCFilterChunkValueImpl::SetSystemTimeValue  
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
 `pkey`  
 Задает ключ свойства.  
  
 `systemTime`  
 Указывает значение фрагмента данных.  
  
 `chunkType`  
 Флаги указывают, содержит ли этот фрагмент текста тип или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 `locale`  
 Язык, связанный с фрагмента текста. Фрагмент языка используется индексаторов документа для выполнения правильной разбиение по словам текста. Если фрагмент не является ни тип текста, ни тип значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле обрабатывается.  
  
 `cwcLenSource`  
 Длина в символах, производными от которого текущий фрагмент исходного текста. Нулевое значение означает символ за символом соответствие между исходного текста и производные текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 `cwcStartSource`  
 Смещение, из которого исходный текст для производных фрагмента запускает в блоке исходного.  
  
 `chunkBreakType`  
 Тип разрыва, разделяющий предыдущего фрагмента в текущем блоке. Значения из перечисления CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settextvalue"></a>CMFCFilterChunkValueImpl::SetTextValue  
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
 `pkey`  
 Задает ключ свойства.  
  
 `pszValue`  
 Указывает значение фрагмента данных.  
  
 `chunkType`  
 Флаги указывают, содержит ли этот фрагмент текста тип или тип значения свойства. Флаг значения берутся из перечисления CHUNKSTATE.  
  
 `locale`  
 Язык, связанный с фрагмента текста. Фрагмент языка используется индексаторов документа для выполнения правильной разбиение по словам текста. Если фрагмент не является ни тип текста, ни тип значения с типом данных VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле обрабатывается.  
  
 `cwcLenSource`  
 Длина в символах, производными от которого текущий фрагмент исходного текста. Нулевое значение означает символ за символом соответствие между исходного текста и производные текст. Ненулевое значение означает, что такие прямое соответствие.  
  
 `cwcStartSource`  
 Смещение, из которого исходный текст для производных фрагмента запускает в блоке исходного.  
  
 `chunkBreakType`  
 Тип разрыва, разделяющий предыдущего фрагмента в текущем блоке. Значения из перечисления CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK в случае успешного выполнения; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

