---
title: Класс CTable | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs:
- C++
helpviewer_keywords:
- CTable class
- Open method
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 34eb8cb8a6b839f8a4dcd8d699c7fcb4851d57f6
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42571620"
---
# <a name="ctable-class"></a>Класс CTable
Предоставляет средства для прямого доступа к простому набору строк (без параметров).  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CNoAccessor, 
            template <typename T> class TRowset = CRowset>  
class CTable :  
   public CAccessorRowset <TAccessor, TRowset>  
```  
  
### <a name="parameters"></a>Параметры  
 *TAccessor*  
 Класс, метод доступа.  
  
 *TRowset*  
 Класс набора строк.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Открыть](#open)|Открытие таблицы.|  
  
## <a name="remarks"></a>Примечания  
 См. в разделе [CCommand](../../data/oledb/ccommand-class.md) сведения о том, как выполнить команду, чтобы получить доступ к набор строк.  

## <a name="open"></a> CTable::Open
Открытие таблицы.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  

HRESULT Open(const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  

HRESULT Open(const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 *Сеанс*  
 [in] Сеанс, в течение которого открыт таблицы.  
  
 *wszTableName*  
 [in] Имя таблицы, передаваемое в виде строки Юникода.  
  
 *szTableName*  
 [in] Имя таблицы, переданного как строку ANSI.  
  
 *dbid*  
 [in] `DBID` Таблицы, чтобы открыть.  
  
 *pPropSet*  
 [in] Указатель на массив [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) структур, содержащих свойства и значения, которые можно установить. См. в разделе [наборов свойств и группы свойств](/previous-versions/windows/desktop/ms713696\(v=vs.85\)) в *справочнике программиста OLE DB* в Windows SDK. Значение NULL по умолчанию задает свойства отсутствуют.  
  
 *ulPropSets*  
 [in] Число [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) структуры, передаются в *pPropSet* аргумент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [IOpenRowset::OpenRowset](/previous-versions/windows/desktop/ms716724\(v=vs.85\)) в *Справочник программиста OLE DB по*.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   