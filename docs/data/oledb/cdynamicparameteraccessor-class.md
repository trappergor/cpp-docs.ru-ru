---
title: Класс CDynamicParameterAccessor | Документация Майкрософт
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
- ATL::CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor.GetParamCount
- GetParamCount
- ATL.CDynamicParameterAccessor.GetParamCount
- GetParamIO
- CDynamicParameterAccessor::GetParamIO
- ATL.CDynamicParameterAccessor.GetParamIO
- CDynamicParameterAccessor.GetParamIO
- ATL::CDynamicParameterAccessor::GetParamIO
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
- CDynamicParameterAccessor::GetParamName
- ATL.CDynamicParameterAccessor.GetParamName
- GetParamName
- CDynamicParameterAccessor.GetParamName
- ATL::CDynamicParameterAccessor::GetParamName
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
- CDynamicParameterAccessor.GetParamType
- CDynamicParameterAccessor:GetParamType
- CDynamicParameterAccessor::GetParamType
- ATL.CDynamicParameterAccessor.GetParamType
- GetParamType
- ATL::CDynamicParameterAccessor::GetParamType
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
- CDynamicParameterAccessor::SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamStatus
- ATL::CDynamicParameterAccessor::SetParamStatus
- CDynamicParameterAccessor.SetParamStatus
- SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
- GetParam method
- GetParamCount method
- GetParamIO method
- GetParamLength method
- GetParamName method
- GetParamStatus method
- GetParamString method
- GetParamType method
- SetParam method
- SetParamLength method
- SetParamStatus method
- SetParamString method
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a92f52f7d97e3c89de3d147c2c1b798d4af6d3a4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019464"
---
# <a name="cdynamicparameteraccessor-class"></a>Класс CDynamicParameterAccessor

