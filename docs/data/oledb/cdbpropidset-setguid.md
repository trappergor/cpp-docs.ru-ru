---
title: CDBPropIDSet::SetGUID | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87878b6cc7ae38f2c9ffcf597a56ab020d8e9c8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090330"
---
# <a name="cdbpropidsetsetguid"></a>CDBPropIDSet::SetGUID
Задает GUID поля в **DBPROPIDSET** структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
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