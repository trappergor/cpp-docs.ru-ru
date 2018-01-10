---
title: "CDBPropIDSet::SetGUID | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs: C++
helpviewer_keywords: SetGUID method
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aa70e704cd8e132404442ef390ea5582155a76e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropidsetsetguid"></a>CDBPropIDSet::SetGUID
Задает GUID поля в **DBPROPIDSET** структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `guid`  
 [in] Идентификатор GUID, используемый для задания **guidPropertySet** поле [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) структуры.  
  
## <a name="remarks"></a>Примечания  
 В этом поле задается [конструктор](../../data/oledb/cdbpropidset-cdbpropidset.md) также. Эта функция вызывается в том случае, если вы используете конструктор по умолчанию для этого класса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)