Аналогичную [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) Однако получает сведения о параметрах, чтобы задать, вызвав [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CDynamicParameterAccessor](#cdynamicparameteraccessor)|Конструктор.|
|[GetParam](#getparam)|Получает данные параметров из буфера.|
|[GetParamCount](#getparamcount)|Получает число параметров в методе доступа.|
|[GetParamIO](#getparamio)|Определяет, является ли указанный параметр входным или выходным.|
|[GetParamLength](#getparamlength)|Получает длину указанного параметра, сохраненного в буфере.|
|[GetParamName](#getparamname)|Получает имя указанного параметра.|
|[GetParamStatus](#getparamstatus)|Получает состояние указанного параметра, сохраненного в буфере.|
|[GetParamString](#getparamstring)|Получает строковые данные указанного параметра, сохраненного в буфере.|
|[GetParamType](#getparamtype)|Получает тип данных указанного параметра.|
|[SetParam](#setparam)|Задает буфер, используя данные параметра.|
|[SetParamLength](#setparamlength)|Задает длину указанного параметра, сохраненного в буфере.|
|[SetParamStatus](#setparamstatus)|Задает состояние указанного параметра, сохраненного в буфере.|
|[SetParamString](#setparamstring)|Задает строковые данные указанного параметра, сохраненного в буфере.|

## <a name="remarks"></a>Примечания

Для использования этого класса поставщик должен поддерживать интерфейс `ICommandWithParameters` для потребителя.

Сведения о параметрах хранятся в буфере, создаваемом и управляемом данным классом. Получить данные параметров из буфера можно с помощью методов [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) и [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).

Пример, демонстрирующий, как этот класс используется для выполнения хранимой процедуры SQL Server и возврата значения выходных параметров, см. в разделе [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) пример кода в [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) репозитории на сайте GitHub.

## <a name="cdynamicparameteraccessor"></a> CDynamicParameterAccessor::CDynamicParameterAccessor

Конструктор.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor(eBlobHandling, nBlobSize )  
```  
  
#### <a name="parameters"></a>Параметры  

*eBlobHandling*<br/>
Определяет, как обрабатывать данные большого двоичного ОБЪЕКТА. Значение по умолчанию — DBBLOBHANDLING_DEFAULT. См. в разделе [CDynamicAccessor::SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) описание DBBLOBHANDLINGENUM значения.  
  
*nBlobSize*<br/>
Максимальный размер большого двоичного ОБЪЕКТА в байтах; столбец данных, это значение рассматривается как большой двоичный объект. Значение по умолчанию — 8000. См. в разделе [CDynamicAccessor::SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) сведения.  
  
### <a name="remarks"></a>Примечания  

См. в разделе [CDynamicAccessor::CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) конструктор Дополнительные сведения об обработке большого двоичного ОБЪЕКТА. 

## <a name="getparam"></a> CDynamicParameterAccessor::GetParam

Извлекает нестроковые данные для указанного параметра из параметра буфера.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,   
   ctype* pData) const throw();  

template <class ctype> bool GetParam(TCHAR* pParamName,   
   ctype* pData) const throw();  

void* GetParam(DBORDINAL nParam) const throw();  

void* GetParam(TCHAR* pParamName) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*ctype*<br/>
Шаблонный параметр, который является типом данных.  
  
*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
*pParamName*<br/>
[in] Имя параметра.  
  
*pData*<br/>
[out] Указатель на буфер, содержащий данные, полученные из буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  

Для версий нешаблонного точек в памяти, содержащей данные получить из буфера. Для шаблона версии возвращает **true** в случае успешного выполнения или **false** в случае сбоя.  
  
Используйте `GetParam` для получения нестроковые данные параметров из буфера. Используйте [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) для извлечения строковых параметра данных из буфера.  

## <a name="getparamcount"></a> CDynamicParameterAccessor::GetParamCount

Возвращает число параметров, сохраненных в буфере.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
DB_UPARAMS GetParamCount() const throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  

Число параметров.  

## <a name="getparamio"></a> CDynamicParameterAccessor::GetParamIO

Определяет, является ли указанный параметр входным или выходным.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetParamIO(DBORDINAL nParam,   
   DBPARAMIO* pParamIO) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
*pParamIO*<br/>
Указатель на переменной, содержащей `DBPARAMIO` типа (входной или выходной) указанного параметра. Определяется следующим образом:  
  
```cpp  
typedef DWORD DBPARAMIO;  
  
enum DBPARAMIOENUM {  
    DBPARAMIO_NOTPARAM   = 0,  
    DBPARAMIO_INPUT      = 0x1,  
    DBPARAMIO_OUTPUT     = 0x2  
};  
```  
  
### <a name="return-value"></a>Возвращаемое значение  

Возвращает **true** в случае успешного выполнения или **false** в случае сбоя.  

## <a name="getparamlength"></a> CDynamicParameterAccessor::GetParamLength

Получает длину указанного параметра, сохраненного в буфере.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetParamLength(DBORDINAL nParam,  
   DBLENGTH* pLength);  

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
*pLength*<br/>
[out] Указатель на переменную, содержащее длину в байтах указанного параметра.  
  
### <a name="remarks"></a>Примечания  

Первое переопределение возвращает **true** в случае успешного выполнения или **false** в случае сбоя. Второе переопределение точек на область памяти, содержащее длину параметра. 

## <a name="getparamname"></a> CDynamicParameterAccessor::GetParamName

Извлекает имя указанного параметра.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
LPOLESTR GetParamName(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
### <a name="return-value"></a>Возвращаемое значение  

Имя указанного параметра.  

## <a name="getparamstatus"></a> CDynamicParameterAccessor::GetParamStatus

Получает состояние указанного параметра, сохраненного в буфере.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetParamStatus(DBORDINAL nParam,  
   DBSTATUS* pStatus);  

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
*pStatus*<br/>
[out] Указатель на переменную, содержащую DBSTATUS состояние указанного параметра. Дополнительные сведения о значениях DBSTATUS, см. в разделе [состояние](/previous-versions/windows/desktop/ms722617\(v=vs.85\)) в *Справочник программиста OLE DB по*, или выполните поиск DBSTATUS в oledb.h.  
  
### <a name="remarks"></a>Примечания  

Первое переопределение возвращает **true** в случае успешного выполнения или **false** в случае сбоя. Второе переопределение точек на буфер, содержащий состояние указанного параметра.

## <a name="getparamstring"></a> CDynamicParameterAccessor::GetParamString

Получает строковые данные указанного параметра, сохраненного в буфере.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetParamString(DBORDINAL nParam,  
   CSimpleStringA& strOutput) throw();

bool GetParamString(DBORDINAL nParam,  
   CSimpleStringW& strOutput) throw();
   
bool GetParamString(DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen) throw();

bool GetParamString(DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen) throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
*strOutput*<br/>
[out] ANSI (`CSimpleStringA`) или Юникод (`CSimpleStringW`) строковые данные указанного параметра. Необходимо передать параметр типа `CString`, например:  
  
[!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
*pBuffer*<br/>
[out] Указатель на ANSI (**CHAR**) или Юникод (**WCHAR**) строковые данные указанного параметра.  
  
*pMaxLen*<br/>
[out] Указатель на размер буфера, на которые указывают *pBuffer* (в символах, включая завершающий символ NULL).  
  
### <a name="remarks"></a>Примечания  

Возвращает **true** в случае успешного выполнения или **false** в случае сбоя.  
  
Если *pBuffer* имеет значение NULL, этот метод будет задать необходимый размер буфера в памяти, на которые указывают *pMaxLen* и вернуть **true** без копирования данных.  
  
Этот метод завершится ошибкой, если буфер *pBuffer* недостаточно велик, чтобы вместить всю строку.  
  
Используйте `GetParamString` для извлечения строковых параметра данных из буфера. Используйте [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) извлекаемого нестроковые данные параметров из буфера.  

## <a name="getparamtype"></a> CDynamicParameterAccessor::GetParamType

Получает тип данных указанного параметра.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetParamType(DBORDINAL nParam,  
   DBTYPE* pType) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
*pType*<br/>
[out] Указатель на переменную, содержащую тип данных указанного параметра.  
  
### <a name="return-value"></a>Возвращаемое значение  

Возвращает **true** в случае успешного выполнения или **false** в случае сбоя.  

## <a name="setparam"></a> CDynamicParameterAccessor::SetParam

Задает параметр буфер, используя указанные данные (без строк).  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,  
   constctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK) throw();  

template <class ctype>  
bool SetParam(TCHAR* pParamName,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*ctype*<br/>
Шаблонный параметр, который является типом данных.  
  
*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. Пример:  
  
[!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]  
  
*pParamName*<br/>
[in] Имя параметра.  
  
*pData*<br/>
[in] Указатель на буфер, содержащий данные для записи в буфер.  
  
*status*<br/>
[in] DBSTATUS состояние столбца. Дополнительные сведения о значениях DBSTATUS, см. в разделе [состояние](/previous-versions/windows/desktop/ms722617\(v=vs.85\)) в *Справочник программиста OLE DB по*, или выполните поиск DBSTATUS в oledb.h.  
  
### <a name="return-value"></a>Возвращаемое значение  

Возвращает **true** в случае успешного выполнения или **false** в случае сбоя.  
  
Используйте `SetParam` присвоить нестроковые данные параметров в буфере. Используйте [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) для задания параметра строковых данных в буфере.  

## <a name="setparamlength"></a> CDynamicParameterAccessor::SetParamLength

Задает длину указанного параметра, сохраненного в буфере.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool SetParamLength(DBORDINAL nParam,  
   DBLENGTH length);  
```  
  
#### <a name="parameters"></a>Параметры  

*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
*length*<br/>
[in] Длина указанного параметра в байтах.  
  
### <a name="remarks"></a>Примечания  

Возвращает **true** в случае успешного выполнения или **false** в случае сбоя. 

## <a name="setparamstatus"></a> CDynamicParameterAccessor::SetParamStatus

Задает состояние указанного параметра, сохраненного в буфере.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool SetParamStatus(DBORDINAL nParam,  
   DBSTATUS status);  
```  
  
#### <a name="parameters"></a>Параметры  

*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
*status*<br/>
[in] DBSTATUS состояние указанного параметра. Дополнительные сведения о значениях DBSTATUS, см. в разделе [состояние](/previous-versions/windows/desktop/ms722617\(v=vs.85\)) в *Справочник программиста OLE DB по*, или выполните поиск DBSTATUS в oledb.h.  
  
### <a name="remarks"></a>Примечания  

Возвращает **true** в случае успешного выполнения или **false** в случае сбоя. 

## <a name="setparamstring"></a> CDynamicParameterAccessor::SetParamString

Задает строковые данные указанного параметра, сохраненного в буфере.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool SetParamString(DBORDINAL nParam,   
   constCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,   
   constWCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*nParam*<br/>
[in] Параметр с номером (начиная с 1). Параметр 0 зарезервирован для возвращаемых значений. Параметр с номером является индексом параметра, в зависимости от их порядка SQL или вызов хранимой процедуры. См. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) пример.  
  
*pString*<br/>
[in] Указатель на ANSI (**CHAR**) или Юникод (**WCHAR**) строковые данные указанного параметра. См. в разделе DBSTATUS в oledb.h.  
  
*status*<br/>
[in] DBSTATUS состояние указанного параметра. Дополнительные сведения о значениях DBSTATUS, см. в разделе [состояние](/previous-versions/windows/desktop/ms722617\(v=vs.85\)) в *Справочник программиста OLE DB по*, или выполните поиск DBSTATUS в oledb.h.  
  
### <a name="remarks"></a>Примечания  

Возвращает **true** в случае успешного выполнения или **false** в случае сбоя.  
  
`SetParamString` завершится ошибкой при попытке задать строку, размер которых превышает максимальный размер, указанный для *pString*.  
  
Используйте `SetParamString` для задания параметра строковых данных в буфере. Используйте [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) присвоить нестроковые данные параметров в буфере. 

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс CAccessor](../../data/oledb/caccessor-class.md)<br/>
[Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  