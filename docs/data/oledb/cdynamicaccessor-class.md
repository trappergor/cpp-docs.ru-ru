---
title: Класс CDynamicAccessor | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
- ATL::CDynamicAccessor::AddBindEntry
- AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
- ATL::CDynamicAccessor::Close
- ATL.CDynamicAccessor.Close
- CDynamicAccessor.Close
- CDynamicAccessor::Close
- ATL.CDynamicAccessor.GetBlobHandling
- CDynamicAccessor::GetBlobHandling
- ATL::CDynamicAccessor::GetBlobHandling
- GetBlobHandling
- CDynamicAccessor.GetBlobHandling
- ATL::CDynamicAccessor::GetBlobSizeLimit
- CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor::GetBlobSizeLimit
- GetBlobSizeLimit
- ATL.CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetColumnCount
- ATL::CDynamicAccessor::GetColumnCount
- CDynamicAccessor::GetColumnCount
- CDynamicAccessor.GetColumnCount
- GetColumnCount
- CDynamicAccessor.GetColumnFlags
- ATL::CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnFlags
- CDynamicAccessor::GetColumnFlags
- GetColumnFlags
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
- ATL::CDynamicAccessor::GetColumnName
- GetColumnName
- ATL.CDynamicAccessor.GetColumnName
- CDynamicAccessor::GetColumnName
- CDynamicAccessor.GetColumnName
- ATL.CDynamicAccessor.GetColumnType
- CDynamicAccessor::GetColumnType
- GetColumnType
- CDynamicAccessor.GetColumnType
- ATL::CDynamicAccessor::GetColumnType
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
- CDynamicAccessor.GetOrdinal
- ATL::CDynamicAccessor::GetOrdinal
- CDynamicAccessor::GetOrdinal
- ATL.CDynamicAccessor.GetOrdinal
- GetOrdinal
- ATL::CDynamicAccessor::GetStatus
- CDynamicAccessor.GetStatus
- ATL.CDynamicAccessor.GetStatus
- CDynamicAccessor::GetStatus
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
- ATL::CDynamicAccessor::SetLength
- CDynamicAccessor.SetLength
- CDynamicAccessor::SetLength
- ATL.CDynamicAccessor.SetLength
- CDynamicAccessor::SetStatus
- ATL::CDynamicAccessor::SetStatus
- CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- CDynamicAccessor class
- AddBindEntry method
- CDynamicAccessor class, constructor
- Close method
- GetBlobHandling method
- GetBlobSizeLimit method
- GetBookmark method
- GetColumnCount method
- GetColumnFlags method
- GetColumnInfo method
- GetColumnName method
- GetColumnType method
- GetLength method
- GetOrdinal method
- GetStatus method
- GetValue method
- SetBlobHandling method
- SetBlobSizeLimit method
- SetLength method
- SetStatus method
- SetValue method
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a4a1b08d82e915780817a47abddcf417fe5ab715
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338250"
---
# <a name="cdynamicaccessor-class"></a>Класс CDynamicAccessor
Позволяет доступ к источнику данных, когда схема базы данных (базовая структура).  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CDynamicAccessor : public CAccessorBase  
```  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddBindEntry](#addbindentry)|При переопределении метода доступа по умолчанию добавляет запись привязки выходных столбцов.|  
|[CDynamicAccessor](#cdynamicaccessor)|Создает и инициализирует `CDynamicAccessor` объекта.|  
|[Закрыть](#close)|Отменяет привязку столбцов по, освобождает выделенную память и освобождает [IAccessor](https://msdn.microsoft.com/library/ms719672.aspx) указатель на интерфейс в классе.|  
|[GetBlobHandling](#getblobhandling)|Извлекает BLOB-ОБЪЕКТОВ, обработки значения для текущей строки.|  
|[GetBlobSizeLimit](#getblobsizelimit)|Получает максимальный размер большого двоичного ОБЪЕКТА в байтах.|  
|[GetBookmark](#getbookmark)|Извлекает закладки для текущей строки.|  
|[GetColumnCount](#getcolumncount)|Возвращает число столбцов в наборе строк.|  
|[GetColumnFlags](#getcolumnflags)|Получает характеристики столбца.|  
|[GetColumnInfo](#getcolumninfo)|Извлекает метаданные столбца.|  
|[GetColumnName](#getcolumnname)|Извлекает имя указанного столбца.|  
|[GetColumnType](#getcolumntype)|Возвращает тип данных указанного столбца.|  
|[GetLength](#getlength)|Извлекает максимально возможная длина столбца в байтах.|  
|[GetOrdinal](#getordinal)|Получает индекс столбца, заданному имени столбца.|  
|[GetStatus](#getstatus)|Получает состояние указанного столбца.|  
|[GetValue](#getvalue)|Извлекает данные из буфера.|  
|[SetBlobHandling](#setblobhandling)|Задает BLOB-ОБЪЕКТОВ, обработки значения для текущей строки.|  
|[SetBlobSizeLimit](#setblobsizelimit)|Задает максимальный размер большого двоичного ОБЪЕКТА в байтах.|  
|[SetLength](#setlength)|Задает длину столбца в байтах.|  
|[SetStatus](#setstatus)|Задает состояние указанного столбца.|  
|[SetValue](#setvalue)|Сохраняет данные в буфер.|  
  
## <a name="remarks"></a>Примечания  
 Используйте `CDynamicAccessor` методов, чтобы получить сведения о столбцах, таких как имена столбцов, число столбцов, тип данных и т. д. Затем используйте эти сведения для столбца для динамического создания метода доступа во время выполнения.  
  
 Сведения о столбцах хранятся в буфере, который создается и управляется данным классом. Получение данных из буфера с помощью [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).  
  
 Обсуждение и примеры использования классов динамического метода доступа, см. в разделе [с помощью динамических методов доступа](../../data/oledb/using-dynamic-accessors.md).  

## <a name="addbindentry"></a> CDynamicAccessor::AddBindEntry
Добавляет запись привязки для выходных столбцов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *Сведения о*  
 [in] Объект `DBCOLUMNINFO` структура, содержащая сведения о столбце. См. в разделе «Структур DBCOLUMNINFO» в [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/library/ms722704.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, если переопределение доступа по умолчанию, созданные с помощью `CDynamicAccessor` (см. в разделе [инструкции выборки данных?](../../data/oledb/fetching-data.md)). 
  
## <a name="cdynamicaccessor"></a> CDynamicAccessor::CDynamicAccessor
Создает и инициализирует `CDynamicAccessor` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000);  
```  
  
