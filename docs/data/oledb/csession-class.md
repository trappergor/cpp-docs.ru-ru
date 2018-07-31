---
title: Класс CSession | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
- CSession.Abort
- CSession::Abort
- ATL.CSession.Abort
- ATL::CSession::Abort
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
- CSession.Commit
- ATL.CSession.Commit
- ATL::CSession::Commit
- CSession::Commit
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
- CSession::StartTransaction
- StartTransaction
- ATL.CSession.StartTransaction
- CSession.StartTransaction
- ATL::CSession::StartTransaction
dev_langs:
- C++
helpviewer_keywords:
- CSession class
- Abort method
- Close method
- Commit method
- GetTransactionInfo method
- Open method
- StartTransaction method
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 72ac1a5be4f2e114e5b90b65542b09733c43d174
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338867"
---
# <a name="csession-class"></a>класс CSession
Представляет сеанс доступа к отдельной базы данных.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CSession  
```  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Abort](#abort)|Отменяет (прекращает) транзакции.|  
|[Закрыть](#close)|Завершает сеанс.|  
|[Фиксации](#commit)|Завершает транзакцию.|  
|[GetTransactionInfo](#gettransactioninfo)|Возвращает сведения, касающиеся транзакции.|  
|[Открыть](#open)|Открывает новый сеанс для объекта источника данных.|  
|[StartTransaction](#starttransaction)|Начинает новую транзакцию для этого сеанса.|  
  
## <a name="remarks"></a>Примечания  
 Один или несколько сеансов можно связать с каждым подключением поставщика (источник данных), который представляется [CDataSource](../../data/oledb/cdatasource-class.md) объекта. Чтобы создать новую `CSession` для `CDataSource`, вызовите [CSession::Open](../../data/oledb/csession-open.md). Для начала транзакции базы данных, `CSession` предоставляет `StartTransaction` метод. После запуска транзакции можно также выполнять его с помощью `Commit` метод, или отмените его с помощью `Abort` метод.  
  
## <a name="abort"></a> CSession::Abort
Завершает транзакцию.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Abort(BOID* pboidReason = NULL,   
   BOOL bRetaining = FALSE,   
   BOOL bAsync = FALSE) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ITransaction::Abort](https://msdn.microsoft.com/library/ms709833.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT. 

## <a name="close"></a> CSession::Close
Закрывает сеанс, который был открыт с [CSession::Open](../../data/oledb/csession-open.md).  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
void Close() throw();  
```  
  
### <a name="remarks"></a>Примечания  
 Выпуски `m_spOpenRowset` указатель.  

## <a name="commit"></a> CSession::Commit
Завершает транзакцию.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Commit(BOOL bRetaining = FALSE,   
   DWORD grfTC = XACTTC_SYNC,   
   DWORD grfRM = 0) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ITransaction::Commit](https://msdn.microsoft.com/library/ms713008.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [ITransaction::Commit](https://msdn.microsoft.com/library/ms713008.aspx).  

## <a name="gettransactioninfo"></a> CSession::GetTransactionInfo
Возвращает сведения, касающиеся транзакции.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetTransactionInfo(XACTTRANSINFO* pInfo) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/library/ms714975.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/library/ms714975.aspx) в *Справочник программиста OLE DB по*. 

## <a name="open"></a> CSession::Open
Открывает новый сеанс для объекта источника данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Open(const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *доменных служб Active Directory*  
 [in] Источник данных, для которого будет открыть сеанс.  
  
 *pPropSet*  
 [in] Указатель на массив [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) структур, содержащих свойства и значения, которые можно установить. См. в разделе [наборов свойств и группы свойств](https://msdn.microsoft.com/library/ms713696.aspx) в *справочнике программиста OLE DB* в Windows SDK.  
  
 *ulPropSets*  
 [in] Число [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) структуры, передаются в *pPropSet* аргумент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Необходимо открыть объект источника данных с помощью [CDataSource::Open](../../data/oledb/cdatasource-open.md) перед их передачей `CSession::Open`.  

## <a name="starttransaction"></a> CSession::StartTransaction
Начинает новую транзакцию для этого сеанса.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT StartTransaction(ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,  
   ULONG isoFlags = 0,  
   ITransactionOptions* pOtherOptions = NULL,  
   ULONG* pulTransactionLevel = NULL) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/library/ms709786.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/library/ms709786.aspx) в *Справочник программиста OLE DB по*. 
  
## <a name="see-also"></a>См. также  
 ["CatDB"](../../visual-cpp-samples.md)   
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)