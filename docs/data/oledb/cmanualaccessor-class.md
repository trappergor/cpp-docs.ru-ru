---
title: Класс CManualAccessor | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
- ATL::CManualAccessor::CreateParameterAccessor
- ATL.CManualAccessor.CreateParameterAccessor
- CManualAccessor.CreateParameterAccessor
- CreateParameterAccessor
- CManualAccessor::CreateParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CManualAccessor class
- AddBindEntry method
- AddParameterEntry method
- CreateAccessor method
- CreateParameterAccessor method
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59bc14040e9dfc7ba69d95525bae7ad795de43b8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42573089"
---
# <a name="cmanualaccessor-class"></a>Класс CManualAccessor
Представляет тип метода доступа, предназначен для опытных пользователей.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CManualAccessor : public CAccessorBase  
```  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddBindEntry](#addbindentry)|Добавляет запись привязки для выходных столбцов.|  
|[AddParameterEntry](#addparameterentry)|Добавляет запись параметра в метод доступа к параметру.|  
|[CreateAccessor](#createaccessor)|Выделяет память для столбца структуры привязки и инициализирует элементы данных столбцов.|  
|[CreateParameterAccessor](#createparameteraccessor)|Выделяет память для параметра привязки структур и инициализирует параметризованные члены данных.|  
  
## <a name="remarks"></a>Примечания  
 С помощью `CManualAccessor`, можно указать параметр и выходная привязка столбца путем вызова функции времени выполнения.  

## <a name="addbindentry"></a> CManualAccessor::AddBindEntry
Добавляет запись привязки для выходных столбцов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
void AddBindEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845\(v=vs.85\)) в *справочнике программиста OLE DB*.  
  
 *nOrdinal*  
 [in] Номер столбца.  
  
 *wType*  
 [in] Тип данных.  
  
 *nColumnSize*  
 [in] Размер столбца в байтах.  
  
 *pData*  
 [in] Указатель на данные столбца, сохраненного в буфере.  
  
 *pLength*  
 [in] Указатель длины поля, если это необходимо.  
  
 *pStatus*  
 [in] Указатель на переменную для привязки к состояние столбца, если это необходимо.  
  
### <a name="remarks"></a>Примечания  
 Чтобы использовать эту функцию, необходимо сначала вызвать [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md). Не удается добавить больше записей, чем количество столбцов, указанных в `CreateAccessor`. 
  
## <a name="addparameterentry"></a> CManualAccessor::AddParameterEntry
Добавляет запись параметра запись на параметр структуры.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
void AddParameterEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL,  
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845\(v=vs.85\)) в *справочнике программиста OLE DB*.  
  
 *nOrdinal*  
 [in] Номер параметра.  
  
 *wType*  
 [in] Тип данных.  
  
 *nColumnSize*  
 [in] Размер столбца в байтах.  
  
 *pData*  
 [in] Указатель на данные столбца, сохраненного в буфере.  
  
 *pLength*  
 [in] Указатель длины поля, если это необходимо.  
  
 *pStatus*  
 [in] Указатель на переменную для привязки к состояние столбца, если это необходимо.  
  
 *eParamIO*  
 [in] Указывает, является ли параметр, с которой связана привязка ввода, ввода вывода или вывода.  
  
### <a name="remarks"></a>Примечания  
 Чтобы использовать эту функцию, необходимо сначала вызвать [CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md). 

## <a name="createaccessor"></a> CManualAccessor::CreateAccessor
Выделяет память для столбца структуры привязки и инициализирует элементы данных столбцов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT CreateAccessor(int nBindEntries,   
  void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nBindEntries*  
 [in] Число столбцов. Это число должно соответствовать количество вызовов [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) функции.  
  
 *pBuffer*  
 [in] Указатель на буфер, где хранятся выходные столбцы.  
  
 *nBufferSize*  
 [in] Размер буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию перед вызовом метода `CManualAccessor::AddBindEntry` функции.  

## <a name="createparameteraccessor"></a> CManualAccessor::CreateParameterAccessor
Выделяет память для параметра привязки структур и инициализирует параметризованные члены данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT CreateParameterAccessor(int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nBindEntries*  
 [in] Число столбцов.  
  
 *pBuffer*  
 [in] Указатель на буфер, где хранятся входные столбцы.  
  
 *nBufferSize*  
 [in] Размер буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Вы должны вызвать эту функцию перед вызовом [AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md).

## <a name="see-also"></a>См. также  
 [DBViewer](../../visual-cpp-samples.md)   
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны OLE DB потребителя](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Класс CAccessor](../../data/oledb/caccessor-class.md)   
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)