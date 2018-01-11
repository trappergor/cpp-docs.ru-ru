---
title: "CTable::Open | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e664ddb310892004b95c81c8c7d93d8035b82cd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ctableopen"></a>CTable::Open
Открытие таблицы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `session`  
 [in] Сеанс, для которого открывается таблица.  
  
 *wszTableName*  
 [in] Имя таблицы, чтобы открыть, передается как строка Юникода.  
  
 *szTableName*  
 [in] Имя таблицы, чтобы открыть, передана в качестве строки ANSI.  
  
 *DBID*  
 [in] **DBID** таблицы, чтобы открыть.  
  
 *pPropSet*  
 [in] Указатель на массив [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структур, содержащих свойства и значения, задаваемые. В разделе [наборов свойств и группы свойств](https://msdn.microsoft.com/en-us/library/ms713696.aspx) в *справочника программиста OLE DB* в Windows SDK. Значение по умолчанию NULL указывает нет свойств.  
  
 `ulPropSets`  
 [in] Число [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структуры, передаются в *pPropSet* аргумент.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) в *Справочник программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CTable](../../data/oledb/ctable-class.md)