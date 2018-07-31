---
title: Класс IErrorRecordsImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
- GetCustomErrorObject
- GetErrorInfo
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7339b345ad63f59a2db24251c06b80774305ab00
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338123"
---
# <a name="ierrorrecordsimpl-class"></a>Класс IErrorRecordsImpl
Реализует OLE DB [IErrorRecords](https://msdn.microsoft.com/library/ms718112.aspx) интерфейс, добавления записей и извлечения записей из элемента данных ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) типа **CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class RecordClass = ATLERRORINFO>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Класс, производный от `IErrorRecordsImpl`.  
  
 *RecordClass*  
 Класс, который представляет объект ошибки OLE DB.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[GetErrorDescriptionString](#geterrordescriptionstring)|Получает строку описания ошибки из записи об ошибке.|  
|[GetErrorGUID](#geterrorguid)|Получает ошибку GUID из записи об ошибке.|  
|[GetErrorHelpContext](#geterrorhelpcontext)|Получает идентификатор контекста справки из записи об ошибке.|  
|[GetErrorHelpFile](#geterrorhelpfile)|Получает полный путь файла справки из записи об ошибке.|  
|[GetErrorSource](#geterrorsource)|Получает исходный код ошибки из записи об ошибке.|  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[AddErrorRecord](#adderrorrecord)|Добавляет запись в объекте ошибки OLE DB.|  
|[GetBasicErrorInfo](#getbasicerrorinfo)|Возвращает основные сведения об ошибке, например кода возврата и номер ошибки от поставщика.|  
|[GetCustomErrorObject](#getcustomerrorobject)|Возвращает указатель на интерфейс объекта пользовательских ошибок.|  
|[GetErrorInfo](#geterrorinfo)|Возвращает [IErrorInfo](https://msdn.microsoft.com/library/ms718112.aspx) указатель интерфейса на указанную запись.|  
|[GetErrorParameters](#geterrorparameters)|Возвращает параметры ошибки.|  
|[GetRecordCount](#getrecordcount)|Возвращает число записей в объекте запись OLE DB.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_rgErrors](#rgerrors)|Массив записей ошибок.|  

## <a name="geterrordescriptionstring"></a> IErrorRecordsImpl::GetErrorDescriptionString
Получает строку описания ошибки из записи об ошибке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Параметры  
 *rCurError*  
 `ERRORINFO` Записей в `IErrorInfo` интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, описывающую ошибку.  
  
## <a name="geterrorguid"></a> IErrorRecordsImpl::GetErrorGUID
Получает ошибку GUID из записи об ошибке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Параметры  
 *rCurError*  
 `ERRORINFO` Записей в `IErrorInfo` интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на идентификатор GUID для ошибки.  

## <a name="geterrorhelpcontext"></a> IErrorRecordsImpl::GetErrorHelpContext
Получает идентификатор контекста справки из записи об ошибке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Параметры  
 *rCurError*  
 `ERRORINFO` Записей в `IErrorInfo` интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор контекста справки для ошибки.  

## <a name="geterrorhelpfile"></a> IErrorRecordsImpl::GetErrorHelpFile
Возвращает имя пути файла справки из записи об ошибке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Параметры  
 *rCurError*  
 `ERRORINFO` Записей в `IErrorInfo` интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, содержащую путь файла справки для ошибки.

## <a name="geterrorsource"></a> IErrorRecordsImpl::GetErrorSource
Получает исходный код, который вызвал ошибку из записи об ошибке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Параметры  
 *rCurError*  
 `ERRORINFO` Записей в `IErrorInfo` интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, содержащую исходный код для ошибки. 

## <a name="adderrorrecord"></a> IErrorRecordsImpl::AddErrorRecord
Добавляет запись в объекте ошибки OLE DB.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,  
   DWORD dwLookupID,  
   DISPPARAMS *pdispparams,  
   IUnknown *punkCustomError,  
   DWORD dwDynamicErrorID);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::AddErrorRecord](https://msdn.microsoft.com/library/ms725362.aspx) в *справочнике программиста OLE DB*.  

## <a name="getbasicerrorinfo"></a> IErrorRecordsImpl::GetBasicErrorInfo
Возвращает основные сведения об ошибке, например кода возврата и номер ошибки от поставщика.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,  
   ERRORINFO *pErrorInfo);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/library/ms723907.aspx) в *справочнике программиста OLE DB*. 

## <a name="getcustomerrorobject"></a> IErrorRecordsImpl::GetCustomErrorObject
Возвращает указатель на интерфейс объекта пользовательских ошибок.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/library/ms725417.aspx) в *справочнике программиста OLE DB*.  

## <a name="geterrorinfo"></a> IErrorRecordsImpl::GetErrorInfo
Возвращает [IErrorInfo](https://msdn.microsoft.com/library/ms718112.aspx) указатель интерфейса на указанную запись.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,  
   LCID lcid,  
   IErrorInfo **ppErrorInfo);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) в *справочнике программиста OLE DB*.

## <a name="geterrorparameters"></a> IErrorRecordsImpl::GetErrorParameters
Возвращает параметры ошибки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,  
   DISPPARAMS *pdispparams);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/library/ms715793.aspx) в *справочнике программиста OLE DB*.  

## <a name="getrecordcount"></a> IErrorRecordsImpl::GetRecordCount
Возвращает число записей в объекте запись OLE DB.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::GetRecordCount](https://msdn.microsoft.com/library/ms722724.aspx) в *справочнике программиста OLE DB*.  

## <a name="rgerrors"></a> IErrorRecordsImpl::m_rgErrors
Массив записей ошибок.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CAtlArray< RecordClass > m_rgErrors;  
```  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)