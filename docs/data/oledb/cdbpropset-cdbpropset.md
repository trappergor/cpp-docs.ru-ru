---
title: "CDBPropSet::CDBPropSet | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
dev_langs: C++
helpviewer_keywords: CDBPropSet class, constructor
ms.assetid: 02ae5d9e-c067-47ca-8111-a03e86b5626b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c1b583ca5639ad542011fd9d4db0839034a4389e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cdbpropsetcdbpropset"></a>CDBPropSet::CDBPropSet
Конструктор. Инициализирует **rgProperties**, **cProperties**, и **guidPropertySet** поля [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      CDBPropSet(  
   const GUID& guid   
);  
CDBPropSet(   
   const CDBPropSet& propset    
);  
CDBPropSet( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `guid`  
 [in] Идентификатор GUID, используемый для инициализации **guidPropertySet** поля.  
  
 *набор свойств*  
 [in] Другой `CDBPropSet` объект для создания копии.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDBPropSet-класс](../../data/oledb/cdbpropset-class.md)   
 [CDBPropSet::SetGUID](../../data/oledb/cdbpropset-setguid.md)   
 [Структуры DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)