#### <a name="parameters"></a>Параметры  
 *eBlobHandling*  
 Определяет, как обрабатывать данные больших двоичных объектов (BLOB). Значение по умолчанию — DBBLOBHANDLING_DEFAULT. См. в разделе [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) описание DBBLOBHANDLINGENUM значения.  
  
 *nBlobSize*  
 Максимальный размер большого двоичного ОБЪЕКТА в байтах; столбец данных, это значение рассматривается как большой двоичный объект. Значение по умолчанию — 8000. См. в разделе [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) сведения.  
  
### <a name="remarks"></a>Примечания  
 Если вы используете конструктор для инициализации `CDynamicAccessor` объекта, можно указать, как он выполняет привязку больших двоичных объектов. Больших двоичных объектов может содержать двоичные данные, такие как графический, звук или скомпилированный код. Поведение по умолчанию — обрабатывать более 8000 байт столбцы как большие двоичные объекты и попытке привязать их к `ISequentialStream` объекта. Тем не менее можно указать другое значение размера большого двоичного ОБЪЕКТА.  
  
 Также можно указать как `CDynamicAccessor` обрабатывает столбец данных, определяемая как данные большого двоичного ОБЪЕКТА: он может обрабатывать данные большого двоичного ОБЪЕКТА по умолчанию; его можно пропустить (привязки) данных больших двоичных ОБЪЕКТОВ; или его можно привязать данные большого двоичного ОБЪЕКТА в память, выделенную поставщика.  

