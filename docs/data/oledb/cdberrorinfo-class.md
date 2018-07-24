---
title: Класс CDBErrorInfo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetBasicErrorInfo
- ATL.CDBErrorInfo.GetBasicErrorInfo
- CDBErrorInfo.GetBasicErrorInfo
- ATL::CDBErrorInfo::GetBasicErrorInfo
- GetBasicErrorInfo
- CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetCustomErrorObject
- CDBErrorInfo.GetCustomErrorObject
- ATL::CDBErrorInfo::GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- GetErrorParameters
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- CDBErrorInfo class
- GetAllErrorInfo method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetErrorRecords method
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0a219024c56bd1b976682c7262d84ce26bce0930
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208615"
---
# <a name="cdberrorinfo-class"></a>Класс CDBErrorInfo
Обеспечивает поддержку обработки ошибок OLE DB, использующий OLE DB [IErrorRecords](https://msdn.microsoft.com/library/ms718112.aspx) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CDBErrorInfo  
``` 

## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h 
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[GetAllErrorInfo](#getallerrorinfo)|Возвращает все сведения об ошибке, содержащиеся в записи об ошибке.|  
|[GetBasicErrorInfo](#getbasicerrorinfo)|Вызовы [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/library/ms723907.aspx) для возврата основные сведения об указанной ошибке.|  
|[GetCustomErrorObject](#getcustomerrorobject)|Вызовы [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/library/ms725417.aspx) для возврата указателя на интерфейс объекта пользовательских ошибок.|  
|[GetErrorInfo](#geterrorinfo)|Вызовы [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) для возврата `IErrorInfo` указатель интерфейса на указанную запись.|  
|[GetErrorParameters](#geterrorparameters)|Вызовы [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/library/ms715793.aspx) для определения параметров ошибки.|  
|[GetErrorRecords](#geterrorrecords)|Возвращает записи об ошибках для указанного объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс возвращает один или несколько записей ошибок для пользователя. Вызовите [CDBErrorInfo::GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) первой, чтобы получить число записей ошибок. После чего вызывается один доступа к функции, такие как [CDBErrorInfo::GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), чтобы получить сведения об ошибке для каждой записи.  
  
## <a name="getallerrorinfo"></a> CDBErrorInfo::GetAllErrorInfo
Возвращает все типы сведений об ошибках, содержащихся в записи об ошибке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetAllErrorInfo(ULONG ulRecordNum,  
   LCID lcid,  BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *ulRecordNum*  
 [in] Отсчитываемый от нуля номер записи, для которой возвращаются сведения об ошибке.  
  
 *lcid*  
 [in] КОД языка для сведения об ошибке должны быть возвращены.  
  
 *pbstrDescription*  
 [out] Указатель на текстовое описание ошибки или значение NULL, если языковой стандарт не поддерживается. См. заметки.  
  
 *pbstrSource*  
 [out] Указатель на строку, содержащую имя компонента, вызвавшего ошибку.  
  
 *pguid*  
 [out] Указатель на идентификатор GUID интерфейса, определившего ошибку.  
  
 *pdwHelpContext*  
 [out] Указатель на идентификатор контекста справки для ошибки.  
  
 *pbstrHelpFile*  
 [out] Указатель на строку, содержащую путь к файлу справки с описанием ошибки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK при успешном выполнении. См. в разделе [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) в *Справочник программиста OLE DB по* другие возвращаемые значения.  
  
### <a name="remarks"></a>Примечания  
 Выходное значение *pbstrDescription* внутренне получается путем вызова `IErrorInfo::GetDescription`, который задает значение, значение NULL, если языковой стандарт не поддерживается, или в том случае, если выполняются оба из следующих условий:  
  
1.  значение *lcid* не США Английский и  
  
2.  значение *lcid* является значение, возвращенное GetUserDefaultLCID не равно. 

## <a name="getbasicerrorinfo"></a> CDBErrorInfo::GetBasicErrorInfo
Вызовы [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/library/ms723907.aspx) для возврата основные сведения об ошибке, например кода возврата и номер ошибки от поставщика.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetBasicErrorInfo(ULONG ulRecordNum,   
  ERRORINFO* pErrorInfo) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/library/ms723907.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  

## <a name="getcustomerrorobject"></a> CDBErrorInfo::GetCustomErrorObject
Вызовы [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/library/ms725417.aspx) для возврата указателя на интерфейс объекта пользовательских ошибок.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetCustomErrorObject(ULONG ulRecordNum,   
   REFIID riid,IUnknown** ppObject) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/library/ms725417.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  

## <a name="geterrorinfo"></a> CDBErrorInfo::GetErrorInfo
Вызовы [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) для возврата [IErrorInfo](https://msdn.microsoft.com/library/ms718112.aspx) указатель интерфейса на указанную запись.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetErrorInfo(ULONG ulRecordNum,   
   LCID lcid,IErrorInfo** ppErrorInfo) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  

## <a name="geterrorparameters"></a> CDBErrorInfo::GetErrorParameters
Вызовы [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/library/ms715793.aspx) для определения параметров ошибки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetErrorParameters(ULONG ulRecordNum,   
  DISPPARAMS* pdispparams) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/library/ms715793.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  

## <a name="geterrorrecords"></a> CDBErrorInfo::GetErrorRecords
Возвращает записи об ошибках для указанного объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords) throw();  


HRESULT GetErrorRecords(ULONG* pcRecords) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Интерфейс к объекту, для которого необходимо получить записи об ошибках.  
  
 *IID*  
 [in] Идентификатор IID интерфейса, с которым связана ошибка.  
  
 *pcRecords*  
 [out] Указатель на количество записей ошибок (начинающийся с единицы).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Используйте первую форму функции, если вы хотите проверить, какой интерфейс, чтобы получить сведения об ошибке из. В противном случае используйте второй форме.  
  
## <a name="see-also"></a>См. также  
 [DBViewer](../../visual-cpp-samples.md)   
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)