---
title: "CSession::Open | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d83a1b18e6ddc404330c44591a86b451adfdc3d7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="csessionopen"></a>CSession::Open
Открывает новый сеанс для объекта источника данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT Open(  
   const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `ds`  
 [in] Источник данных, для которого требуется открыть сеанс.  
  
 *pPropSet*  
 [in] Указатель на массив [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структур, содержащих свойства и значения, задаваемые. В разделе [наборов свойств и группы свойств](https://msdn.microsoft.com/en-us/library/ms713696.aspx) в *справочника программиста OLE DB* в Windows SDK.  
  
 `ulPropSets`  
 [in] Число [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структуры, передаются в *pPropSet* аргумент.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Необходимо открыть объект источника данных с помощью [CDataSource::Open](../../data/oledb/cdatasource-open.md) перед передачей `CSession::Open`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CSession](../../data/oledb/csession-class.md)