## <a name="close"></a> CDynamicAccessor::Close
Отменяет привязку столбцов по, освобождает выделенную память и освобождает [IAccessor](https://msdn.microsoft.com/library/ms719672.aspx) указатель на интерфейс в классе.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
void Close() throw();  
```  

## <a name="getblobhandling"></a> CDynamicAccessor::GetBlobHandling
Извлекает BLOB-ОБЪЕКТОВ, обработки значения для текущей строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
const DBBLOBHANDLINGENUM GetBlobHandling() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает большой двоичный объект, обработка значение *eBlobHandling* как задается [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md). 

## <a name="getblobsizelimit"></a> CDynamicAccessor::GetBlobSizeLimit
Получает максимальный размер большого двоичного ОБЪЕКТА в байтах.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
const DBLENGTH GetBlobSizeLimit() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает большой двоичный объект, обработка значение *nBlobSize* как задается [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md).  

## <a name="getbookmark"></a> CDynamicAccessor::GetBookmark
Извлекает закладки для текущей строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *pBookmark*  
 [out] Указатель на [CBookmark](../../data/oledb/cbookmark-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Необходимо задать `DBPROP_IRowsetLocate` значение VARIANT_TRUE для получения закладки. 

## <a name="getcolumncount"></a> CDynamicAccessor::GetColumnCount
Возвращает число столбцов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
DBORDINAL GetColumnCount() const throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Получить число столбцов.  

## <a name="getcolumnflags"></a> CDynamicAccessor::GetColumnFlags
Получает характеристики столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetColumnFlags(DBORDINAL nColumn,   
   DBCOLUMNFLAGS* pFlags) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
 *pFlags*  
 [out] Указатель на Битовая маска, которая описывает характеристики столбца. См. в разделе «DBCOLUMNFLAGS перечисляемый тип» в [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/library/ms722704.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если характеристики столбца успешно получены. В противном случае возвращается значение **false**.  
  
### <a name="remarks"></a>Примечания  
 Номер столбца смещается от одного. Нулевым столбцом является особым случаем; Это закладки, если он доступен.

## <a name="getcolumninfo"></a> CDynamicAccessor::GetColumnInfo
Возвращает метаданные столбца, требуемые большинством объектов-получателей.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetColumnInfo(IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *pRowset*  
 [in] Указатель на [IRowset](https://msdn.microsoft.com/library/ms720986.aspx) интерфейс.  
  
 *pColumns*  
 [out] Указатель на буфер, в которой должна возвращаться количество столбцов в наборе строк. Этот номер столбца закладки он включается, если таковой имеется.  
  
 *ppColumnInfo*  
 [out] Указатель на область памяти, в которую будет возвращен массив `DBCOLUMNINFO` структуры. См. в разделе «Структур DBCOLUMNINFO» в [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/library/ms722704.aspx) в *справочнике программиста OLE DB*.  
  
 *ppStringsBuffer*  
 [out] Указатель на область памяти, в которую будет возвращен указатель в хранилище для всех строковых значений (имена используются как в пределах *columnid* или *pwszName*) в одном блоке распределения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/library/ms722704.aspx) в *Справочник программиста OLE DB по* сведения о типах данных `DBORDINAL`, `DBCOLUMNINFO`, и `OLECHAR`.  

## <a name="getcolumnname"></a> CDynamicAccessor::GetColumnName
Извлекает имя заданного столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
LPOLESTR GetColumnName(DBORDINAL nColumn) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя заданного столбца.  

## <a name="getcolumntype"></a> CDynamicAccessor::GetColumnType
Возвращает тип данных указанного столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetColumnType(DBORDINAL nColumn,   
   DBTYPE* pType) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
 *pType*  
 [out] Указатель на тип данных указанного столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** в случае успешного выполнения или **false** в случае сбоя.  

## <a name="getlength"></a> CDynamicAccessor::GetLength
Получает длину указанного столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetLength(DBORDINAL nColumn,   
   DBLENGTH* pLength) const throw();  

bool GetLength(const CHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  

bool GetLength(const WCHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
 *pColumnName*  
 [in] Указатель на строку символов, содержащая имя столбца.  
  
 *pLength*  
 [out] Указатель на целое число, содержащее длину столбца в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при обнаружении указанного столбца. В противном случае эта функция возвращает **false**.  
  
### <a name="remarks"></a>Примечания  
 Первое переопределение принимает номер столбца, а второй и третий переопределения принимают имя столбца в формате ANSI или Юникода, соответственно. 

## <a name="getordinal"></a> CDynamicAccessor::GetOrdinal
Получает номер столбца, заданному имени столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetOrdinal(const CHAR* pColumnName,  
   DBORDINAL* pOrdinal) const throw();  

bool GetOrdinal(const WCHAR* pColumnName,  
   DBORDINAL* pOrdinal) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *pColumnName*  
 [in] Указатель на строку символов, содержащая имя столбца.  
  
 *pOrdinal*  
 [out] Указатель на номер столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если столбец с указанным именем найден. В противном случае эта функция возвращает **false**.

## <a name="getstatus"></a> CDynamicAccessor::GetStatus
Получает состояние указанного столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool GetStatus(DBORDINAL nColumn,   
   DBSTATUS* pStatus) const throw();  

bool GetStatus(const CHAR* pColumnName,  
   DBSTATUS* pStatus) const throw();  

bool GetStatus(const WCHAR* pColumnName,  
   DBSTATUS* pStatus) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
 *pColumnName*  
 [in] Указатель на строку символов, содержащая имя столбца.  
  
 *pStatus*  
 [out] Указатель на переменную, содержащую состояние столбца. См. в разделе [DBSTATUS](https://msdn.microsoft.com/library/ms722617.aspx) в *Справочник программиста OLE DB по* Дополнительные сведения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при обнаружении указанного столбца. В противном случае эта функция возвращает **false**.  

## <a name="getvalue"></a> CDynamicAccessor::GetValue
Извлекает данные для указанного столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
void* GetValue(DBORDINAL nColumn) const throw();  

void* GetValue(const CHAR* pColumnName) const throw();  

void* GetValue(const WCHAR* pColumnName) const throw();  

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *ctype*  
 [in] Шаблонный параметр, который обрабатывает любые типы данных, кроме строковые типы (`CHAR*`, `WCHAR*`), который требует специальной обработки. `GetValue` использует соответствующий тип данных зависимости от того, что указано здесь.  
  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
 *pColumnName*  
 [in] Имя столбца.  
  
 *pData*  
 [out] Указатель на содержимое указанного столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если вы хотите передать строковые данные, использовать версии без шаблона `GetValue`. Версии без шаблона этого метода возвращают `void*`, который указывает на часть буфер, содержащий данные указанного столбца. Возвращает значение NULL, если столбец не найден.  
  
 Для всех других типов данных, проще использовать шаблонного версии `GetValue`. Шаблонный версии возвращают **true** в случае успешного выполнения или **false** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Используете версии без шаблона для возврата столбцов, содержащих строки и шаблонного версии для столбцов, содержащих другие типы данных.  
  
 В режиме отладки, будет выведено утверждение размер *pData* не равно размер столбца, на который он указывает.  

## <a name="setblobhandling"></a> CDynamicAccessor::SetBlobHandling
Задает BLOB-ОБЪЕКТОВ, обработки значения для текущей строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);  
```  
  
#### <a name="parameters"></a>Параметры  
 *eBlobHandling*  
 Определяет, как обрабатывать данные большого двоичного ОБЪЕКТА. Он может принимать следующие значения:  
  
-   DBBLOBHANDLING_DEFAULT: Обработка данных столбца, размер которых превышает *nBlobSize* (как задается `SetBlobSizeLimit`) как данные большого двоичного ОБЪЕКТА и получить его через `ISequentialStream` или `IStream` объекта. Этот параметр будет предпринята попытка привязки каждый столбец, содержащий данные, размер которых превышает *nBlobSize* или как DBTYPE_IUNKNOWN, как данные большого двоичного ОБЪЕКТА в списке.  
  
-   DBBLOBHANDLING_NOSTREAMS: Обработка данных столбца, размер которых превышает *nBlobSize* (как задается `SetBlobSizeLimit`) как данные большого двоичного ОБЪЕКТА и получить его через ссылку в выделенных поставщика, потребителя памяти. Этот параметр полезен для таблиц, имеющих более одного столбца BLOB-ОБЪЕКТОВ, а поставщик поддерживает только один `ISequentialStream` объекта на каждый метод доступа.  
  
-   DBBLOBHANDLING_SKIP: Пропустить (привязки) столбцов, допускающих как с большими двоичными объектами (метод доступа не привязать или получить значение столбца, но будет по-прежнему получать столбец состояния и длины).  
  
### <a name="remarks"></a>Примечания  
 Перед вызовом `SetBlobHandling` следует вызвать метод `Open`.  
  
 Метод-конструктор [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) задает значение DBBLOBHANDLING_DEFAULT обработки большого двоичного ОБЪЕКТА.

## <a name="setblobsizelimit"></a> CDynamicAccessor::SetBlobSizeLimit
Задает максимальный размер большого двоичного ОБЪЕКТА в байтах.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
void SetBlobSizeLimit(DBLENGTH nBlobSize);  
```  
  
#### <a name="parameters"></a>Параметры  
 *nBlobSize*  
 Задает предельный размер большого двоичного ОБЪЕКТА.  
  
### <a name="remarks"></a>Примечания  
 Задает максимальный размер большого двоичного ОБЪЕКТА в байтах; столбец данных, размер которых превышает это значение рассматривается как большой двоичный объект. Некоторые поставщики предоставляют очень больших размеров для столбцов (например, 2 ГБ). Вместо того чтобы пытаться выделить память для столбца этот размер, обычно будет выполнена попытка привязать эти столбцы в виде больших двоичных объектов. Таким образом, нет необходимости выделять всю память, но вы по-прежнему может читать все данные, не опасаясь усечения. Тем не менее, существуют случаи, в которых может потребоваться принудительно `CDynamicAccessor` привязать больших столбцов в собственных типах данных. Чтобы сделать это, вызовите `SetBlobSizeLimit` перед вызовом `Open`.  
  
 Метод-конструктор [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) задает максимальный размер большого двоичного ОБЪЕКТА на значение по умолчанию 8 000 байт.  

## <a name="setlength"></a> CDynamicAccessor::SetLength
Задает длину указанного столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool SetLength(DBORDINAL nColumn,   
   DBLENGTH nLength)throw();  

bool SetLength(const CHAR* pColumnName,   
   DBLENGTH nLength) throw();  

bool SetLength(const WCHAR* pColumnName,   
   DBLENGTH nLength) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
 *nLength*  
 [in] Длина столбца в байтах.  
  
 *pColumnName*  
 [in] Указатель на строку символов, содержащая имя столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если длина указанного столбца устанавливается успешно. В противном случае эта функция возвращает **false**.  

## <a name="setstatus"></a> CDynamicAccessor::SetStatus
Задает состояние указанного столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool SetStatus(DBORDINAL nColumn,   
   DBSTATUS status)throw();  

bool SetStatus(const CHAR* pColumnName,   
   DBSTATUS status) throw();  

bool SetStatus(const WCHAR* pColumnName,   
   DBSTATUS status) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
 *status*  
 [in] Состояние столбца. См. в разделе [DBSTATUS](https://msdn.microsoft.com/library/ms722617.aspx) в *Справочник программиста OLE DB по* Дополнительные сведения.  
  
 *pColumnName*  
 [in] Указатель на строку символов, содержащая имя столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если успешно задано состояние указанного столбца. В противном случае эта функция возвращает **false**. 

## <a name="setvalue"></a> CDynamicAccessor::SetValue
Хранит данные для указанного столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
template <class ctype>
bool SetValue(   
   DBORDINAL nColumn,   
   constctype& data) throw( );  

template <class ctype>    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data) throw( );  

template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 *ctype*  
 [in] Шаблонный параметр, который обрабатывает любые типы данных, кроме строковые типы (`CHAR*`, `WCHAR*`), который требует специальной обработки. `GetValue` использует соответствующий тип данных зависимости от того, что указано здесь.  
  
 *pColumnName*  
 [in] Указатель на строку символов, содержащая имя столбца.  
  
 *data*  
 [in] Указатель на буфер, содержащий данные.  
  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если вы хотите задать строковые данные, использовать версии без шаблона `GetValue`. Версии без шаблона этого метода возвращают `void*`, который указывает на часть буфер, содержащий данные указанного столбца. Возвращает значение NULL, если столбец не найден.  
  
 Для всех других типов данных, проще использовать шаблонного версии `GetValue`. Шаблонный версии возвращают **true** в случае успешного выполнения или **false** в случае сбоя.  

## <a name="see-also"></a>См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны OLE DB потребителя](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Класс CAccessor](../../data/oledb/caccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)